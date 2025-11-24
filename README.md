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

## 3. Dockerizálás

A projekt tartalmaz egy `Dockerfile` fájlt, amelynek a célja, hogy a React-ből buildelt statikus fájlokat egy Nginx-alapú konténerből lehessen kiszolgálni.

### Docker image építése

docker build -t hello-devops:v1 .

Konténer indítása
docker run --rm -p 8080:80 hello-devops:v1

A fenti parancsok futtatásához Docker telepítése szükséges. A konfiguráció úgy lett elkészítve, hogy elvileg egy ilyen környezetben az alkalmazás a http://localhost:8080 címen legyen elérhető.

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
