# DevOps beadandó – Hello DevOps (React + Vite)

Ez a projekt egy egyszerű, HTTP-n elérhető „Hello, DevOps!” alkalmazás React és Vite segítségével.  
A cél az alap DevOps lépések bemutatása:

- kódkészítés
- buildelés
- verziókezelés (trunk-based megközelítés)
- Docker konténerizálás
- DevContainer használata (választott extra feladat)

---

## 1. Alkalmazás futtatása

A projekt indítása fejlesztői módban:

```bash
npm install
npm run dev
A böngészőben ezután megnyitható:

http://localhost:5173

A felületen megjelenik a „Hello, DevOps!” felirat.

2. Buildelés
Production build készítése:

bash
Copy code
npm run build
A buildelt fájlok a dist/ mappába kerülnek.

3. Dockerizálás
A projekt tartalmaz egy Dockerfile-t, amely:

elkészíti a React buildet,

Nginx szerverbe csomagolja,

és futtatáskor automatikusan elindítja a statikus tartalmat kiszolgáló szervert.

Docker image buildelése
bash
Copy code
docker build -t hello-devops:v1 .
Konténer futtatása
bash
Copy code
docker run --rm -p 8080:80 hello-devops:v1
A böngészőben ekkor:

http://localhost:8080

4. Verziókezelés (Git)
A projekt trunk-based szemléletet követ:

a main ág a trunk,

új módosítások külön feature/* branch-eken készülnek,

a commit üzenetek a változtatásokat egyértelműen rögzítik.

Példák:

feat: initial project setup

feat: add Hello DevOps message

feat: add Dockerfile

5. DevContainer (választott extra feladat)
A projekt tartalmaz DevContainer konfigurációt, amely lehetővé teszi,
hogy Visual Studio Code-ban konténeres fejlesztői környezetben fusson.

A .devcontainer mappa tartalmazza a konfigurációs fájlokat.

Összefoglalás
A projekt teljesíti a beadandó DevOps követelményeit:

HTTP-n elérhető alkalmazás

buildelhető

Docker konténer készíthető belőle

dokumentált folyamatok

trunk-based verziókezelés

opcionális DevContainer megvalósítva
