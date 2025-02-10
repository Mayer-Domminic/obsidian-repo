Parameter hard limit of my GPU, being 12GB VRAM (4070ti) makes me sad. Something interesting of note is that this can be offset using CPU+RAM as an extension of CUDA hardware, it does lead to worse performance depending on the facilities of the model.

If I can somehow get to 20GB of vram, it would be huge. ([R1 32B on top](https://huggingface.co/spaces/mike-ravkine/can-ai-code-results))

| Model Size | 4-bit | 8-bit | 16-bit | Recommended |
| ---------- | ----- | ----- | ------ | ----------- |
| 1-3B       | 1.5-2 | 2.5-3 | 5-6    | 8 bit       |
| 7B         | 4-5   | 7-8   | 13-14  | 4 bit       |
| 13-15      | 8-9   | 12-13 | 24-25  | 4 bit       |
| 16B        | 10+   | 16+   | 32+    | 4 bit       |

```python
MODELS_TO_TEST = [
	"deepseek-ai/DeepSeek-R1-Distill-Qwen-32B",
	"deepseek-ai/DeepSeek-R1-Distill-Llama-8B",
	"deepseek-ai/DeepSeek-Coder-V2-Lite-Instruct",
	"bigcode/starcoder2-15b",
	"bigcode/starcoder2-7b",
	"meta-llama/CodeLlama-7b-Python-hf",
	"Qwen2.5-Coder-32B-Instruct",
	"Qwen2.5-Coder-14B-Instruct",
	"Phi 4",
]

```
List of [DeepSeekCoder-V2 models](https://huggingface.co/collections/deepseek-ai/deepseekcoder-v2-666bf4b274a5f556827ceeca).
[Github](https://github.com/deepseek-ai/DeepSeek-Coder-V2).

### List of Models

| Model                                       | Size | Latency | Rating | Comments   | Temp |
| ------------------------------------------- | ---- | ------- | ------ | ---------- | ---- |
| CohereForAI/c4ai-command-r7b-12-2024        | 7B   | 25.46   |        | low temp   | .1   |
| deepseek-ai/DeepSeek-Coder-V2-Lite-Instruct | 16B  | 40.72   |        | high temp  | .9   |
| deepseek-ai/DeepSeek-R1-Distill-Qwen-14B    | 14B  | 39.66   |        | gotta test | .5   |
| microsoft/phi-4                             | 14B  | 14.58   |        | low temp   | .3   |
| Qwen/Qwen2.5-Coder-14B-Instruct             | 14B  | 30      |        | lower temp | .3   |
| DeepSeek-R1-Distill-Qwen-7B                 | 7B   | 38.13   |        | lower temp | .25  |
| Qwen/Qwen2.5-Coder-7B-Instruct-GPTQ-Int4    |      |         |        |            |      |

