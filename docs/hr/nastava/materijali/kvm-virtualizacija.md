---
author: Mladen Bočev, Vedran Miletić
---

# Virtualizacija korištenjem KVM-a i QEMU-a

Virtualizacija je okvir ili metodologija dijeljenja resursa računalnog hardvera u više izvršnih okruženja, primjenom jednog ili više koncepata ili tehnologija poput hardverskog i softverskog particioniranja, dijeljenja vremena, djelomične ili potpune strojne simulacije, emulacije, kvalitete usluge, i mnogih drugih.

Pojednostavljeno rečeno, moderna virtualizacija omogućava da se više instanci operacijskih sustava izvodi istovremeno na jednom računalu, što ima čitav niz primjena. Nekoliko kratkih videoklipova o primjenama virtualizacije objavio je Red Hat u [serijalu pod imenom Real tech](https://youtu.be/TVrH1Oox_nE?list=PL099047F847F3C791) iz 2007. godine. Radi se o reklami i zato ne zahtijeva posebno predznanje.

Virtualizacija je tijekom 2000-ih godina ubrzano razvijala i bila jedna od najpopularnijih tema u području informacijske tehnologije, a danas je dovoljno zrela da je koristimo gotovo rutinski. Interes za virtualizacijom je nastao prvenstveno zato što omogućuje:

- povećanje raspoloživosti i iskorištenosti postojeće infrastrukture i aplikacija,
- smanjenje količine potrebne infrastrukture i smanjenje potrebne administracije,
- smanjenje troškova infrastrukture,
- pokretanje Windowsa ili Linuxa na Mac OS X-u (i brojne druge kombinacije).

Virtualizacija se danas koristi gotovo svuda, ili se namjerava preći na nju kod sljedeće nadogradnje. Primjerice, poslužitelj koji pogoni [lab.miletic.net](https://lab.miletic.net/) je isto virtualni stroj (tzv. virtualni privatni server, VPS), iznajmljen kod [Hetznera](https://www.hetzner.com/). Porast snage računala, specifično povećanje broja jezgara procesora i količine memorije, učinio je da jedno računalo ima dovoljno resursa za izvođenje više operacijskih sustava te je, usputno s razvojem tehnologije virtualizacije koja omogućuje takvo dijeljenje računala u više njih, razvijena i ekonomija iznajmljivanja virtualnih računala (u "oblaku") po potrebi.

## Potreba za virtualizacijom

Potreba za virtualizacijom proizlazi iz 4 osnovna razloga:

- neiskorištenost hardvera,
- nedostatak prostora u podatkovnim centrima,
- zelene inicijative zahtijevaju bolju energetsku efikasnost,
- nakupljanje troškova administracije sustava.

Povećanjem snage i padom cijene računala došlo se do točke kada je postalo neisplativo imati više poslužitelja koji većinu vremena stoje neiskorišteni jer imaju previše resursa za zadaće koje su im dodijeljene.

Moguće je više usluga podržati jednim poslužiteljem, ali to otvara niz mogućih sigurnosnih problema, pa je virtualizacijom omogućeno da se na svakom računalu pokrene nekoliko izdvojenih "podračunala" koja dijele njegove resurse i svako od njih funkcionira neovisno.

Virtualizacija je također omogućila IT odjeljenjima da se riješe prastarih računala i njih nepromijenjene pokrenu u virtualnom obliku na jednom od novih računala. To štedi električnu energiju, a time i novac.

## Osnovni pojmovi virtualizacije

Virtualni stroj, često i virtualna mašina (engl. *virtual machine*), je softversko okruženje koje simulira stvarni hardver i unutar kojeg se može izvršavati određeni operacijski sustav.

Gostujući operacijski sustav (engl. *guest operating system*) je operacijski sustav koji se izvršava unutar virtualnog stroja.

Operacijski sustav domaćina (engl. *host operating system*) je operacijski sustav fizičkog računala na kojem se izvršavaju monitor virtualnih strojeva i virtualni strojevi. Primjerice, ukoliko korisnik koristi Windows Virtual PC da bi pokrenuo Windows XP Mode na Windowsima 7, tada je Windows 7 operacijski sustav domaćina, a Windows XP gostujući operacijski sustav.

Monitor virtualnih strojeva (engl. *virtual machine monitor*), ponekad nazvan *hipervizor* (engl. *hypervisor*), upravlja hardverskim resursima i prilagođava ih zahtjevima više gostujućih operacijskih sustava i aplikacijskih stogova. Na temelju fizičkog hardvera nad kojim se izvršavaju virtualni strojevi on predstavlja virtualni skup procesorskih, memorijskih, ulazno/izlaznih i diskovnih resursa koji su dostupni svakom virtualnom stroju.

### Popekovi i Goldbergovi uvjeti

Gerald J. Popek i Robert P. Goldberg su 1974. godine objavili rad *Formal Requirements for Virtualizable Third Generation Architectures* [u kojem formaliziraju uvjete računalne arhitekture za podršku virtualizaciji](https://blog.acolyer.org/2016/02/19/formal-requirements-for-virtualizable-third-generation-architectures/), a koji se i u današnje vrijeme smatra referentnim polazištem pri dizajniranju monitora virtualnih strojeva.

Uvjeti/značajke koje oni navode su:

- **Ekvivalentnost** -- Softver koji se izvršava pod VMM-om treba pokazati predvidljivo "ponašanje" koje je u osnovi jednako pokazanom ponašanju" kada se softver izvršava izravno na inherentnom hardveru.
- **Upravljanje resursima** -- upravitelj virtualnih strojeva neprestano mora imati potpunu kontrolu hardverskih resursa virtualiziranih za gostujuće operacijske sustave.
- **Učinkovitost** -- Velik broj strojnih instrukcija virtualnih strojeva treba se izvršiti i bez intervencije upravitelja virtualnih strojeva, odnosno hardver ih sam treba biti u stanju izvršiti.

## Vrste virtualizacije

Osnovne vrste virtualizacije su:

- potpuna virtualizacija, čija je podrvrsta hardverski potpomognuta virtualizacija,
- paravirtualizacija,
- virtualizacija na razini operacijskog sustava.

### Potpuna virtualizacija

Potpuna virtualizacija podrazumijeva simulaciju hardvera fizičkog stroja što omogućava softverima (gostujućem operacijskom sustavu i njegovim programima) da se pokreću bez promjene.

Neka od rješenja za potpunu virtualizaciju su:

- Microsoft [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/about/), nasljednik [Windows Virtual PC](https://support.microsoft.com/en-us/help/958559/description-of-windows-virtual-pc),
- Oracle (nekad Sun, InnoTek) [VirtualBox](https://www.virtualbox.org/),
- Parallels [Desktop](https://www.parallels.com/products/desktop/), nekad i [Workstation](https://en.wikipedia.org/wiki/Parallels_Workstation),
- [QEMU](https://www.qemu.org/), [KVM](https://www.linux-kvm.org/) i [Virtual Machine Manager](https://virt-manager.org/),
- VMWare [Workstation Pro](https://www.vmware.com/products/workstation-pro.html) i [vSphere](https://www.vmware.com/products/vsphere.html).

Mi ćemo u nastavku koristiti QEMU, KVM i Virtual Machine Manager. Na operacijskom sustavu Microsoft Windows možete koristiti Oracle VirtualBox.

#### Hardverski potpomognuta virtualizacija

Hardverski potpomognuta virtualizacija, ponekad nazvana i izvorna virtualizacija, je pristup koji omogućuje efikasnu potpunu virtualizaciju korištenjem mogućnosti hardvera na kojem radi, prvenstveno procesora.

Podrška za hardverski potpomognutu virtualizaciju dodana je u obliku procesorskih ekstenzija za x86 procesore koje su neovisno implementirali Intel i AMD. Tako su nastale dvije tehnologije:

- [Intel Virtualization Technology for x86 (Intel VT-x)](https://www.intel.com/content/www/us/en/virtualization/virtualization-technology/intel-virtualization-technology.html) (jedna od [komponenata Intel VT](https://www.thomas-krenn.com/en/wiki/Overview_of_the_Intel_VT_Virtualization_Features)),
- [AMD Virtualization (AMD-V)](https://www.amd.com/en/technologies/virtualization).

Iako su one po specifikacijama različite, obje postižu isti cilj: omogućuju izvođenje virtualnih mašina s nepromijenjenim OS-ovima brzinom koja je vrlo slična situaciji kada se OS pokreće direktno na računalu. Prije uvođenja tih ekstenzija za virtualnu mašinu procesor je bilo potrebno emulirati, što je činilo da je virtualizirani OS u izvođenju bio bitno sporiji od onoga koji se izravno pokretao na računalu.

Rješenje koje na Linuxu omogućuje hardverski potpomogntu virtualizaciju naziva se [KVM](https://www.linux-kvm.org/). Razvila ga je tvrtka Qumranet, koju je kasnije [kupio Red Hat](https://www.redhat.com/en/about/press-releases/qumranet).

#### Kernel-based Virtual Machine (KVM)

KVM sustav omogućuje pokretanje virtualnih mašina na x86 sustavima koji podržavaju hardverski potpomognutu virtualizaciju. KVM koristi već spomenuti alat za potpunu virtualizaciju QEMU; QEMU podržava [emulaciju brojnih platformi](https://wiki.qemu.org/Documentation/Platforms), a na x86 procesorima podržava emulaciju i BIOS-a i [UEFI firmwarea](https://www.linux-kvm.org/page/OVMF).

Linux jezgra podržava Intel VT-x od verzije 2.6.15, a AMD-V od verzije 2.6.16. KVM podržava obje tehnologije i [dio je jezgre od verzije 2.6.20](https://news.softpedia.com/news/KVM-To-Be-Merged-Into-Linux-Kernel-2-6-20-42708.shtml), a sastoji se od 3 modula:

- `kvm` -- zajednički dio,
- `kvm_intel` -- podrška za Intel VT-x,
- `kvm_amd` -- podrška za AMD-V.

Ima li procesor u našem računalu podršku za hardverski-potpomognutu virtualizaciju možemo provjeriti tako da u `/proc/cpuinfo` tražimo zastavice:

- `vmx` za Intel procesore,
- `svm` za AMD procesore.

KVM podržava i druge arhitekture osim x86(-64), specifično [ARM, PowerPC i S/390](https://www.linux-kvm.org/page/Processor_support), a [bilo je i pokušaja podrške IA-64](https://lwn.net/Articles/622729/).

#### Virtualizacija ulazno/izlaznih jedinica

Virtualizacija ulazno/izlaznih jedinica omogućuje virtualnim mašinama *izravno* korištenje perifernih uređaja (npr. mrežnih adaptera i grafičkih procesora, diskovnih kontrolera i slično) na računalu na kojem rade.

Imena dvaju tehnologija koje omogućuju virtualizaciju upravitelja ulaznim/izlaznim jedinicama (IOMMU) na x86 procesorima su:

- Intel VT-d -- Intel Virtualization Technology for Directed I/O,
- AMD-Vi -- AMD I/O Virtualization Technology.

Obje tehnologije proširenje su postojećih tehnologija za hardverski potpomognutu virtualizaciju.

### Paravirtualizacija

Paravirtualizacija, za razliku od potpune virtualizacije, je virtualizacijska tehnika koja s ciljem poboljašanja performansi ne emulira sav hardver računalnog sustava i stoga očekuje da je gostujući operacijski sustav prilagođen radu u virtualnoj mašini.

Najznačajnije rješenje u ovom području je [Xen Project](https://xenproject.org/), čiji razvoj financira Linux Foundation, a nekad je bio u vlasništu tvrtke [Citrix Systems](https://www.citrix.com/), koja je [kupila XenSource](https://www.citrix.com/blogs/2016/08/24/10-years-of-xenserver/).

Ovo spominjemo radi potpunosti i ovdje se detaljnije ovom vrstom virtualizacije nećemo baviti.

### Virtualizacija na razini operacijskog sustava

virtualizacija na razini operacijskog sustava je virtualizacijska metoda kod koje jezgra operacijskog sustava omogućuje pokretanje više izoliranih instanci prostora korisničkih aplikacija umjesto samo jedne. Svaka od tih instanci, koje se često nazivaju kontejneri (engl. *containers*) ili zatvori (engl. *jails*), iz pozicije korisnika unutar nje izgleda kao stvarni poslužitelj.

[Linux Containers (LXC)](https://linuxcontainers.org/) je virtualizacija na razini operacijskog sustava namijenjena za Linux koja na osnovu [kontrolnih grupa jezgre](https://www.kernel.org/doc/Documentation/cgroup-v1/cgroups.txt) (engl. *kernel control groups*) i [izolacije imenika](https://prefetch.net/blog/2018/02/22/making-sense-of-linux-namespaces/) (engl. *namespace isolation*).

Alternativna rješenja koja se u praksi sreću su [Linux-VServer](http://www.linux-vserver.org/) i [OpenVZ](https://openvz.org/) za Linux, [Jails](https://wiki.freebsd.org/Jails) za FreeBSD i [Solaris Containers/Zones](https://www.usenix.org/legacy/event/lisa04/tech/full_papers/price/price.pdf) za Oracle Solaris.

Ovo također spominjemo radi potpunosti i ovdje se detaljnije ovom vrstom virtualizacije nećemo baviti.

## Virtualizacija i obični korisnici

Virtualizacija se relativno brzo preselila sa poslužitelja na radne stanice i desktope običnih korisnika.

Korisnicima je omogućen istovremeni rad s dva ili više operacijskih sustava, što otvara čitav niz primjena, primjerice:

- korištenje Windowsa XP na Windowsima 7 zbog potrebe pokretanja stare verzije Clariona,
- korištenje Windowsa Vista na [Arch Linuxu](https://www.archlinux.org/) zbog potrebe pokretanja Adobe Flasha,
- korištenje Ubuntua na Windowsima 10 za vježbanje Operacijskih sustava 1 i 2,
- korištenje Debiana na Windowsima 8 za pokretanje mrežnog simulatora [ns-3](https://www.nsnam.org/).

### VirtualBox

VirtualBox je najfleksibilnije besplatno i djelomično slobodno rješenje za potpunu virtualizaciju. Može se instalirati i koristiti [na većini modernih operacijskih sustava današnjice](https://www.virtualbox.org/manual/ch01.html#hostossupport), a [podrška za gostujuće operacijske sustave je također prilično dobra](https://www.virtualbox.org/wiki/Guest_OSes).

VirtualBox se najviše koristi kod desktop korisnika. Jedna od značajki koja se često ističe je to što omogućuje korisniku da integrira radnu površinu operacijskog sustava domaćina s radnom površinom gostujućeg operacijskog sustava i na isti način radi s programima oba sustava. To se naziva bešavni (engl. *seamless*) način rada.

#### Baratanje modulima jezgre

Kako procesor računala na kojem demonstriramo rad s VirtualBoxom ima podršku za hardverski potpomognutu virtualizaciju, moramo prvo odčitati automatski učitane KVM-ove module. U protivnom VirtualBox neće imati pristup hardverski-potpomognutoj virtualizaciji koju procesor podržava.

Za učitavanje i odčitavanje modula koristimo naredbu `modprobe`. Pritom:

- `modprobe kvm` učitava modul `kvm`,
- `modprobe -r kvm` odčitava modul `kvm`.

Međutim, ukoliko pokušamo ovo drugo, sustav će nam javiti pogrešku `FATAL: Module kvm is in use.`

Pomoću naredbe `lsmod` možemo vidjeti popis trenutno korištenih modula, i uočavamo da modul `kvm_intel` ovisi o modulu `kvm`. O modulu `kvm_intel` ne ovisi ni jedan drugi modul, pa njega možemo odčitati. Pritom sustav automatski odčitava i `kvm`, zato što je zapamtio da ga je automatski i učitao kada je prepoznao da naš procesor podržava Intelovu VT-x ekstenziju za hardversku virtualizaciju.

Sada VirtualBox može raditi bez konflikata sa KVM-om. Naravno, da naš procesor nema podršku za hardverski potpomognutu virtualizaciju, ovaj gore opisani postupak ne bi bio potreban. Postupak u slučaju kada se u računalu nalazi AMD procesor je sasvim analogan.

Naravno, VirtualBox ima svoje module jezgre, koji su otprilike ekvivalentni KVM-ovim modulima. Jedna od funkcija tih modula je, primjerice, da omogućuje da VirtualBox koristi postojeću vezu na Internet koja postoji na računalu na kojem je pokrenut. Drugim riječima, kada smo spojeni na Internet na računalu na kojem su pokrenute virtualne mašine, u zadanim postavkama sve one mogu pristupati Internetu (a i komunicirati međusobno).

### Virtualne primjene

Virtualna primjena je slika virtualnog stroja namijenjena pokretanju na određenoj virtualizacijskoj platformi.

[Open Virtualization Format (OVF)](https://www.dmtf.org/standards/ovf) je otvoreni standard za pakiranje i distribuciju virtualnih primjena i općenitog softvera za virtualne strojeve.

!!! admonition "Zadatak"
    - Preuzmite [virtualnu primjenu s poslužitelja inf2](https://inf2.uniri.hr/VM/).
    - Pokrenite virtualnu primjenu.
