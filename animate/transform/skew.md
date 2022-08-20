# skew()
Наклон элемента. Может задаваться в следующих единицах: `deg`, `rad`, `grad`, `turn`. При положительных значениях, элемент наклоняется влево, при отрицательных, вправо.

- transform: skewX(15deg) // наклон элемента относительно оси X
- transform: skewY()
- transform: skew()

Примеры:

    transform: skewX(45deg);
    transform: skewY(45deg);
    transform: skew(30deg); // только по оси X
    transform: skew(30deg, 30deg);
    transform: skewX(30deg) skewY(30deg);
    transform: skewY(30deg) skewX(30deg);

У трех последних примеров анимация отличается, не смотря на одинаковые значения.
