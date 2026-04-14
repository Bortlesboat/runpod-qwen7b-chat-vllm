# Qwen 2.5 7B Cheap Chat vLLM Worker

Deploy `Qwen/Qwen2.5-7B-Instruct` on RunPod Hub with an OpenAI-compatible `vLLM` worker tuned for affordable 24 GB GPU use.

## Best for

- lower-cost chatbots and internal assistants,
- app backends that want a popular ungated Qwen instruct model,
- users searching for a practical `RTX 4090` or 24 GB `vLLM` listing.

## Request shapes

- `prompt` for `/v1/completions`
- `messages` for `/v1/chat/completions`
- `route` + `body` for explicit OpenAI-compatible requests

## Main knobs

- `MODEL_NAME`
- `MAX_MODEL_LEN`
- `GPU_MEMORY_UTILIZATION`
- `MAX_NUM_SEQS`
- `DEFAULT_MAX_TOKENS`
- `MAX_CONCURRENCY`

The default deployment model is `Qwen/Qwen2.5-7B-Instruct`, while the smoke test uses a smaller Qwen model to keep validation faster and cheaper.
