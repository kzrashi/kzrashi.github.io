# 数学Ⅲ

## 1. 極限

## 2. 微分
### 2.1. 導関数

$$
f'(x) = \lim_{h \to 0} \frac{f(x+h)-f(x)}{h}
$$



$$
(x^{n})' = nx^{n-1}
$$

$$
\{k{f(x)'}\} = kf'(x)
$$

$$
\{{f(x)'} + g(x)'\} = f'(x) + g'(x)
$$

$$
\{k{f(x)'} + lg(x)'\} = kf'(x) + lg'(x)
$$


- 積の微分法(積の導関数)  

$$
\{f(x)g(x)\}' = f'(x)g(x) + f(x)g'(x)
$$

ex)

$$
y = (2x)(3x)
$$

$$
y' = 2 \times (3x) + (2x)\times 3
$$

- 商の微分法(商の導関数)  

$$
\{\frac{f(x)}{g(x)}\}' = \frac{f'(x)g(x) - f(x)g'(x)}{\{g(x)^{2}\}}
$$


$$
\{\frac{1}{g(x)}\}' = \frac{f'(x)g(x) - f(x)g'(x)}{\{g(x)^{2}\}}
$$

## 3. 合成関数  
- xx
$$
\{\frac{f(x)}{g(x)}\}' = \frac{f'(x)g(x) - f(x)g'(x)}{\{g(x)^{2}\}}
$$

- ex)

$$
y=(x^{3})^{2}

$$
$$
y'=((x^{3})^{2})' \times (x^{3})' = 2(x^{3}) \times (3x^{2})
$$

## 4. 逆関数の導関数  
- 公式

$$
(x^{r})' = rx^{r-1} 
$$

- ex)

$$
y = \sqrt[5]{x^{2}}
$$

$$
y' = x^{\frac{2}{5} - 1} = \frac{2}{5} \times x^{- \frac{3}{5}} = \frac{2}{5 \sqrt[5]{x^{3}}}
$$



## 5. 三角関数の導関数
- sinの微分

$$
(\sin{x})' = \cos{x}
$$

- cosの微分

$$
(\cos{x})' = -\sin{x}
$$

- tanの微分

$$
(\tan{x})' = \frac{1}{\cos{x}^{2}}
$$

- ex)
合成関数の公式と三角関数の公式を組み合わせる

$$
y = \sin^{2}{x}
$$


$$
y' = (\sin{x})^{2} = 2 \times (\sin{x}) \times (\sin{x})'= 2 \times (\sin{x}) \times (\cos{x})= 2\sin{x}\cos{x}
$$

$$
y' = (\sin{x})^{2} = \\
2 \times (\sin{x}) \times (\sin{x})'= \\
2 \times (\sin{x}) \times (\cos{x}) = \\
2\sin{x}\cos{x}
$$

## 6. 対数関数の導関数

- 底がeの場合

$$
(\log{x})' = \frac{1}{x}
$$

- 底がe**以外**の場合

$$
(\log_{a}{x})' = \frac{1}{xlog{a}}
$$


- 底がeの場合で、絶対値有り

$$
(\log{|x|})' = \frac{1}{x}
$$

- 底がe**以外**の場合で、絶対値有り

$$
(\log_{a}{|x|})' = \frac{1}{xlog{a}}
$$


## 6. 指数関数の導関数

- 基数がeの場合

$$
(e^{x})' = e^{x}
$$

- 基数がe**以外**の場合

$$
(a^{x})' = a^{x} \times \log{a}
$$

- ex
合成関数を組み合わせる

$$
y' = (e^{-x^{2}})' = e^{-x^{2}} \times (-x^{2})' = -2xe^{-x^{2}}
$$


