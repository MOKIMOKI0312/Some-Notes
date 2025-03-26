## Laplace Transform
$$
F(s) = \int_0^\infty f(t) e^{-st} dt
$$

Example:
$$
f(t) = e^{at}
$$
- depends on t and a
$$
F(s) = \int_0^\infty e^{at} e^{-st} dt = \frac{e^{(a-s)t}}{a-s} \bigg|_0^\infty = \frac{1}{s-a}
$$
- depends on s and a
- "pole" at s=a, "zero" at s=0

$$
\frac{dy}{dt} - ay = 0 \tag{1}
$$
$$
\frac{dy}{dt} \xrightarrow{LT} \int_0^\infty \frac{dy}{dt} e^{-st} dt = \int_0^\infty y(t)(-se^{-st}) dt +[y(0)e^{-st}]_0^\infty = sY(s) - y(0)
$$

SO 
$$
(1) \xrightarrow{LT} sY(s) - y(0) - ay = 0 ,
$$
$$
Y(s) = \frac{y(0)}{s+a} \xRightarrow{INVERSE,L.T} y(t) = y(0)e^{-at} \tag{2}
$$

---

$$
\frac{dy}{dt} - ay = e^{ct} \tag{3}
$$
$$
sY(s) - y(0) - aY(s) = \frac{1}{s-c} 
$$
$$
Y(s) = \frac{1}{(s-a)(s-c)} + \frac{y(0)}{(s-a)}\tag{4}
$$
> what do we do with this?
seprate the two terms, and take inverse L.T. of each term.

$$
Y(s) = \frac{1}{(s-a)(s-c)}= \frac{1}{(s-c)(c-a)} + \frac{1}{(a-c)(s-a)}\xRightarrow{L.t}
\frac{e^{ct}-e^{at}}{c-a}
$$


> I still don't get it....

## 1. 引入
$$
\dot{x} + 3x(t) = 0
$$
想得到代数方程：
$$
sX(s) - x(0) + 3X(s) = 0
$$
$$
X(s) = \frac{x(0)}{s+3}
$$
> 频域
> 得到频域变换中的解后，经过逆变换，得到时域解

$$
F(s)  =\int_0^\infty f(t)e^{-st} dt
$$

## 2. 常见的拉氏变换对
1. 阶跃函数
$$
f(t) = 
\begin{cases}
0 & t < 0 \\
1 & t \geq 0
\end{cases}
$$
$$
F(s) = \int_0^\infty e^{-st} dt = - \frac{1}{s}\int_0^\infty e^{-st} d(st) = \frac{1}{s}
$$

2. 斜坡信号
$$
f(t) = t 
$$
$$
F(s) = \mathcal{L}[f(t)] = \int_0^\infty t e^{-st} dt = \frac{1}{s^2}
$$

3. 加速度函数
$$
f(t) = \frac{1}{2}t^2
$$
$$
F(s) = \mathcal{L}[f(t)] = \int_0^\infty \frac{1}{2}t^2 e^{-st} dt = \frac{2}{s^3}
$$

4. 冲激函数
$$
\delta(t) =
\begin{cases}
0 & t \neq 0 \\
\infty & t = 0
\end{cases}
$$
$$
F(s) = \int_0^\infty \delta(t) e^{-st} dt = 1
$$

## 3. 拉氏变换的性质
1. 线性性质
$$
\mathcal{L}[af(t) + bg(t)] = aF(s) + bG(s)
$$
2. 位移性质
$$
\mathcal{L}[f(t)] = F(s) \Rightarrow \mathcal{L}[e^{-at}f(t)] =F(s+a)
$$
3. 延迟性质
$$
\mathcal{L}[f(t)] = F(s) \Rightarrow \mathcal{L}[f(t-\tau)] = e^{-s\tau}F(s)
$$

## 4. 定理
1. 微分定理
$$
\mathcal{L}[f'(t)] = sF(s) - f(0)
$$
2. 积分定理
$$
\mathcal{L}[\int_0^t f(\tau) d\tau] = \frac{1}{s}F(s)
$$
3. 终值定理
$$
\lim_{t \to \infty} f(t) = \lim_{s \to 0} sF(s)
$$