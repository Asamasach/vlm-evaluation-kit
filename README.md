# VLM Evaluation Kit

Benchmarking framework for evaluating Vision-Language Models (VLMs) on industrial inspection tasks.

## Overview
VLMs like GPT-4V, Qwen-VL, and LLaVA show promise for zero-shot visual inspection, but their reliability in industrial settings is poorly understood. This toolkit provides standardized evaluation across multiple industrial tasks and datasets.

## Supported Tasks
- **Defect Classification:** Is this part defective? What type of defect?
- **Defect Localization:** Where is the defect in this image?
- **Quality Grading:** Rate the quality of this surface (pass/fail/borderline)
- **Visual Question Answering:** Domain-specific VQA for inspection reports

## Supported Models
- GPT-4V / GPT-4o
- Qwen-VL / Qwen2.5-VL
- LLaVA
- InternVL
- Custom ONNX models

## Evaluation Metrics
- Accuracy, Precision, Recall, F1 per task
- Latency (ms per image)
- Cost per inference (API-based models)
- Confusion matrices and per-class breakdowns

## Usage
```python
from vlm_eval import Evaluator, load_dataset

dataset = load_dataset("textile_defects")
evaluator = Evaluator(model="qwen-vl-plus")
results = evaluator.run(dataset)
results.summary()
```

## Industrial Datasets Tested
- Textile defects (holes, stains, pattern breaks)
- Metal surface defects (scratches, dents, corrosion)
- Glass inspection (bubbles, cracks, inclusions)
- PCB inspection (solder bridges, missing components)

## Tech Stack
- Python, HuggingFace Transformers, OpenAI API
- Pandas for result analysis
- Matplotlib for visualization
