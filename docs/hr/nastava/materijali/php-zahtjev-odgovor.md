---
author: Vedran Miletić
---

# Obrada HTTP zahtjeva i stvaranje odgovora u jeziku PHP

U ovom dijelu nastavljamo koristiti ugrađeni web poslužitelj interpretera PHP-a i pretpostavljamo da je pokrenut tako da poslužuje sadržaj direktorija `public` u kojem se nalazi datoteka `index.php`.

## Usmjeravanje zahtjeva

### Usmjeravanje po putanji

Promijenimo kod u datoteci `public/index.php` tako da odgovara na zahtjeve upućene na putanju `/grafit` sadržajem `<p>Uvijek me uhvate kad šaram grafite po z`, a na sve ostale zahtjeve sadržajem `<p>Hello, world!</p>`. To možemo izvesti korištenjem uvijek dostupne varijable koja sadrži putanju u HTTP zahtjevu, a ta varijabla je `$_SERVER["REQUEST_URI"]` iz polja `$_SERVER` ([dokumentacija](https://www.php.net/manual/en/reserved.variables.server.php)). Provjeru putanje vršimo na način:

``` php
<?php

if ($_SERVER["REQUEST_URI"] == "/grafit") {
    echo "<p>Uvijek me uhvate kad šaram grafite po z\n";
} else {
    echo "<p>Hello, world!</p>\n";
}
```

Uvjerimo se da naše usmjeravanje zahtjeva upućenih na putanju `/grafit` radi ispravno:

``` shell
$ curl http://localhost:8000/grafit
<p>Uvijek me uhvate kad šaram grafite po z
```

Dodatno možemo postaviti statusni kod odgovora funkcijom `http_response_code()` ([dokumentacija](https://www.php.net/manual/en/function.http-response-code.php)) iz [dijela Network](https://www.php.net/manual/en/book.network.php). Postavimo statusni kod na [206 Partial Content](https://http.cat/206) ([više detalja o HTTP statusnom kodu 206 Partial Content na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/206)) kod odgovora na zahtjeve upućene na putanju `/grafit`:

``` php
<?php

if ($_SERVER["REQUEST_URI"] == "/grafit") {
    http_response_code(206);
    echo "<p>Uvijek me uhvate kad šaram grafite po z\n";
} else {
    echo "<p>Hello, world!</p>\n";
}
```

Uvjerimo se da se statusni kod odgovora promijenio:

``` shell
$ curl -v http://localhost:8000/grafit
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET /grafit HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 206 Partial Content
< Host: localhost:8000
< Date: Mon, 02 Nov 2020 22:28:59 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Content-type: text/html; charset=UTF-8
<
<p>Uvijek me uhvate kad šaram grafite po z
* Closing connection 0
```

Isti kod vidimo na strani poslužitelja:

```
[Mon Nov  2 23:28:59 2020] [::1]:52808 Accepted
[Mon Nov  2 23:28:59 2020] [::1]:52808 [206]: GET /grafit
[Mon Nov  2 23:28:59 2020] [::1]:52808 Closing
```

### Preusmjeravanje zahtjeva na drugu putanju

Zaglavlje odgovora možemo dopuniti dodatnim elementima korištenjem funkcije `header()` ([dokumentacija](https://www.php.net/manual/en/function.header.php)) iz [dijela Network](https://www.php.net/manual/en/book.network.php). Primjerice, možemo svakom korisničkom agentu kod odgovaranja na njegov zahtjev jasno reći koja je PHP-ova maskota dodavanjem vlastitog nestandardnog zaglavlja `PHP-Mascot` na način:

``` php
<?php

header("PHP-Mascot: ElePHPant");
```

Uvjerimo se da je korisnički agent saznao koja je PHP-ova maskota:

``` shell
$ curl -v http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Wed, 30 Dec 2020 00:29:52 GMT
< Connection: close
< X-Powered-By: PHP/8.0.0
< PHP-Mascot: ElePHPant
< Content-type: text/html; charset=UTF-8
<
* Closing connection 0
```

Primijenimo isti pristup na neko od [često korištenih zaglavlja u odgovorima](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers). Primjerice, kod primanja statusnog koda [302 Found](https://http.cat/302) ([više detalja o HTTP statusnom kodu 302 Found na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/302)) klijent očekuje URL na kojem je sadržaj moguće pronaći u zaglavlju `Location` ([više detalja o HTTP zaglavlju Location na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Location)). Recimo da želimo sve zahtjeve na `/grafiti` preusmjeriti korištenjem statusnog koda 302 Found na `/grafit`; to ćemo izvesti postavljanjem statusnog koda 302 u odgovoru i dodavanjem zaglavlja `Location` koje sadrži vrijednost `/grafit`:

``` php
<?php

if ($_SERVER["REQUEST_URI"] == "/grafit") {
    http_response_code(206);
    echo "<p>Uvijek me uhvate kad šaram grafite po z\n";
} else if ($_SERVER["REQUEST_URI"] == "/grafiti") {
    http_response_code(302);
    header("Location: /grafit");
} else {
    echo "<p>Hello, world!</p>\n";
}
```

Uvjerimo se da preusmjeravanje radi korištenjem cURL-ovog parametra `--location`, odnosno `-L` koji će učiniti da cURL ponovi HTTP zahtjev na novoj lokaciji navedenoj u zaglavlju `Location`:

``` shell
$ curl -v -L http://localhost:8000/grafiti
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET /grafiti HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 302 Found
< Host: localhost:8000
< Date: Mon, 02 Nov 2020 22:38:20 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Location: /grafit
< Content-type: text/html; charset=UTF-8
<
* Closing connection 0
* Issue another request to this URL: 'http://localhost:8000/grafit'
* Hostname localhost was found in DNS cache
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#1)
> GET /grafit HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 206 Partial Content
< Host: localhost:8000
< Date: Mon, 02 Nov 2020 22:38:20 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Content-type: text/html; charset=UTF-8
<
<p>Uvijek me uhvate kad šaram grafite po z
* Closing connection 1
```

Na strani poslužitelja poruke su oblika:

```
[Mon Nov  2 23:38:20 2020] [::1]:52822 Accepted
[Mon Nov  2 23:38:20 2020] [::1]:52822 [302]: GET /grafiti
[Mon Nov  2 23:38:20 2020] [::1]:52822 Closing
[Mon Nov  2 23:38:20 2020] [::1]:52824 Accepted
[Mon Nov  2 23:38:20 2020] [::1]:52824 [206]: GET /grafit
[Mon Nov  2 23:38:20 2020] [::1]:52824 Closing
```

Relativne putanje u zaglavlju `Location` se rijetko koriste. Ako želimo u zaglavlje `Location` upisati čitav URL, možemo iskoristiti dodatne varijable iz ranije korištenog polja `$_SERVER`:

- `$_SERVER["SERVER_NAME"]` -- ime poslužitelja (u našem slučaju `localhost`)
- `$_SERVER["SERVER_PORT"]` -- vrata poslužitelja (u našem slučaju `8000`)

pa umjesto koda:

``` php
<?php

header("Location: /grafit");
```

staviti kod:

``` php
<?php

$name = $_SERVER["SERVER_NAME"];
$port = $_SERVER["SERVER_PORT"];
header("Location: http://$name:$port/grafit");
```

Uvjerimo se da sada u zaglavlju `Location` nalazi cjeloviti URL:

``` shell
$ curl -v -L http://localhost:8000/grafiti
(...)
< Location: http://localhost:8000/grafit
< Content-type: text/html; charset=UTF-8
<
* Closing connection 0
* Issue another request to this URL: 'http://localhost:8000/grafit'
(...)
```

Dodatno možemo po potrebi koristiti i sljedeće podatke o web poslužitelju:

- `$_SERVER["SERVER_SOFTWARE"]` -- softver koju poslužitelj koristi (u našem slučaju `PHP 7.4.11 Development Server`)
- `$_SERVER["SERVER_PROTOCOL"]` -- protokol koji poslužitelj koristi (u našem slučaju `HTTP/1.1`)

### Usmjeravanje po metodi

Metodu koju HTTP zahtjev koristi možemo saznati iz varijable `$_SERVER["REQUEST_METHOD"]` i to iskoristiti na način:

``` php
<?php

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    echo "<p>Hello, post-world!</p>\n";
} else {
    echo "<p>Hello, world!</p>\n";
}
```

Uvjerimo se da provjera metode radi:

``` shell
$ curl -X POST http://localhost:8000/
<p>Hello, post-world!</p>
```

Provjere putanje i metode možemo kombinirati korištenjem logičkih operatora negacije (`!`), "i" (`&&`) i "ili" (`||`) ([dokumentacija](https://www.php.net/manual/en/language.operators.logical.php)). Primjerice, možemo u HTTP odgovoru postaviti statusni kod na [400 Bad Request](https://http.cat/400) ([više detalja o HTTP statusnom kodu 400 Bad Request na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/400)) ako se koristi metoda POST na putanji `/grafit`, ali dozvoliti ostale metode na navedenoj putanji. Za to nam treba logički operator "i" (`&&`):

``` php
<?php

if ($_SERVER["REQUEST_METHOD"] == "POST" && $_SERVER["REQUEST_URI"] == "/grafit") {
    http_response_code(400);
    echo "<p>Zahtjev metodom POST na /grafit nije ispravan</p>\n";
} else if ($_SERVER["REQUEST_URI"] == "/grafit") {
    http_response_code(206);
    echo "<p>Uvijek me uhvate kad šaram grafite po z\n";
} else {
    echo "<p>Hello, world!</p>\n";
}
```

Lako ćemo se uvjeriti da se postavljeni statusni kod javlja u HTTP odgovoru:

``` shell
$ curl -v -X POST http://localhost:8000/grafit
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> POST /grafit HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 400 Bad Request
< Host: localhost:8000
< Date: Tue, 03 Nov 2020 07:54:07 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Content-type: text/html; charset=UTF-8
<
<p>Zahtjev metodom POST na /grafit nije ispravan</p>
* Closing connection 0
```

Odgovarajuća poruka na strani poslužitelja je oblika:

```
[Tue Nov  3 08:54:07 2020] [::1]:52918 Accepted
[Tue Nov  3 08:54:07 2020] [::1]:52918 [400]: POST /grafit
[Tue Nov  3 08:54:07 2020] [::1]:52918 Closing
```

## Dohvaćanje i obrada zaglavlja zahtjeva

Korištenjem varijabli iz polja `$_SERVER` možemo dohvatiti i druga zaglavlja HTTP zahtjeva:

- korištenjem varijable `$_SERVER["HTTP_HOST"]` zaglavlje `Host` koje sadrži ime domaćina (u našem slučaju `localhost`); [više detalja o HTTP zaglavlju Host na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Host)
- korištenjem varijable `$_SERVER["HTTP_USER_AGENT"]` zaglavlje `User-Agent` koje sadrži korisnički agent, odnosno ime i verziju web klijenta koji se koristi (u našem slučaju `curl/7.72.0`); [više detalja o HTTP zaglavlju User-Agent na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent)
- korištenjem varijable `$_SERVER["HTTP_ACCEPT"]` zaglavlje `Accept` koje sadrži skup MIME tipova koje klijent prihvaća (u našem slučaju `*/*`, odnosno svi); [više detalja o HTTP zaglavlju Accept na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept)

### Provjera prihvatljivih oblika odgovora

Poslužitelj može biti postavljen da podatke o studentu šalje u različitom obliku ovisno o navedenoj vrijednosti u zaglavlju `Accept` HTTP zahtjeva. Primjerice, uzmimo da poslužitelj koji šalje podatke o studentu (ime, prezime i studijska grupa) omogućuje klijentu da navede kao prihvatljiv oblik:

- JSON (poznati format za razmjenu podataka među aplikacijama; [službena stranica](https://www.json.org/), [više detalja o JSON-u na MDN-u](https://developer.mozilla.org/en-US/docs/Glossary/JSON)) koji ima MIME tip `application/json`,
- HTML koji ima MIME tip `text/html` i
- obični tekst koji ima MIME tip `text/plain`.

MIME tipova koji se koriste u praksi ima još, a [popis često korištenih moguće je pronaći na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types)). Od poslužitelja se ne očekuje da može vratiti odgovor koji je u svakom od formata koje oni reprezentiraju pa je, u slučaju da zaglavlje `Accept` sadrži nepodržan MIME tip, potrebno postaviti statusni kod na [406 Not Acceptable](https://http.cat/406) ( [više detalja o HTTP statusnom kodu 406 Not Acceptable na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/406)).

``` php
<?php

if ($_SERVER["HTTP_ACCEPT"] == "application/json") {
    header("Content-type: application/json");
    echo '{"ime":"Ivan","prezime":"Horvat","studij":"Informatika"}';
} else if ($_SERVER["HTTP_ACCEPT"] == "text/html") {
    echo "<p>Ivan Horvat (Informatika)</p>\n";
} else if ($_SERVER["HTTP_ACCEPT"] == "text/plain") {
    header("Content-type: text/plain");
    echo "Ivan,Horvat,Informatika\n";
} else {
    http_response_code(406);
    echo "<p>Nejasan zahtjev. Podržani MIME tipovi su application/json, text/html i text/plain.</p>\n";
}
```

Uočimo da kod JSON-a za imenovanje polja i navođenje njihovih vrijednosti koristimo dvostruke navodnike pa za omeđivanje znakovnog niza kod ispisa naredbom `echo` koristimo jednostruke.

Zatražimo cURL-om prvo JSON navođenjem odgovarajuće vrijednosti zaglavlja `Accept` parametrom `--header`, odnosno `-H`:

``` shell
$ curl -v -H "Accept: application/json" http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: application/json
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Fri, 13 Nov 2020 13:50:52 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Content-type: application/json
<
* Closing connection 0
{"ime:"Ivan","prezime":"Horvat","studij":"Informatika"}
```

Zatim zatražimo HTML pa čisti tekst:

``` shell
$ curl -v -H "Accept: text/html" http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: text/html
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Fri, 13 Nov 2020 13:51:03 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Content-type: text/html; charset=UTF-8
<
<p>Ivan Horvat (Informatika)</p>
* Closing connection 0

$ curl -v -H "Accept: text/plain" http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: text/plain
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Fri, 13 Nov 2020 13:51:14 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Content-type: text/plain
<
Ivan,Horvat,Informatika
* Closing connection 0
```

Uočimo da smo u sva tri slučaja dobili očekivane odgovore. Provjerimo da u slučaju da ne navedemo neku od te tri vrijednosti zaglavlja `Accept` u zahtjevu, poslužitelj odgovara porukom o pogrešci:

``` shell
$ curl -v http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 406 Not Acceptable
< Host: localhost:8000
< Date: Fri, 13 Nov 2020 13:51:24 GMT
< Connection: close
< X-Powered-By: PHP/7.4.11
< Content-type: text/html; charset=UTF-8
<
<p>Nejasan zahtjev. Podržani MIME tipovi su application/json, text/html i text/plain.</p>
* Closing connection 0
```

### Provjera ostalih zaglavlja

Osim spomenutih zaglavlja HTTP zahtjeva, možemo obrađivati i sva druga. Sva zaglavlja koja zahtjev sadrži dohvatit ćemo funkcijom `getallheaders()` ([dokumentacija](https://www.php.net/manual/en/function.getallheaders.php)), a zatim svako pojedino zaglavlje dohvaćamo kao i ranije.

Primjerice, u zahtjevu možemo dodati zaglavlje `Najjaci-Fakultet` koje nije standardizirano, ali se nama sviđa da ima vrijednost `Odjel za informatiku`. Na poslužitelju možemo funkcijom `array_key_exists()` ([dokumentacija](https://www.php.net/manual/en/function.array-key-exists.php)) provjeriti je li zaglavlje postavljeno pa onda ima li odgovarajuću vrijednost na način:

``` php
<?php

$request_headers = getallheaders();
if (array_key_exists("Najjaci-Fakultet", $request_headers) && $request_headers["Najjaci-Fakultet"] == "Odjel za informatiku") {
    echo "<p>Dobrodošli, kolega.</p>\n";
} else {
    http_response_code(418);
    echo "<p>Na ovoj stranici nema ništa.</p>\n";
}
```

U slučaju da provjera autorizacije ne prođe uspješno, odgovor ima statusni kod [418 I'm a teapot](https://http.cat/418) koji je šaljiv statusni kod proizašao iz prvoaprilskih [RFC-a 2324 pod naslovom Hyper Text Coffee Pot Control Protocol (HTCPCP/1.0)](https://tools.ietf.org/html/rfc2324) i [RFC-a 7168 pod naslovom The Hyper Text Coffee Pot Control Protocol for Tea Efflux Appliances (HTCPCP-TEA)](https://tools.ietf.org/html/rfc7168), a u praksi se nekad koristi za odgovor na zahtjeve kojima se poslužitelj ne želi baviti ([više detalja o HTTP statusnom kodu 418 I'm a teapot na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/418)).

Uvjerimo se da ova provjera zaglavlja radi ispravno:

``` shell
$ curl -v -H "Najjaci-Fakultet: MIT" http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
> Najjaci-Fakultet: MIT
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 418 I'm a teapot
< Host: localhost:8000
< Date: Wed, 30 Dec 2020 00:56:39 GMT
< Connection: close
< X-Powered-By: PHP/8.0.0
< Content-type: text/html; charset=UTF-8
<
<p>Na ovoj stranici nema ništa.</p>
* Closing connection 0

$ curl -v -H "Najjaci-Fakultet: Odjel za informatiku" http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> GET / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
> Najjaci-Fakultet: Odjel za informatiku
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Wed, 30 Dec 2020 00:57:11 GMT
< Connection: close
< X-Powered-By: PHP/8.0.0
< Content-type: text/html; charset=UTF-8
<
<p>Dobrodošli, kolega.</p>
* Closing connection 0
```

## Specifičnosti metode GET

Varijable navedene kod slanja zahtjeva HTTP metodom GET možemo dohvatiti putem varijable `$_GET` ([dokumentacija](https://www.php.net/manual/en/reserved.variables.get.php)). Primjerice, recimo da skripta index.php očekuje ime i prezime na način da dajete zatjeve na putanju `/profil?ime=Ivan&prezime=Horvat`. Možemo se ponadati da bismo obradu takvih zahtjeva mogli izvesti kodom:

``` php
<?php

if ($_SERVER["REQUEST_METHOD"] == "GET" && $_SERVER["REQUEST_URI"] == "/profil") {
    $ime = $_GET["ime"];
    $prezime = $_GET["prezime"];
    echo "<p>Vi ste $ime $prezime.</p>\n";
}
```

Međutim, `$_SERVER["REQUEST_URI"]` će uključivati čitavu putanju u kojoj se nalazi i upit (u našem slučaju `?ime=Ivan&prezime=Horvat`) pa nam kod neće raditi kako očekujemo. Putanja bez upita je sadržana u varijabli `$_SERVER["PATH_INFO"]` pa je ispravan kod oblika:

``` php
<?php

if ($_SERVER["REQUEST_METHOD"] == "GET" && $_SERVER["PATH_INFO"] == "/profil") {
    $ime = $_GET["ime"];
    $prezime = $_GET["prezime"];
    echo "<p>Vi ste $ime $prezime.</p>\n";
}
```

Kako ljuska tretira `?` i `&` kao posebne znakove, URL je kod izvođenja zahtjeva potrebno staviti pod navodnike na način:

``` shell
$ curl -v "http://localhost:8000/profil?ime=Ivan&prezime=Horvat"
*   Trying 127.0.0.1:8000...
* TCP_NODELAY set
* Connected to localhost (127.0.0.1) port 8000 (#0)
> GET /profil?ime=Ivan&prezime=Horvat HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.68.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Tue, 03 Nov 2020 12:55:51 GMT
< Connection: close
< X-Powered-By: PHP/7.4.3
< Content-type: text/html; charset=UTF-8
<
<p>Vi ste Ivan Horvat.</p>
* Closing connection 0
```

## Specifičnosti metode POST

Podatke možemo primati i metodom POST i dohvatiti ih putem varijable `$_POST` ([dokumentacija](https://www.php.net/manual/en/reserved.variables.post.php)) na način:

``` php
<?php

if ($_SERVER["REQUEST_METHOD"] == "POST" && $_SERVER["REQUEST_URI"] == "/profil") {
    $ime = $_POST["ime"];
    $prezime = $_POST["prezime"];
    echo "<p>Vi ste $ime $prezime.</p>\n";
}
```

Ovdje putanja ne sadrži upit pa nam `$_SERVER["REQUEST_URI"]` ostaje `/profil` pa ne moramo koristiti `$_SERVER["PATH_INFO"]`. Zahtjev izvodimo na način:

``` shell
$ curl -v -X POST -d "ime=Ivan" -d "prezime=Horvat" http://localhost:8000/profil
Note: Unnecessary use of -X or --request, POST is already inferred.
*   Trying 127.0.0.1:8000...
* TCP_NODELAY set
* Connected to localhost (127.0.0.1) port 8000 (#0)
> POST /profil HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.68.0
> Accept: */*
> Content-Length: 23
> Content-Type: application/x-www-form-urlencoded
>
* upload completely sent off: 23 out of 23 bytes
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Tue, 03 Nov 2020 13:02:47 GMT
< Connection: close
< X-Powered-By: PHP/7.4.3
< Content-type: text/html; charset=UTF-8
<
<p>Vi ste Ivan Horvat.</p>
* Closing connection 0
```

Uočimo također kako je sada po prvi put postavljeno HTTP zaglavlje `Content-Type` i u zahtjevu te ima vrijednost `application/x-www-form-urlencoded`, što je MIME tip podataka poslanih web formom. Drugim riječima, ovdje cURL-om šaljemo podatke isto kao što bismo na web sjedištu nekog sustava za učenje slali nakon popunjavanja podataka na svom profilu i pristiska na gumb za spremanje.

## Provjera poslanih varijabli u zahtjevima metodom GET i POST

Dodatno možemo provjeriti jesu li u zahtjevu poslane varijable koje želimo iskoristiti, što ćemo izvesti funkcijom `isset()` ([dokumentacija](https://www.php.net/manual/en/function.isset.php)). Zatim ćemo formirati adekvatan odgovor u slučaju da varijable nisu postavljene; primjerice, postavit ćemo već ranije korišteni statusni kod 400 Bad Request i poslati pripadnu poruku:

``` php
<?php

if ($_SERVER["REQUEST_URI"] == "/profil" && $_SERVER["REQUEST_METHOD"] == "POST") {
    $ime = $_POST["ime"];
    $prezime = $_POST["prezime"];
    if (isset($ime) && isset($prezime)) {
        echo "<p>Vi ste $ime $prezime.</p>\n";
    } else {
        http_response_code(400);
        echo "<p>Niste poslali ime ili prezime.</p>\n";
    }
}
```

Uvjerimo se da smo uhvatili sve situacije kad u zahtjevu nedostaje neka od varijabli:

``` shell
$ curl -X POST http://localhost:8000/profil
<p>Niste poslali ime ili prezime.</p>
$ curl -X POST -d "ime=Ivan" http://localhost:8000/profil
<p>Niste poslali ime ili prezime.</p>
$ curl -X POST -d "prezime=Horvat" http://localhost:8000/profil
<p>Niste poslali ime ili prezime.</p>
```

Na analogan način provjerili bismo poslane varijable u slučaju kad se koristi metoda GET.

## Specifičnosti metode HEAD

Zahtjev HTTP metodom HEAD učinit će da poslužitelj vrati odgovor koji ima samo zaglavlja, odnosno nema tijelo ([više detalja o HTTP metodi HEAD na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD)). Uzmimo da je datoteka `index.php` sadržaja:

``` php
<?php

if ($_SERVER["REQUEST_METHOD"] == "HEAD") {
    header("Moj-Head: ne prodajemo skije i štapove");
    echo "<p>Ovaj dio neće biti sadržan u odgovoru</p>\n";
}
```

Napravimo HTTP zahtjev HEAD cURL-om da se uvjerimo da naš poslužitelj radi kako treba:

``` shell
$ curl -v -X HEAD http://localhost:8000/
Warning: Setting custom HTTP method to HEAD with -X/--request may not work the
Warning: way you want. Consider using -I/--head instead.
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> HEAD / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Host: localhost:8000
< Date: Wed, 30 Dec 2020 18:41:39 GMT
< Connection: close
< X-Powered-By: PHP/8.0.0
< Moj-Head: ne prodajemo skije i štapove
< Content-type: text/html; charset=UTF-8
<
* Closing connection 0

$ curl -I http://localhost:8000/
HTTP/1.1 200 OK
Host: localhost:8000
Date: Wed, 30 Dec 2020 18:41:43 GMT
Connection: close
X-Powered-By: PHP/8.0.0
Moj-Head: ne prodajemo skije i štapove
Content-type: text/html; charset=UTF-8
```

Vidimo zaglavlja među kojima je i naše prilagođeno zaglavlje `Moj-Head`, a tijelo je prazno kao što smo i očekivali.

## Specifičnosti metode CONNECT

Zahtjev HTTP metodom CONNECT izvršit će samo spajanje na poslužitelj i pritom ne očekuje nikakav odgovor ([više detalja o HTTP metodi CONNECT na MDN-u](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT)). Zbog toga HTTP poslužitelji uglavnom uopće ne implementiraju metodu CONNECT, što je u skladu sa standardom ([odjeljak 4.3.6. pod naslovom CONNECT u RFC-u 7231 pod naslovom Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content](https://tools.ietf.org/html/rfc7231#section-4.3.6)). Bez obzira kakav kod imali u datoteci `index.php`, odgovor na zahtjev tom metodom bit će prazan:

``` shell
$ curl -v -X CONNECT http://localhost:8000/
*   Trying ::1:8000...
* Connected to localhost (::1) port 8000 (#0)
> CONNECT / HTTP/1.1
> Host: localhost:8000
> User-Agent: curl/7.72.0
> Accept: */*
>
* Empty reply from server
* Connection #0 to host localhost left intact
curl: (52) Empty reply from server
```

Kako metoda CONNECT nije implementirana, na strani poslužitelja imamo poruku o neispravnom HTTP zahtjevu:

```
[Wed Dec 30 19:44:37 2020] [::1]:52244 Accepted
[Wed Dec 30 19:44:37 2020] [::1]:52244 Invalid request (Malformed HTTP request)
[Wed Dec 30 19:44:37 2020] [::1]:52244 Closing
```
