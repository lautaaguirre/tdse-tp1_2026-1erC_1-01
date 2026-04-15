Modelo de sensor

Eventos: EV\_BTN\_XX\_UP / EV\_BTN\_XX\_DOWN
Estados:ST\_BTN\_XX\_UP / ST\_BTN\_XX\_FALLING /ST\_BTN\_XX\_DOWN / ST\_BTN\_XX\_RISING
Signal: EV\_SYS\_XX\_UP / EV\_SYS\_XX\_DOWN



|CURRENT STATE|EVENT|\[GUARD]|NEXT STATE|ACTIONS|
|-|-|-|-|-|
|ST\_BTN\_XX\_UP|EV\_BTN\_XX\_UP||ST\_BTN\_XX\_UP||
|ST\_BTN\_XX\_UP|EV\_BTN\_XX\_DOWN||ST\_BTN\_XX\_FALLING|tick = DEL\_BTN\_XX\_MAX|
|ST\_BTN\_XX\_FALLING|EV\_BTN\_XX\_UP|\[tick > 0]|ST\_BTN\_XX\_FALLING|tick--|
|ST\_BTN\_XX\_FALLING|EV\_BTN\_XX\_UP|\[tick == 0]|ST\_BTN\_XX\_UP||
|ST\_BTN\_XX\_FALLING|EV\_BTN\_XX\_DOWN|\[tick > 0]|ST\_BTN\_XX\_FALLING|tick--|
|ST\_BTN\_XX\_FALLING|EV\_BTN\_XX\_DOWN|\[tick == 0]|ST\_BTN\_XX\_DOWN|raise EV\_SYS\_XX\_DOWN|
|ST\_BTN\_XX\_DOWN|EV\_BTN\_XX\_UP||ST\_BTN\_XX\_RISING|tick = DEL\_BTN\_XX\_MAX|
|ST\_BTN\_XX\_DOWN|EV\_BTN\_XX\_DOWN||ST\_BTN\_XX\_DOWN||
|ST\_BTN\_XX\_RISING|EV\_BTN\_XX\_UP|\[tick > 0]|ST\_BTN\_XX\_RISING|tick--|
|ST\_BTN\_XX\_RISING|EV\_BTN\_XX\_UP|\[tick == 0]|ST\_BTN\_XX\_UP|raise EV\_SYS\_XX\_UP|
|ST\_BTN\_XX\_RISING|EV\_BTN\_XX\_DOWN|\[tick > 0]|ST\_BTN\_XX\_RISING|tick--|
|ST\_BTN\_XX\_RISING|EV\_BTN\_XX\_DOWN|\[tick == 0]|ST\_BTN\_XX\_DOWN||



