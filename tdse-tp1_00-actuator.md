

|CURRENT STATE|EVENT|GUARD|NEXT STATE|ACTION|
|-|-|-|-|-|
|ST\_LED\_OFF|EV\_LED\_ON||ST\_LED\_ON|led\_on()|
|ST\_LED\_OFF|EV\_LED\_OFF||ST\_LED\_OFF||
|ST\_LED\_OFF|EV\_LED\_BLINK||ST\_LED\_BLINK|tick=MAX\_BLINK, led\_on()|
|ST\_LED\_ON|EV\_LED\_ON||ST\_LED\_ON||
|ST\_LED\_ON|EV\_LED\_OFF||ST\_LED\_OFF|led\_off()|
|ST\_LED\_ON|EV\_LED\_BLINK||ST\_LED\_BLINK|tick=MAX|
|ST\_LED\_BLINK|EV\_LED\_ON||ST\_LED\_ON|led\_on()|
|ST\_LED\_BLINK|EV\_LED\_OFF||ST\_LED\_OFF|led\_off()|
|ST\_LED\_BLINK|EV\_LED\_BLINK|tick>MAX\_MEDIO|ST\_LED\_BLINK|tick--|
|ST\_LED\_BLINK|EV\_LED\_BLINK|tick==MAX\_MEDIO|ST\_LED\_BLINK|led\_off(), tick--|
|ST\_LED\_BLINK|EV\_LED\_BLINK|tick<MAX\_MEDIO|ST\_LED\_BLINK|tick--|
|ST\_LED\_BLINK|EV\_LED\_BLINK|tick==0|ST\_LED\_BLINK|led\_on(),tick = MAX\_BLINK|



