# Дискретное преобразование фурье

Пусть есть 
```math
f(x) \in R[x], f = \sum^{n - 1}_{j = 0}f_jx^j <=> f=(f_0, f_1, \dots, f_{n-1}) \in R^n
```
$$f + g: \quad \sum_j(f_j + h_j)x^j <=> (f_0 + h_0, f_1 + g_1, \dots ,f_n + g_{n-1})$$
$$f g = \sum^{2n - 2}_{j=0}(\sum_{k+l = j}f_kg_e)x^j$$

Конкретно тема

Пусть R -- коммутативное кольцо с 1.

**Определение**
Пусть $n \in N, w \in R$
Тогда w -- корень n-ой степени из 1, если $w^n = 1$

**Определение** Примитивный корень n-ой степени из 1: $w \in R:$
```math
w^n = 1 \space и\space  \forall p \in P:\space p|n \space w^{\frac{n}{p}} - 1 \neq 0 \space(или\space w^{\frac{n}{p}}-1 \space не \space является \space делителем)
```
**Лемма** 

Пусть $w \in R$ -- примитивный корень n-ой степени из 1  
    $\forall l: \space 1 < l < n$. Тогда  
    1) $w_{n-1}^{l} - 1$ -- не делитель 0  
    2) $\sum^{n - 1}_{j = 0} \space w^{e}j = 0$  
Докозательство:  
```math 
\forall r \in R: (r - 1) \sum_{j=0}^{m-1} * r^{j} = r^{m} - 1, \space m \in N
```
g = ged(l, n)$  
p - простое: p|n  
g | $\frac{n}{p}$  
Пусть  
```math
r = w^g, \space m = \frac{n}{pg} \space (w^g - 1) \sum_{j=0}^{m-1}w^{gj} = (w^g)^{\frac{n}{pg} - 1}, \space (w^g - 1) = t = w^{\frac{n}{p}} - 1
``` 
Предположим $\exists s \in R:  s(w^g - 1) = 0$
```math
0 = s(w^g - 1)t = (w^{\frac{n}{p} - 1})s => s = 0
```
  
```math
\exists a, b: (по \space расш \space алг \space Евклида)
```
  
$a l + bn = g$  
$r = w^l, m = a$  
$\exists t \in R:$  
```math
(w^l - 1)t = w^{al}*1 - 1 = w^{al + bn} - 1 = w^g - 1
```
Пусть $r = w^l, \space m = n \space => \space \sum_{j=0}^{n-1} w^{lj} = 0$

## Что-то еще
**Пусть** $f \in R, \space deg \space f< n, \space w \in R$ -- примитивный корень n-ой степени из 1  
***Определение. Дискретным преобразованием Фурье (ДПФ\DFT) называется:***
```math
DFT_w : R^n \to R^n  

f \to (f(1), f(w), f(f^2), \dots, f(w^{n-1}))
```

**Определение.** Сверткой многочленов $f, g \in R[x], \space deg \space f \lt n, \space deg \space f \space g \lt n$  
наз $h \in R[x], \space deg \space h < n:$
```math
h = f \star g = (h_0, h_1, \dots, h_{n-1}), \space где \space h_R = \sum_{i + j = R(mod\space n)}f_i g_j
```

*Замечание.* $f, g \in R[x], \space deg \space f \lt n, \space deg \space g \lt \space n$:
```math
f\dot g \space mod(x^n - 1) = f \star g
```
**Доказательство:**  
  $x^m \space mod(x^n - 1)$  
  $x^n \space mod(x^n) = (x^n - 1 + 1)mod(x^n - 1) = 1$  
  $x^{g - n} \space mod(x^n - 1)= 1$  
  $m = g - n + l: \space x^m = x^{g - n L} \space mod(x^n - 1)= x^l = x^{m \space mod n}$  

**Лемма**  
$f, g \in R[x], \space \space f \lt n, \space deg \space g \lt n$
```math
DFT_w(f \star g) = DFT_w(f)* DFT_w(g) \space (покомпонентное)
```

**Доказательство:**  
```math
(f * g)mod(x^n - 1) = f \star g \quad f \star g = f * g + g(x)(x^n - 1)
```

```math
f \star g(w^l) = f(w^l) * g(w^l) + g(w^l)*(w^{ln} - 1), \quad f \star g(w^l) = f(w^l)* g(w^l)
```

*Замечание.*  
$h, g \in R[x]: \quad deg \space f + deg \space g \lt n$  
Тогда $f \star g = f * g$  
Утв. Вс условиях предыдущего замечания  
```math
f* g = f \star g = DFT_{w}^{-1}(DFT_w(f)*DFT_w(g))
```

  Утв.  $DFT_w^{-1} = DFT_{w^{-1}}$
  
