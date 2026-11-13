# Results: 329 vLLM Token-Generation Benchmark

**Main goal:** Measure vLLM token generation rate  
**Tools:** Start python -m vllm.entrypoints.openai.api_server on port 8000, then run scripts/benchmark_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_138 · recorded 2026-11-12). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 26.04.1 LTS · kernel 7.0.0-38-generic · driver 7.1.9.31600000
- **Run:** 2026-11-12T23:53:17Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 02:37 · benchmark 00:39 · whole run 04:22
- **Source:** run 329_20261112_235317
- **Command:** `bash run_benchmark.sh --smoke --model-name mistralai/Mistral-7B-v0.3 --dtype bfloat16 --tensor-parallel-size 1 --gpu-memory-utilization 0.9 --input-len 64 --output-len 16 --max-num-seqs 2 --max-concurrency 2`

| # | Metric | Result |
|---|---|---|
| 1 | Generated token rate (output_token_throughput_tokens_sec) | 372.73841974863103 |
| 2 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 4.591089633352871 |
| 3 | Time To First Token, ms (ttft_p50_msec) | 11.969563999628008 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 4.726089999621763 |
| 5 | End-to-end request latency p50, ms (end_to_end_request_latency_msec) | 80.83590849992106 |
<!-- /profile:smoke -->
