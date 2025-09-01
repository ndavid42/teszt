belépés az angular 

**node installálás:
npm init -y

--> package.json létrejön


**mongo db cuccok telepítése
npm install express mongoose cors

--> node_modules mappa is létrejött

config.js létrehozása
	--> module.exports = { mongoUrl: "x", dbName: "y", collectionName: "z" };

server.js létrehozása
	--> const express = require('express');
	--> const mongoose = require('mongoose');
	--> const cors = require('cors');
	app.use (cors());
	app.use(express.js)
	--> apt.get
	schema
	--> app.listen() 			ettől indul el a szerver, ez a futtatás
								konzolba:		node server.js

_szerver fut_

---------
törlés, ID alapján fut

app.delete() => {
	kontent
}

----------
a háttérben fut a szerver, arra fogunk csatlakozni angularral

ng new dolgozo-crud --standalone --no-ssr			//standalone és nincs server side rendering
cd dolgozo-crud

npm install bootstrap
	angular.json-ba be kell hivatkozni a bootstrapet (styles és scripts)
	
create component dolgozok
	src/app/app.routes.ts-be: route-okat beírogatni, behivatkozni a dolgozok componentet
	
ng serve --> fut a szerver, h lehessen csekkolni már
	
app.html-be: törölni a felesleget

új mappa: models (a mongo miatt)
	--> ide új fájl: dolgozo.model.ts
			--> export interface Dolgozo {
				_id?: string;
				nev: string;
				kor: number;
				fizetes
				stb...
			}

ng g s services/dolgozo (generate service) ide jönnek a különböző lekérések a szerver részéről (get, post, delete stb.)
	--> dolgozo.ts
			--> import { HttpClient }
				import { Observable }
				import { Dolgozo }
				
				export class DolgozoService {
					//port
					//constructor
						//get<Dolgozo[]>
						//del...
						//create...
						//update...
				}

app.config.ts
	--> provideRouter(routes)
	--> provideHttpClient()
	stb




