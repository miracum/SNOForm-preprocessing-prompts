# SNOForm: LLM prompts for pre-processing of clinical data entry forms

## Overview

We used an LLM to pre-process items of German clinical data entry forms in a four step process to prepare the items for annotation with SNOMED CT. This repository contains the prompts exactly as they were used in the described pre-processing pipeline.

| Step | File | Purpose |
|------|------|---------|
| 1 | `prompts/{variant}/01_identify_relevant_parts.md` | Identify the relevant parts of an item |
| 2 | `prompts/{variant}/02_expand_abbreviations.md` | Expand abbreviations and shortened terms |
| 3 | `prompts/{variant}/03_translate_item_de_en.md` | Translate the German item into English |
| 4 | `prompts/{variant}/04_hallucination_check.md` | Check the pre-processed item for hallucinations and changes in meaning |

Each step exists in two variants, stored in separate folders:
- `prompts/OncoForm/`: prompts tailored to data entry forms used in tumor boards
- `prompts/MultiForm/`: generalized prompts not tailored to a specific clinical domain

## Model and settings

- Model: [Mistral-Small-24B-Instruct-2501](https://huggingface.co/mistralai/Mistral-Small-24B-Instruct-2501) (Mistral AI, 2025)
- Steps were run as separate calls, with the output of each step passed to the next.
- Prompt placeholders are explained in the respective prompt-files.
