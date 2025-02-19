---
author: Luka Vretenar, Vedran Miletić
---

# Upravljanje uslugama operacijskog sustava

!!! hint
    Za više informacija proučite [Chapter 6. Managing Services with systemd](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/System_Administrators_Guide/chap-Managing_Services_with_systemd.html) u [Red Hat Enterprise Linux 7 System Administrator's Guide](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/System_Administrators_Guide/).

- moderni operacijski sustavi bazirani na Linux jezgri koriste `systemd` za upravljane procesima i podizanje sustava

    - relativno novi alat, razvoj započeo Lennart Poettering 2010. godine tekstom [Rethinking PID 1](http://0pointer.de/blog/projects/systemd.html)
    - koristi značajke specifične za Linux jezgru kao što su [kontrolne grupe](https://en.wikipedia.org/wiki/Cgroups) (engl. *control groups*, cgroups), [signalfd](https://en.wikipedia.org/wiki/Event_loop), [epoll](https://en.wikipedia.org/wiki/Epoll) i druge
    - predmet [brojnih](https://www.zdnet.com/article/linus-torvalds-and-others-on-linuxs-systemd/) [debata](https://wiki.debian.org/Debate/initsystem/systemd), [kritika](https://ewontfix.com/14/) i [inženjerskih](https://plus.google.com/+LennartPoetteringTheOneAndOnly/posts/VUzeRLf5g5m) [šala](https://archive.rebeccablacktech.com/g/thread/44805517)

- najpopularniji prethodno korišteni sustav te vrste `sysvinit` izlazi iz prakse i vrijedan je samo spomena; postoji [šalabahter](https://fedoraproject.org/wiki/SysVinit_to_Systemd_Cheatsheet) za prebacivanje između ta dva sustava

## Systemd ekosustav

- systemd ekosustav sadrži veći broj međusobno povezanih i donekle neovisnih alata, od kojih su najznačajniji:

    - `systemd` init procesa, to je prvi proces koji pokreće Linux jezgra nakon učitavanja i on je zadužen za pokretanje i upravljanje životnim vijekom drugih procesa
    - `systemd` usluga, datoteka koje definiraju zahtjeve, redoslijed i instrukcije za pokretanje ostalih procesa potrebnih za rad sustava
    - `systemctl` alata, za pregled i upravljanje stanjima definiranih usluga
    - `journalctl` alata, za pregled sistemskih događaja i događaja vezanih za pojedinu uslugu

!!! admonition "Zadatak"
    Proučite na [systemd službenim stranicama](http://www.freedesktop.org/wiki/Software/systemd/) dio o imenovanju alata, a zatim proučite [objavu na autorovom blogu](http://0pointer.de/blog/projects/why.html) koja govori o tome kako systemd pomaže u sprječavanju balkanizacije Linuxa aplikacijskih programskih sučelja.

## Pokretanje sustava

Pokretanje sustava razlikuje se u situaciji kada se koristi SysVinit od situacije kada se koristi Systemd.

### Pokretanje sustava korištenjem SysVinita

- [init](https://en.wikipedia.org/wiki/init) (naredba `init`) pokreće usluge na operacijskom sustavu

    - BSD-style vs. SysV-style
    - razina pokretanja (engl. *runlevel*) opisuje stanje računala

        - sastoji se od usluga (engl. *services*)
        - razine 0, 1, 2, 3, 4, 5, 6, S/s
        - naredba `telinit` postavlja razinu pokretanja na zadanu

    - rezervirane razine

        - 0 -> isključivanje računala (engl. *halt*)
        - 1 -> jednokorisnički način rada (engl. *single-user mode*) u kojem se može prijaviti samo `root` korisnik
        - 6 -> ponovno pokretanje računala (engl. *reboot*)

    - najčešće se koriste razine pokretanja 3 i 5, razina pokretanja 4 se ne koristi

Kada se za init koristi SysVinit vrijedi:

- razina je definirana `:initdefault:` u `/etc/inittab`
- usluge su u `/etc/init.d/`
- ostale naredbe su u `/etc/rc.local`
- poveznice na usluge po razinama pokretanja su u `/etc/rc[0123456].d/`

!!! admonition "Zadatak"
    - Pokreće li se usluga `apache2` u razinama pokretanja 1, 2 i 3?
    - Pokreće li se usluga `postgresql` prije ili nakon procesa `exim4` u razinama pokretanja 3 i 5?

### Systemd jedinka cilja pokretanja

Systemd jedinka (engl. *unit*) je konfiguracijska datoteka koja se koristi za implementaciju usluga i ciljeva pokretanja:

- usluge koje pokreću procese demone definirane su `*.service` datotekama,
- ciljevi pokretanja definirani su `*.target` datotekama.

Alat `systemd` podiže sustav u predefinirani cilj koji se sastoji od određenih pokrenutih usluga. Predefinirani ciljevi pokretanja su:

- `poweroff.target` (pandan SysV `runlevel0'`)
- `reboot.target` (pandan SysV `runlevel6`)
- `multi-user.target` (pandan SysV `runlevel[234]`)
- `graphical.target` (pandan SysV `runlevel5`)
- `rescure.target` (pandan SysV `runlevel1`)
- `emergency.target`

U općem slučaju `systemd` podiže sustav u stanje `default.target` koji tipično pokazuje na `graphical.target`.

Maredbom `systemctl isolate TARGET` moguće je prebaciti sustav u željeni cilj pokretanja.

!!! admonition "Zadatak"
    Provjerite koji je cilj pokretanja trenutno aktivan na sustavu. Prebacite se u cilj pokretanja ..., a zatim usporedite popis procesa.

!!! todo
    Ovdje nedostaje konkretan zadatak.

- sve konfiguracijske datoteke i datoteke koje opisuju usluge se nalaze u direktoriju `/etc/systemd`
- usluge se nalaze u direktoriju `/etc/systemd/system`

!!! admonition "Zadatak"
    Pronađite u popisu uslugu ... i pronađite njezine datoteke na sustavu.

!!! todo
    Ovdje nedostaje konkretan zadatak.

## Upravljanje pojedinom uslugom

Baratanje pojedinom uslugom razlikuje se u situaciji kada se koristi SysVinit od situacije kada se koristi Systemd.

### Upravljanje uslugom korištenjem SysVinita

- `/etc/init.d/usluga start` pokreće uslugu, ekvivalentno `service usluga start`
- `/etc/init.d/usluga stop` zaustavlja uslugu, ekvivalentno `service usluga stop`
- `/etc/init.d/usluga status` ispisuje stanje usluge, ekvivalentno `service usluga status`
- naredba `service --status-all` prikazuje status svih usluga

### Systemd naredba `systemctl`

- pregled stanja pojedine usluge `USLUGA` možemo izvršiti naredbom `systemctl status USLUGA`
- upravljati stanjem usluge `USLUGA` možemo slijedećim naredbama:

    - `systemctl start USLUGA`
    - `systemctl stop USLUGA`
    - `systemctl restart USLUGA`
    - `systemctl reload USLUGA`

Pregled svih praćenih usluga i njihovih stanja se vrši pokretanjem alata `systemctl`.

!!! admonition "Zadatak"
    - Provjerite status usluga `ntpd` i `ntpdate`, a zatim ih zaustavite i ponovno pokrenite.
    - Naredba `netstat -a` daje, između ostalog, popis otvorenih lokalnih portova (konekcije u stanju `LISTEN`). Otkrijte koje su to usluge u našem slučaju. Ima li `ntpd` u popisu nakon zaustavljanja daemona?

!!! admonition "Zadatak"
    Iskoristite `yum` da bi instalirali `vsftpd`, a zatim ga pokrenite. Iskoristite `ftp` dostupan na računalu na kojem radite da bi se povezali na poslužitelj (sama prijava vam neće raditi; to zasad zanemarite).

## Upravljanje uslugama pojedinog cilja pokretanja

Baratanje uslugama cilja ili razine pokretanja razlikuje se u situaciji kada se koristi SysVinit od situacije kada se koristi Systemd.

### Upravljanje uslugama citalja pokretanja korištenjem SysVinita

- naredba `chkconfig` omogućuje da se uključuje ili isključuje pojedine usluge u pojedinim razinama pokretanja
- `chkconfig --list usluga` ispisuje jesu li usluge uključene ili isključene u pojedinim razinama pokretanja
- `chkconfig usluga on --level 2345` uključuje uslugu za pokretanje u razinama 2, 3, 4 i 5
- `chkconfig usluga off --level 01` isključuje uslugu za pokretanje u razinama 0 i 1

### Upravljanje uslugama citalja pokretanja korištenjem Sytemda

- usluge koji žele biti pokrenute u određenom cilju pokretanja moraju o istome ovisiti
- `systemctl enable`
- `systemctl disable`

!!! admonition "Zadatak"
    Uključite uslugu `vsftpd` u runlevelima 3, 4 i 5.

## Systemd jedinka usluge

Usluge su implementirane kao *service units*, npr. `acpid.service`, `sshd.service`.

!!! todo
    Ovdje nedostaje kompletan tekst.
