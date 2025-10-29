# Dataset Description

This dataset contains paired files defining interaction potentials and their corresponding structure factors.  
Each row in the two files represents one data sample — the same row index corresponds to the same configuration.

- **`./target_xxx.csv`** → Potential parameters  
- **`./input_xxx.csv`** → Structure factors $ S(Q) $

---

## File 1: `target_xxx.csv`
Each row contains four scalar parameters:

| Column | Symbol | Description |
|:------:|:--------|:-------------|
| 1 | $ \phi $ | Volume fraction |
| 2 | $ 1/\kappa $ | Debye screening length |
| 3 | $ \beta A $ | Contact potential amplitude |
| 4 | $ Z $ | Effective charge (redundant) |

Only three parameters are independent:  
$ Z $ can be determined from $ \kappa D $ and $ A $.

---

## File 2: `input_xxx.csv`
Each row contains a vector of structure factor values $ S(Q) $ corresponding to the potential parameters in the same row of `target_xxx.csv`.
- Each $S(Q)$ vector has **80 points** sampled over  
  $$
  Q = \{ 0.02, 0.04, 0.06, \ldots, 16.00 \}
  $$
  i.e. $ Q_i = 0.02 \times i $ for $ i = 1, 2, \ldots, 80 $.
- Columns correspond to these fixed $ Q $-bins. 

---