---
author: Vedran Miletić
---

# Teme završnih i diplomskih radova

U nastavku je popis predloženih i odabranih tema završnih i diplomskih radova. Popis predloženih tema se kontinuirano nadopunjuje i poboljšava vođen sugestijama studenata. Među predloženim temama dio nije potpuno opisan i/ili nema pripadnu literaturu, ali ne očajavajte: ukoliko vam je neka od tema zanimljiva i smatrate da u prijedlogu sadržaja ili literature nešto nedostaje, javite se putem e-maila pa ćemo je prilagoditi vašim interesima.

## Osnovne informacije i preporuke za pisanje radova

### Akademsko pisanje

Završni i diplomski radovi su akademski radovi, a prilikom pisanja akademskih radova slijedimo uvriježena stilska i strukturna pravila kako bi ti radovi bili čitljivi i potencijalno korisni i drugim članovima akademske zajednice. O pisanju radova [dr. sc. Vanja Pupovac](https://portal.uniri.hr/portfelj/1712) na [mrežnim stranicama Akademsko pisanje](https://www.akademsko-pisanje.uniri.hr/o-nama/) i u istoimenoj knjižici kaže sljedeće:

> Akademsko pisanje je oblik komunikacije u akademskoj zajednici. Postoje različiti oblici akademskog pisma, a neki od najpoznatijih su esej, seminarski rad, završni, diplomski ili doktorski rad, te stručni ili znanstveni rad. Svrha akademskog pisanje je savladavanje i sažimanje znanja o pojedinoj temi, proširivanje rasprava (novim informacijama ili mišljenjima), prenošenje informacija (znanstvenicima, stručnjacima ili javnosti) i ovjeravanje znanja.
>
> Osnovna karakteristika akademskog rada je logički način razmišljanja; ideje moraju biti sustavno i jednostavno prezentirane, a mišljenja moraju biti potkrijepljena relevantnim i uvjerljivim razlozima i dokazima. No, to nije uvijek lako ostvarivo, stoga proces pisanja akademskog rada dijelimo u četiri faza. Na mrežnim stranicama [Proces pisanja](https://www.akademsko-pisanje.uniri.hr/proces-pisanja/) donosimo pregled osnovnih pravila i aktivnosti za svaku fazu u procesu pisanja.
>
> Pisanjem akademskog rada uključujemo se u aktualnu raspravu o odabranoj temi. Za uspješno uključivanje u raspravu potrebno je upoznati se s već postojećim činjenicama, idejama i argumentima čitajući relevantnu stručnu ili znanstvenu literaturu. Na taj način osigurat ćemo da vlastite ideje razvijemo na čvrstim znanstvenim temeljima i iskazat ćemo poštovanje prema iskusnijim znanstvenicima. Povjerenje zajednice u vlastiti rad zadobit ćemo preciznim citiranjem i referiranjem izvora što je pojašnjeno na stranici [Rad s izvorima](https://www.akademsko-pisanje.uniri.hr/rad-s-izvorima/). Kredibilitet i vjerodostojnost autora se sporo gradi u akademskoj zajednici, ali lako narušava, stoga savjetujemo da proučite materijale prezentirane na stranici [Akademska čestitost](https://www.akademsko-pisanje.uniri.hr/akademska-cestitost/).

Za više informacija slijedite poveznice u tekstu iznad i proučite [mrežne stranice Akademsko pisanje](https://www.akademsko-pisanje.uniri.hr/) ili [preuzmite knjižicu Akademsko pisanje u formatu PDF](../downloads/knjizica-akademsko-pisanje.pdf).

### Softverski alati

Za pisanje radova koristite [LibreOffice](https://www.libreoffice.org/) i format [OpenDocument](http://opendocumentformat.org/). Ako preferirate pisanje markupa umjesto korištenja alata tipa [WYSIYG](https://en.wikipedia.org/wiki/WYSIWYG), umjesto LibreOfficea i OpenDocumenta možete koristiti neki od sljedećih alata i formata:

- [Markdown](https://commonmark.org/), [Pandoc](https://pandoc.org/) i proširenja navedena u [objavi Jaana Tollandera de Balscha](https://jaantollander.com/post/scientific-writing-with-markdown/) (preporučeni uređivači: [HackMD](https://hackmd.io/) i [Visual Studio Code](https://code.visualstudio.com/)),
- [LaTeX](https://www.latex-project.org/) i [Edvin Močibobov](https://edvin.me/) [predložak za završni i diplomski rad](https://bitbucket.org/emocibob/latex-predlozak-za-diplomski-i-zavrsni-rad) (preporučeni uređivači: [TeXstudio](https://texstudio.org/) i [Texmaker](https://www.xm1math.net/texmaker/)),
- [reStructuredText](https://docutils.readthedocs.io/en/sphinx-docs/user/rst/quickstart.html), [Sphinx](http://www.sphinx-doc.org/en/master/) i [Jeff Terraceov](https://jeffterrace.com/) [snop ekstenzija za akademske radove](https://jterrace.github.io/sphinxtr/) (preporučeni uređivač: [Visual Studio Code](https://code.visualstudio.com/) s proširenjem [reStructuredText](https://marketplace.visualstudio.com/items?itemName=lextudio.restructuredtext)) ili
- [AsciiDoc](https://asciidoc.org/) i [Asciidoctor](https://asciidoctor.org/) (preporučeni uređivač: [Visual Studio Code](https://code.visualstudio.com/) s proširenjem [AsciiDoc](https://marketplace.visualstudio.com/items?itemName=asciidoctor.asciidoctor-vscode)).

LibreOffice i LaTeX rade izvrsne PDF-ove (Sphinx također stvara PDF korištenjem LaTeX-a), i mogu, ako je potrebno, napraviti [PDF/A](https://en.wikipedia.org/wiki/PDF/A), varijantu PDF-a prikladnu za arhiviranje i dugoročno čuvanje digitalnih dokumenata.

Za upravljanje navodima možete koristiti [Zotero](https://www.zotero.org/) (koji ima i plug-in za LibreOffice) i/ili [BibTeX](http://www.bibtex.org/). Koristite [stil citiranja IEEE](https://ieee-dataport.org/sites/default/files/analysis/27/IEEE%20Citation%20Guidelines.pdf).

Kojom god temom da se bavite, svakako koristite slobodne softvere otvorenog koda kad god možete. Na će taj način onaj koji koristi vaš rad za vlastito učenje moći lako doći do softvera s kojim u radu radite.

## Ponuđene teme završnih radova

### Upravljanje kontejnerima aplikacija korištenjem Podmana {[UMS](nastava/kolegiji/UMS.md)}

**Opis teme:**

Kontejneri su postali sastavni dio skupa alata koje koriste i razvijatelji softvera i upravitelji računalnih sustava (sistemci), a najkorištenije rješenje je Docker. Red Hat je u suradnji sa zajednicom slobodnog softvera otvorenog koda razvio alternativu Dockeru imena Podman. Osim toga, razvijena je i alternativa bazi kontejnera Docker Hub pod imenom Quay. Zadatak rada je opisati način rada Podmana i usporediti ga s Dockerom

**Literatura:**

1. [Docker](https://www.docker.com/)
1. [Podman](https://podman.io/)
1. [Quay](https://quay.io/)

### Doprinos projekta Berkeley Software Distribution i potomaka u razvoju interneta {[RM2](nastava/kolegiji/RM2.md)}

**Opis teme:**

Tijekom 80-ih godina na Kalifornijskom sveučilištu u Berkeleyu Keith Bostic, Bill Joy, Marshall Kirk McKusick, Sam Leffler, Mike Karels i drugi članovi Computer Systems Research Group razvijaju Berkeley Software Distribution (BSD) kao derivat AT&T-evog Unixa. U istom desetljeću DARPA financira razvoj TCP/IP-a na BSD-u pa BSD postaje nositelj razvoja tehnologija interneta. Korištenje BSD-a u istraživanju nastavlja se i narednih desetljeća, kroz japanski projekt KAME, FER-ov projekt IMUNES i brojne druge. Zadatak rada je dati detaljan pregled primjene BSD-a u istraživanju i standardizaciji internetskih tehnologija kroz posljednjih četiri desetljeća.

**Literatura:**

1. [Computer Systems Research Group](https://en.wikipedia.org/wiki/Computer_Systems_Research_Group)
1. [KAME](http://www.kame.net/)
1. [IMUNES](http://imunes.net/)
1. [Jones, T. FreeBSD in Network Research and Standardization (FreeBSD in Research). FreeBSD Journal, January/February 2020.](https://www.freebsdfoundation.org/past-issues/freebsd-in-research/)
1. [Leffler, S. J., Joy, W. N., Fabry, R. S., & Karels, M. J. Networking Implementation Notes 4.3 BSD Edition. Unix System Manager's Manual, 1986.](https://docs.freebsd.org/44doc/smm/18.net/paper.pdf)

### Interaktivni interpreter Cling za programski jezik C++ {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

...

**Literatura:**

1. [LLVM](https://llvm.org/)
1. [Clang](https://clang.llvm.org/)
1. [CLing](https://root.cern.ch/cling)

### Prenosivost znanstvenog softvera među operacijskim sustavima sličnim Unixu {[OS2](nastava/kolegiji/OS2.md)}

**Opis teme:**

...

**Literatura:**

1. [illumos](https://illumos.org/)
1. [GROMACS](http://www.gromacs.org/)

### Modularni usmjerivač Click {[RM1](nastava/kolegiji/RM1.md)}

**Opis teme:**

**Literatura:**

1. [The Click modular router](https://github.com/kohler/click)

### Implementacija konfiguracijskih datoteka korištenjem TOML-a {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

...

**Literatura:**

1. [RxDock](https://www.rxdock.org/)
1. [toml11](https://github.com/ToruNiina/toml11)
1. [cpptoml](https://github.com/skystrife/cpptoml)

### Mjerenje performansi jezika OpenCL i CUDA korištenjem skupa alata za mjerenje brzine izvođenja SHOC {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

NVIDIA je vodeća tvrtka u domeni vizualizacije i računanja na grafičkim procesorima. SHOC je skup alata za mjerenje brzine hardvera prilikom izvođenja aplikacija pisanim u jezicima CUDA i OpenCL. Zadatak rada je izmjeriti performanse SHOC-a na NVIDIA-inim grafičkim procesorima korištenjem tehnologije CUDA i tehnologije OpenCL te analizirati mjerenja.

**Literatura:**

1. [SHOC](https://github.com/vetter/shoc)
1. NVIDIA-ina službena dokumentacija za CUDA-u i OpenCL

### Usporedba arhitekture i značajki Waylanda i X.Org X11 Servera {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

X.Org je tradicionalni display server koji se koristi na operacijskim sustavima sličnim Unixu za prikaz grafičkog korisničkog sučelja. Wayland je protokol za komunikaciju između display servera i njegovih klijenata, a isto se ime koristi i za referentnu implementaciju tog protokola. Wayland je dosegao stabilnu verziju i softvera i protokola te će vjerojatno biti u skoroj budućnosti korišten umjesto X.Org X11 Servera. Zadatak rada je opisati oba display servera i međusobno ih usporediti.

**Literatura:**

1. [X.Org Wiki](https://www.x.org/wiki/)
1. [Wayland](https://wayland.freedesktop.org/)

### Named Data Networking {[RM1](nastava/kolegiji/RM1.md)}

**Opis teme:**

**Literatura:**

1. [Named Data Networking Project](https://named-data.net/)

### Automatsko generiranje SSL certifikata korištenjem CA Let’s Encrypt i klijenta Certbot {[RM2](nastava/kolegiji/RM2.md)}

**Opis teme:**

**Literatura:**

1. [Let's Encrypt](https://letsencrypt.org/)
1. [Certbot](https://certbot.eff.org/)
1. [HTTPS Tops 30%: How Google Is Winning the Long War (Moz)](https://moz.com/blog/https-tops-30-how-google-is-winning-the-long-war)
1. [Let's Encrypt Stats](https://letsencrypt.org/stats/)
1. [Halfway there! Firefox users now visit over 50% of pages via HTTPS (Naked Security)](https://nakedsecurity.sophos.com/2016/10/18/halfway-there-firefox-users-now-visit-over-50-of-pages-via-https/)

### CoCCA: softver otvorenog koda za upravljanje registrom domena {[RM2](nastava/kolegiji/RM2.md)}

**Opis teme:**

**Literatura:**

1. [CoCCA](https://cocca.org.nz/)

### FRED: softver otvorenog koda za upravljanje registrom domena {[RM2](nastava/kolegiji/RM2.md)}

**Opis teme:**

CZ.NIC je upravitelj Češke državne domene .cz, a softver FRED koji koriste za upravljanje registrom domene su izbacili kao slobodni softver otvorenog koda. Isti softver koristi se za upravljanje državnih domena Angole, Tanzanije, Kostarike, Farskih Otoka, Estonije, Albanije i Makedonije. Cilj rada je analizirati mogućnosti softvera i opisati način konfiguracije.

**Literatura:**

1. [FRED](https://fred.nic.cz/)
1. [ICANN Wiki](https://icannwiki.org/)
1. [ICANN-ove informacije o registrima](https://www.icann.org/resources/pages/registries/registries-en)

### Domain Name Registry System: softver otvorenog koda za upravljanje registrom domena {[RM2](nastava/kolegiji/RM2.md)}

**Opis teme:**

**Literatura:**

1. [Domain Name Registry System](https://sourceforge.net/projects/dnrs/)

### Prekršaji licence GNU GPL i njihovo rješavanje {[OS1](nastava/kolegiji/OS1.md)}

**Opis teme:**

GPL violations: Linksys WRT54G, Linux devices, SF Conservancy, SF Law Center

**Literatura:**

1. [[Ksummit-discuss] [CORE TOPIC] GPL defense issues](https://lists.linuxfoundation.org/pipermail/ksummit-discuss/2016-August/003578.html)
1. [GPL violations](http://gpl-violations.org/)
1. [Software Freedom Law Center](https://softwarefreedom.org/)
1. [Software Freedom Conservancy](https://sfconservancy.org/)
1. [Bradley M. Kuhn's Blog](http://www.ebb.org/bkuhn/blog/)

### Migracije sa vlasničkih formata dokumenata uredskih aplikacija na OpenDocument {[OS1](nastava/kolegiji/OS1.md)}

**Opis teme:**

OpenDocument je format dokumenata uredskih aplikacija zasnovan na XML-u. OpenDocument je otvoreni standard organizacija OASIS i ISO, neovisan o određenom proizvođaču softvera, te je vrlo pogodan za dugoročno arhiviranje dokumenata. Pored LibreOffice-a i Apache OpenOffice-a, OpenDocument podržavaju i Adobe Acrobat Digital Cloud, Corel WordPerfect Office, Microsoft Office i Office Online, te SoftMaker Office. Zadatak rada je proučiti dosadašnje migracije na OpenDocument i opisati tehničke i društvene izazove koje su se pojavili prilikom migracija, te uspješna rješenja tih izazova koja su primijenjena.

**Literatura:**

1. [OpenDocument adoption](https://en.wikipedia.org/wiki/OpenDocument_adoption)
1. [Digital dark age](https://en.wikipedia.org/wiki/Digital_dark_age)
1. [LibreOffice users and deployments](https://en.wikipedia.org/wiki/LibreOffice#Users_and_deployments)

### Tehnički i društveni problemi Digital Rights Managementa {[OS1](nastava/kolegiji/OS1.md)}

**Opis teme:**

**Literatura:**

## Ponuđene teme diplomskih radova

### Simulatori heterogene sustavske arhitekture {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

Heterogena sustavska arhitektura ...

**Literatura:**

1. Hwu, W. Heterogeneous system architecture: practical applications for industry. (Elsevier, 2015).

### Usporedba program prevoditelja NVIDIA nvcc i Clang za programskih jezik CUDA {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

CUDA je vlasnički programski jezik za heterogeno paralelno programiranje korištenjem grafičkih procesora tvrtke NVIDIA. Iako su pojedini dijelovi NVIDIA-inog programskog stoga slobodni softveri otvorenog koda, većina je ipak zatvorena i nad njima kontrolu ima NVIDIA. Motiviran zatvorenošću NVIDIA-e, Google je korištenjem LLVM-a razvio vlastiti program prevoditelj jezika CUDA gpucc koji je potom uključen u Clang. Zadatak rada je usporediti dva program prevoditelja u terminima značajki koje podržavaju te u terminima performansi prevođenja i izvođenja nekoliko aplikacija otvorenog koda po koje koriste CUDA-u.

**Literatura:**

1. [2015 LLVM Developers’ Meeting: Jingyue Wu "Optimizing LLVM for GPGPU"](https://youtu.be/JHfb8z-iSYk?list=PL_R5A0lGi1AA4Lv2bBFSwhgDaHvvpVU21)
1. Službena NVIDIA-ina dokumentacija za CUDA-u

### Grafički procesor otvorenog koda MIAOW {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

**Literatura:**

1. [MIAOW GPU](http://miaowgpu.org/)
1. [Southern Islands Series Instruction Set Architecture](https://developer.amd.com/wordpress/media/2012/12/AMD_Southern_Islands_Instruction_Set_Architecture.pdf)

### Opis backenda program-prevoditelja AMDGPU u infrastrukturi za izgradnju program-prevoditelja LLVM {[PPHS](nastava/kolegiji/PPHS.md)}

**Opis teme:**

**Literatura:**

### Instalacija i konfiguracija poslužitelja datoteka {[UMS](nastava/kolegiji/UMS.md)}

**Opis teme:**

Poslužitelj datoteka je dio gotovo svakog suvremenog poslovnog sustava. Bio taj poslužitelj dio komecijalnih oblaka kao što su Google Drive i Microsoft OneDrive ili dio vlastitog oblaka kao što je Nextcloud, njegova uloga uloga u poslovnom sustavu je ista: spremanje i dijeljenje datoteka koje omogućuju poslovanje. Dakako, taj poslužitelj zahtijeva odgovarajući hardver da bi ispravno obavljao svoju zadaću. Zadatak rada je opisati kompletan postupak postavljanja poslužitelja datoteka, što uključuje:

- hardversku osnovu poslužitelja: svojstva i vrste medija za pohranu podataka koji se koriste (tvrdi diskovi i diskovi čvrstog stanja) te sučelja i kontroleri koje mediji za pohranu podataka koriste,
- softverska osnova poslužitelja, sustavski dio: hardverske i softverske implementacije RAID-a (Redundant Array of Inexpensive/Independent Disks), specifično Linuxov softverski RAID te razine RAID-a koje se koriste,
- softverska osnova poslužitelja, aplikacijski dio: prikazati postupak instalacije poslužitelja datoteka (Samba i NFS).

**Literatura:**

1. [File Server (Ubuntu Server Guide)](https://ubuntu.com/server/docs/samba-file-server)
1. [Using Samba as a server (Red Hat Enterprise Linux 8 Documentation: Deploying different types of servers)](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/deploying_different_types_of_servers/assembly_using-samba-as-a-server_deploying-different-types-of-servers)

## Odabrane teme završnih radova akademske 2020/2021. godine

### Izrada web aplikacije korištenjem Djanga {[DWA2](nastava/kolegiji/DWA2.md)} [Antonela Troha]

**Naslov na engleskom:** Web application development using Django

**Opis teme:**

**Literatura:**

### Izrada web aplikacije korištenjem Flaska {[DWA2](nastava/kolegiji/DWA2.md)} [Ivan Modrić]

**Naslov na engleskom:** Web application development using Flask

**Opis teme:**

imao bih glavni server na kojem će biti flask REST API. Na njemu bi korisnik imao pristup trima opcijama: index page na kojoj će upisati što želi pretraživati, zatim pretraga gdje će korisnik dobiti rezultate pretrage, te obavijest gdje se pruža mogućnost registracije na obavijesti vezane uz promjenu cijene u smislu da korisnik unese nekakvu cijenu i kad se artikl spusti na tu cijenu ili ispod te cijene, korisnik dobije obavijest.
Kad se odabere pretraga glavni server pozivao bi AWS lambda funkciju koja će biti zapravo web spider, ali ujedno i web scraping alat preko kojeg će se izvlačiti cijene. Spomenuta lambda funkcija vraćala bi web trgovine i cijene za navedeni proizvod u JSON formatu. Ako se odabere obavijest onda se pokreće lambda funkcija koja u DynamoDB bazu zapisuje email korisnika, proizvod, željenu cijenu, zadnju poznatu cijenu i je li ta obavijest još uvijek aktivna jer ako je taj mail ranije poslan korisniku onda ga ne želimo opet slati.
To bi se realiziralo cloudwatch eventom (trigger) koji će u nekom određenom intervalu pokretati lambdu za provjeru obavijesti. Ona bi čitala iz DynamoDB baze koje su obavijesti aktivne i zatim pokretala lambdu za web spider i web scraping. Nakon što se vrate rezultati lambda za slanje obavijesti bi provjerila ako je cijena jednaka ili manja od cijene koju je korisnik unio kao željenu te ovisno o tome korisnik bi dobio obavijest putem AWS SNS servisa.

**Literatura:**

### Paralelizacija izračuna dubokih neuralnih mreža na grafičkim procesorima {[PPHS](nastava/kolegiji/PPHS.md)} [Andrija Poleksić]

**Naslov na engleskom:** Parallelization of deep neural network computation on the GPU

**Opis teme:**

**Literatura:**

### Predikcija vrijednosti kriptovaluta metodama strojnog učenja i analizom blockchain informacija {[PPHS](nastava/kolegiji/PPHS.md)}  [Dominik Frković]

**Naslov na engleskom:** Predicting the values of cryptocurrencies using machine learning methods and blockchain information

**Mentor:** [v. pred. dr. sc. Vedran Miletić](https://vedran.miletic.net/)

**Komentor:** doc. dr. sc. Sanda Bujačić

**Opis teme:**

Kriptovalute su danas vrlo aktualna i intrigantna tema, kako u području informacijsko-komunikacijske tehnologiju, tako u području financija. Izrazito turbulentan tijek kretanja cijena kriptovaluta je značajna pojava, kako iz ekonomskog, tako i iz tehnološkog aspekta, a velikim je dijelom generiran špekulacijama i utjecajima koje nije moguće procijeniti i predvidjeti na klasičan način. Popularnost kriptovaluta je u kontinuiranom rastu, a najviše zbog osobina kao što su decentraliziranost, transparentnost  i  sigurnost.  U radu se predstavljaju i analiziraju osnovne metode strojnog učenja koje se koriste u predikciji vrijednosti kriptovaluta na temelju analize blockchain informacija. U  radu  će  bit  opisani  pristupi  i rješenja  za  predviđanje  cijena kriptovaluta te će se oslanjati na  informacije  o  blockchain tehnologiji  što nije slučaj koji se javlja u trgovanju uobičajenim valutama na svjetskim burzama kapitala.

**Literatura:**

1. Rivest, R. L. Cryptography and Machine Learning, Advances in Cryptology -- ASIACRYPT '91 (H. Imai, R. L. Rivest, and T. Matsumoto, eds.), (Berlin, Heidelberg), pp. 427--439, Springer Berlin Heidelberg, 1993.
1. Alessandretti, L., ElBahrawy, A., Aiello, L. M., & Baronchelli, A. Anticipating cryptocurrency prices using machine learning. Complexity, 2018.
1. Nakamoto, S. Bitcoin: A Peer-to-Peer Electronic Cash System. Dostupno na: [bitcoin.org/bitcoin.pdf](https://bitcoin.org/bitcoin.pdf)
1. Ellis, S. Juels, A., & Nazarov, S. ChainLink -- A Decentralized Oracle Network. Dostupno na: [link.smartcontract.com/whitepaper](https://link.smartcontract.com/whitepaper)

### Optimizacijske tehnike kod sjenčanja u Unreal Engineu {[PPHS](nastava/kolegiji/PPHS.md)} [Mia Doričić]

**Naslov na engleskom:** Shading optimization techniques in Unreal Engine

**Opis teme:**

Optimizacija (statička i PGO), shaderi na GPU-ima različitih generacija, nivoi optimizacije

**Literatura:**

1. [Shader Development (Unreal Engine Documentation)](https://docs.unrealengine.com/en-US/ProgrammingAndScripting/Rendering/ShaderDevelopment/)

### Krivulje u računalnoj grafici {[PPHS](nastava/kolegiji/PPHS.md)} [Mikaela Oklen]

**Naslov na engleskom:** Curves in computer graphics

**Mentor:** [v. pred. dr. sc. Vedran Miletić](https://vedran.miletic.net/)

**Komentor:** doc. dr. sc. Sanda Bujačić

**Opis teme:**

U računalnoj grafici se razrađuju temeljni koncepti i tehnike prikazivanja 2D i 3D objekata koji su nužni prilikom izrade grafičkih programa na računalu. Jedna od temeljnih karakteristika današnjeg strelovito brzog i uspješnog razvoja računalne grafike jest implementacija optimiziranih grafičkih algoritama u grafičke aplikacije korištenjem standardnih API-ja kao što su OpenGL, Vulkan i vlasničkih API-ja kao što je DirectX. No, uz sve napredne funkcije i mogućnosti koje računalna grafika posjeduje, za ovladavanje svijetom računalne grafike nužno je poznavanje osnovnih i temeljnih koncepata u grafici: od temeljnih pojmova kao što su točka i krivulja do postupka interpolacije i orijentacije promatranih objekata. Cilj rada je predstaviti temeljne matematičke koncepte koji se koriste u računalnoj grafici kao što su točka, vektor, pravac i krivulja te razraditi pristupe koji se koriste prilikom iscrtavanja navedenih pojmova na računalu. Poseban se naglasak stavlja na krivulje čija se matematička svojstva analiziraju i koreliraju sa svojstvima koja su karakteristična za krivulje koje se koriste u računalnoj grafici. Jedan od čestih zadataka u računalnoj grafici je crtanje glatke krivulje između zadanog niza točaka (aproksimacija krivulje), a rješenjetog tipičnog problema numeričke matematike i računalne grafike su aproksimacijske i interpolacijske Bezierove krivulje. Implementaciju algoritama student može izvesti u programskom jeziku po želji te za vizualizaciju može koristiti OpenGL ili Vulkan.

**Literatura:**

1. J. Kiusalaas, Numerical Methods in Engineering with Python 3, Cambridge University Press, 2013.
1. M. Čupić, Ž. Mihajlović, Interaktivna računalna grafika kroz primjere u OpenGL-u, udžbenik Fakulteta elektronike i računarstva, 2018.
1. R. Scitovski, Numerička matematika, 3. izmijenjeno i dopunjeno izdanje, Odjel za matematiku, Sveučilište u Osijeku, 2015.

### Razvoj aplikacije korištenjem mrežne i kriptografske biblioteke NaCl {[RM2](nastava/kolegiji/RM2.md)} [Đino Prenc, preneseno iz 2019/2020.]

**Opis teme:**

Brojne mrežne aplikacije koje svakodnevno vrše šifriranje i dešifriranje sadržaja. Primjerice, web preglednik Firefox i web poslužitelj Apache HTTP Server koriste velik broj različitih kriptografskih algoritama koje podržava protokol Transport Layer Security (TLS) kako bi bili interoperabilni s raznim web poslužiteljima, odnosno klijentima na internetu. Poslužitelj i klijent virtualne privatnu mreže OpenVPN također koristi protokol TLS za šifriranje podataka u komunikaciji i pritom podržava veliki broj algoritama zbog kompatibilnosti s velikim brojem platformi na kojima radi te sa vlastitim starijim verzijama. Navedeni programi uglavnom koriste OpenSSL za izvođenje kriptografskih algoritama koji im trebaju, što zbog veličine OpenSSL-ovog koda i velikog broja podržanih algoritama otežava sigurnosni pregled dobivenog rješenja. Zbog toga se novije aplikacije odlučuju na vlastitu implementaciju kriptografskih algoritama (primjerice, tako radi sustav za virtualnu privatnu mrežu WireGuard) ili koriste manje i lakše provjerljive biblioteke kao što je NaCl (kratica od Networking and Cryptography library) i njezin fork Sodium, namijenjen za jednostavnije višeplatformsko korištenje, pakiranje i instalaciju. Cilj rada je razviti vlastitu mrežnu aplikaciju čija je namjena po izboru studenta i koja kod šifriranja koristi kriptografske algoritme iz biblioteke Sodium.

**Literatura:**

1. [NaCl: Networking and Cryptography library](https://nacl.cr.yp.to/)
1. [Libsodium documentation](https://libsodium.gitbook.io/)

### Tehnike paralelizma u pogonima računalnih igara {[PPHS](nastava/kolegiji/PPHS.md)} [Marko Zoretić, preneseno iz 2019/2020.]

**Opis teme:**

**Literatura:**

### Prvoaprilski RFC-i {[RM2](nastava/kolegiji/RM2.md)} [Dino Šarković, preseneno iz 2018/2019.]

**Opis teme:**

Osim ozbiljnih RFC-a, kao što su primjerice oni koji opisuju TCP, IPv6 ili ICMP, postoji i određeni broj RFC-a objavljenih na prvi april koji sadrže inženjerske šale. Bez obzira na njihov humorističan karakter, većina prvoaprilskih RFC-a može se povezati s aktualnim tehnologijama i problemima u domeni računalnih mreža te su stoga zanimljivi za analizu. Cilj rada je analizirati nekolicinu prvoaprilskih RFC-a po izboru studenta, i povezati ih s ozbiljnim RFC-ima na koje se vežu.

**Literatura:**

1. [April Fools' Day Request for Comments](https://en.wikipedia.org/wiki/April_Fools%27_Day_Request_for_Comments)
1. Limoncelli, T. A. & Salus, P. H. [The Complete April Fools' Day RFCs.](https://www.rfchumor.com/) (Peer-to-Peer Communications, 2007.)

## Odabrane teme diplomskih radova akademske 2020/2021. godine

### Ponovljiva izgradnja programske podrške {[UMS](nastava/kolegiji/UMS.md)} [Matija Banjan]

**Naslov na engleskom:** Reproducible building of software

**Opis teme:**

...

**Literatura:**

1. [Reproducible Builds](https://reproducible-builds.org/)

### Kvantno računarstvo i digitalna sigurnost {[UMS](nastava/kolegiji/UMS.md)} [Kristian Nekić]

**Naslov na engleskom:** Quantum computing and digital security

**Opis teme:**

...

**Literatura:**

1. [Quantum Computing Is the Next Big Security Risk (Wired)](https://www.wired.com/story/quantum-computing-is-the-next-big-security-risk/)

### Sigurnost mikroservisa {[UMS](nastava/kolegiji/UMS.md)} [Simon Košmrl]

**Naslov na engleskom:** Microservice security

**Opis teme:**

...

Cilj rada je opisati tehnike napada na mikroservise i web aplikacije, alate koji se za njih koriste i načine obrane od tih napada te u vlastitoj razvojnoj okolini (lokalno ili u oblaku) demonstrirati neke od napada na za tu svrhu razvijenom mikroservisu ili web aplikaciji (za razvoj se može iskoristiti bilo koji od modernih okvira, npr. Express, Lumen, Flask, Sinatra, ASP.NET Core i Spring te relacijska ili nerelacijska baza podataka po želji).

**Literatura:**

1. [Express](https://expressjs.com/)
1. [Lumen](https://lumen.laravel.com/)
1. [Flask](https://flask.palletsprojects.com/)
1. [Sinatra](http://sinatrarb.com/)
1. [ASP.NET Core](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core)
1. [Spring](https://spring.io/)

## Odabrane teme završnih radova akademske 2019/2020. godine

### Utjecaj pandemije COVID-19 na igranje igara za više igrača putem interneta {[RM2](nastava/kolegiji/RM2.md)} [Ana Novokmet]

**Opis teme:**

Pandemija koronavirusa SARS-CoV-2 tijekom 2020. godina učinila je da velik broj država uvede izolacijske mjere kako bi se usporilo širenje virusa među populacijom. Dio populacije je iskoristio priliku za konzumiranje multimedijskog sadržaja, prvenstveno strujanje filmova i serija sa servisa kao što su Netflix i HBO te igranje igara za više igrača s platformi kao što su Steam i PlayStation. Zbog iznenadnog povećanja broja korisnika, te su platforme bile primorane uvesti mjere ograničavanja širine pojasa mreže kod preuzimanja igara i njihovih nadogradnji kako bi infrastruktura za igranje igara za više igrača putem interneta ostala stabilna. Cilj rada je analizirati utjecaj pandemije koronavirusa na performanse interneta sa specifičnim naglaskom na performanse igranja igara za više igrača i povezane usluge kao što su strujanje audiovizualnog sadržaja igrača putem platformi kao što su Twitch i YouTube.

**Literatura:**

1. [UPDATE: Preserving Internet Access for the Entire Community (PlayStation.Blog)](https://blog.us.playstation.com/2020/03/24/preserving-internet-access-for-the-entire-community/)
1. [Managing Steam Bandwidth During COVID-19 Pandemic (Steam Blog)](https://steamcommunity.com/games/593110/announcements/detail/2074411495515541376)
1. [Tracking COVID-19’s Impact on Global Internet Performance (Speedtest Insights)](https://www.speedtest.net/insights/blog/tracking-covid-19-impact-global-internet-performance/)

### Razvoj HTTP web aplikacije korištenjem okvira Drogon {[RM2](nastava/kolegiji/RM2.md)} [Rikardo Jagnjić]

**Opis teme:**

Suvremeni pristupi razvoju web aplikacija dijele aplikaciju na dva osnovna dijela, stražnji (tzv. backend) i prednji dio (tzv. frontend) koji komuniciraju putem aplikacijskog programskog sučelja korištenjem protokola HTTP. To omogućuje implementaciju više aplikacija za različite platforme (primjerice, web i mobilna) koje koriste zajednički stražnji dio aplikacije, što skraćuje te olakšava pronalaženje i ispravljanje grešaka. Cilj rada je korištenjem okvira Drogon razviti stražnji dio web aplikacije čija je namjena po izboru studenta te opisati aplikacijsko programsko sučelje koje taj stražnji dio nudi putem protokola HTTP te način korištenja tog aplikacijskog programskog sučelja od strane nekog prednjeg dijela web aplikacije koji u budućnosti može biti razvijen.

**Literatura:**

1. [REST API Tutorial](https://restfulapi.net/)
1. [Drogon](https://github.com/an-tao/drogon)
1. [C++ reference](http://www.cppreference.com/)
1. [C++ Core Guidelines](https://isocpp.org/guidelines)

### Projekti javnog bežičnog pristupa internetu Wlan slovenija i Otvorena mreža {[RM1](nastava/kolegiji/RM1.md)} [Igor Lipošćak]

**Opis teme:**

Pristup internetu putem bežične mreže dostupan je na brojnim javnim mjestima. Projekti Wlan slovenija i Otvorena mreža žele proširiti tu dostupnost korištenjem jeftinih kućnih routera i slobodnihg softvera otvorenog koda. Projekti se zasnivaju na softveru za bežične usmjerivače OpenWrt i nekolicini softvera vlastitog razvoja. Cilj rada je opisati tehničke karakteristike i društvene ciljeve oba projekta, te napraviti pregled dosadašnjih postignuća.

Literatura

1. [Wlan slovenija](https://wlan-si.net/)
1. [Otvorena mreža](https://www.otvorenamreza.org/)

### Tehnike rasterizacije {[PPHS](nastava/kolegiji/PPHS.md)}  [Mauro Raguzin]

**Mentor:** [v. pred. dr. sc. Vedran Miletić](https://vedran.miletic.net/)

**Komentor:** doc. dr. sc. Sanda Bujačić

**Opis teme:**

Moderni grafički procesori imaju programabilni cjevovod koji koriste za prikaz 3D grafike na računalu. Jedan od koraka u tom prikazu je rasterizacija: proces kojim se objekti u prostoru prikazuju kao pikseli kako bi mogli biti postavljeni na zaslon računala. Cilj rada je objasniti tehnike rasterizacije, specijalno renderiranje koje je manje zahtjevno za resursima račuanala i praćenje zrake (engl. raytracing) koje je zahtjevnije. Od studenta se također očekuje da izvede implementaciju tehnike rasterizacije po želji na modernom grafičkom procesu po želji, uz preferenciju prema korištenju tehnologija otvorenog koda.

**Literatura:**

1. [What’s the Difference Between Ray Tracing and Rasterization? (NVIDIA Blog)](https://blogs.nvidia.com/blog/2018/03/19/whats-difference-between-ray-tracing-rasterization/)
1. [ROCm](https://rocmdocs.amd.com/)
1. [NVIDIA CUDA](https://developer.nvidia.com/cuda-zone)

### Problem performansi računalne mreže Bufferbloat {[RM2](nastava/kolegiji/RM2.md)} [Nikola Terihaj]

**Opis teme:**

Porastom veličine međuspremnika usmjerivača na internetu raste prosječno vrijeme koje paketi čekaju u tim međuspremnicima na putu od izvora do odredišta. Posljednjih 10-ak godina taj se fenomen izučava pod nazivom Bufferbloat pa su vremenom razvijeni alati koji ga mogu mjeriti kao što je Flent i algoritam za aktivno upravljanje redovima čekanja paketa CoDel kojim se Bufferbloat želi izbjeći. Cilj rada je opisati kako dolazi do Bufferbloata, izmjeriti Bufferbloat u konkretnom slučaju po izboru studenta te analizirati način rada algoritma CoDel koji služi za njegovo izbjegavanje i doprinose projekta Make Wi-Fi Fast koji iskustvo stečeno kod rješavanja Bufferbloata prenosi na Wi-Fi.

**Literatura:**

1. [Bufferbloat](https://www.bufferbloat.net/)
1. [DSLReports Speed Test](http://www.dslreports.com/speedtest)
1. [Flent](https://flent.org/)
1. [CoDel](https://www.bufferbloat.net/projects/codel/wiki/)
1. [Make Wi-Fi Fast](https://www.bufferbloat.net/projects/make-wifi-fast/wiki/)
1. Bozkurt, Ilker Nadi, et al. "Why is the Internet so slow?!." International Conference on Passive and Active Network Measurement. Springer, Cham, 2017. Rad dostupan putem [mrežnih stranica Ilkera Nadija Bozkurta](https://users.cs.duke.edu/%7Eilker/papers/conference/pam17.pdf); pojednostavljeni opis zaključaka rada dostupan na [APNIC-ovom blogu](https://blog.apnic.net/2017/06/19/why-is-the-internet-so-slow/)

### Predviđanje pristajanja malih molekula na proteine korištenjem tehnika umjetne inteligencije na grafičkim procesorima {[PPHS](nastava/kolegiji/PPHS.md)} [Adis Tokalić]

**Opis teme:**

Porastom procesne moći računala, naročito zahvaljujući računanju na grafičkim procesorima, snažno raste i primjena tehnika strojnog učenja. Jedna od domena primjene strojnog učenja koja se razvija u posljednjih desetak godina je predviđanje molekularnih interakcija. U praktičnoj primjeni vrlo je zanimljivo predviđanje pristajanja malih molekula koje su potencijalni lijekovi na proteine, za što se koriste slobodni softveri otvorenog koda kao što su AutoDock Vina i RxDock i komercijalni softveri kao što je Glide. Cilj rada je dizajnirati analizirati postojeće algoritme strojnog učenja u području predviđanja pristajanja malih molekula na proteine i zatim dizajnirati algoritam koji uči na temelju izlaznih podataka koji daje neki od ranije navedenih softvera pa usporediti predviđanja algoritma za strojno učenje s predviđanjima samog softvera.

**Literatura:**

1. [NVIDIA CUDA](https://developer.nvidia.com/cuda-zone)
1. [ROCm](https://rocmdocs.amd.com/)
1. Ballester, P. J. & Mitchell, J. B. O. [A machine learning approach to predicting protein--ligand binding affinity with applications to molecular docking](https://academic.oup.com/bioinformatics/article/26/9/1169/199938). Bioinformatics 26, 1169--1175 (2010).
1. Kinnings, S. L. et al. [A Machine Learning-Based Method To Improve Docking Scoring Functions and Its Application to Drug Repurposing](https://pubs.acs.org/doi/abs/10.1021/ci100369f). J. Chem. Inf. Model. 51, 408--419 (2011).
1. [Vina](http://vina.scripps.edu/)
1. [RxDock](https://www.rxdock.org/)
1. [Glide](https://www.schrodinger.com/glide)

### Paralelizacija predviđanja pristajanja malih molekula na proteine {[PPHS](nastava/kolegiji/PPHS.md)}  [Maja Abramović]

**Opis teme:**

Visokoprotočni virtualni pregled molekula koje su potencijalni lijekovi kroz predviđanje pristajanja tih molekula na proteine je tzv. sramotno paralelna operacija; može se trivijalno paralelizirati tako da se pregled svake pojedine molekule vrši na različitom (logičkom) procesoru. Za tu svrhu se na superračunalima uglavnom koriste upravitelji opterećenjem opće namjene kao što je Slurm ili specijalno razvijeni sustavi za skaliranje virtualnog pregleda molekula kao što je Virtual Flow. Na manjim računalnim sustavima kao što su poslužitelji, radne stanice, stolna i prijenosna računala ovakvi sustavi se ne koriste pa je virtualni pregled molekula često ograničen na korištenje samo jednog logičkog procesora i očekuje od korisnika da ručno razdijeli ulazne datoteke s molekulama na više dijelova i pokrene program više puta kako bi iskoristio sve dostupne logičke procesore. Kako suvremena prijenosna računala imaju od 4 do 16 logičkih procesora, stolna računala i radne stanice od 8 do 32 (u nekim slučajevima i do 128), a poslužitelji od 32 do 256, takvo ručno pokretanje zahtijeva izrazito puno rudimentarnog i repetitivnog rada od strane korisnika. Cilj rada je u alatu za visokoprotočni pregled molekula RxDock, forku alata rDock moderniziranom korištenjem C++-a 11, implementirati podršku za višenitni rad korištenjem mehanizmom dostupnim u C++-u po izboru studenta kako bi se olakšalo korištenje dostupnih resursa računalnih sustava s više logičkih procesora.

**Literatura:**

1. [Slurm](https://slurm.schedmd.com/)
1. [Virtual Flow](https://virtual-flow.org/)
1. Ruiz-Carmona S, Alvarez-Garcia D, Foloppe N, Garmendia-Doval AB, Juhos S, Schmidtke P, et al. [rDock: A Fast, Versatile and Open Source Program for Docking Ligands to Proteins and Nucleic Acids](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003571). PLoS Comput Biol 10(4): e1003571 (2014). [doi:10.1371/journal.pcbi.1003571](https://doi.org/10.1371/journal.pcbi.1003571)
1. [RxDock](https://www.rxdock.org/)
1. [C++11 thread support library](https://en.cppreference.com/w/cpp/thread)
1. [Taskflow (C++14)](https://taskflow.github.io/)
1. [C++17 algorithms library](https://en.cppreference.com/w/cpp/algorithm)

### Rješavanje zadataka iz predmeta Računalne mreže na računalu {[RM1](nastava/kolegiji/RM1.md)} [Andrea Hrelja, preneseno iz 2018/2019.]

**Opis teme:**

Predmet Računalne mreže jedan od je temeljnih predmeta preddiplomskog studija informatike. Teorijsko gradivo iz predmeta popraćeno je računskim zadacima koji se rješavaju na papiru, ali mogu se rješavati i na računalu korištenjem bilo kojeg alata ili programskog jezika koji podržava osnovne računske operacije. Cilj rada je isprogramirati rješenja odabranih računskih zadataka iz predmeta Računalne mreže u programskom jeziku po želji studenta kako bi se ti zadaci mogli rješavati na računalu i/ili kako bi računalo moglo provjeriti točnost predloženog rješenja. Isprogramirani zadaci moraju raditi tako da daju rješenja budu točna uz varijaciju brojki i drugih postavki u zadacima.

**Literatura:**

1. Peterson, L. L. & Davie, B. S. Computer networks: a systems approach. (Morgan Kaufmann, 2012.)
1. Dokumentacija odabranog programskog jezika

## Odabrane teme diplomskih radova akademske 2019/2020. godine

### InterPlanetary File System (IPFS) {[UMS](nastava/kolegiji/UMS.md)} [Dario Ognjanović]

**Opis teme:**

...

**Literatura:**

1. [IPFS](https://ipfs.io/)

### Mjerenje performansi poslužiteljskih Java aplikacija u virtualnim strojevima {[UMS](nastava/kolegiji/UMS.md)} [Matija Šegović]

**Opis teme:**

Poslovni sustavi zahtijevaju predvidljiv rad aplikacija o kojima poslovanje ovisi, bez obzira rade li te aplikacije u virtualnom ili u stvarnom okruženju. Jedan od aspekata predvidljivosti rada aplikacije jesu njene performanse koje se najčešće mjere u terminima vremena odziva u ovisnosti o broju korisnika, što se može mjeriti. Povećanjem performansi računala na kojem se aplikacije izvode uglavnom će biti moguće smanjiti vrijeme odziva ili povećati broj korisnika te će ta mjerenja performansi biti vodilja kod odabira računala na kojem će se aplikacija u konačnici izvoditi.

Cilj rada je opisati proces instalacije i konfiguracije poslužiteljskih Java aplikacija na virtualnim strojevima na tipičnom poslužitelju te izmjeriti njihove performanse korištenjem ELK Stacka (Elasticsearch, Logstash i Kibana).

**Literatura:**

1. Nemeth, E., Snyder, G., Hein, T. R., Whaley, B. & Mackin, D. Unix and Linux system administration handbook. (Addison-Wesley, 2017)
1. [Apache Tomcat Documentation](https://tomcat.apache.org/)
1. [JBoss Application Server Official Documentation](https://developer.jboss.org/wiki/JBossApplicationServerOfficialDocumentationPage)
1. [IBM WebSphere Documentation](https://www.ibm.com/support/pages/websphere-ibm-i-documentation)
1. [ELK Stack Documentation](https://www.elastic.co/what-is/elk-stack)

### Proširenje mogućnosti OpenCL stoga otvorenog koda za grafičke procesore AMD Radeon {[PPHS](nastava/kolegiji/PPHS.md)} [Dominik Varelija]

**Opis teme:**

NVIDIA je vodeća tvrtka u domeni vizualizacije i računanja na grafičkim procesorima. U domeni računanja na grafičkim procesorima s NVIDIA-om se natječu AMD i Intel, nudeći podršku za otvoreni standard OpenCL kao alternativu NVIDIA-inoj vlasničkoj tehnologiji CUDA. AMD, pored korištenja otvorenog standarda OpenCL, nudi stog (program-prevoditelj Clang/LLVM, biblioteke, upravljačke programe) otvorenog koda Clover za grafičke procesore Radeon, temeljen na biblioteci Mesa (Gallium). Zadatak rada je usporediti mogućnosti vlasničkog stoga za grafičke procesore tvrtke NVIDIA i stoga otvorenog koda za grafičke procesore AMD Radeon i proširiti mogućnosti stoga da podržava skup alata za molekularne simulacije OpenMM.

**Literatura:**

1. [Mesa 3D Graphics Library documentation](https://docs.mesa3d.org/)
1. [Radeon Feature on X.Org Wiki](https://www.x.org/wiki/RadeonFeature/)
1. [Gallium Compute on DRI Wiki](https://dri.freedesktop.org/wiki/GalliumCompute/)
1. [zogi/mesa (GitHub)](https://github.com/zogi/mesa)
1. [libclc](http://libclc.llvm.org/)
1. [LLVM](http://llvm.org/)
1. [OpenMM](http://openmm.org/)
1. [Make OpenMM OpenCL support work on Clover and RadeonSI](https://bugs.freedesktop.org/show_bug.cgi?id=99764)
1. [Scarpino, Matthew. OpenCL in Action: How to accelerate graphics and computations. (Manning Publications, 2011).](https://www.manning.com/books/opencl-in-action)
1. [Khronos OpenCL Registry](https://www.khronos.org/registry/OpenCL/)
1. [Marchesin, Stéphane. Linux Graphics Drivers: an Introduction. (FreeDesktop, 2012).](https://people.freedesktop.org/~marcheu/linuxgraphicsdrivers.pdf)
1. [Linux Graphics Stack Overview (Simon Kitching, The Mine of Information)](https://moi.vonos.net/linux/graphics-stack/)
1. [Linux graphic stack (Nathan Gauër Blog)](https://studiopixl.com/2017-05-13/linux-graphic-stack-an-overview)
1. [The Linux Graphics Stack (Clean Rinse)](https://blog.mecheye.net/2012/06/the-linux-graphics-stack/)
1. [A brief introduction to the Linux graphics stack (Iago Toral Developer Log, Igalia)](https://blogs.igalia.com/itoral/2014/07/29/a-brief-introduction-to-the-linux-graphics-stack/)

### Prevođenje programa za sjenčanje u strojni kod grafičkog procesora AMD Radeon {[PPHS](nastava/kolegiji/PPHS.md)} [Sanja Božić]

**Opis teme:**

Programi za sjenčanje neizbježan su dio modernih računalnih igara gdje služe za prikaz svjetla i sjene 3D modela, promjenu zasićenja i tona boje, primjenu efekata kao što su volumetričko osvjetljenje te brojne druge svrhe. Proizvođači grafičkih procesora žele igračima osigurati optimalan ugođaj igranja pa je prevođenje programa za sjenčanje koje se događa dok igrač igra igru jedan od većih izazova za optimizaciju performansi; potrebno je postići i brzo prevođenje koda kako bi isti bio spreman za pokretanje prije nego igrač dođe do dijela gdje se kod pokreće i visoke performanse izvođenja rezultirajućeg strojnog koda. U okviru inicijative GPUOpen, započete u prosincu 2015. godine, AMD je u suradnji sa zajednicom okupljenom oko projekata Mesa i LLVM razvio prevoditelj programa za sjenčanje za vlastite grafičke procesore Radeon. Fokus je bio i ostao optimizacija performansi na konkretnim programima za sjenčanje kakvi se javljaju u igrama koje koriste aplikacijska programska sučelja OpenGL i Vulkan. Tijekom 2019. godine Valve je objavio da razvija alternativni prevoditelj programa za sjenčanje nazvan ACO koji LLVM zamjenjuje vlastitim generatorom strojnog koda i ima za cilj skratiti vrijeme prevođenja programa (koje je ovdje kritično) u aktualnim igrama koje koriste Vulkan (Strange Brigade, Rise of The Tomb Raider, Doom (2016) i sl.). Cilj rada je dati pregled strojnih instrukcija grafičkog procesora AMD Radeon arhitektura Graphics Core Next i/ili Radeon DNA te usporediti AMD-ovu i Valveovu implementaciju programa za sjenčanje u terminima dizajna softvera, vremena, točnosti i brzine izvođenja prevedenih programa. Kod prevođenja programa za sjenčanje moguće je razviti vlastite ili koristiti postojeće iz igara i alata Piglit za testiranje implementacija OpenGL-a i Vulkana.

**Literatura:**

1. [Help us test ACO, a new Mesa shader compiler for AMD graphics!](https://steamcommunity.com/games/221410/announcements/detail/1602634609636894200)
1. [Mesa 3D Graphics Library documentation](https://docs.mesa3d.org/)
1. [User Guide for AMDGPU Backend (LLVM)](https://llvm.org/docs/AMDGPUUsage.html)
1. [Piglit](https://piglit.freedesktop.org/)
1. [Gallium Hud, the almost definitive guide on how to use and customize it](https://manerosss.wordpress.com/2017/07/13/howto-gallium-hud/)
1. [Marchesin, Stéphane. Linux Graphics Drivers: an Introduction. (FreeDesktop, 2012).](https://people.freedesktop.org/~marcheu/linuxgraphicsdrivers.pdf)
1. [Linux Graphics Stack Overview (Simon Kitching, The Mine of Information)](https://moi.vonos.net/linux/graphics-stack/)
1. [Linux graphic stack (Nathan Gauër Blog)](https://studiopixl.com/2017-05-13/linux-graphic-stack-an-overview)
1. [The Linux Graphics Stack (Clean Rinse)](https://blog.mecheye.net/2012/06/the-linux-graphics-stack/)
1. [A brief introduction to the Linux graphics stack (Iago Toral Developer Log, Igalia)](https://blogs.igalia.com/itoral/2014/07/29/a-brief-introduction-to-the-linux-graphics-stack/)

## Odabrane teme završnih radova akademske 2018/2019. godine

### Implementacija Kruskalovog algoritma primjenom tehnologije CUDA {[PPHS](nastava/kolegiji/PPHS.md)} [Vicenco Tomaš]

**Mentor:** dr. sc. Draško Tomić

**Zamjenski mentor:** v. pred. dr. sc. Vedran Miletić

**Opis teme:**

NVIDIA CUDA je vodeća tehnologija za računanje na grafičkim procesorima i iskorištena je za paralelizaciju brojnih algoritama. Kruskalov algoritam traži minimalno razapinjuće stablo grafa i koristi se kod planiranja brojnih vrsta mreža (cestovne, električne, komunikacijske i drugih). Cilj rada je analizirati različite postojeće pristupe paralelizaciji Kruskalovog algoritma za izvođenje na grafičkim procesorima korištenjem tehnologije CUDA te implementirati algoritam prema odabranom pristupu.

**Literatura:**

1. [NVIDIA CUDA](https://developer.nvidia.com/cuda-zone)
1. [Kruskal's algorithm](https://en.wikipedia.org/wiki/Kruskal's_algorithm)

## Odabrane teme diplomskih radova akademske 2018/2019. godine

### Performanse upravljačkih programa grafičkog procesora kod izvođenja simulacija molekularne dinamike alatom GROMACS {[PPHS](nastava/kolegiji/PPHS.md)} [Mario Ćuro]

**Opis teme:**

GROMACS je jedan od najkorištenijih alata za simulaciju molekularne dinamike i, zbog vrlo dobrih performansi kod izvođenja na grafičkim procesorima korištenjem CUDA-e, redovito spomenuta aplikacija u NVIDIA-inim katalozima softvera i promotivnim materijalima. Tijekom 2014. godine tvrtka StreamComputing (danas StreamHPC) implementirala je podrška za izvođenje na nekim grafičkim procesorima koji podržavaju tehnologiju OpenCL. Carsten Kutzner i suradnici su u dva rada, jednom objavljenom 2015. i jednom koji je u trenutku zadavanja teme u procesu objave, analizirali performanse GROMACS-a na grafičkim procesorima uglavnom koristeći CUDA-u. Cilj ovog rada je na isti način analizirati performanse GROMACS-a korištenjem OpenCL-a na grafičkim procesorima AMD Radeon. Za tu svrhu može se koristiti i razvojna verzija GROMACS-a koja nudi Python API čime je olakšana automatizacija mjerenja performansi.

**Literatura:**

1. [GROMACS documentation](http://manual.gromacs.org/)
1. [We ported GROMACS from CUDA to OpenCL (StreamHPC)](https://streamhpc.com/blog/2014-11-01/ported-gromacs-cuda-opencl/)
1. [Kutzner, C. et al. Best bang for your buck: GPU nodes for GROMACS biomolecular simulations. Journal of Computational Chemistry 36, 1990--2008 (2015).](https://onlinelibrary.wiley.com/doi/full/10.1002/jcc.24030)
1. [Kutzner, C. et al. More Bang for Your Buck: Improved use of GPU Nodes for GROMACS 2018. arXiv:1903.05918 [physics, q-bio] (2019).](https://arxiv.org/abs/1903.05918)
1. [A free GROMACS benchmark set (MPI-BPC Theoretical and Computational Biophysics)](https://www.mpibpc.mpg.de/grubmueller/bench)
1. [gmxapi Python package](https://gmxapi.readthedocs.io/)

### Ucjenjivački softver {[UMS](nastava/kolegiji/UMS.md)} [Stefano Berneš]

**Opis teme:**

Ucjenjivački softver je vrsta zlonamjernog softvera koja šifrira datoteke na računalu korisnika i zatim traži od korisnika plaćanje određene svote novca u zamjenu za ključ koji može dešifrirati šifrirane datoteke. U naglom je porastu od 2012. godine, a postao je poznat zahvaljujući CryptoLockeru koji je od korisnika iznuđivao plaćanje u Bitcoinima. Zadatak diplomskog rada je objasniti kako radi ucjenjivački softver, opisati povijest i neke najpoznatije ransomeware napade, nabrojiti i opisati različite vrste ucjenjivačkog softvera te navesti načine zaštite od mogućih ransomeware napada. Naposlijetku, potrebno je izraditi dokaz koncepta u kojem će biti prikazan način rada ucjenjivačkog softvera.

**Literatura:**

1. [Ransomware](https://en.wikipedia.org/wiki/Ransomware)
1. [Ransomware doesn’t mean game over (Malwarebytes Labs)](https://blog.malwarebytes.com/101/2016/11/ransomware-doesnt-mean-game-over/)
1. [Massive WannaCry/Wcry Ransomware Attack Hits Countries (Trend Micro Research)](https://www.trendmicro.com/en_us/research/17/e/massive-wannacrywcry-ransomware-attack-hits-various-countries.html)

### Robotska automatizacija procesa {[UMS](nastava/kolegiji/UMS.md)} [Marko Čolak]

**Opis teme:**

Procesi koje radnik unutar poslovnog sustava često izvodi na računalu i koji se mogu opisati nizom akcija koje treba poduzeti zanimljivi su za primjenu robotske automatizacije (engl. *robotic process automation*). U okviru robotske automatizacije koristi se niz softverskih alata (koji su metafora za industrijske robote) koji onda zamjenjuju radnika kod izvođenja repetitivnih radnji.

Zadatak rada je opisati robotsku automatizaciju procesa i razloge njene primjene (ušteda vremena, pojednostavljenje procesa koje radnik izvodi i sl.), a zatim odabrati proces kojeg radnik često izvodi na računalu (primjerice, otvaranje određene web stranice, preuzimanje datoteke s određenim strukturiranim sadržajem s nje pa čitanje, odabir i pretvorba sadržaja koji se potom unosi u poslovnu aplikaciju koja generira izvještaj koji treba preuzeti i poslati e-poštom). Za odabrani proces potrebno je napraviti dijagram procesa korištenjem UML-a (Unified Modeling Language) ili BPMN-a (Business Process Model and Notation) te provesti automatizaciju korištenjem rješenja otvorenog koda kao što su programski jezik Python i njegovi moduli (bilo standardne biblioteke, bilo treće strane), TagUI i/ili Robot Framework koji služe kao alternativa komercijalnim rješenjima u iste namjene (npr. UiPath, BluePrism, AutomationAnywhere). Za automatizaciju pokretanja razvijenih i postojećih alata potrebno je koristiti postojeće usluge operacijskog sustava (npr. init i cron ili systemd na Linuxu).

**Literatura:**

1. Lacity, M., and Willcocks, L. P.. *Robotic process automation: the next transformation lever for shared services.* (London School of Economics Outsourcing Unit Working Research Paper Series, 2015). Rad dostupan putem [mrežnih stranica Sveučilišta u Missouriju u St. Louisu](http://www.umsl.edu/~lacitym/OUWP1601.pdf).
1. Willcocks, L. P., Lacity M. & Craig, A. *Robotic process automation at Xchanging.* (London School of Economics Outsourcing Unit Working Research Paper Series, 2015). Rad dostupan putem [mrežnih stranica Londonske škole ekonomije](http://eprints.lse.ac.uk/64518/1/OUWRPS_15_03_published.pdf).
1. [Robot Framework Documentation](https://robotframework.org/#documentation)

### Instalacija i održavanje računalne učionice {[UMS](nastava/kolegiji/UMS.md)} [Pino Zidarić]

**Opis teme:**

Moderne računalne učionice na fakultetima i u školama rijetko se naivno instaliraju i održavaju računalo po računalo, već je često u pitanju neki oblik centralnog upravljanja instalacijom softvera na svakom pojedinom računalu. Zadatak rada je osmisliti softverski stog i postavke suvremene učionice Odjela zasnovane na operacijskom sustavu Linux. Radi jednostavnosti, može se uzeti da se radi o single-boot sustavu (u praksi to najčešće nije slučaj, ali kako se Linux i Windows na stvarnim računalima na Odjelu za informatiku često stavljaju na različite fizičke diskove, to je dovoljno dobra aproksimacija). Hardver koji se koristi su relativno nove (<5 godina starosti) x86-64 mašine od Intela (i5, rjeđe i7) ili AMD-a (Ryzen 5, možda Ryzen 7). Zahtjevi za učionicom su sljedeći:

- Temelj je zadnji stabilni Debian (u trenutku zadavanja zadatka: 9) ili zadnji Ubuntu LTS (u trenutku zadavanja zadatka: 18.04).
- Potrebno je na svakom računalu stvoriti korisnički račun informatičke podrške koji ima sudo pristup (npr. podrska), korisnički račun nastavnika koji ima sudo pristup (npr. predavac) i korisnički račun studenta koji nema sudo pristup (npr. student).
- Potrebno je omogućiti pristup nastavničkom računalu putem VPN-a (pretpostaviti da negdje postoji VPN poslužitelj na javnoj adresi koji se može koristiti), a osim toga VPN-om se mora omogućiti komunikacija između učionica s nastavničkog računala u jednoj učionici na nastavničko računalo u drugoj učionici) ([OpenVPN](https://openvpn.net/community/), [SoftEther](https://www.softether.org/) ili [Wireguard](https://www.wireguard.com/)).
- Potrebno je instalirati softver za nadzor studentskog rada (poslužiteljska strana na nastavničkom računalu, klijentska strana na studentskim) ([Veyon](https://veyon.io/) ili [Epoptes](http://www.epoptes.org/)).
- Potrebno je postaviti [apt-cacher-ng](https://wiki.debian.org/AptCacherNg) (poslužiteljska strana na nastavničkom računalu, studentska računala ga koriste).
- Potrebno je postaviti [Ansible](https://www.ansible.com/) na nastavničkom računalu kako bi se moglo upravljati instalacijom softvera na studentskim računalima s jednog mjesta.
- Potrebno je napraviti skriptu koja kod poziva s nastavničkog računala na svim studentskim računalima putem vatrozida zabranjuje pristup svim stranicama na internetu osim [Merlina](https://moodle.srce.hr/).
- Potrebno je napraviti skriptu koja kod poziva s nastavničkog računala na svim studentskim računalima odjavljuje studentskog korisnika ako je prijavljen i zatim briše sve datoteke unutar kućnog direktorija tog korisnika pa kopira sadržaj direktorija /etc/skel na njihovo mjesto.

**Literatura:**

1. [DigitalOcean Tutorials](https://www.digitalocean.com/community/tutorials/)
1. [nixCraft HowTos and Tutorials](https://www.cyberciti.biz/faq/)

### Biblioteke heterogene sustavske arhitekture platforme ROCm {[PPHS](nastava/kolegiji/PPHS.md)} [Augustin Sočković]

**Opis teme:**

Dok se aplikacija izvodi u heterogenom računalnom sustavu, grafički i središnji procesor razmjenjuju podatke koje aplikacija koristi za izvođenje operacija.

**Literatura:**

1. W. H. Wen-mei, [Heterogeneous System Architecture: A new compute platform infrastructure.](https://www.elsevier.com/books/heterogeneous-system-architecture/hwu/978-0-12-800386-2) Morgan Kaufmann, 2015.
1. [ROCm: Open Platform For Development, Discovery and Education around GPU Computing (GPUOpen)](https://gpuopen.com/compute-product/rocm/)

## Odabrane teme završnih radova akademske 2017/2018. godine

### Napadi tipa man-in-the-middle na HTTPS i njihovo prepoznavanje {[RM2](nastava/kolegiji/RM2.md)} [Dominik Varelija]

**Opis teme:**

Širenjem interneta i širenjem broja i vrsta uređaja koji internetu pristupaju sigurnost računalnih mreža sve je veći izazov. Unatoč rastu korištenja šifriranja na webu, sam prijelaz na HTTPS nije dovoljan da se onemoguće napadi presretanjem prometa (engl. man-in-the-middle). Primjerice, kako autoriteti certifikata kojima su označeni kao da im se vjeruje mogu izdavati certifikate po želji za bilo koju domenu na internetu, u slučaju zlonamjernog djelovanja mogu omogućiti presretanje šifriranog prometa bez da korisnik to uoči obzirom da i dalje pristupa web stranici putem HTTPS-a. Zadatak rada je opisati navedeni i druge napade tipa man-in-the-middle na HTTPS i metode njiho0vog prepoznavanja i prevencije.

**Literatura:**

1. [Half the Web Is Now Encrypted. That Makes Everyone Safer (Wired)](https://www.wired.com/2017/01/half-web-now-encrypted-makes-everyone-safer/)
1. Durumeric, Zakir, et al. "The Security Impact of HTTPS Interception." Network and Distributed Systems Symposium (NDSS’17). 2017. Rad dostupan putem [mrežnih stranica J. Alexa Hanldermana](https://jhalderm.com/pub/papers/interception-ndss17.pdf).
1. [Detecting HTTPS Interception (Caddy web server)](https://caddyserver.com/docs/mitm-detection)

### Nomulus: softver otvorenog koda za upravljanje registrom domena (Nomulus: open source domain registry management software) {[RM2](nastava/kolegiji/RM2.md)} [Sanja Ivić, preneseno iz 2016/2017.]

**Opis teme:**

Rastom prostora internetskih domena na veći skup ekstenzija vršnog nivoa (engl. top-level domain extensions) od 2011. godine nadalje raste i broj kompanija koje se bave upravljanjem domenama. Posao upravljanja registrom domena, koji su nekoć radili Verisign, Afilias, Neustar i nacionalni registri pojedinih država, danas rade stotine kompanija. Među njima su i, osim kompanija koje nove domene prodaju, kompanije koje nove domene koriste isključivo za vlastite potrebe (BMW za .bmw, Ferrari za .ferrari, Nike za .nike itd.). U takvoj situaciji softver za upravljanje registrom domena umjesto alata koji svaki registar razvija isključivo za internu potrebu postaje potencijalno široko primjenjiv softver, a jedna od mogućnosti razvoja takvog softvera je kroz projekt otvorenog koda. Nomulus je softver otvorenog koda koji Google Registry koristi za upravljanje domenama koje su im dodijeljene (.google, .how, .foo...), a napravljen je tako da ga mogu koristiti i drugi registri domena. Osim Googlea, u razvoju sudjeluje i Donuts, jedan od registara domena nastalih prilikom posljednje ekspanzije prostora internetskih domena. Zadatak rada je analizirati mogućnosti softvera i opisati proces instalacije, konfiguracije i korištenja iz hipotetske perspektive registra domena koji je vlasnik barem dvije nove ekstenzije vršnog nivoa.
Literatura

1. [nTLDStats](https://ntldstats.com/registry/group)
1. [NameStat](https://namestat.org/)
1. [Nomulus](https://nomulus.foo/)
1. [Nomulus na GitHubu](https://github.com/google/nomulus/)
1. [Introducing Nomulus: an open source top-level domain name registry (Google Open Source Blog)](https://opensource.googleblog.com/2016/10/introducing-nomulus-open-source.html)
1. [ICANN New gTLDs](https://newgtlds.icann.org/)

### Ugradbeni softver za bežične usmjerivače OpenWrt / LEDE (OpenWRT/LEDE embedded wireless router software) {[RM1](nastava/kolegiji/RM1.md)} [Matija Banjan, preneseno iz 2016/2017.]

**Opis teme:**

OpenWrt / LEDE je distribucija Linuxa koja se koristi kao ugradbeni softver za bežične usmjerivače. Podržava velik broj usmjerivača, a koristi se primarno kao zamjena za često zastarjeli i nesigurni proizvođačev ugradbeni softver. OpenWrt je slobodni softver otvorenog koda. Zadatak rada je opisati mogućnosti, način instalacije i način rada OpenWrt-a ili LEDE-a.

**Literatura:**

1. [OpenWRT](https://openwrt.org/)
1. [LEDE](https://www.lede-project.org/)

## Odabrane teme diplomskih radova akademske 2017/2018. godine

### Implementacija TCP-a u jezgri Linuxa i njene primjene (TCP implementation in Linux kernel and its applications) {[OS1](nastava/kolegiji/OS1.md)} [Ana Tomasović]

**Mentor:** doc. dr. sc. Božidar Kovačić

**Komentor:** [dr. sc. Vedran Miletić](https://vedran.miletic.net/)

**Opis teme:**

Transmission Control Protocol (TCP) je protokol koji logički pripada četvrtom, transportnom, sloju OSI modela i pruža pouzdan prijenos podataka: slanje paketa u točnom redoslijedu, provjeru i ispravljanje grešaka nastalih u prijenosu te kontrolu zagušenja veze. Sam protokol je standardiziran, ali implementacija protokola je specifična za svaki operacijski sustav sukladno potrebama njegovih korisnika i interesima njegovih razvijatelja. Jezgra operacijskog sustava Linux je otvorenog koda te je implementacija stoga internetskih protokola, specifično i protokola TCP, dostupna za analizu i prilagodbu. Cilj rada je opisati implementaciju TCP-a u stogu internetskih protokola u jezgri operacijskog sustava Linux te opisati primjene dostupnih mehanizama za pouzdan prijenos paketa.

**Literatura:**

1. [Benvenuti, Christian. Understanding Linux network internals. O'Reilly Media, Inc., 2006.](http://shop.oreilly.com/product/9780596002558.do)
1. Lacage, Mathieu. Experimentation tools for networking research. Diss. Nice, 2010.
1. [Sarolahti, Pasi, and Alexey Kuznetsov. "Congestion Control in Linux TCP." USENIX Annual Technical Conference, FREENIX Track. 2002.](https://www.usenix.org/legacy/publications/library/proceedings/usenix02/tech/freenix/full_papers/sarolahti/sarolahti_html/)

### Pogon otvorenog koda za izradu 2D i 3D igara Godot (Godot open source 2D and 3D game engine) {[PPHS](nastava/kolegiji/PPHS.md)} [Kristijan Faust]

**Mentor:** doc. dr. sc. Božidar Kovačić

**Komentor:** [dr. sc. Vedran Miletić](https://vedran.miletic.net/)

**Opis teme:**

Godot je pogon otvorenog koda za izradu 2D i 3D igara dostupand pod licencom MIT. Razvojna okolina radi na Linuxu, macOS-u, Windowsima i drugim operacijskim sustavima, a moguće je izrađivati igre za PC, konzole, mobilne i web platforme korištenjem jezika C++, C# ili vlastitog skriptnog jezika GDScript, sintaksom sličnog Pythonu. Cilj rada je dati generalni opis pogona Godot i pregled aktivnosti koje zajednica provodi u procesu njegovog razvoja, zatim analizirati njegov dizajn, opisati razvojnu okolinu s osobitim naglaskom na GDScript te, naposlijetku, prikazati kako se pakiraju stvorene igre za distribuciju na različitim platformama.

**Literatura:**

1. [Službena dokumentacija pogona Godot](http://docs.godotengine.org/)
1. [GDScript](http://docs.godotengine.org/en/3.0/getting_started/scripting/gdscript/index.html)
1. [Godot 3.0 Open-Source Game Engine Released (Phoronix)](https://www.phoronix.com/scan.php?page=news_item&px=Godot-3.0-Released)
1. [Godot Engine, the open source game engine has evolved with the big 3.0 release (GamingOnLinux)](https://www.gamingonlinux.com/articles/godot-engine-the-open-source-game-engine-has-evolved-with-the-big-30-release.11135)

## Odabrane teme završnih radova akademske 2016/2017. godine

### Utjecaj interneta na rezultat predsjedničkih izbora 2016. godine u Sjedinjenim Američkim Državama (Impact of the Internet on the result of US Presidential Election 2016) {[RM2](nastava/kolegiji/RM2.md)} [Mihael Orlović]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:504221)

**Opis teme:**

Tijekom izbornog ciklusa u Sjedinjenim Američkim Državama 2015. i 2016. nominaciju Republikanske stranke među 17 kandidata osvojio je Donald John Trump, zvijezda reality TV showa Pripravnik (engl. The Apprentice), a nekoliko mjeseci kasnije je na iznenađenje šire javnosti osvojio i predsjedničke izbore. Među različitim glasačkim blokovima, Trump je vrlo rano zainteresirao korisnike interneta koji koriste Twitter, Facebook, Reddit i 4chan za širenje takozvanih memeja, ideja koje čine internetsku kulturu. Taj glasački blok je počeo vrlo aktivno proizvoditi i distribuirati memeje o "God Emperoru" Trumpu i drugim kandidatima Republikanske, Demokratske i ostalih stranaka, s ciljem da mu pomogne osvojiti izbore. Ne ulazeći u radu u ideološke prepirke i ne birajući stranu, zadatak je analizirati dostupne podatke o čitanosti (putem Alexe, SimilarWeba, Google Trendova i drugih izvora), stavovima, anketama i predviđanjima mainstream medija (MSNBC/NBC News, CNN, ABC News, CBS News, New York Times, Washington Post, Fox News), alternativnih medija (Breitbart, InfoWars, RT, New York Post, The Guardian, HuffPost, The Rebel Media, FiveThirtyEight i drugi manji mediji), društvenih mreža i mjesta za diskusiju (Facebook, Twitter, Reddit /r/the_donald i /r/MrTrump, YouTube/Periscope kanali e-celebrityja i političkih komentatora kao što su Lauren Southern, Gavin McInnes, Mike Cernovich, Stefan Molyneux, Milo Yiannopoulos, Paul Joseph Watson), slikovnih ploča (4chan i ostali chanovi). Student može analizirati detaljnije partikularne događaje ili serije događaja sukladno vlastitim interesima (primjerice, doseg, utjecaj i vijesti iz medija na temu Wikileaksovih objava Podestinih e-mailova, aktivnost Southern Poverty Law Centra, ACLU-a i/ili ADL-a, priču o ruskom utjecaju na izbore, problem lažnih vijesti, aktivnost grupe Correct the Record).

**Literatura:**

1. [Google Trends Indicate Trump Landslide (Regated)](https://regated.com/2016/08/googles-trends-indicate-trump-landslide/)
1. Hine, Gabriel Emile, et al. "Kek, Cucks, and God Emperor Trump: A Measurement Study of 4chan’s Politically Incorrect Forum and Its Effects on the Web." *International Conference on Web and Social Media (ICWSM)*. Association for the Advancement of Artificial Intelligence (AAAI), 2017. Rad dostupan na [stranicama laboratorija](https://iseclab.org/media/uploads/zotero/4chan-ICWSM2017.pdf) i [arXivu](https://arxiv.org/abs/1610.03452)
1. [Trump's shrinking electoral map (Politico)](http://www.politico.com/story/2016/08/donald-trump-shrinking-election-map-227076)
1. [How the Trump Campaign Built an Identity Database and Used Facebook Ads to Win the Election (Joel Winston, posted on Medium)](https://medium.com/startup-grind/how-the-trump-campaign-built-an-identity-database-and-used-facebook-ads-to-win-the-election-4ff7d24269ac)
1. [No, Big Data Didn't Win the U.S. Election (Bloomberg)](https://www.bloomberg.com/view/articles/2016-12-08/no-big-data-didn-t-win-the-u-s-election)
1. [Top 10 Trending Keywords in .Com & .Net Registrations in November (Verisign)](https://blog.verisign.com/domain-names/top-10-trending-keywords-in-com-net-registrations-in-november-2/)
1. [Initial D. Trump](https://youtu.be/b89d1oip7WM)
1. [How Facebook Saw Trump Coming When No One Else Did (Erin Pettigrew, posted on Medium)](https://medium.com/@erinpettigrew/how-facebook-saw-trump-coming-when-no-one-else-did-84cd6b4e0d8e)
1. [Trump will win the election and is more popular than Obama in 2008, AI system finds (CNBC)](https://www.cnbc.com/2016/10/28/donald-trump-will-win-the-election-and-is-more-popular-than-obama-in-2008-ai-system-finds.html)
1. [Trump’s Big Data Mind Explains How He Knew Trump Could Win (Wired)](https://www.wired.com/2016/11/trump-polling-data/)
1. [App maker: Trump will win election (USA Today)](https://www.usatoday.com/story/tech/2016/08/13/app-maker---trump-win-election/88640044/)
1. [Clinton vs. Trump: Predicting The Electoral College (HuffPost)](http://www.huffingtonpost.com/richard-north-patterson/clinton-versus-trump-pred_b_9848032.html)
1. [Donald Trump v Hillary Clinton: This Map Predicts Who Wins (Time)](https://time.com/4508467/election-donald-trump-hillary-clinton-map/)
1. [2016 Election Forecast (FiveThirtyEight)](https://projects.fivethirtyeight.com/2016-election-forecast/)
1. [On A Scale From 1 To 10, How Much Should Democrats Panic? (FiveThirtyEight)](https://fivethirtyeight.com/features/on-a-scale-of-1-to-10-how-much-should-democrats-panic/)
1. [Election Update: Democrats Should Panic ... If The Polls Still Look Like This In A Week (FiveThirtyEight)](https://fivethirtyeight.com/features/election-update-democrats-should-panic-if-the-polls-still-look-like-this-in-a-week/)
1. [Visualizing Clinton, Podesta, and the DNC's Wikileaks E-mail Networks](https://clinton.media.mit.edu/)
1. Zannettou, Savvas, et al. "The Web Centipede: Understanding How Web Communities Influence Each Other Through the Lens of Mainstream and Alternative News Sources." *arXiv preprint arXiv:1705.06947* (2017). Rad dostupan na [arXivu](https://arxiv.org/pdf/1705.06947).

### Usporedba Khronos Vulkan i OpenGL API-ja (Comparison of Khronos Vulkan and OpenGL APIs) {[PPHS](nastava/kolegiji/PPHS.md)} [Darko Kraljević]

**Opis teme:**

OpenGL je višeplatformski API za prikaz 2D i 3D vektorske grafiku. Vulkan je višeplatformski API za 3D grafiku i računanje na grafičkim procesorima. Autor oba API-ja je Khronos grupa. Vulkan je dizajniran specifično za moderne grafičke procesore, namijenjen je kao zamjena za OpenGL, a razvijen je na bazi AMD-ovog API-ja Mantle. Vulkan danas koristi nekolicina igara, od kojih je prva na svijetu bila The Talos Principle hrvatske kompanije Croteam. Zadatak rada je opisati i međusobno usporediti značajke oba API-ja, analizirati koje su značajke API-ja i hardvera učinile OpenGL neprikladnim za moderne grafičke procesore i moderne igre, na koje su načine AMD i NVIDIA zaobilazili ograničenja OpenGL-a, opisati nastanak Mantlea i kasnije Vulkana.

**Literatura:**

1. [OpenGL](https://www.opengl.org/)
1. [Vulkan](https://www.khronos.org/vulkan)
1. [List of games with Vulkan support](https://en.wikipedia.org/wiki/List_of_games_with_Vulkan_support)
1. [List of games with OpenGL support](https://en.wikipedia.org/wiki/List_of_games_with_OpenGL_support)
1. [AMD vs NV Drivers: A Brief History and Understanding Scheduling & CPU Overhead](https://youtu.be/nIoZB-cnjc0)

### Testiranje implementacija OpenGL-a i OpenCL-a alatom Piglit (Testing OpenGL and OpenCL implementations using Piglit) {[PPHS](nastava/kolegiji/PPHS.md)} [Mario Ćuro]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:876890)

**Opis teme:**

Piglit je skup testova za implemetacije OpenGL-a i OpenCL-a neovisan o hardveru, te se koristiti za testiranje grafičkih procesora tvrtki AMD, Intel i NVIDIA. Zadatak rada je prezentirati značajke Piglita i opisati testove koje posjeduje u terminima značajki OpenGL-a/OpenCL-a koje zahtijevaju. Potrebno je izvesti testove na hardveru i driveru po izboru studenta te analizirati rezultate.

**Literatura:**

1. [Piglit](https://piglit.freedesktop.org/)
1. [OpenGL](https://www.opengl.org/)
1. [OpenCL](https://www.khronos.org/opencl/)
1. Dokumentacija upravljačkih programa odabranog hardvera

### Ograničenje pokretanja operacijskih sustava tehnologijom UEFI Secure Boot (Restricting operating system boot using UEFI Secure Boot technology) {[OS1](nastava/kolegiji/OS1.md)} [Kristian Nekić, preneseno iz 2015/2016.]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:915124)

**Opis teme:**

S izlaskom operacijskog sustava Microsoft Windows 8 na desktop i laptop računalima pojavljuje se nova tehnologija Secure Boot. Iako u osnovi osmišljena da spriječi pokretanje zlonamjernog softvera na računalima korisnika, Microsoftova gotovo potpuna kontrola nad potpisivanjem softvera pokrenula je brojne kritike. Cory Doctorow nudi viziju sadašnjosti i budućnosti u kojoj su računala samovozeći automobili, medicinska pomagala i kućanski aparati te koriste neku varijantu Secure Boota kako bi spriječili pokretanje nepotpisanih programa, primjerice vlastitog softvera za samovozeći automobil. Doctorowa brine taj izostanak mogućnosti prilagodbe uređaja čiji ste vlasnik, a sam proces uvođenja tehnologija srodnih Secure Bootu naziva "građanskim ratom protiv računarstva opće namjene".
S izlaskom operacijskog sustava Windows 10 zabrinutost kritičara raste, obzirom da Microsoft više ne traži od proizvođača računala da omogući isključivanje Secure Boota ukoliko korisnik to želi i time ne osigurava slobodu korisnika. Zadatak rada je opisati tehničke i društvene izazove koje ova tehnologija donosi. Ovisno o interesu studenta, rad može biti više usmjeren na tehničke značajke i obraditi komplementarne tehnologije (konkretno, Intel BootGuard) ili pak na društveni kontekst i obraditi društvene posljedice građanskog rata protiv računarstva opće namjene.

**Literatura:**

1. [Secure Boot](https://technet.microsoft.com/library/dn486875.aspx)
1. [UEFI Secure Boot](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface#Secure_boot)
1. [UEFI Secure Boot Criticism](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface#Secure_boot_criticism)
1. [Cory Doctorow: "The Coming Civil War over General-purpose Computing" | Talks at Google](https://youtu.be/gbYXBJOFgeI)
1. [DEF CON 23 - Cory Doctorow - Fighting Back in the War on General Purpose Computers](https://youtu.be/pT6itfUUsoQ)
1. [Windows 10 to make the Secure Boot alt-OS lock out a reality](https://arstechnica.com/information-technology/2015/03/windows-10-to-make-the-secure-boot-alt-os-lock-out-a-reality/)
1. [Secure Boot: the good, the bad, and secureboot.me - Vedran Miletić DORS/CLUC 2015](https://youtu.be/mWJj0Gn7SWc)

### Operacijski sustav CoreOS (CoreOS operating system) {[OS2](nastava/kolegiji/OS2.md)} [Matija Šegović, preneseno iz 2015/2016.]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:958447)

**Opis teme:**

CoreOS je operacijski sustav otvorenog koda zasnovan na jezgri Linux koji omogućuje pokretanje aplikacija korištenjem kontejnera. Iako inicijalno zasnovan na Dockeru, danas koristi vlastito rješenje za kontejnersku virtualizaciju. CoreOS je primarno namijenjen za velike instalacije u cloudima, gdje se ne administriraju individualne virtualne mašine već se njima upravlja sistemski korištenjem specijaliziranih alata. Zadatak rada je opisati CoreOS i kontejnere te usporediti CoreOS-om s tradicionalnim operacijskim sustavima za cloude.

**Literatura:**

1. [CoreOS](https://coreos.com/)
1. [Project Atomic](https://www.projectatomic.io/)
1. Scheepers, Mathijs Jeroen. "Virtualization and containerization of application infrastructure: A comparison." (2014).

## Odabrane teme završnih radova akademske 2015/2016. godine

### Datotečni sustavi ZFS i Btrfs (Btrfs and ZFS filesystems) {[OS1](nastava/kolegiji/OS1.md)} [Ana Tomasović]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:566784)

**Opis teme:**

ZFS je transakcijski datotečni sustav i LVM razvijen od strane Sun Microsystems za Solaris. Prebačen je na FreeBSD kao dio jezgre, a na Linuxu je implementiran u korisničkom prostoru korištenjem mehanizma FUSE. Btrfs je datotečni sustav razvijen od strane Oracle-a za upotrebu na Linux sustavima. Btrfs ima brojne značajke koje postoje u ZFS-u, kao što su kopiranje kod zapisivanja (copy-on-write), snimke (snapshots) i kompresija. Razvoj Btrfs-a započeo je 2007. godine, a prva stabilna verzija je proglašena 2014.
Oba datotečna sustava stavljaju naglasak na skaliranje, te na popravak nedostataka postojećih datotečnih sustava, ali svaki od njih ima jedinstven pristup i koncepte. Pored toga, razlikuju se i u licenci, što onemogućuje da ZFS bude dio jezgre Linuxa. Zadatak rada je opisati oba datotečna sustava, usporediti ih međusobno, te s datotečnom sustavima ext4 (Linux) i UFS2 (FreeBSD).

**Literatura:**

1. [OpenZFS](http://www.open-zfs.org/)
1. [ZFS on Linux](http://zfsonlinux.org/)
1. Bonwick, Jeff, et al. "The zettabyte file system." Proc. of the 2nd Usenix Conference on File and Storage Technologies. 2003.
1. Dawidek, Pawel Jakub, and Marshall Kirk McKusick. "porting the Solaris ZFS file system to the FreeBSD operating system." ; login:: the magazine of USENIX & SAGE 32.3 (2007): 19-24.
1. [btrfs Wiki](https://btrfs.wiki.kernel.org/)
1. Rodeh, Ohad, Josef Bacik, and Chris Mason. "BTRFS: The Linux B-tree filesystem." ACM Transactions on Storage (TOS) 9.3 (2013): 9.
1. Heger, Dominique A.. "Workload Dependent Performance Evaluation of the Btrfs and ZFS Filesystems." CMG (2009).

### Intelektualno vlasništvo nad softverom: licence i patenti (Intellectual property rights in software: licences and patents) {[OS1](nastava/kolegiji/OS1.md)} [Milan Petrović]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:960190)

**Opis teme:**

Softver kao autorsko djelo spada pod zakon o autorskom pravu, a pored toga je u pojedinim državama patentabilan. Zakon o autorskom pravu nad softverom uglavnom nije predmet kritike, ali softverski patenti jesu. Iako originalno zamišljeni da štite inovatora od neovlaštenog kopiranja njegove ideje, i daju inovatoru prednost pred drugima na tržištu, danas se uglavnom koriste za obračunavanje velikih korporacija s novonastalom konkurencijom, za obranu velikih korporacija od podjednako velike konkurencije, te od strane takozvanih "patent trollova" za stjecanje profita na temelju kršenju patenata od strane korporacija koje su se probile na tržištu. Zadatak rada je opisati, kategorizirati i međusobno usporediti softverske licence te dati pregled zakonskog okvira koji se odnosi na softverske patenate u EU i SAD-u. Pored toga, potrebno je analizirati nekoliko aktualnih primjera prema izboru studenta velikih korporacija, "patent trollova" i patenata oko kojih su se vodili sudski procesi.

**Literatura:**

1. [GNU Licenses](https://www.gnu.org/licenses/)
1. [Licences at Choose a License](https://choosealicense.com/licenses/)
1. [Licences and Standards at Open Source Initiative](https://opensource.org/licenses)
1. [Copyleft compliance at Software Freedom Conservancy](https://sfconservancy.org/copyleft-compliance/)
1. [EFF on Patents](https://www.eff.org/patent)
1. [EFF's Patent Busting Project](https://www.eff.org/patent-busting)
1. [Open Invention Network](https://www.openinventionnetwork.com/)
1. [Patent Commons](http://www.patent-commons.org/)
1. [Munich Intellectual Property Law Center](https://www.miplc.de/)
1. [Mises Institute](https://mises.org/)
1. Leifeld, Philip, and Sebastian Haunss. "Political discourse networks and the conflict over software patents in Europe." European Journal of Political Research 51.3 (2012): 382-409.
1. Allison, John R., and Ronald J. Mann. "Disputed Quality of Software Patents, The." Wash. UL Rev. 85 (2007): 297.
1. Garfinkel, Simson L., Richard M. Stallman, and Mitchell Kapor. "Why patents are bad for software." High Noon in the Electronic Frontier: Conceptual Issues in Cyberspace (1996).
1. Rychlicki, Tomasz. "GPLv3: new software licence and new axiology of intellectual property law." European Intellectual Property Review 30.6 (2008): 232.
1. Rosen, Lawrence. Open source licensing. Prentice Hall, 2005.
1. Evans, David S., and Anne Layne-Farrar. "Software patents and open source: the battle over intellectual property rights." Va. JL & Tech. 9 (2004): 1.

### ICANN-ov program novih vršnih imena domena (ICANN's new top level domains program) {[RM2](nastava/kolegiji/RM2.md)} [Iris Babić]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:224719)

**Opis teme:**

U jesen 1984. godine RFC 920 pod naslovom "Domain Requirements" uspostavio je prvih šest vršnih domena: .arpa, .gov, .edu, .com, .mil, .org, i najavio uspostavljanje vršnih domena za svaku pojedinu državu (npr. .de za Njemačku, .ch za Švicarsku, .hr za Hrvatsku). Ubrzo nastaje i .net, a 2000. godine nastaju i .aero, .biz, .coop, .info, .museum, .name i .pro, a nekoliko država, uključujući Kolumbiju, Tokelau, Palau i Kokosove Otoke, predaje svoje vršne domene na upravljanje privatnim kompanijama koje ih zatim prodaju kao alternativu prilično zauzetoj .com domeni.

Međutim, prava promjena događa se tek 2012. kad ICANN otvara mogućnost privatnim kompanijama da zauzmu generičku vršnu domenu. Zadatak rada je dati pregled programa novih vršnih domena, usporediti ga s prethodnim komercijalizacijama državnog domenskog prostora i analizirati njegove tehničke i društvene izazove.

**Literatura:**

1. [ICANN New gTLDs](https://newgtlds.icann.org/)
1. [ICANN Wiki](https://icannwiki.org/)
1. [nTLDStats](https://ntldstats.com/)
1. [Uniregistry](https://uniregistry.link/)
1. [XYZ](https://xyz.xyz/)
1. [Google Registry](https://www.registry.google/)
1. [Famous Four Media](https://www.famousfourmedia.com/)
1. [Minds + Machines](https://www.mindsandmachines.com/)
1. [Donuts](http://www.donuts.domains/)
1. [DotClub](http://nic.club/)
1. [Radix](http://radix.website/)
1. [Rightside](http://rightside.co/)

### Slobodni softver za anonimnu komunikaciju Tor (Tor: free software for anonymous communication) {[RM1](nastava/kolegiji/RM1.md)} [Marjana Bjelić]

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:472725)

**Opis teme:**

Tor (The Onion Router) je slobodan softver za anonimnu komunikaciju putem interneta. Iako se u medijima najčešće spominje kao alat za distribuiranje ilegalnih sadržaja i prodaju kontroliranih supstanci, njegove primjene su puno šire: omogućuje anonimnost korisnika interneta koji žele zaobići cenzuru, skriti svoj identitet od zlostavljača, i novinara koji želi objaviti priču koja sadrži povjerljive informacije i čijom objavom bi ugrozio sebe. Usluge unutar Tora nazivaju se skrivenim uslugama i koriste specifičnu domenu .onion koja nije dostupna van Tora (primjerice, Facebook je dostupan putem adrese facebookcorewwwi.onion). Kako .onion domena nema nema centralni registar, potrebno je znati točnu domenu svake usluge kako bi joj se moglo pristupiti. Zadatak rada je opisati način na koji Tor osigurava anonimnost korisnika i način rada skrivenih usluga.

**Literatura:**

1. [Tor Project](https://www.torproject.org/)
1. [Tor: Hidden Services and Deanonymisation [31c3]](https://archive.org/details/youtube-oZdeRmlj8Gw)
1. [Shari Steele on online anonymity: Tor staff are 'freedom fighters'](https://www.theguardian.com/technology/2016/jan/11/shari-steele-tor-encryption-online-anonymity-censorship)

## Odabrane teme diplomskih radova akademske 2015/2016. godine

### Primjena responsive tehnologije za izradu dokumentacije aplikacije CP2K (Application of responisve technology for creating CP2K documentation) {[DS](nastava/kolegiji/DS.md)} [Kristijan Lenković]

**Mentor:** doc. dr. sc. Božidar Kovačić

**Komentor:** [dr. sc. Vedran Miletić](https://vedran.miletic.net/)

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:212688)

**Opis teme:**

CP2K je popularan slobodan softver otvorenog koda za molekularnu dinamiku. Dokumentacija alata CP2K koristi neresponzivan web dizajn što otežava njezino korištenje na različitim uređajima. Cilj rada je korištenjem responzivnih tehnologija weba predložiti novi dizajn i strukturu dokumentacije.

**Literatura:**

1. [Bootstrap](https://getbootstrap.com/)
1. [CP2K](https://www.cp2k.org/)
1. Dokumentacija [Java Platform SE 7](https://docs.oracle.com/javase/7/docs/api/), primjer dizajna korisničkog sučelja
1. Dokumentacija [Doxygena](https://www.stack.nl/~dimitri/doxygen/), primjer dizajna korisničkog sučelja

### Analiza učinkovitosti paralelnih aplikacija (Performance analysis of parallel applications) {[DS](nastava/kolegiji/DS.md)} [Tomislav Šubić]

**Mentor:** doc. dr. sc. Božidar Kovačić

**Komentor:** [dr. sc. Vedran Miletić](https://vedran.miletic.net/)

[Poveznica na rad u repozitoriju](https://urn.nsk.hr/urn:nbn:hr:195:976368)

**Opis teme:**

Za mjerenje performansi paralelnih aplikacija koriste se specijalizirani alati kao VAMPIR, MPPTEST, Allinea MAP i Valgrind. Cilj rada je opisati jedan ili više navedenih alata po izboru studenta te kroz različite primjere pokazati probleme s performansama koje je moguće takvim alatima prepoznati.

**Literatura:**

1. Gropp, William, and Ewing Lusk. "Reproducible measurements of MPI performance characteristics." European Parallel Virtual Machine/Message Passing Interface Users’ Group Meeting. Springer, Berlin, Heidelberg, 1999. Rad dostupan putem [mrežnih stranica Williama D. Groppa](http://wgropp.cs.illinois.edu/bib/papers/pdata/1999/pvmmpi99/mpptest.pdf)
1. [VAMPIR](https://www.vampir.eu/)
1. [MPPTEST](https://www.mcs.anl.gov/research/projects/mpi/mpptest/)
1. [Allinea MAP](https://www.allinea.com/products/map/)
1. [Valgrind](http://valgrind.org/)
