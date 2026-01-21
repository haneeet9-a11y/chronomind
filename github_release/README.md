# TimeEval Knowledge Evaluation Dataset

This repository contains filtered knowledge evaluation question datasets for the TimeEval project, prepared for GitHub release. All files contain only the necessary fields for evaluation and exclude sensitive or redundant information.

## Dataset Overview

The dataset includes 6 filtered JSON files containing knowledge evaluation questions across different modules and languages:

- **Total Questions**: 6406 (all with Gold Responses)
- **Modules**: Knowledge Boundary, Knowledge Retrospection, Knowledge Revision, Temporal Localization
- **Languages**: English (en), Chinese (zh)
- **Gold Responses**: 100% coverage (all questions include GPT-5.1 reference answers)

## File Structure

Each JSON file follows this structure:

```json
{
  "module_type": "knowledge_boundary|knowledge_retrospection|knowledge_revision|temporal_localization",
  "prompt_language": "en|zh",
  "total_questions": 1000,
  "instances": [
    {
      "scene": "Scene description text",
      "event": "Event summary",
      "summary": "Spatio-temporal label",
      "question": "Question text",
      "Spatio_Label": "Spatio-temporal label (duplicate of summary)",
      "Reference_Time": "Time reference (e.g., 'Book 4, Chapter 24, night')",
      "Gold_Response": "GPT-5.1 model answer"
    }
  ]
}
```

## Files

| Filename | Module | Language | Questions | Gold Responses | Coverage |
|----------|--------|----------|-----------|----------------|----------|| knowledge_boundary_en_questions_filtered.json | Knowledge Boundary | EN | 991 | 991 | 100.0% |\n| knowledge_boundary_zh_questions_filtered.json | Knowledge Boundary | ZH | 989 | 989 | 100.0% |\n| knowledge_retrospection_en_questions_filtered.json | Knowledge Retrospection | EN | 805 | 805 | 100.0% |\n| knowledge_revision_en_questions_filtered.json | Knowledge Revision | EN | 999 | 999 | 100.0% |\n| knowledge_revision_zh_questions_filtered.json | Knowledge Revision | ZH | 1624 | 1624 | 100.0% |\n| temporal_localization_zh_questions_filtered.json | Temporal Localization | ZH | 998 | 998 | 100.0% |\n
## Field Descriptions

- **`scene`**: Contextual scene description
- **`event`**: Summary of the key event
- **`summary`**: Spatio-temporal context label
- **`question`**: The evaluation question text
- **`Spatio_Label`**: Duplicate of summary field for convenience
- **`Reference_Time`**: Temporal reference point in the Harry Potter series
- **`Gold_Response`**: Reference answer from OpenRouter GPT-5.1 model

## Notes

- All questions include Gold Responses from the OpenRouter GPT-5.1 model
- Questions without valid Gold Responses have been removed
- Files have been filtered to remove internal evaluation metadata and model responses other than the GPT-5.1 reference answers

## Usage

```python
import json

# Load any filtered dataset
with open('knowledge_boundary_en_questions_filtered.json', 'r', encoding='utf-8') as f:
    data = json.load(f)

# Access questions
for instance in data['instances']:
    question = instance['question']
    gold_answer = instance['Gold_Response']
    # ... process questions
```

## License

[Add appropriate license information]
