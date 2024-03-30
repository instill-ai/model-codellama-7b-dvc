---
Task: TextGeneration
Tags:
  - TextGeneration
  - Codellama-7b
---

# Model-Codellama-7b-dvc

🔥🔥🔥 Deploy [Codellama-7b](https://github.com/facebookresearch/codellama) model on [VDP](https://github.com/instill-ai/vdp). 

This repository contains the Llama2-7b Text Completion Generation Model in the [vLLM](https://github.com/vllm-project/vllm) and Transformers format, managed using [DVC](https://dvc.org/). For information about available extra parameters, please refer to the documentation on [SamplingParams](https://github.com/vllm-project/vllm/blob/v0.2.0/vllm/sampling_params.py) in the vLLM library.

Following is an example of query parameters:

**Create Model**

```json
{
    "id": "llamacode-7b-gpu",
    "description": "Llamacode-7b, from Huggingface, is trained to generate text based on your prompts.",
    "model_definition": "model-definitions/container",
    "visibility": "VISIBILITY_PUBLIC",
    "region": "REGION_GCP_EUROPE_WEST_4",
    "hardware": "GPU",
    "configuration": {
        "task": "TASK_TEXT_GENERATION_CHAT"
    }
}
```

**Inference model**

```
{
    "task_inputs": [
        {
            "text_generation": {
                "prompt": "The capital city of Franch is ",
                "max_new_tokens": "300",
                "stop_words": "['city']",
                "temperature": "0.8",
                "top_k": "50",
                "random_seed": "42",
                "extra_params": "{\"top_p\": 0.8, \"repetition_penalty\": 2.0}"
            }
        }
    ]
}```