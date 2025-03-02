#Useful

1. We can write operators on $\mathbb{C}^2\otimes \mathbb{C} ^2$ in tensor product notation, or directly in terms of states on the whole Hilbert space e.g.
    
    $$ |0\rangle\langle0|\otimes |1\rangle\langle1|=|01\rangle\langle01| $$
    
    More generally, if $a,b,c,d=0,1$ label the basis states, then
    
    $$ |a\rangle\langle b|\otimes |c\rangle\langle d|=|ac\rangle\langle bd| $$
     ^33c84e
2. Recall that the matrix of an operator $A$ can be written as
    
    $$ A_{jk}=\langle v_j|A|v_k\rangle $$
    
    Consider now $\mathbb{C}^2\otimes \mathbb{C} ^2$. The standard basis is $|00\rangle, |01\rangle, |10\rangle,|11\rangle$ in that order. The $4\times 4$ matrix of an operator here is then
    
    $$ \begin{bmatrix}A_{00,00}&A_{00,01}&\cdots\\A_{01,00}&\cdots\\\vdots\\A_{11,00}&\cdots&&A_{11,11}\end{bmatrix} $$
    
    where $A_{00,00}=\langle00|A|00\rangle$ etc.
    
    For example then, the matrix of $X\otimes Z$ w.r.t. the standard basis is
    
    $$ \begin{bmatrix}0&0&1&0\\0&0&0&-1\\1&0&0&0\\0&-1&0&0\end{bmatrix} $$