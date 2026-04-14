# Qwen 2.5 7B Cheap Chat Worker For RunPod Hub

[![RunPod](https://api.runpod.io/badge/Bortlesboat/runpod-qwen7b-chat-vllm)](https://console.runpod.io/hub/Bortlesboat/runpod-qwen7b-chat-vllm)

This repo packages an OpenAI-compatible `vLLM` worker around `Qwen/Qwen2.5-7B-Instruct` for lower-cost 24 GB GPU deployments on RunPod Serverless.

Deploy on RunPod Hub:

- https://console.runpod.io/hub/Bortlesboat/runpod-qwen7b-chat-vllm

Good search terms for this listing:

- `qwen 7b`
- `qwen2.5-7b-instruct`
- `cheap chat`
- `vllm`
- `openai-compatible`
- `rtx 4090`

It is meant to be the broad-market listing in this small portfolio:

- cheaper than the H100-focused 32B worker,
- simpler than a bring-your-own-model starter,
- practical for chatbots, internal assistants, and lightweight app backends.

## Positioning

This listing is optimized for the part of the Hub most likely to see repeat usage:

- 24 GB GPU deployment targets,
- a popular ungated Qwen instruct model,
- OpenAI-style request shapes that plug into existing app code quickly.

The handler still forwards plain completions, chat completions, and explicit OpenAI-style routes through the local `vLLM` server inside the worker container.

## Presets

The Hub metadata ships with presets tuned for affordable general use:

- `Starter 1.5B`
- `Cheap 7B`
- `Long Context 7B`

The default model is:

- `Qwen/Qwen2.5-7B-Instruct`

## Important note about automated tests

The Hub submission smoke test uses `Qwen/Qwen2.5-1.5B-Instruct` instead of the default 7B deployment model. That keeps automated validation faster and cheaper while still proving the worker boots and answers successfully.

## Local verification

```bash
python -m unittest discover -s tests -v
python -m json.tool .runpod/hub.json
python -m json.tool .runpod/tests.json
python -m py_compile handler.py tests/test_handler.py
```

## Publish flow

1. Cut a GitHub release.
2. Submit the repo to RunPod Hub.
3. Let RunPod build and test the release.
4. Iterate by publishing new releases rather than rewriting old tags.
