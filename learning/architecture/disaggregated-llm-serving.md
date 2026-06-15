# Disaggregated LLM serving `[paper]`

## One-sentence TL;DR

Disaggregated serving splits prefill and decode onto separate workers, then transfers KV cache so each phase can use batching, placement, and parallelism matched to its latency target.

## Citation

Zhong, Y., Liu, S., Chen, J., Hu, J., Zhu, Y., Liu, X., Jin, X., & Zhang, H. (2024). *DistServe: Disaggregating Prefill and Decoding for Goodput-optimized Large Language Model Serving.* OSDI 2024. [arxiv.org/abs/2401.09670](https://arxiv.org/abs/2401.09670)

## Related papers

- Qin, R., Li, Z., He, W., Zhang, M., Wu, Y., Zheng, W., & Xu, X. (2024). *Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving.* [arxiv.org/abs/2407.00079](https://arxiv.org/abs/2407.00079)
- Liu, Y., Cheng, Y., Yao, J., An, Y., Chen, X., Feng, S., Huang, Y., Shen, S., Zhang, R., Du, K., & Jiang, J. (2025). *LMCache: An Efficient KV Cache Layer for Enterprise-Scale LLM Inference.* [arxiv.org/abs/2510.09665](https://arxiv.org/abs/2510.09665)
- Li, J., Zhu, Y., Lee, E. K., & Nahrstedt, K. (2025). *Revisiting Disaggregated Large Language Model Serving for Performance and Energy Implications.* [arxiv.org/abs/2601.08833](https://arxiv.org/abs/2601.08833)

## What the architecture does

LLM serving has two major phases. Prefill processes the prompt and creates the request's KV cache. Decode extends the response one token at a time while repeatedly reading that cache.

DistServe argues that colocating prefill and decode creates interference and forces one resource-allocation plan onto phases with different bottlenecks. It assigns prefill and decode to different GPUs, then places the phases with cluster bandwidth in mind because KV cache must cross the boundary.

Mooncake makes the same split in a KV-cache-centered serving system for Kimi. It separates prefill and decode clusters, uses CPU, DRAM, and SSD capacity for disaggregated cache storage, and schedules around KV cache reuse and latency service-level objectives.

LMCache shows the infrastructure layer this pattern needs in common inference engines. It extracts and transfers KV cache for vLLM and SGLang, including prefill-decode disaggregation across engines or GPUs.

## What the papers claim

- DistServe reports serving up to 7.4x more requests or meeting 12.6x tighter service-level objectives than its evaluated baselines while satisfying latency constraints for more than 90% of requests.
- Mooncake reports up to 525% higher simulated throughput in selected long-context scenarios and 75% more real-workload requests handled by Kimi.
- LMCache reports up to 15x throughput improvement with vLLM on workloads such as multi-round question answering and document analysis.
- Li et al. caution that disaggregation does not guarantee a win. Request load, KV-transfer medium, and energy costs can erase the benefit.

Treat those numbers as workload- and cluster-specific evidence, not portable speedups.

## Why it matters

- TTFT and TPOT can be optimized separately instead of sharing one batch and parallelism policy.
- KV cache becomes a network and storage object, not only per-GPU memory.
- Long prompts, high concurrency, and strict latency service-level objectives are the natural fit.
- Network bandwidth, placement, serialization overhead, cache hit rate, and failure handling can dominate the gain.

## Read it when

- You are choosing between colocated and prefill-decode-disaggregated serving.
- You are evaluating vLLM, SGLang, Mooncake, LMCache, or similar serving stacks.
- You need to understand why long-context serving can be bottlenecked by KV-cache movement rather than model FLOPs.

## Related entries

- `learning/architecture/kv-cache.md` — the cache object that crosses the prefill/decode boundary.
- `learning/architecture/multi-token-prediction.md` — another serving-time technique that targets decode latency.
- `self-hosted/runners/README.md` — where runtime-specific support and caveats belong.

## Status

`[paper]`. Current as of 2026-06-15; re-check runtime support, request mix, and network topology before assuming disaggregation helps a specific deployment.
