# Applying SCM to SAT

Submitted to CPAIOR'24 and will be published as part of a larger SAT encoding library at a later stage / after publication.

Each file `scm/w_c.txt` has an optimal circuit to compute `y=c*x`, where `x` is a binary encoded integer variable `x` using `w` bits which is multiplied by constant `c` to create `y` with the minimal number of half/full adders. In files where `w=0`, the circuit is minimal in the number of additions/subtractions (regardless of the actual bit width of `x`). The recipes are defined in a self-explanatory format with descriptive comments:

```
> cat 4_117.txt 
# x=4,c=117,k=4,a=12
1,0,1,+,0,0
2,0,4,+,0,0
3,1,4,+,0,0
4,2,2,+,3,0
# 3x = 2*x + x
# 17x = 16*x + x
# 49x = 16*3x (=48) + x
# 117x = 4*17x (=68) + 49x
```

In `ecm/w_c.txt`, optimal CNF encodings are derived using Espresso, containing no additional variables (outside those to encode `x` and `y`).

