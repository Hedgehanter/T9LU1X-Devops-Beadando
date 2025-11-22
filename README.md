📘 DevOps Beadandó – Hello DevOps (React + Vite)

Ez a projekt egy egyszerű, HTTP-n elérhető „Hello, DevOps!” alkalmazás React és Vite segítségével.
A projekt célja az alap DevOps lépések bemutatása:

✔ Kódkészítés

✔ Buildelés

✔ Verziókövetés (trunk-based elméletben, commitokkal igazolható)

✔ Docker konténerizálás

✔ DevContainer (opcionális bővítés – később hozzáadható)

🚀 1. Alkalmazás futtatása

A projekt indítása fejlesztői módban:

npm install
npm run dev


Ezután a böngészőben nyisd meg:
👉 http://localhost:5173

Itt látható a Hello, DevOps! felirat.

🏗️ 2. Buildelés

A production build elkészítése:

npm run build


A buildelt statikus fájlok a dist/ mappába kerülnek.

🐳 3. Dockerizálás

A projekt tartalmaz egy Dockerfile-t, amely:

elkészíti a React buildet,

Nginx-be csomagolja,

a konténer indulásakor automatikusan elindítja a szervert.

Docker image buildelése:
docker build -t hello-devops:v1 .

Konténer futtatása:
docker run --rm -p 8080:80 hello-devops:v1


Ezután a böngészőben:
👉 http://localhost:8080

🌿 4. Verziókezelés (Git)

A projekt trunk-based fejlesztési modellt követ:

main ág = trunk

új funkciók külön feature/* branch-eken

merge vissza a main-re értelmes commit üzenetekkel

Példa commitokra:

feat: initial project setup

feat: add Hello DevOps message

feat: add Dockerfile

🛠️ 5. DevContainer (opcionális, bővítés)

A projekt kiegészíthető .devcontainer mappával, amely lehetővé teszi, hogy VS Code DevContainers-ben fusson.

🐳 6. DevContainer használata

A projekt támogatja a DevContaineres futtatást Visual Studio Code-ban.

Hogyan indítható?

Telepítsd a VS Code programot

Telepítsd a következő bővítményt:
👉 Dev Containers (Microsoft hivatalos)

Nyisd meg a projekt mappáját VS Code-ban

A bal alsó sarokban kattints a zöld ikonra:
“Reopen in Container”

VS Code automatikusan:

felépíti a .devcontainer/Dockerfile.dev konténert

telepíti az npm csomagokat

előkészíti a fejlesztői környezetet

Dev módban futtatáshoz:
npm install
npm run dev


Ezután a böngészőben nyisd meg:
👉 http://localhost:5173/

✔ Összefoglalás

Ez a projekt megfelel a beadandó DevOps követelményeinek:

HTTP-n elérhető app

Buildelhető

Docker konténer készíthető belőle

Dokumentált parancsok

Verziókezelési modell leírva"# T9LU1X-Devops-Beadando" 


Ez egy extra sor a feature branch teszteléséhez.
