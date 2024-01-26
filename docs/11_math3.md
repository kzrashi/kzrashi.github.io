# 数学 Ⅲ

## 1. 分数関数

- 基本形

$$
y = \frac{k}{x-p} + q
$$

- 派生形

$$
y = \frac{ax+b}{bx+d}
$$

- ex)
  分子(2x+1)を分母(x+1)で割ると、2 余り 1

$$
y = \frac{2x+1}{x+1} = \frac{2(2x+1)-1}{x+1} = \frac{2(x+1)}{x+1} - \frac{-1}{x+1} = 2 - \frac{-1}{x+1}
$$

## 2. 極限

## 3. 微分

### 3.1. 導関数

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

- 分子が 1 の場合、以下の公式が使える  
  ※**マイナス**がつくことに注意

$$
\{\frac{1}{g(x)}\}' = \color{red}-\color{black} \frac{g(x)'}{\{g(x)^{2}\}}
$$

- ex)

$$
\{\frac{1}{2x+3}\}' = - \frac{2}{(2x+3)^{2}}
$$

### 3.2. 合成関数

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

### 3.3. 逆関数の導関数

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

### 3.4. 三角関数の導関数

- sin の微分

$$
(\sin{x})' = \cos{x}
$$

- cos の微分

$$
(\cos{x})' = -\sin{x}
$$

- tan の微分

$$
(\tan{x})' = \frac{1}{\cos{x}^{2}}
$$

- tan の微分

$$
(\frac{1}{\tan{x}})' = - \frac{1}{\sin{x}^{2}}
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

### 3.5. 対数関数の導関数

- 底が e の場合

$$
(\log{x})' = \frac{1}{x}
$$

- 底が e**以外**の場合

$$
(\log_{a}{x})' = \frac{1}{xlog{a}}
$$

- 底が e の場合で、絶対値有り

$$
(\log{|x|})' = \frac{1}{x}
$$

- 底が e**以外**の場合で、絶対値有り

$$
(\log_{a}{|x|})' = \frac{1}{xlog{a}}
$$

### 3.6. 指数関数の導関数

- 基数が e の場合

$$
(e^{x})' = e^{x}
$$

- 基数が e**以外**の場合

$$
(a^{x})' = a^{x} \times \log{a}
$$

- ex
  合成関数を組み合わせる

$$
y' = (e^{-x^{2}})' = e^{-x^{2}} \times (-x^{2})' = -2xe^{-x^{2}}
$$

## 4. 積分

### 4.1. 不定積分

- a != 1 のとき

$$
\int x^{a} dx = \frac{1}{a+1} \cdot x^{a+1} + C
$$

- a = -1

$$
\int \frac{1}{x} dx = \log |x| + C
$$

- ex

$$
\int \frac{1}{x^{4}} dx = (x^{-4}) dx = \frac{1}{-4+1} \cdot x^{-4+1} = - \frac{1}{3x^{3}} + C
$$

### 4.2. 三角関数の不定積分

$$
\int \sin{x} dx = -\cos{x} + C
$$

$$
\int \cos{x} dx = \sin{x} + C
$$

$$
\int \frac{1}{\cos^{2}{x} } dx = \tan{x} + C
$$

$$
\int \frac{1}{\sin^{2}{x} } dx = - \frac{1}{\tan{x}} + C
$$

### 4.3. 指数関数の不定積分

$$
\int e^{x}dx = e^{x} + C
$$

$$
\int a^{x}dx = \frac{a^{x}}{log{a}} + C
$$

### 4.4. 対数関数の不定積分

$$
\int log{x}dx = \int 1 \times log{x}dx = xlogx - x + c
$$

### 4.5. 三角関数の不定積分

$$
\sin{x} \cos{x} = \frac{sin2x}{1}
$$

$$
\sin^{2}{x} = \frac{1 - cos2x}{2}
$$

$$
\cos^{2}{x} = \frac{1 + cos2x}{2}
$$

$$
\sin{\alpha} \cos{\beta} = \frac{1}{2}(\sin{\alpha + \beta} + \sin{\alpha - \beta})
$$

$$
\cos{\alpha} \sin{\beta} = \frac{1}{2}(\sin{\alpha + \beta} - \sin{\alpha - \beta})
$$
