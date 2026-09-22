# Série de Fourier

Se $f(t)$ é uma função periódica de período $T$. Então:

$$
\omega_o = \frac{2\pi}{T}
$$

Seja a série de Fourier:

$$
f(t) = \sum_{n=0}^{\infty} [a_n \cos(n\omega_o t) + b_n \sin(n\omega_o t)] \tag{1}
$$

Para entender esta função é necessário encontrar os índices $a_n$ e $b_n$. Para determinar $a_n$, é necessário supor que existem funções periódicas distintas inicialmente para analisar o seu comportamento, supondo que exista uma função $\cos(m\omega_o t)$, onde será multiplicado e integrado temporalmente em (1) na forma:

$$
\int_0^T f(t)\cos(m\omega_o t)\,dt = \sum_{n=0}^{\infty}\Big[a_n\int_0^T \cos(n\omega_o t)\cos(m\omega_o t)\,dt + b_n\int_0^T \cos(n\omega_o t)\sin(m\omega_o t)\,dt\Big]
$$

Observe que para este caso, existe uma simetria na segunda integral, resultando em valor **nulo**. Isso implica que a solução só será possível nas seguintes condições, que podem ser representadas pela **Delta de Kronecker**:

$$
\delta_{nm} =
\begin{cases}
1, & n = m \\
0, & n \neq m
\end{cases}
\tag{2}
$$

Substituindo na equação:

$$
\int_0^T f(t)\cos(m\omega_o t)\,dt = \sum_{n=0}^{\infty} a_n \frac{T}{2}\delta_{nm} = a_m\frac{T}{2}
$$

Portanto, o índice $a_m$ será determinado na seguinte forma:

$$
a_m = \frac{2}{T}\int_0^T f(t)\cos(m\omega_o t)\,dt
$$

Pela equação (2), pode-se atribuir que $a_m = a_n$, então:

$$
a_n = \frac{2}{T}\int_0^T f(t)\cos(n\omega_o t)\,dt \tag{3}
$$

De maneira análoga, $b_n$ será:

$$
b_n = \frac{2}{T}\int_0^T f(t)\sin(n\omega_o t)\,dt \tag{4}
$$

De maneira geral, as equações (3) e (4) podem se associar ao espaço complexo ($\mathbb{C}$) de tal forma que:

$$
f(t) = \sum_{n=-\infty}^{\infty} C_n e^{in\omega_o t} \tag{5}
$$

ou,

$$
f(t) = \sum_{n=-\infty}^{\infty} C_n \exp(in\omega_o t) \tag{6}
$$

Onde,

$$
e^{in\omega_o t} = \exp(in\omega_o t) = \cos(n\omega_o t) + i\sin(n\omega_o t) \tag{7}
$$

## Funções de onda

Considere o exemplo de uma função de onda $y(x,t)$, com as seguintes condições de contorno na função:

$$
y(x=0, t) = 0
$$

$$
y(x=1, t) = 0
$$

e na derivada,

$$
\frac{\partial y}{\partial t}(x,0) = 0
$$

Dada a função de onda na representação diferencial:

$$
\frac{\partial^2 y}{\partial t^2} = v^2 \frac{\partial^2 y}{\partial x^2} \tag{8}
$$

Supondo que $y$ possa ser representado por um produto de funções $y(x,t) = X(x)T(t)$, a equação pode ser reescrita:

$$
D_t^2[T(t)]X(x) = v^2 \, \partial_x^2[X(x)]T(t)
$$

$$
D_x^2[X(x)]X(x)v^2 = \partial_t^2[T(t)]T(t) = -\omega^2
$$

Observe que ao lado direito da equação acima se encontra devido às funções temporais do sistema. Isso implica que temos um sistema:

$$
\begin{cases}
D_t^2[T(t)] = -\omega^2 T(t) \\[4pt]
D_x^2[X(x)] = \dfrac{-\omega^2}{v^2} X(x) = -K^2 X(x)
\end{cases}
\tag{9}
$$

Nas equações em (9), temos **Equações Diferenciais Ordinárias Lineares de Segunda Ordem**, cuja solução se enquadra fisicamente como soluções de oscilações ou em sistemas de massa-mola. Ao resolver essas equações, seus resultados são definidos como:

$$
\begin{cases}
X(x) = A \cos(Kx) + B \sin(Kx) \\
T(t) = C \cos(\omega t) + B \sin(\omega t)
\end{cases}
\tag{10}
$$

Isso fica nítido devido à relação $\omega$ com o tempo, evidenciando o comportamento perpétuo do sistema.

Aplicando as condições de contorno para determinar os índices da equação da posição em (10):

$$
X(0) = 0 = A \Leftrightarrow A = 0
$$

$$
X(L) = 0 = B \sin(KL) \Leftrightarrow KL = n\pi \Leftrightarrow K = \frac{n\pi}{L}
$$

Então, a solução espacial será

$$
X(x) = B \sin\left(\frac{n\pi x}{L}\right) \tag{11}
$$

onde $n = 1, 2, 3, \dots$

Determinando a parte temporal,

$$
\frac{\partial y}{\partial x}(x, 0) = 0 \Leftrightarrow D_t^1[T(t)] = 0
$$

cuja solução

$$
D_t^1[T(t)] = -\omega (C\sin(\omega t) + D\cos(\omega t)) = 0
$$

para $t = 0 \rightarrow D = 0$. Então:

$$
T(t) = C \cos(\omega t) \tag{12}
$$

Diante dessas soluções, é possível interpretar que na equação (11), $n$, além de ser um número positivo, pode representar um conjunto de família de funções chamadas $y_n(x,t)$. Isso permite generalizar a função na seguinte forma:

$$
y_n(x,t) = BC \sin\left(\frac{n\pi}{L}x\right) \cos\left(\frac{n\pi\omega}{L}t\right)
$$

As constantes $B$ e $C$ também são associadas à família de funções de $y_n$, acompanhando de tal maneira que seus respectivos valores podem ser obtidos por meio de uma expansão em série, então: $BC = \sum_{n=0}^{\infty} E_n$. Isso implica que pode ser escrito na forma

$$
y_n(x,t) = \sum_{n=0}^{\infty} E_n \sin\left(\frac{n\pi}{L}x\right) \cos\left(\frac{n\pi\omega}{L}t\right) \tag{13}
$$

No entanto, existe uma abordagem mais adequada para obter $E_n$. Observe que na equação (13), se associa a uma série de Fourier, que consequentemente pode ser escrito

$$
E_n = \frac{2}{L}\int_0^L g(x)\sin\left(\frac{n\pi}{L}x\right)dx \tag{14}
$$

onde $g(x) = y_n(x, t=0)$.

## Transformada de Fourier

As Transformadas de Fourier são interpretadas como a extensão das Séries de Fourier, cuja ideia inicial é determinar a mudança de espaços dependendo de como o problema é tratado. Utilizando a equação (6), para uma frequência natural ($\omega_o$) de um sistema qualquer será determinada na forma que se assemelha às equações (3) e (4):

$$
C_n = \frac{1}{T}\int_{T/2}^{T/2} f(t)e^{-in\omega_o t}\,dt \tag{15}
$$

onde $\omega_o = 2\pi/T$, sendo $T$ o período de oscilação.

Analisando os casos extremos entre frequência e período, sendo $T \rightarrow \infty \Rightarrow \omega_o \rightarrow 0$. Então, $\omega_o = \Delta\omega \rightarrow 0 \Rightarrow n\omega_o = n\Delta\omega = \omega$. A frequência $\omega$ caracteriza o comportamento contínuo da grandeza ao longo do sistema.

Sendo assim, na relação frequência e período, pode-se substituir o valor de $T$ como sendo

$$
T = \frac{2\pi}{\Delta\omega}
$$

Então a equação (15) ficará na forma

$$
C_n = \frac{1}{\frac{2\pi}{\Delta\omega}}\int_{-\infty}^{\infty} f(t)e^{-i\omega t}\,dt
$$

$$
C(\omega) = \frac{2\pi}{\Delta\omega}\int_{-\infty}^{\infty} f(t)e^{-i\omega t}\,dt \tag{16}
$$

Substituindo a equação (16) na equação (6)

$$
f(t) = \sum_{-\infty}^{\infty} \left[\frac{\Delta\omega}{2\pi}\right] \left[\int_{-\infty}^{\infty} f(t)\,e^{-i\omega t}\,dt\right] e^{-in\Delta\omega t} \tag{17}
$$

onde,

$$
F(n\Delta\omega) = \left[\frac{\Delta\omega}{2\pi}\right] \left[\int_{-\infty}^{\infty} f(t)\, e^{-i\omega t}\, dt\right]
$$

Então,

$$
f(t) = \frac{1}{2\pi} \sum_{-\infty}^{\infty} F(n\Delta\omega)\, e^{-in\Delta\omega t}\, \Delta\omega
$$

Aplicando o limite da função, obtemos a transformada

$$
f(t) = \frac{1}{2\pi}\int_{-\infty}^{\infty} F(\omega)\, e^{i\omega t}\, d\omega \tag{18}
$$

A equação (18) explica a transição de espaços de tempo e frequência que dependem de como o tratamento do problema será analisado.