# DevOps beadandó – Hello DevOps (React + Vite)

Ez a projekt egy egyszerű, HTTP-n elérhető „Hello, DevOps!” alkalmazás React és Vite segítségével.  
A cél az alap DevOps lépések bemutatása egy kis példán keresztül:

- kódkészítés
- buildelés
- verziókezelés (trunk-based szemlélettel)
- Docker konténerizálás
- DevContainer használata (választott extra feladat)

---

## 1. Alkalmazás futtatása fejlesztői módban

A projekt mappájában:

```bash
npm install
npm run dev
Ezután a böngészőben:

URL: http://localhost:5173

Az oldalon a „Hello, DevOps!” felirat jelenik meg.

2. Buildelés
Production build készítése:

bash
Copy code
npm run build
A buildelt statikus fájlok a dist/ mappába kerülnek.

3. Dockerizálás
A projekt tartalmaz egy Dockerfile fájlt, amely:

elkészíti a React buildet,

Nginx konténerbe csomagolja a dist tartalmát,

a konténer indulásakor automatikusan elindítja az Nginx szervert.

Docker image buildelése
bash
Copy code
docker build -t hello-devops:v1 .
Konténer futtatása
bash
Copy code
docker run --rm -p 8080:80 hello-devops:v1
Ezután a böngészőben:

URL: http://localhost:8080

4. Verziókezelés (Git, trunk-based)
A projekt Git repóban van verziókezelve.

a main ág a „trunk”

új módosításokhoz/fejlesztésekhez külön feature brancheket használok
(pl. feature/readme-update)

a változtatások értelmes commit üzenetekkel kerülnek be a repóba

Példa commit üzenetek:

feat: initial project setup with Hello DevOps app and Dockerfile

feat: add extra line to README for feature branch testing

feat: add DevContainer configuration

docs: add DevContainer usage instructions to README

5. DevContainer (választott extra feladat)
A projekt tartalmaz DevContainer konfigurációt, hogy Visual Studio Code-ból konténeres fejlesztői környezetben is futtatható legyen.

Struktúra:

text
Copy code
.devcontainer/
  ├─ Dockerfile.dev
  └─ devcontainer.json
DevContainer használata (VS Code)
Visual Studio Code telepítése

„Dev Containers” bővítmény telepítése (Microsoft)

A projektmappa megnyitása VS Code-ban

Bal alsó sarokban: „Reopen in Container”

A VS Code ezután:

felépíti a .devcontainer/Dockerfile.dev alapján a fejlesztői konténert,

lefuttatja a npm install parancsot a repóban,

előkészíti a környezetet a fejlesztéshez.

A konténeren belül a fejlesztői futtatás:

bash
Copy code
npm install
npm run dev
Böngészőben:

URL: http://localhost:5173/

6. Összefoglalás
A projekt teljesíti a beadandó követelményeit:

HTTP-n elérhető alkalmazás („Hello, DevOps!”)

dokumentált build folyamat (npm run build)

Dockerfile és dokumentált Docker build/futtatás

Git verziókezelés, trunk + feature branch használatával

DevContainer konfiguráció és annak használatának leírása








