# Многоканальные системы связи

https://docs.google.com/document/d/1tLINO26MNxYWR0DsPJchuuvhmUGLGZRDDzkwemwnJ0w/

К коммутатору подсоединяется много входных проводов. Коммутатор передаёт все их сигналы дальше по одному проводу. Выходной коммутатор должен разделить эти сигналы на много выходных проводов.

## Временное разделение
В один момент времени передаётся сигнал одного провода. Приёмник и передатчик должны быть синхронизированы по времени. Для принудительной синхронизации иногда передаются синхросигналы.

В основном она используется в цифровых системах передачи.

Три уровня синхоронизации:

1. Тактовая: обестпечивает равенство скоростей обработки сигналов в линейных регенераторах, кодеках и прочем.

2. Цикловая: обеспечивает выделение кодовых групп сигналов, декодирование сигналов и распределение сигналов по соответствующим каналам

3. Сверхцикловая: обеспечивает распределние сигналов управления и взаимодействия по соответсвующим каналам на приёмной стороне системы связи.

## Частотное разделение
https://en.wikipedia.org/wiki/Frequency-division_multiplexing

У нас есть полоса частот, в которой мы можем передавать сигналы. Разделим её на промежутки (разделённые полосой непропускания), и в каждом промежутке будем передавать по хитрому закодированный сигнал.

Baseband - сигнал, который мы хотим закодировать. Carrier - сигнал, которым мы переносим закодированный. Его частота заметно больше.

Baseband запихивается в carrier с помощью модуляции: амплитодной или угловой (частотная и фазовая).

Про модуляцию: https://docs.google.com/document/d/1sTnMLiTremnwZUvpF7XVG0y9BptAzU5e9tHtRyl3z-M/edit и конец https://docs.google.com/document/d/1YdOoOsuV8So59lmoTvCwExqVGnBXd5_QVfsQJBbQHMw/edit