Generate C++ exercises for a given topic.

## Usage
/new-topic <topic> [số lượng bài]

## Behavior
1. Ask the user for the topic if not provided.
2. Generate exercises (default: 5) ordered easy → hard.
3. Each exercise includes: Mô tả, Input, Output, Ví dụ, Gợi ý (optional), Lời giải with step-by-step explanation in Vietnamese.
4. Append the exercises to the correct file based on the topic → file mapping in CLAUDE.md.
5. Confirm which file was updated.

## Example
/new-topic mảng 1 chiều 3
→ Generates 3 exercises on 1D arrays and appends to 1DArray.md
