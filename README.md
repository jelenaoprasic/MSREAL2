**Domaći zadatak 2 iz Mikroračunarskih sistema u realnom vremenu**

*Zadatak: konfigurisati AXI Timer IP jezgro da radi u kaskadnom modu. Iskoristiti ovako konfigurisano jezgro za realizaciju štoperice.*

Uključivanje drajvera u kernel se realizuje komandom: _insmod ./axi_timer.ko_

Komunikacija korisnika sa drajverom se ostvaruje pomoću tri komande:
- Ukoliko korisnik posalje komandu: _echo "start" > /dev/axi_driver_, štoperica kreće da odbrojava.
- Ukoliko korisnik posalje komandu: _echo "stop" > /dev/axi_driver_, štoperica se zaustavlja.
- Ukoliko korisnik posalje komandu: _echo "restart" > /dev/axi_driver_, štoperica se resetuje na nulu.

Kada je štoperica zaustavljena _stop_ komandom, moguće je pokrenuti ponovo _start_ komandom, nakon čega se brojanje nastavlja.

Čitanje iz drajvera je realizovano komandom: _cat /dev/axi_driver_. Pozivanje ove komande ispisuje odbrojano vreme u terminalu. 
Očekivan format ispisa je sati: minute: sekunde. milisekunde, mikrosekunde. 

Isključivanje drajvera iz kernela je moguće komandom: _rmmod axi_timer.ko_.

