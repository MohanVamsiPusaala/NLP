# Q4 – Minimum Edit Distance: Sunday → Saturday





## 1. Minimum Edit Distance

We are converting **Sunday → Saturday**.

### Model A: Sub = 1, Ins = 1, Del = 1

- Cost table (simplified calculation):

Operations (one possible optimal sequence):
S u n d a y
↓ ↓ ↓ ↓ ↓ ↓
S a t u r d a y

**Steps (one valid sequence):**  
1. Substitute `u → a` → cost 1  
2. Insert `t` after `a` → cost 1  
3. Substitute `n → u` → cost 1  
4. Insert `r` after `u` → cost 1  
5. Insert `a` before `y` → cost 1  

**Total minimum edit distance:** 5

---

### Model B: Sub = 2, Ins = 1, Del = 1

- Substitution is more expensive now.  
- Using the same sequence:

1. Substitute `u → a` → cost 2  
2. Insert `t` → cost 1  
3. Substitute `n → u` → cost 2  
4. Insert `r` → cost 1  
5. Insert `a` → cost 1  

**Total minimum edit distance:** 7

---

## 2. One Valid Edit Sequence (Step by Step)

| Step | Word       | Operation             | Cost |
|------|------------|---------------------|------|
| 0    | Sunday     | -                   | 0    |
| 1    | Sanday     | Sub u→a             | 1(A)/2(B) |
| 2    | Satnday    | Insert t            | 1    |
| 3    | Satuday    | Sub n→u             | 1(A)/2(B) |
| 4    | Saturday   | Insert r            | 1    |
| 5    | Saturday  | Insert a            | 1    |

- Total distance: **5 (Model A)**, **7 (Model B)**

---

## 3. Reflection

- Both models produce **different distances** because Model B penalizes substitutions more heavily.  
- **Insertions and substitutions** were the most useful operations to align the words.  
- Deletions were not needed in this sequence.  
- Model choice affects applications:  
  - For **spell checking**, equal costs (Model A) work well for minor typos.  
  - For **DNA alignment**, substitution costs are often higher (Model B) to account for rare mutations.  
- Understanding operation costs helps select the right model for the problem.

