# CLAUDE.md — C++ Basic Study Repo

## Project Purpose
This repo is for learning basic C++. The user sends a topic, and Claude generates exercises with solutions. All exercise content (problem descriptions, explanations, comments) must be in **Vietnamese**. Rule files are in English.

## Language Rules
- **Rule files** (CLAUDE.md, skill files): English.
- **Exercise content** (problem description, hints, explanations, code comments): Vietnamese.
- **Code identifiers** (variable names, function names): English.

## C++ Code Standards
- Standard: **C++17**, compiler `g++`.
- Only include headers that are actually used.
- Use `using namespace std;` is allowed in exercise code.
- No warnings when compiled with `g++ -std=c++17 -Wall`.
- Variable names must be meaningful (avoid single-letter names except for loop counters or math variables).

## Exercise File Format
Each topic has its own `.md` file. Exercises must follow this structure:

```markdown
## Bài N: Tên bài

**Mô tả**
...

**Input**
...

**Output**
...

**Ví dụ**
Input: ...
Output: ...

**Gợi ý** (optional)
...

**Lời giải**
\`\`\`cpp
// code here
\`\`\`
**Giải thích:** ...
```

## When Generating Exercises
- Generate **5 exercises per topic** by default, ordered easy → hard, unless the user specifies otherwise.
- Each exercise must include: problem description, input/output format, example, and a complete working solution with explanation.
- The solution must compile and produce correct output for the given example.
- Explain the logic step-by-step in Vietnamese before the code.
- If multiple approaches exist, show the simplest one first.

## Topic → File Mapping
| Topic | File |
|-------|------|
| Data types, variables | `Data-type.md` |
| Conditions (if/else, switch) | `condition.md` |
| Loops (for, while, do-while) | `loop.md` |
| Functions, pass-by-value/ref | `function.md` |
| 1D Arrays | `1DArray.md` |
| 2D Arrays & Strings | `2D-array-N-String.md` |
| Recursion | `recursion.md` |
| Binary Search | `BinarySearch.md` |
| Linear Search | `LinearSearch.md` |
| Stringstream | `Stringstream.md` |
| Stack | `Stack.md` |

## When Adding to a File
- Append new exercises at the end of the file.
- Maintain difficulty progression within the file.
- Do not duplicate existing exercises.
