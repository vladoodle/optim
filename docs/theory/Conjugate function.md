---
layout: default
parent: Theory
title: Conjugate function
nav_order: 5
---

# Conjugate (dual) function

Пусть $$f: \mathbb{R}^n \to \mathbb{R}$$. 
Функция $$f^*: \mathbb{R}^n \to \mathbb{R}$$ называется сопряжённой функцией к функции $$f(x)$$ и определена как

$$
f^*(y) = \sup\limits_{x \in \mathbf{dom} \; f} \left( \langle y,x\rangle - f(x)\right).
$$
Область определения $$f^*$$  это множество таких $$y$$, что супремум конечен. 
![](../conj.svg)

## Properties
* $$f^*(y)$$ - выпуклая функция как поточечный супремум функций выпуклых по $$y$$
* Неравенство Фенхеля - Юнга: 
	
	$$
	f(x) + f^*(y) \ge \langle y,x \rangle
	$$

* Пусть функции $$f(x). f^*(y), f^{**}(x)$$ определены на $$\mathbb{R}^n$$. Тогда $$f^{**}(x) = f(x)$$ тогда и только тогда, когда $$f(x)$$ - выпуклая функция.

![](../doubl_conj.svg)

* Частный случай сопряжения, когда функция дифференцируема называется преобразованием Лежандра. Пусть $$f(x)$$ - выпукла и дифференцируема, $$\mathbf{dom}\; f = \mathbb{R}^n$$. Тогда $$x^* = \underset{x}{\operatorname{argmin}} \langle x,y\rangle - f(x)$$. В этом случае $$y = \nabla f(x^*)$$. Стало быть:
	
	$$
	f^*(y) = \langle \nabla f(x^*), x^* \rangle - f(x^*)
	$$

	$$
	f^*(y) = \langle \nabla f(z), z \rangle - f(z), \;\;\;\;\;\; y = \nabla f(z), \;\; z \in \mathbb{R}^n
	$$

* Пусть $$f(x,y) = f_1(x) + f_2(y)$$, где $$f_1, f_2$$ - выпуклые функции, тогда 
	
	$$
	f^*(p,q) = f_1^*(p) + f_2^*(q)
	$$

* Пусть $$f(x) \le g(x)\;\; \forall x \in X$$. Пусть так же $$f^*(y), g^*(y)$$ определены на $$Y$$. Тогда $$\forall x \in X, \forall y \in Y$$
	
	$$
	f^*(y) \ge g^*(y) \;\;\;\;\;\; f^{**}(y) \le g^{**}(y)
	$$

## Examples

Схема поиска сопряженной функции, в целом, стандартна:
1. Запись $$f^*(y) = \sup\limits_{x \in \mathbf{dom} \; f} \left( \langle y,x\rangle - f(x)\right)  = \sup\limits_{x \in \mathbf{dom} \; f} f(x,y)$$
1. Поиск тех значений $$y$$, при которых $$ \sup\limits_{x \in \mathbf{dom} \; f} f(x,y)$$ конечен. Эти значения составляют область определения сопряженной функции $$f^*(y)$$
1. Поиск $$x^*$$, при котором $$f(x,y)$$ достигает своего максимального значения как функция по $$x$$. $$f^*(y) = f(x^*, y)$$

### 1 
Найти $$f^*(y)$$, если $$f(x) = ax + b$$

Решение:
* Рассмотрим функцию, супремумом которой является сопряженная: $$\langle y,x\rangle - f(x) = yx - ax - b$$
* Построим область определения (т.е. те $$y$$, для которых $$\sup$$ конечен). Это одна точка $$y = a$$
* Значит, $$f^*(a) = -b$$

### 2
Найти $$f^*(y)$$, если $$f(x) = -\log x, \;\; x\in \mathbb{R}_{++}$$

Решение:
* Рассмотрим функцию, супремумом которой является сопряженная: $$\langle y,x\rangle - f(x) = yx + \log x$$.
* Эта функция не ограничена сверху при $$y \ge 0$$. Значит, $$\mathbf{dom} \; f^* = \{y < 0\}$$
* Её максимум достигается при $$x = -1/y$$. Значит, $$f^*(y) = -\log(-y) - 1$$

### 3
Найти $$f^*(y)$$, если $$f(x) = e^x$$

Решение:
* Рассмотрим функцию, супремумом которой является сопряженная: $$\langle y,x\rangle - f(x) = yx -e^x$$.
* Эта функция не ограничена сверху при $$y < 0$$. Значит, $$\mathbf{dom} \; f^* = \{y \ge 0\}$$ (с нулем лучше поработать аккуратнее)
* Её максимум достигается при $$x = \log y$$. Значит, $$f^*(y) = y \log y - y$$. Полагая, что $$0 \log 0 = 0$$.

### 4
Найти $$f^*(y)$$, если $$f(x) = x \log x, x \neq 0, \;\;\; f(0) = 0, \;\;\; x \in \mathbb{R}_+$$

Решение:
* Рассмотрим функцию, супремумом которой является сопряженная: $$\langle y,x\rangle - f(x) =xy - x \log x$$.
* Эта функция ограничена сверху при всех $$y$$. Значит, $$\mathbf{dom} \; f^* = \mathbb{R}$$ (с нулем лучше поработать аккуратнее)
* Её максимум достигается при $$x = e^{y-1}$$. Значит, $$f^*(y) = e^{y-1}$$.

### 5
Найти $$f^*(y)$$, если $$f(x) =\frac{1}{2} x^T A x, \;\;\; A \in \mathbb{S}^n_{++}$$

Решение:
* Рассмотрим функцию, супремумом которой является сопряженная: $$\langle y,x\rangle - f(x) =y^Tx - \frac{1}{2}x^TAx$$.
* Эта функция ограничена сверху при всех $$y$$. Значит, $$\mathbf{dom} \; f^* = \mathbb{R}$$ (с нулем лучше поработать аккуратнее)
* Её максимум достигается при $$x = A^{-1}y$$. Значит, $$f^*(y) =  \frac{1}{2}y^TA^{-1}y$$.

### 6
Найти $$f^*(y)$$, если $$f(x) =\max\limits_{i} x_i, \;\;\; x \in \mathbb{R}^n$$

Решение:
* Рассмотрим функцию, супремумом которой является сопряженная: $$\langle y,x\rangle - f(x) =y^Tx - \max\limits_{i}x_i$$.
* Заметим, что если вектор $$y$$ имеет хотя бы одну отрицательную компоненту, то эта функция не ограничена по $$x$$.
* Пусть теперь $$y \succeq 0, \;\;\; 1^T y > 1$$. $$y \notin \mathbf{dom \; f^*(y)}$$
* Пусть теперь $$y \succeq 0, \;\;\; 1^T y < 1$$. $$y \notin \mathbf{dom \; f^*(y)}$$
* Остается только $$y \succeq 0, \;\;\; 1^T y = 1$$. Тогда $$x^Ty \le \max\limits_i x_i$$
* Значит, $$f^*(y) = 0$$.