# JSON-Whisperer Dataset

[![Dataset](https://img.shields.io/badge/Dataset-JSON--Whisperer-blue.svg)](https://github.com/emnlp2025/JSON-Whisperer)
[![Files](https://img.shields.io/badge/Files-423-green.svg)](#)
[![Format](https://img.shields.io/badge/Format-JSON-orange.svg)](#)
[![License](https://img.shields.io/badge/License-Research-red.svg)](#)

## Overview

The **JSON-Whisperer** dataset is a comprehensive collection of JSON editing tasks designed for training and evaluating AI models on structured data manipulation. This dataset contains **423 JSON files** organized into training and test sets across multiple instruction categories.

## Dataset Structure

```
datasets/
└── edit_scene/
    ├── train_set/     # 211 training examples
    └── test_set/      # 210 test examples  
```

## Instruction Categories

### **Training Set Categories** (211 files)

| Category | Count | Description |
|----------|-------|-------------|
| **indexing_riddles** | 64 | Complex indexing and data navigation challenges |
| **Multiple_Creative_Instruction** | 36 | Multi-step creative editing tasks |
| **unsupported** | 24 | Edge cases and unsupported operations |
| **Creative_Instruction** | 19 | Single creative modification tasks |
| **Complex_Instruction_with_Broad_Implications** | 18 | High-complexity tasks with wide-ranging effects |
| **Multiple_Simple_Instruction** | 18 | Multi-step basic editing tasks |
| **Instruction_with_Implications** | 17 | Tasks requiring understanding of consequences |
| **Simple_Instruction** | 15 | Basic single-step editing operations |

### **Test Set** (210 files)
Similar distribution across the same categories for comprehensive evaluation.

## Sample JSON Structure

Each JSON file contains a complete scene editing task with the following structure:

```json
{
  "context": {
    "characters": {
      "list_display_order": "qa,hf,tr,xc",
      "qa": {
        "name": "Emily",
        "essence": "Imaginative and lonely child",
        "appearance": "Small, with curly brown hair and freckles",
        "character_age": "8 years old",
        "clothing": "Colorful t-shirt and overalls"
      },
      "hf": {
        "name": "Mr. Whiskers",
        "essence": "Emily's imaginary cat friend",
        "appearance": "Large, fluffy white cat with blue eyes",
        "character_age": "Unknown",
        "clothing": "None"
      }
      // ... more characters
    }
  },
  "json_to_edit": {
    "voice_over": "Sometimes, the line between imagination and reality blurs...",
    "description": "Emily's imaginary friend suddenly becomes real...",
    "location": "Emily's bedroom",
    "lighting": "Soft, dreamy natural light",
    "weather": "Sunny with occasional clouds",
    "ambience_sound_keywords": "Gentle breeze, distant laughter, soft purring",
    "number_of_shots": "6",
    "name": "Imaginary Friend's Reality",
    "scene_summary": "Emily's imaginary cat friend unexpectedly becomes real...",
    "shots": {
      "list_display_order": "qa,hf,tr,xc,ka,fn",
      "qa": {
        "type": "Wide-shot",
        "sfx_keywords": "soft breeze, curtains rustling",
        "action": "Emily's colorful bedroom filled with drawings..."
      }
      // ... more shots
    }
  },
  "edit_command": "Add one more shot to the scene",
  "label": {
    "updated_json": {
      // Expected result after applying the edit command
    },
    "is_unsupported": false,
    "rationale": "Explanation of how and why the edit was performed"
  },
  "json_diff": [
    {
      "op": "replace",
      "path": "/number_of_shots",
      "value": "7"
    }
    // ... more diff operations
  ],
  "validation_labels": []
}
```

## Key Components

- **Context**: Character definitions and scene setup
- **JSON to Edit**: The target JSON structure to be modified  
- **Edit Command**: Natural language instruction for the desired change
- **Label**: Expected output with rationale
- **JSON Diff**: Precise diff operations showing the changes
- **Validation**: Quality assurance labels

## Usage

This dataset is designed for:
- Training JSON editing models
- Evaluating structured data manipulation capabilities  
- Benchmarking natural language to JSON transformation
- Research in creative content generation

## Statistics

- **Total Files**: 423 JSON files
- **Split Ratio**: ~50/50 train/test

---

*This dataset represents a comprehensive resource for advancing research in structured data editing and natural language understanding.*
