# Цифровая обработка аналоговых сигналов

https://docs.google.com/document/d/1r4StdxBV8QP-geDSIKnM5J4Ywu0DQqEcr0f7SR8_Ta0/edit

http://kunegin.com/ref/lec/631.htm

[Цифра в общем](./digital.md)

Теорема Котельникова: любой непрерывный сигнал, ограниченный сверху частотой F, полностью представляется системой своих дискретных отсчётов с периодом T = 1/2F

АЦП: дискретизация (во времени) -> квантование (в амплитуде) -> кодирование

## Дискретизация
Вместо непрерывного сигнала берём значения сигнала в точки времени, расположенные на одном расстоянии. Период дискретизации из теоремы Котельникова.

## Квантование
Округляем амплитуду до ближайшей точки. Чтобы лучше уложиться в биты, количество точек - степень двойки. Эти точки - уровни квантования. Напряжение ограничения - верхнее значение напряжений уровней квантования.

Мощность шумов квантования и защищённость от шумов квантования.

Квантование может быть неравномерным, если шаги разной длины. Обычно имеет смысл делать более малые шаги на малых мощностях.

## Кодирование

Дискретные квантованные сигналы преобразуются в биты, а биты преобразуются в новый аналоговый сигнал.
