npm install mongodb
npm install mongoose
npm install express --save

**FUTTATÁS:**
node futtatando_cucc.js

**kollekció létrehozása:**
await db.createCollection("dolgozok");

**egy új adat hozzáadása a kollekcióhoz:**
await db.collection("mintaKollekcio").insertOne(ujAdat);

**egy adat kiolvasása a kollekcióból:**
const elsoAdat = await collection.findOne();
if("nev" in elsoAdat) console.log("első elem neve: ", elsoAdat.nev);

**egy adat módosítása a kollekcióban:**
const keresesiMinta = {nev: "Békés Csaba"}; //MIT módosít
const ujErtek = {$set: {kor: 68}}; //MIRE módosít
const eredmeny = await collection.updateOne(keresesiMinta, ujErtek);

**egy adat törlése a kollekcióból**
const torlesiMinta = {nev: "Békés Csaba"}; //MIT törlünk
const eredmeny = await collection.deleteOne(torlesiMinta);

**több adat hozzáadása a kollekcióhoz**
var ujAdatok = [{a: 1, b: rece},{a: 2, b: fice}];
await db.collection("dolgozok").insertMany(ujAdatok);

**több adat módosítása a kollekcióban:**
const keresesiMinta = {$or: [{beosztas: "Irodai Titkár"}, {beosztas: "Takarító"}]}; //MIT módosít
const ujErtek = {$set: {fizetes: 260000}}; //MIRE módosít
const eredmeny = await collection.updateMany(keresesiMinta, ujErtek);

**több adat törlése a kollekcióból**
const torlesiMinta = {$or: [{beosztas: "Ügyvezető Igazgató"}, {beosztas: "Marketing Manager"}, {beosztas: "Irodai Titkár"}]}; //MIT törlünk
const eredmeny = await collection.deleteMany(torlesiMinta);

**kollekció törlése**
await db.collection("dolgozok").drop();

---------------------------------------------------------
**adatok kiolvasása**
const eredmeny = await collection.find().toArray();
console.log("minden adat: ", eredmeny);

**adatok kiolvasása rendezéssel**
//1 növekvő - név szerint ABC
//-1 csökkenő - szám esetén csökken
const rendezesBeallitasa = {nev: 1};
const eredmeny = await collection.find().sort(rendezesBeallitasa).toArray();

**adatok kiolvasása limittel**
//az első 3-at fogja kilistázni csak
const rendezesBeallitasa = {fizetes: -1};
const eredmeny = await collection.find().sort(rendezesBeallitasa).limit(3).toArray();

**adatok kiolvasása ha az adat...**
const eredmeny = await collection.find({
    fizetes: {$gt: 300000}             	//Greater Than >
    fizetes: {$gte: 300000}             //Greater Than or Equal >=
	
	fizetes: {$lt: 300000}             	//Lesser Than <
	fizetes: {$lte: 300000}             //Lesser Than or Equal <=
	
	$or: [{beosztas: "Irodai Titkár"},	//OR
		{beosztas: "Üzem Orvos"}
	]
	
	$and: [{fizetes: {$gte: 200000}},	//AND
		{fizetes: {$lte: 300000}}
	]
	
	fizetes: { $not: {$gt: 200000}}		//NOT
	
	beosztas: {$in: ["Irodai Titkár", "Üzem Orvos"]}	//konkrét adatokat listáz csak ki
	
}).toArray();

**adatok kiolvasása, de csak bizonyos tulajdonságok megjelenítése**
const rendezesBeallitasa = {fizetes: -1};
const eredmeny = await collection.find({
	//ide jönne a szűrési feltétel
}, {
	//ide jön a projekció
	projection: {
		_id: 0, 
		nev: 1, 
		beosztas: 1, 
		kor: 1
		}	
}).sort(rendezesBeallitasa).limit(3).toArray(); //végén egyéb tulajdonságok




npm init -y
npm install express mongoose cors		//alap dolgok telepítése
node server.js							//szerver futtatása












**Hogyan telepíthetjük a bootstrap modulját az angular projektünkbe, legegyszerűbben?
npm install bootstrap

**melyik paranccsal telepítjük az Angular node modult?
ng gc angular?????



**új komponens létrehozás
ng g c ujKomponens


