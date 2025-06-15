# Cel ćwiczenia

Oblicz Całkę $\frac{1}{2\pi i} \oint_C \frac{e^z dz}{z(1-z)^3}$ gdy:
- Punkt $z=0$ leży wewnątrz konturu $C$,
- Punkt $z=1$ leży wewnątrz konturu $C$,
- Zarówno punkt $z=0$ jak i $z=1$ leżą wewnątrz konturu $C$.

# Wstęp teoretyczny

```{admonition} Twierdzenie Cauchy'ego o residuach
W rozwiązaniu zadania skorzystano przede wszystkim z twierdzenia **Cauchy'ego o residuach**.
Twierdzenie to mówi, że:

$$
\oint_C f(z) dz = 2\pi i \sum_{k} Res(f, z_k)
$$ (tw-cauchy)

([literatura 1. i 2.](#literatura))
```

```{admonition} Wzór na residuum w biegunie
W celu obliczenia biegunu $n$-rzędu w punkcie $z_0$ można wykorzystać
następujący wzór:

$$
Res(f, z_0) = \frac{1}{(n-1)!} \lim_{z \to z_0} \frac{d^{n-1}}{dz^{n-1}} \left( (z-z_0)^n f(z) \right)
$$ (res)

([literatura 3. i 4.](#literatura))
```

# Rozwiązanie

## Obliczenie Residuów

Pierwszym krokiem jest obliczenie residuów funkcji $f(z) = \frac{e^z}{z(1-z)^3}$ w punktach $z=0$ i $z=1$.
Korzystająz ze wzoru {eq}`res` mamy:

Dla $z_0 = 0$

$$
Res(f, 0) &= \frac{1}{(1-1)!} \lim_{z \to 0} \frac{d^{1-1}}{dz^{1-1}} \left( (z-0)^1 f(z) \right) \\
&= \lim_{z \to 0} z f(z) \\
&= \lim_{z \to 0} \cancel{z} \frac{e^z}{\cancel{z}(1-z)^3} \\
&= \lim_{z \to 0} \frac{e^z}{(1-z)^3} \\
&= 1
$$ (res0)

Natomiast dla $z_0 = 1$:

$$
Res(f, 1) &= \frac{1}{(3-1)!} \lim_{z \to 1} \frac{d^{3-1}}{dz^{3-1}} \left( (z-1)^3 f(z) \right) \\
&= \frac{1}{2} \lim_{z \to 1} \frac{d^{2}}{dz^{2}} \left( (z-1)^3 \frac{e^z}{z(1-z)^3} \right) \\
&= \frac{1}{2} \lim_{z \to 1} \frac{d^{2}}{dz^{2}} \left( \cancel{(z-1)^3} \frac{-e^z}{z\cancel{(z-1)^3}} \right) \\
&= \frac{1}{2} \lim_{z \to 1} \frac{d^{2}}{dz^{2}} \left( \frac{-e^z}{z} \right) \\
&= \frac{1}{2} \lim_{z \to 1} \frac{d}{dz} \left( \frac{-e^z}{z} + \frac{e^z}{z^2} \right) \\
&= \frac{1}{2} \lim_{z \to 1} \frac{d}{dz} e^z \left( \frac{1}{z^2} - \frac{1}{z} \right) \\
&= \frac{1}{2} \lim_{z \to 1} e^z \left( \frac{1}{z^2} - \frac{1}{z} \right) + e^z \left( \frac{-2}{z^3} + \frac{1}{z^2} \right) \\
&= \frac{1}{2} \lim_{z \to 1} e^z \left( \frac{-1}{z} + \frac{2}{z^2} - \frac{2}{z^3} \right) \\
&= \frac{1}{2} e \left( -1 + 2 - 2 \right) \\
&= \frac{-e}{2}
$$ (res1)

## Obliczenie wartości całek

Zgodnie z twierdzeniem {eq}`tw-cauchy` możemy teraz obliczyć wartość całki

$$
I = \frac{1}{2\pi i} \oint_C \frac{e^z}{z(1-z)^3} dz = \frac{1}{\cancel{2\pi i}} \cancel{2\pi i} \sum_{k} Res(f, z_k)
$$

### Gdy $z=0$ leży wewnątrz konturu $C$

$$
I = 1
$$

### Gdy $z=1$ leży wewnątrz konturu $C$

$$
I = \frac{-e}{2}
$$

### Gdy zarówno $z=0$ jak i $z=1$ leżą wewnątrz konturu $C$

$$
I = 1 - \frac{e}{2}
$$

# Literatura

1. _Residue Theorem_ [https://en.wikipedia.org/wiki/Residue_theorem](https://en.wikipedia.org/wiki/Residue_theorem). Dostęp: 14.06.2025 16:06
2. _Mariusz Przybycień - Matematyczne Metody Fizyki II: Wykład 2_ [https://home.agh.edu.pl/~mariuszp/wfiis_mmf2/wyklad_mmf2_2.pdf](https://home.agh.edu.pl/~mariuszp/wfiis_mmf2/wyklad_mmf2_2.pdf). Dostęp: 14.06.2025 16:06
3. _Residue (complex analysis): Calculation of residues_ [https://en.wikipedia.org/wiki/Residue_(complex_analysis)](https://en.wikipedia.org/wiki/Residue_(complex_analysis)). Dostęp: 14.06.2025 16:21
4. _Mariusz Przybycień - Matematyczne Metody Fizyki II: Wykład 3_ [https://home.agh.edu.pl/~mariuszp/wfiis_mmf2/wyklad_mmf2_3.pdf](https://home.agh.edu.pl/~mariuszp/wfiis_mmf2/wyklad_mmf2_3.pdf). Dostęp: 14.06.2025 16:25
