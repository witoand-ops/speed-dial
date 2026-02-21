# ⊞ Speed Dial Groups

Vizuális gyorstárcsák csoportokba rendezve, weboldal előnézettel.  
Google bejelentkezés + adattárolás a saját Google Drive-odban.  
Bármilyen eszközről elérhető, szinkronban.

---

## Telepítés (15 perc, ingyenes)

### 1. lépés: Google Cloud projekt + OAuth Client ID

1. Nyisd meg: **https://console.cloud.google.com**
2. Felül kattints a projekt nevére → **New Project** → név: `Speed Dial` → Create
3. Bal menü → **APIs & Services** → **Library**
4. Keresd meg: **Google Drive API** → kattints rá → **Enable**
5. Bal menü → **APIs & Services** → **OAuth consent screen**
   - **User type**: External → Create
   - **App name**: `Speed Dial Groups`
   - **User support email**: a te email címed
   - **Developer contact**: a te email címed
   - Mentés → tovább → tovább → **Back to Dashboard**
6. Bal menü → **Credentials** → **+ CREATE CREDENTIALS** → **OAuth client ID**
   - **Application type**: Web application
   - **Name**: `Speed Dial`
   - **Authorized JavaScript origins**: add hozzá:
     - `https://FELHASZNALONEVED.github.io`
   - Kattints **CREATE**
7. **Másold ki a Client ID-t** (valami ilyesmi: `123456789-abc.apps.googleusercontent.com`)

### 2. lépés: Client ID beírása

1. Nyisd meg az `index.html` fájlt egy szövegszerkesztőben
2. Keresd meg ezt a sort (kb. 83. sor):
   ```
   var CLIENT_ID = 'IDE_IRD_BE_A_CLIENT_ID.apps.googleusercontent.com';
   ```
3. Cseréld ki a saját Client ID-dra:
   ```
   var CLIENT_ID = '123456789-abc.apps.googleusercontent.com';
   ```
4. Mentsd el

### 3. lépés: Feltöltés GitHub Pages-re

1. Menj a **https://github.com** oldalra (regisztrálj ha nincs fiókod)
2. Kattints **+** → **New repository**
   - **Repository name**: `speed-dial` (vagy amit akarsz)
   - **Public** (a GitHub Pages-hez kell)
   - Kattints **Create repository**
3. Kattints **uploading an existing file**
4. Húzd be az `index.html` fájlt
5. Kattints **Commit changes**
6. Menj a repo **Settings** → **Pages** fülre
   - **Source**: Deploy from a branch
   - **Branch**: `main` → `/ (root)` → **Save**
7. Várj 1-2 percet, aztán elérhető lesz:  
   **`https://FELHASZNALONEVED.github.io/speed-dial/`**

### 4. lépés: Kész!

Nyisd meg a linket bármilyen eszközön, jelentkezz be Google-lel, és használd!

---

## Gyakori kérdések

**Hol tárolódnak az adataim?**  
A saját Google Drive-od rejtett alkalmazás-mappájában (`appDataFolder`). 
Más nem látja, csak ez az alkalmazás.

**Működik telefonon?**  
Igen, reszponzív design.

**Mi kell a működéshez?**  
Csak egy böngésző és Google fiók.

**Biztonságos?**  
Az alkalmazás csak a saját rejtett mappájához fér hozzá a Drive-odon. 
Semmilyen más fájlodat nem látja és nem módosítja.

**Miért Public a repo?**  
A GitHub Pages ingyenes verziója csak public repóval működik. 
Az adataid NEM a repóban vannak, hanem a Drive-odban.

---

## Funkciók

- 🔐 Google bejelentkezés
- ☁️ Google Drive szinkronizáció (több eszköz)
- 🖼️ Weboldal képernyőképek a tárcsákon
- 📊 Top oldalak hozzáadása
- ⏱️ Stopper és visszaszámláló
- 📝 Jegyzetek
- ⚙️ Beállítások (oszlopok, méret, tárcsák/oldal, keresőmotor)
- 📄 Lapozás
- 🌙 Sötét/világos téma
- ➕ Csoportok létrehozása, átnevezése, törlése
- 🔀 Drag & drop átrendezés
