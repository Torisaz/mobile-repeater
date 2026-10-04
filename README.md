Meshcore 1.17 Modded repeater
This allows you to run a main house repeater,  with a sub repeater, mobile or fixed backup, 
that will only transmit when not in range of the main repeater or will transmit if the 
main repeater does not hear a message

setting tx delays up to 1.0 is fine in both mobile rep and house rep 
set prox.list put your house repeater instead of aa or it wont work

example settings

set loop.detect strict
set prox on
set prox.snr 8
set prox.hold 0
set prox.list aa,aaaa,aaaaaa
set txdelay 0.5
set txdelay.direct 0.5

get loop.detect
get prox
get txdelay
get direct.delay


-D MOBILE_DELAY=6000 ; generic for mobile rep up to txdelay 1.0

and they will then be staggered approx 6 seconds + txdelay

table of txdelay and direct.txdelay settings to real world

Setting | Random transmit delay window | Approx average delay

txdelay 0.2 | 0 to 1000 ms | 500 ms

txdelay 0.3 | 0 to 1500 ms | 750 ms

txdelay 0.5 | 0 to 2500 ms | 1250 ms

txdelay 0.8 | 0 to 4000 ms | 2000 ms

txdelay 1.0 | 0 to 5000 ms | 2500 ms

if you run with txdelay of 0.5 then -D MOBILE_DELAY=3000 ; will bring down latency

I haven't got round to trying it monitoring 2 repeaters before transmitting eg
set prox.list aa,aaaa,aaaaaa,bb,bbbb,bbbbbb

It was based on the following code.. 

https://github.com/lil-jimmy-93/ProximitySuppress 

