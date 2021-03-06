# Иерархия цифровых систем передачи

[Цифра в общем](./digital.md)

Зачем нужна иерархия? Потому что мы хотим стандартизовать способы мультиплексирования. Ступень иерархии - это способ мультиплексирования N каналов. Следующая ступень - `k*N` каналов

1. Плезиохронная цифровая иерархия - исторически первая. Бывает европеская, североамериканская, японская.
2. Синхронная цифровая иерархия

Оба используют временное разделение каналов.

64 КБит/с - оцифрованный поток на выходе из микрофона - основной цифровой канал.

## Европейская плезиохронная

https://ru.wikipedia.org/wiki/Плезиохронная%5Fцифровая%5Fиерархия

https://docs.google.com/document/d/1r4StdxBV8QP-geDSIKnM5J4Ywu0DQqEcr0f7SR8_Ta0/edit

Допускает разные скорости потоков на разных станциях, даже в пределах одной ступени. Но разность должна быть в пределахх нестабильности частот задающих генераторов.

Уровни:
1. 30 ОЦК, 2 МБит/с
2. 4 первых уровней и 8 МБит/с
3. 4 вторых уровня и 34 МБит/с
4. 4 третьих уровня и 140 МБит/с

Большие скорости не допускаются.

Объединение меньших уровней - поочерёдно записываются пакеты каждого ОЦК в групповой поток

Передача на первом уровне: цикл в 32 интервала, один интервал - 8 бит. 0-й и 16-й интервалы - синхросигналы и служебная информация. У антохи подробнее таблица, что за служебная информация.

Передача на высших уровнях: 8 бит служебной информации || 256 бит нижнего уровня.
На нечётных итерациях посылается цикловой синхросигнал в служебной информации.
Биты нижнего уровня передаются по очереди: 1-2-3-4-1-... по одному биту.

[синхронизация](./multichannel.md)

Недостатки PDH:
1. Их три разновидности
2. Затруднён ввод и вывод потоков низших уровней иерархии
3. Отсутствуют средства автоматизированного контроля и управления
4. При потере синхронизации на восстановление уходит долгое время

## Синхронная цифровая иерархия

https://docs.google.com/document/d/1nFcGuUpsbsZuzOcPaM5vLhSPq9z7TMgQEY32jFhGhDE/edit

https://en.wikipedia.org/wiki/Synchronous_optical_networking#Framing

Исправляет недостатки PDH.
Позволяет создать универсальную транспортную сеть, сочетающую в себе функции
передачи, контроля и управления.
Обеспечивает скорости от 155 МБит/с и позволяет транспортировать потоки почти
всех известных цифровых систем передачи.
Системы программно управляемы и интегрируют в себе функции из второго предложения.
А ещё аппаратура стандартизована.

Среда передачи - оптоволокно, хотя можно радиореле.
Делится на три независимых функциональных слоя. Каждый слой обслуживает вышележащий и имеет определённые точки доступа к этому слою. Независимость слоёв позволяет им иметь свои средства контроля и управления.

Подробные детали структуры вообще непонятные. Там есть контейнеры, есть виртуальные контейнеры, но единица передачи - это вроде как STM, и не монада, а синхронный транспортный модуль.
