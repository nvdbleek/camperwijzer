# Camperwijzer: op GitHub Pages met Firebase

De site bestaat uit drie bestanden: `index.html`, `firebase-config.js` en `firestore.rules`. GitHub Pages host de pagina gratis. Firebase (gratis Spark-abonnement) bewaart de trips en vinkjes en deelt ze live tussen jullie telefoons. Een eigen server is niet nodig.

## 1. Firebase-project aanmaken (± 10 minuten)

1. Ga naar https://console.firebase.google.com en kies **Project toevoegen**. Geef het een naam, bv. `camperwijzer`. Google Analytics mag uit.
2. **Firestore**: menu *Build → Firestore Database → Database maken*. Kies een locatie in Europa (bv. `europe-west`) en start in **productiemodus**.
3. **Regels**: open in Firestore het tabblad *Regels*. Plak de inhoud van `firestore.rules` en vul jullie eigen Google-adressen in. Klik **Publiceren**. Alleen die adressen kunnen de trips lezen en afvinken.
4. **Inloggen**: menu *Build → Authentication → Aan de slag → Google*. Zet die aan en sla op.
5. **Web-app**: ga naar *Projectinstellingen* (tandwiel) → *Je apps* → het web-icoon `</>`. Geef een naam; Hosting is niet nodig. Kopieer het `firebaseConfig`-blok naar `firebase-config.js` op de plek van de `VUL_IN`-waarden.

## 2. Op GitHub Pages zetten

1. Maak op GitHub een nieuwe repository, bv. `camperwijzer`. Openbaar is nodig voor Pages met een gratis account.
2. Upload de drie bestanden (*Add file → Upload files*). `README.md` mag mee.
3. Ga naar *Settings → Pages*. Zet bij *Source* **Deploy from a branch**, kies `main` en map `/ (root)`, en sla op.
4. Na ± een minuut staat de site op `https://<jouw-gebruikersnaam>.github.io/camperwijzer/`.

## 3. GitHub-adres toestaan in Firebase

In Firebase: *Authentication → Settings → Authorized domains → Domein toevoegen*. Vul `<jouw-gebruikersnaam>.github.io` in. Zonder deze stap werkt inloggen niet.

## Goed om te weten

- **Is de config geheim?** Nee, die waarden zijn openbaar bedoeld. De beveiliging zit in de Firestore-regels met de lijst van toegestane e-mailadressen. Iemand toevoegen: zet het adres in die lijst en publiceer de regels opnieuw.
- **Kosten:** het gratis Spark-abonnement is ruim genoeg voor dit gebruik. Een betaalkaart is niet nodig.
- **Zonder Firebase** werkt de site ook. Je ziet dan een melding en de trips blijven op het eigen toestel.
- **Op je telefoon:** open de site en kies in het browsermenu *Zet op beginscherm*. Dan opent hij als een app.
