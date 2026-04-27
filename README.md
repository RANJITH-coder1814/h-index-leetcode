# 274. H-Index

## 🟡 Difficulty
Medium

## 📌 Problem Statement
Given an array of integers `citations` where `citations[i]` is the number of citations a researcher received for their ith paper, return the researcher's **h-index**.

The h-index is defined as the maximum value of `h` such that the researcher has published at least `h` papers that have each been cited at least `h` times.

---

## 💡 Approach
1. Sort the citations in **descending order**
2. Traverse the array:
   - If `citations[i] >= i + 1`, update `h`
   - Else break

---

## 🚀 Code (C++)
```cpp
class Solution {
public:
    int hIndex(vector<int>& citations) {
        sort(citations.begin(), citations.end(), greater<int>());
        
        int h = 0;
        for (int i = 0; i < citations.size(); i++) {
            if (citations[i] >= i + 1) {
                h = i + 1;
            } else {
                break;
            }
        }
        
        return h;
    }
};
