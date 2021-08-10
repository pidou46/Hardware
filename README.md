# Hardware


Switch from experimental breadbord wirring with dev kit boards to a more permanent solution, but not a mass production, this still for hobist.

#BOM

##ESP32-S modules :
- smaller
- economic : around 2_€ each
- power efficient (no usb to ttl, no led, to powering)












ESP32-S socket 3D printed




















STL file link

- very easy to print
- not a lot of material
- direct reading of pin number
- easy to solder
- ESP32-S module pad protection

soldering directly a wire to the pads works but cause them to peel very quickly

Soldering a module on this kind of adapter is barely impossible with soldering iron even with soldering flux. A hot air gun is mandatory 





















Flashing socket (adapter) :

This is quite expensive, but you only need one of these, it is used to (re)flash the modules. I guess it’s possible to avoid it and make the wiring by yourself on a separate board, but does it worth it ?



















Experimentation PCB :

10 unit = 0,7€



















https://fr.aliexpress.com/item/32952118086.html?spm=a2g0s.9042311.0.0.27426c37BQG98I


wires :

I use wires collected from phone cable from france (I think it’s the same wire than those in RJ45 cables)


Voltage regulator :

https://fr.aliexpress.com/item/32810810604.html?spm=a2g0s.9042311.0.0.27426c37BQG98I

price : 2 unit : 1_€

ultra-low Quiescent current





















Wiring to keep aces to serial REPL and flashing.









Module de flashage 




















Test avec le module de flashage 
ESP32-S
EN → 12,5_kohm → 3v3

ESP3-S → module flashage
EN → EN
IO0 → IO0
3v3 → 3v3
TX → TX
RX → RX



La broche EN doit être reliée au 3v3 par une résistance de l’ordre de 10Kohm (je n’en ai pas j’ai mis 12,5kohm. Y-a-t’il une conséquence sur la conso?)
Sinon le module reste en boucle.

Lorsque je connecte les broches au module de flashage, le bouton RST fonctionne correctement

Suivant les spécifications, la broche IO0 doit aussi être raccordée au 3v3 par une résistance de 10kohm, mais si je la raccorde je ne parviens pas a flasher avec Thonny.
Si je ne la raccorde pas cela fonctionne : testé uniquement avec un module déjà flashé préalablement avec un firmware micropython.

Test avec  USB TO TTL – CP2102

La communication fonctionne avec cette configuration



