**TERMINÁL
> ng new PROJEKTNEVE --no-standalone			(ng = aNGular)

ha kész:
> cd .\PROJEKTNEVE\


**bootstrap importálása:
> npm i bootstrap								(vagy npm install ~ node package manager)

**bootstrap importálása az angular.json-be:
"styles: [
	"./node_modules/bootstrap/dist/css/bootstrap.css",
	"src/styles.css"
],


**új elemek, komponensek készítése
> ng g c KOMPONENSNEVE							(generate component
> ng g c MÁSIKKOMPONENS
> ng g c HIBA


----
**lehet futtatni a teszteléshez:
> ng serve --open								(szerver indítása, meg is nyitja)

----

**src/app/app.html:
ki lehet üríteni, csak a router-outlet maradjon (ide kerülhet az a kontent, ami minden oldalon meg fog jelenni.
így a bootstrapes cuccok is rendezve vannak:
<div class="container">
	<router-outlet />
</div>

**src/app/app-module.ts:
imports: [
	BrowserModule,
	AppRoutingModule,
	FormsModule
],

**src/app/app-routing-module.ts:
const routes: Routes = [
  {path: "valasztasok", component: Valasztasok},
  {path: "hiba", component: Hiba},
  {path: "masikkomponens", component: MÁSIKKOMPONENS},
  {path: "", redirectTo: "valasztasok", pathMatch: "full"},
  {path: "**", component: Hiba}
];

**hiba.html-be
elég egy alert


elemek hozzárendelése a navigációs sávba:
<a class="nav-link" href="#" routerLink="/valasztasok">LINK NEVE</a>
<a class="nav-link" href="#" routerLink="/masikkomponens">MÁSIKKOMPONENS</a>
<a class="nav-link" href="#" routerLink="/hiba">Hiba</a>

---- ---- ---- ---- ---- ---- ----
előkészítés kész!
---- ---- ---- ---- ---- ---- ----
**komponensen belül:
KOMPONENSNEVE1\KOMPONENS.ts

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


----
**HTML
KOMPONENSNEVE1\KOMPONENS.html

**adatok feltöltése
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

**adatok szűrése:
<input type="text" class="form-control mb-5" [(ngModel)]="kereso" placeholder="Keresés...">

**adatok megjelenítése
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


//HA KELL SZŰRÉS:
		<tr *ngFor="let adatok of fifaadatok">
			<ng-container *ngIf="szures(adatok)">
				<td>{{adatok.nev}}</td>
				<td>{{adatok.szam}}</td>
				<td>{{adatok.masikszam}}</td>
			</ng-container>
		</tr>