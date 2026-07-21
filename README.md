# Experiment No. 2 — Naive, Rabin-Karp & KMP String Matching

**Subject:** CS5303 – Design and Analysis of Algorithms

## Problem Statement
Given a text string T of length n and a pattern string P of length m,
implement all three string matching algorithms and compare the number of
character comparisons made. Use a text of 10000 characters and patterns of
varying lengths (5, 10, 20, 50 characters).

## Aim
To implement and compare three string matching algorithms — Naive, Rabin-Karp,
and Knuth-Morris-Pratt (KMP) — and analyze their time complexity and performance.

## Files
| File | Description |
|------|-------------|
| `string_matching.py` | Naive, KMP, and Rabin-Karp implementations with comparison counts |
| `index.html` | Visual report of pseudocode, program, and sample output |
| `README.md` | This file |

## How to Run
```bash
python string_matching.py
```

## Algorithms
- **Naive Search:** O(nm) worst case — brute-force sliding comparison
- **KMP (Knuth-Morris-Pratt):** O(n + m) — uses the LPS (failure) array to avoid re-comparisons
- **Rabin-Karp:** O(n + m) average — uses a rolling hash to filter mismatches quickly

## Sample Output
```
Text:    AABAACAADAABAABA
Pattern: AABA

Naive  -> Matches at: [0, 9, 12], Comparisons: 24
KMP    -> Matches at: [0, 9, 12], Comparisons: 19
RK     -> Matches at: [0, 9, 12], Comparisons: 12

     Pattern      Naive        KMP         RK
--------------------------------------------------
          AB       9985       9998       3012
        ABCD       9987      10001       1254
      ABCDAB       9985       9998        643
    ABCDABCD       9984       9997        322
```

## Result
All three algorithms correctly identified pattern matches at positions
[0, 9, 12]. KMP reduced comparisons by ~21% vs Naive for the sample text.
Rabin-Karp showed the fewest character-level comparisons for longer patterns
due to hash filtering.

## Inference
Naive search is simple but O(nm) in the worst case. KMP achieves O(n+m) using
the failure function to avoid re-comparisons, making it ideal for natural
language text. Rabin-Karp's rolling hash reduces character comparisons
significantly for longer patterns, making it efficient for plagiarism
detection and multi-pattern search. KMP is generally the best choice for
single-pattern matching in general text.

## Practice Problems
1. Given the text 'AABCAABXAAAZ' and pattern 'AABXAA', trace through the KMP
   algorithm manually showing the LPS array and all shifts. Verify using your
   Python implementation.
2. Implement a 2D pattern matching system that searches for a 3x3 pattern
   matrix inside a 10x10 text matrix using the Naive approach, and count the
   number of element comparisons required.
