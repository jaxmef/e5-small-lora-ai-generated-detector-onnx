# LoRA Fine-Tuned AI-generated Detector

> Disclaimer
>
> This ONNX model was converted from the original model, which is available in safetensors format. The conversion was done to ensure compatibility with frameworks and tools that utilize ONNX models.
>
> This repository is not affiliated with the original creators of the model. All credit for the development of the model belongs to its original authors.
>
> To access the original model and its details, please visit the following links:
>  - [Original Model on Hugging Face](https://huggingface.co/MayZhou/e5-small-lora-ai-generated-detector)
>  - [Original Model on GitHub](https://github.com/menglinzhou/microsoft-hackathon-24)
>
> The converted ONNX model is also available on Hugging Face for easy access:
>  - [Converted ONNX Model on Hugging Face](https://huggingface.co/jaxmef/e5-small-lora-ai-generated-detector-onnx)
>
> For questions about the original model, including its licensing or usage, please refer to the source links provided above.

This is a e5-small model fine-tuned with LoRA for sequence classification tasks. It is optimized to classify text into AI-generated or human-written with high accuracy.

- **Label_0**: Represents **human-written** content.
- **Label_1**: Represents **AI-generated** content.

## Model Details

- **Base Model**: `intfloat/e5-small`
- **Fine-Tuning Technique**: LoRA (Low-Rank Adaptation)
- **Task**: Sequence Classification
- **Use Cases**: Text classification for AI-generated detection.
- **Hyperparameters**: 
   - Learning rate: `5e-5`
   - Epochs: `3`
   - LoRA rank: `8`
   - LoRA alpha: `16`


## Training Details

- **Dataset**:
    - 10,000 twitters and 10,000 rewritten twitters with GPT-4o-mini.
    - 80,000 human-written text from [RAID-train](https://github.com/liamdugan/raid).
    - 128,000 AI-generated text from [RAID-train](https://github.com/liamdugan/raid).
- **Hardware**: Fine-tuned on a single NVIDIA A100 GPU.
- **Training Time**: Approximately 2 hours.
- **Evaluation Metrics**:
| Metric | (Raw) E5-small | Fine-tuned |
|--------|---------------:|-----------:|
|Accuracy| 65.2%          | 89.0%      |
|F1 Score| 0.653          | 0.887      |
| AUC    | 0.697          | 0.976      |

## Collaborators

- **Menglin Zhou**
- **Jiaping Liu**
- **Xiaotian Zhan**


## Citation
If you use this model, please cite the RAID dataset as follows:
```
@inproceedings{dugan-etal-2024-raid,
    title = "{RAID}: A Shared Benchmark for Robust Evaluation of Machine-Generated Text Detectors",
    author = "Dugan, Liam  and
      Hwang, Alyssa  and
      Trhl{\'\i}k, Filip  and
      Zhu, Andrew  and
      Ludan, Josh Magnus  and
      Xu, Hainiu  and
      Ippolito, Daphne  and
      Callison-Burch, Chris",
    booktitle = "Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)",
    month = aug,
    year = "2024",
    address = "Bangkok, Thailand",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.acl-long.674",
    pages = "12463--12492",
}
```
