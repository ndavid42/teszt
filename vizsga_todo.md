1) gmail login (pw: ch....)
2) github login (w/ gmail) [or pw: ch.....]
3) vscode login (w/ github)
4) vscode sync
---



background-image: linear-gradient(black, gray, black);

#          BOOTSTRAP
```
  xs   sm   md   lg    xl    xxl
0   576  768  992  1200  1400

bármi elem méret:
.[w/h]-[25/50/75/100] - szélesség, magasság %

.container  -  fő divre érdemes rátenni (max széles minden nézeten, de erre is rátehetők a -xs/sm...stb dolgok)
.container-[xs/sm/md/lg/xl/xxl/fluid  -  fluid=sima .container, azaz 100% mindenhol
.row  -  elemek egy sorba helyezése
.col  -  oszlopok a soron belül
.col-[1/2/3/4/6/12]  -  mennyi szélességet foglaljon el az oszlop (a 12-ből)
.col-[xs/sm/md/lg/xl]-[1/2/3/4/6/12]  -  különböző nézetekben mennyit foglaljon el (reszpó)

szöveg igazítás vizszintesen
.text-start    .text-center    .text.end

szöveg átalakítás
.text-lowercase  .TEXT-UPPERCASE  .Text-Capitalize

betűvastagság (FontWeight)
.fw-light  .fw-normal  .fw-bold

betűstílus (Font STyle)
.fst-italic  .fst-normal

szövegszínek
.text-primary  .text-secondary  .text-success  .text-danger  .text-warning  .text-info  .text-light  .text-dark  .text-muted
(kék)          (szürke)        (zöld)          (piros)       (sárga)        (v.kék)    (világos)     (sötét)     (halvány)

szöveg deko
.text-decoration-underline  .text-decoration-line-through  .text-decoration-none
```
---
Margin/Padding
```
.m[t/b/l/r/x/y/nincs]-[0/1/2/3/4/5/auto]    pl.: .mb-3  .mx-auto
.p[t/b/l/r/x/y/nincs]-[0/1/2/3/4/5]    pl.: .p-3  .px-5
```
---------
TABLE
```
<caption><thead><tbody><tfoot>
.table  - alap tábla
.table-striped  -   csíkos
.table-[bordered/borderless]  -  van border / nincs border
.table-hover  -  hoverre sor kiemelés
.table-sm  -  alacsonyabb sorok

  tábla/sor, cella, fejléc színek: (halványabb színek)
.table-[primary/secondary/success/danger/warning/info/light/dark]

  cella színek: (erősebb színek)
  .bg-[primary...dark]
  
reszponzív:
.table-responsive-[sm/md/lg/xl]

egyéb:
.caption-top  -  caption felül lesz
.align-middle  - vertical center
.text-center  -  horizontal center
```
---
IMG
```
.img-fluid  -  kép szélessége 100%, arányos
.img-thumbnail  -  vékony lekerekített szegély
.rounded[-top/-bottom/-left/-right]  -  lekerekítés
.rounded-circle - körig/oválisig lekerekítés

kép igazítás:
.float-[start/end]
.clearfix  -  lebegtetett képek után törjön a tartalom

kép árnyék:
  .shadow-[ / sm / lg]  -  árnyék alap / kicsi / nagy

.placeholder  -  placeholder kép
```

-----------
BUTTON
```
.btn  -  alap button
.btn-[primary...dark]  -   színes gom
.btn-outline-[primary...dark]  -  körvonalas gomb
disabled  -  inaktív gomb (nem class! hanem egy boolean érték (= disabled=true)
.btn-[sm/lg]  -  kicsi/nagy
```
------
FORM
```html
  <h1>Validálási beállítások, kinézetének beállítása</h1>
  <form action="" style="width:500px; margin:0px auto;" class="needs-validation" novalidate>
        <!--[needs-validation] bekapcsolja a validálási funkciót az adott formnál-->
        <!--[novalidate] érték pedig kikapcsolja a böngésző alapértelmezett validálását, engedi a bootstrap validációt használni!-->
        <div class="row">
            <div class="col">
                <!--[is-invalid] tulajdonsággal alapértelmezetten az invalid kinézetet adhatjuk a form elemünknek-->
                <div class="form-group">
                    <label for="vnev">Vezeték név:</label>
                    <input type="text" name="vnev" id="vnev" class="form-control" required>
                    <!--[is-invalid]-ot a classon belül kell megadni -->
                    <div class="invalid-feedback">Hibás</div>
                </div>
            </div>
            <div class="col">
                <!--[is-valid] tulajdonsággal alapértelmezetten a valid kinézetet adhatjuk a form elemünknek-->
                <div class="form-group">
                    <label for="knev">Kereszt név:</label>
                    <input type="text" name="knev" id="knev" class="form-control" required>
                    <!--[is-valid]-ot a classon belül kell megadni -->
                    <div class="valid-feedback">Megfelel</div>
                </div>
            </div>
        </div>
        <div class="form-group">
            <label for="fnev">Felhasználói név:</label>
            <input type="text" name="fnev" id="fnev" class="form-control" required>
            <small class="form-text text-muted">
                <!--A small tag-ekre beállított szöveggel, alsó feliratot állíthatunk be a form elemnek-->
                <!--Ezt az elemet a [form-text] tulajdonsággal formázza a bootstrap a megfelelőre-->
                <!--A [text-muted] tulajdonság pedig az alapéretelmezetten fekete betűszínt cseréli szürkésre!-->
                Megjegyzés szöveg, ami a form elem alatt jelenik meg.
            </small>
            <div class="invalid-feedback">Hibás</div>
            <div class="valid-feedback">Megfelel</div>
        </div>
        <div class="form-group">
            <label for="jsz">Jelszó:</label>
            <input type="password" name="jsz" id="jsz" class="form-control" required>
        </div>
        <div class="form-group">
            <label for="tanf">Tanfolyam típusa</label>
            <select name="tanf" id="tanf" class="form-control"">
            <option>Webfejlesztő</option>
            <option>Junior frontend fejlesztő</option>
        </select>
        </div>
        <div class=" form-check">
                <label for="check" class="form-check-label">Felhasználói feltételek elfogadása</label>
                <input type="checkbox" name="check" id="check" class="form-check-input" required>
        </div>
        <button type="submit">Küldés</button>
        <!--Ha rajta hagyjuk a submit tulajdonságot, a gombon is végrehajtódik a bootstrap validáció-->
        <!--A háttérben futó JS kódot a fájl végében találod meg-->

    </form>

 <h1>Lebegő címkék</h1>
    <form action="" style="width:500px; margin:0px auto;" class="needs-validation" novalidate>
        <div class="row">
            <div class="col">
                <!--A "lebegő címkékhez 3 dologra van szükségünk bootstrapnél"-->
                <!--1. a [form-floating] osztály [form-group] helyett-->
                <!--Arra hogy a mező rendelkezzen placeholder tulajdonsággal-->
                <!--Illetve hogy a címkéket(label) ezúttal a mező után helyezzük el és ne elé-->
                <!--Ha ezek közül a követelmények közül bármelyik is hiányzik, nem fog működni a lebegtetés-->
                <div class="form-floating">
                    <!--Az osztály az első szügséges összevető amivel jelezzük hogy itt most lebegtetni szeretnénk-->
                    <input type="text" name="vnev" id="vnev" class="form-control" placeholder="Vezeték neved" required>
                    <!--A működéshez szüksége a placeholder elemet is elhelyezni a form elemben-->
                    <label for="vnev">Vezeték név:</label>
                    <!--A címkét a mező után kell elhelyezni a helyes működéshez-->
                    <div class="invalid-feedback">Hibás</div>
                </div>
            </div>
            <div class="col">
                <div class="form-floating">
                    <!--Az osztály az első szügséges összevető amivel jelezzük hogy itt most lebegtetni szeretnénk-->

                    <input type="text" name="knev" id="knev" class="form-control" placeholder="Keresztneved" required>
                    <!--A működéshez szüksége a placeholder elemet is elhelyezni a form elemben-->
                    <label for="knev">Kereszt név:</label>
                    <!--A címkét a mező után kell elhelyezni a helyes működéshez-->
                    <div class="valid-feedback">Megfelel</div>
                </div>
            </div>
        </div>
        <div class="form-floating">
            <!--Az osztály az első szügséges összevető amivel jelezzük hogy itt most lebegtetni szeretnénk-->
            <input type="text" name="fnev" id="fnev" class="form-control" placeholder="Felhasználói név" required>
            <!--A működéshez szüksége a placeholder elemet is elhelyezni a form elemben-->
            <label for="fnev">Felhasználói név:</label>
            <!--A címkét a mező után kell elhelyezni a helyes működéshez-->
            <small class="form-text text-muted">
                Megjegyzés szöveg, ami a form elem alatt jelenik meg.
            </small>
            <div class="invalid-feedback">Hibás</div>
            <div class="valid-feedback">Megfelel</div>
        </div>
        <div class="form-floating">
            <!--Az osztály az első szügséges összevető amivel jelezzük hogy itt most lebegtetni szeretnénk-->
            <input type="password" name="jsz" id="jsz" class="form-control" placeholder="Jelszó" required>
            <!--A működéshez szüksége a placeholder elemet is elhelyezni a form elemben-->
            <label for="jsz">Jelszó:</label>
        </div>
        <div class="form-floating">
            <!--Az osztály az első szügséges összevető amivel jelezzük hogy itt most lebegtetni szeretnénk-->
            <select class="form-select" name="tanf" id="tanf" class="form-control"
                aria-label="Floating label select example">
                <option>Webfejlesztő</option>
                <option>Junior frontend fejlesztő</option>
            </select>
            <label for="tanf">Tanfolyam típusa</label>
            <!--A címkét a mező után kell elhelyezni a helyes működéshez-->
        </div>
        <button type="submit">Küldés</button>

    </form>
```
===
              JAVASCRIPT
===
```
var  -  global scope (nem redeklarálható, pláne mert mindenhol elérhető, blokkon belül is)
let  -  block scope (redeklarálható más blokkon belül, mivel csak oda terjed ki a hatása)
const   -  konstans (nem redeklarálható, hiszen konstans)
```
szövegbe ágyazott változó: console.log(`balra dőlő aposztrófok között ${valtozoNeve} ez egy változó`);

-------
loop:
```javascript
for(let i = 0; i < 5; i++) {
  console.log(i);
}

let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}

let i = 0;
do {
  console.log(i)
  i++;
} while (i < 5)
```
-------
array:
```javascript
const cars = ["Saab", "Fiat", "BMW"];
const cars = new Array("Saab", "Fiat", "BMW");

numeric sort:
const points = [40, 100, 1, 5];
points.sort()function(a, b){return a - b};
```
```javacript
új elem a tömb végére: cars.push("Audi");      // eredmény nincs    illetve["Saab", "Fiat", "BMW", "Audi"]
utolsó elem kiszedés a tömbből: cars.pop();    // eredmény: "Audi"  illetve ["Saab", "Fiat", "BMW"]
első elem kiszedés a tömbből: cars.shift();    // eredmény: "Saab"  illetve ["Fiat", "BMW"]
új elem a tömb elejére: cars.unshift("Lada");  // eredmény: length  illetve ["Lada"; "Saab", "Fiat", "BMW"]
```

------
object:
```javascript
const car = {
  type: "Fiat", 
  model: "500", 
  weight: 850, 
  isRunning: false,
  car_start: function() {
    if (!isRunning) {
      this.isRunning = true;
    }
  }
}
car.car_start(); //az isRunning true lesz
```
VAGY:
```javascript
const car = new Object({type: "Fiat", model: "500", weight: 850, isRunning: true});

console.log(car.type) --> "Fiat"
```
constructor:
```javascript
function Person(first, last, age, active) {
  this.firstName = first;
  this.lastName = last;
  this.ageYears = age;
  this.isActive = active;

  this getFullName = function() {
    return this.firstName + " " + this.lastName;
  }
}

const worker1 = new Person("John", "Doe", 42, true);
const worker2 = new Person("Lara", "Croft", 30, false);

worker2.isActive = true;
console.log(worker2.getFullName());
```
-----
arrow:
```javascript
myFunction = (a, b) => a * b;
let result = myFunction(4, 5);
```
eredmény 20 lesz


------
class:
js classes are templates for js objects
```javascript
class ClassName {
  constructor(name, year, working) {
    this.name = name;
    this.year = year;
    this.isWorking = working;
  }

  status() {
    let status = "";
    if (isWorking) {
      return "yes";
    } else {
      return "no";
    }
  }
}

const car1 = new ClassName("Ford", 2014, true);
const car2 = new ClassName("Audi", 2020, false);

console.log("working? " + car2.status());
```


===
#TYPESCRIPT
===

=js szuperszett
transpiler
típusbiztonság, erősen típusos
```
-----
telepítés: https://nodejs.org/en/
teszt, h működik-e, terminálban (vs code legyen újraindítva): node -v
teszt, h működik-e az NPM: npm -v
  ha hiba!: powershell: Get-ExecutionPolicy --> ha restricted, akkor: Set-ExecutionPolicy RemoteSigned

typescript telepítés: npm install -g typescript
teszt, h felment-e: tsc -v

.ts fájl lefordítása: tsc tesztfile.ts
.ts fájl lefordítása folyamatos figyeléssel (watch): tsc tesztfile.ts -w

(jquery használata ts-sel: npm i @types/jquery --save-dev
aztán hivatkozás a jquery file-ban a saját js hivatkozások előtt)

TS tesztelő felület: https://www.typescriptlang.org/play/

-----
```

változó név: nem lehet benne SPACE. nem kezdődhet számmal. kezdődhet _ vagy $ karakterrel, ezek lehetnek máshol is
```typecript
let valtozoNev: string = "érték";
let valtozoMasikNev: number = 2;
let valtozoHarmadikNev: boolean = false;
let valtozoNegyedikNev: any = "akármi lehet, mint a js-ben";
let valtozoOtodikNev: unknown = "dettó, csak ez kényszerít a használat előtti típusellenőrzésre"; (akkor jó, ha nem tudjuk biztosan, h milyen adat érkezik, de kell a típusvédelem) typeof vagy as string/as number konvertálás utána használható
let email: string | null = null; //jelenleg nincs érték, adat egyelőre nincs betöltve

let valasz: string | number; //union típus, elfogadja mindkettőt. használat előtt typeof típusellenőrzés!)
```

----
tömbök:
```typecript
let szovegesTomb: string[] = ["egy", "kettő", "három"];
let szamTomb. Array<number> = [512, 64, 42, 51];
```
-----
függvények:

nincs visszatérési érték:      function funkcioNeve(): void {}
return nélkül, paraméterrel:   function funkcioNeve(nev: string): void {}
csak return van:               function funkcioNeve(): number { ... return 42; }
mindkettő van:                 function funkcioNeve(darab: number, nev: string): boolean { ... return true; }
tuple returnnal:               function funkcioNeve(nev: string): [number, string] { ... return [42, "szoveg"]; }

opcionális paraméter:          function funkcioNeve(nev?: string): void { //nem kötelező megadni. ha nincs érték, undefined lesz, de nem lesz hiba }
param default értékkel:        function funkcioNeve(nev: string = "John Doe"): void { //nem kötelező megadni, lesz alapérték}
soha nincs visszatérés:        function funkcioNeve(nev: string): never { throw new Error(msg); }

arrow:
```typecript
const osszead = (a: number, b: number): number => { return a+b; };
```
----
tuple: rögzített elemszámú és típuskiosztású tömb
```typecript
let user: [string, number] = ["anna", 23];
let data: [string, number?];  //a number az opcionális
let data: [string | number, boolean]; //többféle típus egy indexen
```
-----
enum: felsorolás, előre meghatározott név-érték párok. van numeric és string enum

>numeric enum:
```typecript
enum Status {
  OK,
  Warning,
  Error
}
console.log(Status.Warning); //eredménye: 1
console.log(Status[1]);   //eredménye: "Warning"
```
>string enum: (ha fontosabb az olvashatóság
```typecript
enum UserTipus {
  Admin = "admin",
  User = "user",
  Guest = "guest"
}
let alap_felhasznalo: UserTipus = UserTipus.User; 
console.log(alap_felhasznalo); // "user"

let rendszergazda: UserTipus = UserTipus.Admin; 
console.log(rendszergazda); // "admin"
```
---
interface: minta (szabályrendszer), ami meghatározza az objektum szerkezetét (milyen mezők, azok milyen tipusúak, milyen metódusok tartoznak hozzá)
```typecript
interface Dolgozo { 
  nev: string; 
  eletkor: number; 
  aktiv?: boolean;  //opcionális mező
  readonly id: number; //csak olvasható
  getNev(): string;
} 

var interfaceObjektum1: Dolgozo = {nev: "Teszt Elek", eletkor: 30, aktiv: true};
console.log(interfaceObjektum1.nev);
```
interface és osztály:
```typecript
class HR_munkatars implements Dolgozo {
  nev: string;
  eletkor: number;
  aktiv: boolean;
  constructor(nevInput: string, eletkorInput: number, aktivInput: boolean) {
    this.nev = nevInput;
    this.eletkor = eletkorInput;
    this.aktiv = aktivInput;
  }
  getNev() {
    return this.nev;
  }
}
```

----
literál: közvetlenül megadott konkrét érték.
pl. string literál:
let szoveg1: string = "egykéthá";
let szam: number = 42;

literal type:
let irany: "bal" | "jobb" | "előre" | "hátra"    //csak ezeket az értékeket veheti fel


----
type alias. pl.:
type Nev = string;
let nev: Nev = "Anna";  //tehát nem :string lesz, hanem :Nev a típus

===
## DOM
Típusmegadás:

-generikus
const inputElem = document.querySelector<HTMLInputElement>('#szamInput');     - iztonságosabb és ajánlottabb módszer (generic type annotation)

-típus-kényszerítés
const inputElem = document.querySelector("#szamInput") as HTMLInputElement;     - nincs ellenőrzés, nem garantált (type cast/assertion)

HTML elem TypeScript típusa
```
<input>      HTMLInputElement
<form>       HTMLFormElement
<select>     HTMLSelectElement
<textarea>   HTMLTextAreaElement
<button>     HTMLButtonElement
<a> (link)   HTMLAnchorElement
<img>        HTMLImageElement
<video>      HTMLVideoElement
<audio>      HTMLAudioElement
<label>      HTMLLabelElement
<table>      HTMLTableElement
<tr>         HTMLTableRowElement
<td> / <th>  HTMLTableCellElement
<div>        HTMLDivElement
<span>       HTMLSpanElement
<canvas>     HTMLCanvasElement
<ul> / <ol>  HTMLUListElement / HTMLOListElement
<li>         HTMLLIElemen
```

----
```javascript
gomb?.addEventListener('click', () => {...});    //csak akkor hívja meg, ha a gomb nem null v undefined. nem garantálja h az eseménykezelő mindig hozzárendelődik
gomb!.addEventListener('click', () => {...});    //ha biztosan tudjuk, h nem null v undefined (akkor érdemes használni, ha tuti ott van az elem)
if(!gomb) {console.error("hiba"!); return;}      //teljes kontroll, biztonságos

gomb?.addEventListener('click', (event: MouseEvent) => { console.log("kattintás történt") });
```

nem arrow funkcióval:
const gomb = document.querySelector<HTMLButtonElement>('#kuldesGomb');
function kattintasKezelo(event: MouseEvent): void {
  alert('Kattintottál a gombra!');
}
// esemény regisztrálása
gomb?.addEventListener('click', kattintasKezelo);
```
MOUSEEVENT
click – kattintás
dblclick – dupla kattintás
mousedown – egérgomb lenyomása
mouseup – egérgomb felengedése
mousemove – egér mozgatása
mouseover – egér rámegy egy elemre
mouseout – egér elhagyja az elemet
contextmenu – jobb klikk (helyi menü)

KEYBOARDEVENT
keydown – billentyű lenyomása
keyup – billentyű felengedése

SUBMITEVENT VAGY EVENT
submit – űrlap elküldése
reset – űrlap visszaállítása
change – beviteli elem értékének módosítása
input – beírás input mezőbe (valós időben)
```
---------------------------
----------------------------
OBJEKTUM (csak ez az egy van)
const Felhasznalo_objektum = {
  nev: "Anna",
  kor: 25,
  koszones: function() {
    console.log(`Szia, ${this.nev}!`);
  }
};
Felhasznalo_objektum.koszones(); // Szia, Anna

-----------------------
OSZTÁLY (példányosítható!)
```javascript
class ClassName {
  name: string;
  year: number;
  isWorking: boolean;

  constructor(name: string, year: number, working: boolean) {
    this.name = name;
    this.year = year;
    this.isWorking = working;
  }

  status(): string {
    let status = "";
    if (isWorking) {
      return "yes";
    } else {
      return "no";
    }
  }
}

const userobject1 = new ClassName("John", 28, true);
const userobject2 = new ClassName("Rita", 36, false);
```

======================
        ANGULAR
======================
telepítés:
npm install -g @angular/cli

verzió csekkolás:
ng v


**TERMINÁL
> ng new PROJEKTNEVE --no-standalone			(ng = aNGular)

ha kész:
> cd .\PROJEKTNEVE\


**bootstrap importálása:
> npm i bootstrap								(vagy npm install ~ node package manager)

**bootstrap importálása az angular.json-be:
"styles: [
	"./node_modules/bootstrap/dist/css/bootstrap.css",     (VAGY SIMÁN node_modules/bootstrap...)
	"src/styles.css"
],


**új elemek, komponensek készítése
> ng g c KOMPONENSNEVE							(generate component
> ng g c MÁSIKKOMPONENS
> ng g c HIBA


----

**src/app/app.html:
ki lehet üríteni, csak a router-outlet maradjon (ide kerülhet az a kontent, ami minden oldalon meg fog jelenni.
így a bootstrapes cuccok is rendezve vannak:
```html
<div class="container">
	<router-outlet />
</div>
```

**src/app/app-module.ts:
```typecript
imports: [
	BrowserModule,
	AppRoutingModule,
	FormsModule
],
```

**src/app/app-routing-module.ts:
```typecript
const routes: Routes = [
  {path: "valasztasok", component: Valasztasok},
  {path: "hiba", component: Hiba},
  {path: "masikkomponens", component: MÁSIKKOMPONENS},
  {path: "", redirectTo: "valasztasok", pathMatch: "full"},
  {path: "**", component: Hiba}
];
```

**hiba.html-be
elég egy alert


elemek hozzárendelése a navigációs sávba:
```html
<a class="nav-link" href="#" routerLink="/valasztasok">LINK NEVE</a>
<a class="nav-link" href="#" routerLink="/masikkomponens">MÁSIKKOMPONENS</a>
<a class="nav-link" href="#" routerLink="/hiba">Hiba</a>
```

----
**lehet futtatni a teszteléshez:
> ng serve --open								(szerver indítása, meg is nyitja)


---- ---- ---- ---- ---- ---- ----
előkészítés kész!
---- ---- ---- ---- ---- ---- ----

**komponensen belül:
KOMPONENSNEVE1\KOMPONENS.ts
```typecript
@Component({

})

export class KOMPONENS {
	//NINCS VAR
	//NINCS FUNCTION
	
	//ezek a html-ben a formokhoz kellenek (!= üres is lehet)
	nevInput!:string;
	szamInput!:number;
	masikszamInput!:number;
	
	kereso!:string;
	szures(adatok: any): boolean {
		if(!this.kereso) return true; //nincs szűrés
		const keres = this.kereso.toLowerCase();
		
		return (
			adatok.nev?.toLowerCase().includes(keres) ||
			adatok.szam?.toString().toLowerCase().includes(keres) ||			
			adatok.masikszam?.toString().toLowerCase().includes(keres)
		);
	}
	
	//input adatbázis
	csapatAdat: string[] = [
		"egyikNév;3,8",
		"masikNév;5,2"	
	]

//lehet minden FifaElem is! azaz class. nem kell interfaceként
	objektumFeltolto(feltoltendoElem: string[]): FifaAdat[] {
		let beolvasottAdatok: FifaAdat[] = [];
		for (let i: number = 0; i < feltoltendoElem.length; i++) {
			let daraboltAdatok = feltoltendoElem[i].split(";");
			let ujCsapat: FifaAdat = new FifaElem(daraboltAdatok[0], Number(daraboltAdatok[1]), Number(daraboltAdatok[2]));
			
			//let ujCsapat: FifaAdat = {
			//	nev: daraboltAdatok[0],
			//	szam: Number(daraboltAdatok[1]),
			//	masikszam: Number(daraboltAdatok[2])
			//}
			beolvasottAdatok.push(ujCsapat);
		}
		return beolvasottAdatok;
	}
	
	fifaadatok = this.objektumFeltolto(this.csapatAdat);
	
	Mentes() {
		let ujCsapat: FifaAdat = new FifaElem(this.nevInput, this.szamInput, this.masikszamInput);
		this.fifaadatok.push(ujCsapat);
	}
}

//AZ INTERFACE AZ EXPORT CLASSON KÍVÜL LEGYEN
interface FifaAdat {
	nev: string;
	szam: number;
	masikszam: number;
}

class FifaElem implements FifaAdat {
	nev: string;
	szam: number;
	masikszam: number;

	construktor(nev: string, szam: number, masikszam: number) {
		this.nev = nev;
		this.szam = szam;
		this.szam = szam;
		this.masikszam = masikszam;
	}
}
```

----
**HTML
KOMPONENSNEVE1\KOMPONENS.html

**adatok feltöltése
```html
<div class="form-group">
    <label for="nevInput">Név</label>
    <input type="text" class="form-control" [(ngModel)]="nevInput" id="nevInput">
</div>
<div class="form-group">
    <label for="szamInput">Szám</label>
    <input type="number" class="form-control" [(ngModel)]="szamInput" id="szamInput">
</div>
<div class="form-group">
    <label for="masikszamInput">Másik szám</label>
    <input type="number" class="form-control" [(ngModel)]="masikszamInput" id="masikszamInput">
</div>
<button class="btn btn-success w-100 my-3" (click)="Mentes()">Adatok mentése</button>
```

**adatok szűrése:
```html
<input type="text" class="form-control mb-5" [(ngModel)]="kereso" placeholder="Keresés...">
```

**adatok megjelenítése
```html
<table class="table table-success table-striped table-sm table-bordered table-hover">
	<thead>
		<tr>
			<td>Név</td>
			<td>Szám</td>
			<td>Másik szám</td>
		</tr>
	</thead>
	<tbody>
		<tr *ngFor="let adatok of fifaadatok">
			<td>{{adatok.nev}}</td>
			<td>{{adatok.szam}}</td>
			<td>{{adatok.masikszam}}</td>
		</tr>
	</tbody>
</table>


<!--HA KELL SZŰRÉS:-->
		<tr *ngFor="let adatok of fifaadatok">
			<ng-container *ngIf="szures(adatok)">
				<td>{{adatok.nev}}</td>
				<td>{{adatok.szam}}</td>
				<td>{{adatok.masikszam}}</td>
			</ng-container>

		</tr>
```


---
adat tömb feldolgozás interface-szel

```typescript
var snookerInfo: string[] = ["52;Akani Sunny;Thaiföld;118500",
							"38;Zhou Yuelong;Kína;150250",
							]

interface snookerElem {
    helyezes: string;
    nev: string;
    orszag: string;
    nyeremeny: number;
}

function Objektumfeltolto(feltoltendoElem: string[]): snookerElem[] {
    var beolvasottAdatok: snookerElem[] = [];
    for (let i: number = 0; i < feltoltendoElem.length; i++) {
        let darabolandoSor: string[] = feltoltendoElem[i].split(";");
        let objektum: snookerElem = {
            helyezes: darabolandoSor[0],
            nev: darabolandoSor[1],
            orszag: darabolandoSor[2],
            nyeremeny: Number(darabolandoSor[3])
        };
        beolvasottAdatok.push(objektum);
    }
    return beolvasottAdatok;
}
var snookerAdatok: snookerElem[] = this.Objektumfeltolto(this.snookerInfo);

function LegtobbNyeremeny(vizsgaltObjektum: snookerElem[]): number {
    var maxNyeremeny: number = vizsgaltObjektum[0].nyeremeny;
    for (let i: number = 0; i < vizsgaltObjektum.length; i++) {
        if (vizsgaltObjektum[i].nyeremeny > maxNyeremeny) {
            maxNyeremeny = vizsgaltObjektum[i].nyeremeny;
        }
    }
    return maxNyeremeny;

}
```
===
DATA BINDING
```
{{expression}}
FE<-------BE interpolation: egyszerű hivatkozás. a komponensben lévő elem értékét jelenítjük meg a DOM felületén
BE:		let szoveg: string = "brekk"
FE:		<p>{{szoveg}}</p>

[property] = "expression"
FE<-------BE one way binding: tulajdonság hivatkozás. komponensben lévő adatot húzunk a DOM-os tulajdonságba
BE:		let webcim_url: string = "http://www.brekk.hu";
FE:		<a [href]="webcim_url" target="_blank">brekk</a>

(event) = "statement"
FE-------->BE event binding: események kezelése. DOM eseményekre reagálva hajtunk végre vmit a komponensen, pl. klikk, mozgás
BE:		uzenet(): void { alert("klikkeléskor ez fut le"); }
FE:		<button type="button" (click)="uzenet()">alertet kiváltó gomb</button>

[(ngModel)] = "property"
FE<-------->BE two way binding: kétirányú kötés, DOM-ban módosított érték módosul a komponensben is és viszont.
BE:		a_Oldal: number = 2;
FE:		<input type="number" id="a_Oldal" [(ngModel)]="a_Oldal">
		<p>a négyzet oldalának mérete: {{a_Oldal}}</p>			//ez már ugye egy egyszerű hivatkozás 
```
Űrlapok esetén kell a FormsModule (app.module.ts-be kell importálni)

tömb értékeit kilistázni:
```
BE:		eredmenyek: string[] = [];
FE:		<ul><li *ngFor="let adatsor of eredmenyek">{{adatsor}}</li></ul>
```


---
===
még egy feltöltő

```
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-kektura',
  templateUrl: './kektura.component.html',
  styleUrls: ['./kektura.component.css']
})
export class KekturaComponent implements OnInit {

  constructor() { }

  ngOnInit(): void {
  }

  kektura: string[] = [
    "Sumeg, vasutallomas;Sumeg, buszpalyaudvar;1,208;16;6;n",
    "Sumeg, buszpalyaudvar;Mogyorosi-domb, geologiai bemutatohely;1,512;24;8;n",
    "Mogyorosi-domb, geologiai bemutatohely;Sumegi bazaltbanya vasutallomas;1,576;13;43;n"
  ];

  ObjektumFeltolto(feltoltendoElem: string[]): turaSzakasz[] {
    var beolvasottAdatok: turaSzakasz[] = [];
    for (let i: number = 0; i < feltoltendoElem.length; i++) {
      let elemDarabok: string[] = feltoltendoElem[i].split(";");
      let objektum: turaSzakasz = {
        kiinduloPont: elemDarabok[0],
        vegPont: elemDarabok[1],
        szakaszHossza: Number(elemDarabok[2].replace(",", ".")),
        emelkedes: Number(elemDarabok[3]),
        lejtes: Number(elemDarabok[4]),
        pecsetelohelyE: elemDarabok[5]
      }
      beolvasottAdatok.push(objektum);
    }
    return beolvasottAdatok;
  }

  megjelenitendoAdatok: turaSzakasz[] = this.ObjektumFeltolto(this.kektura);

  kiinduloPontNeve!: string;
  vegPontNeve!: string;
  szakaszHossz!: number;
  emelkedesMerteke!: number;
  lejtesMerteke!: number;
  pecseteloHelyInfo!: string;

  UjAdatok(): void {
    if (this.kiinduloPontNeve != null && this.vegPontNeve != null && this.szakaszHossz != null && this.emelkedesMerteke != null && this.lejtesMerteke != null && this.pecseteloHelyInfo != null) {
      let ujAdat: turaSzakasz = {
        kiinduloPont: this.kiinduloPontNeve,
        vegPont: this.vegPontNeve,
        szakaszHossza: this.szakaszHossz,
        emelkedes: this.emelkedesMerteke,
        lejtes: this.lejtesMerteke,
        pecsetelohelyE: this.pecseteloHelyInfo
      }
      this.megjelenitendoAdatok.push(ujAdat);
    }
    else {
      alert("Hiányzó adat!");
    }
  }
}

export interface turaSzakasz {
  kiinduloPont: string;
  vegPont: string;
  szakaszHossza: number;
  emelkedes: number;
  lejtes: number;
  pecsetelohelyE: string;
}

---

<div class="form-group">
        <label for="kiinduloPontNeve">Kiindulópont neve</label>
        <input type="text" id="kiinduloPontNeve" [(ngModel)]="kiinduloPontNeve" class="form-control">
</div>
<button type="button" class="btn btn-dark form-control mb-3 mt-3" (click)="UjAdatok()"> Adatok feltöltése</button>

 <table class="table table-dark table-striped">
        <thead>
            <tr>
                <th>Kiindulópont neve</th>
                <th>Végpont neve</th>
                <th>Túraszakasz hossza</th>
                <th>Emelkedés</th>
                <th>Lejtés</th>
                <th>Pecsételőhely-e?</th>
            </tr>
        </thead>
        <tbody>
            <tr *ngFor="let szakaszAdatok of megjelenitendoAdatok">
                <td>{{szakaszAdatok.kiinduloPont}}</td>
                <td>{{szakaszAdatok.vegPont}}</td>
                <td>{{szakaszAdatok.szakaszHossza}}</td>
                <td>{{szakaszAdatok.emelkedes}}</td>
                <td>{{szakaszAdatok.lejtes}}</td>
                <td>{{szakaszAdatok.pecsetelohelyE}}</td>
            </tr>
        </tbody>
    </table>
```
