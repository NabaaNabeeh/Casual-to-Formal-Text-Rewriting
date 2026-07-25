# Casual-to-Formal Text Rewriting — LoRA Fine-Tune

## Task
-  rewrite casual workplace messages (Slack/email) into formal English
-## Model
-  Qwen2.5-1.5B-Instruct + LoRA (r=16, alpha=32, attention layers)
## Trainable params
-  0.28% (~4.3M of 1.5B)
## Data
74 hand-written casual→formal pairs (requests, apologies, follow-ups, scheduling)
## Why hand-written
narrow style-transfer task, small clean set > large messy one
## Training
HF `Trainer`, 4 epochs, lr 2e-4, fp16
## Loss
7.28 → 0.23 (40 steps, ~33 sec on T4)
## Test sentences
held out from training data (true generalization check)
## Files
- `casualtoformal.ipynb`, `formality_dataset.json`, `formality_lora_adapter/`
## Run 
attach dataset → run all cells (Kaggle, T4 GPU)
