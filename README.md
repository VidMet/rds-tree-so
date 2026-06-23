# 📘 Brukerveiledning: RDS Universal Editor

**RDS Universal Editor** er et todelt verktøy utviklet for å forenkle og automatisere håndteringen av RDS-koder (Reference Designation System) og andre egenskaper på IFC-modeller.

Systemet består av:
1. **Trimble Connect-utvidelsen (Web):** Et grafisk verktøy for å analysere, fargelegge, sortere og redigere RDS-koder direkte i 3D-visningen.
2. **Desktop-appen (RDS_Oppdaterer.exe):** Et lokalt program som tar endringene dine fra nettleseren og skriver dem permanent inn i de faktiske IFC-filene.

---

## Del 1: Slik bruker du utvidelsen i Trimble Connect

### 1. Oppstart og skanning
1. Åpne Trimble Connect i nettleseren og last inn 3D-modellen(e) du vil jobbe med.
2. Åpne utvidelsen **RDS Universal Editor** fra sidepanelet.
3. For å hente inn objekter: Marker objektene i 3D-modellen, og trykk på **"▶ Bygg tre"**.
4. Utvidelsen vil nå analysere egenskapene og bygge et mappetre basert på RDS-strukturen.

### 2. Navigasjon og Toveis-synkronisering
* **Fra tre til 3D:** Klikker du på et objekt eller en mappe i treet, vil disse umiddelbart markeres og zoomes til i 3D-modellen.
* **Fra 3D til tre:** Klikker du på et objekt i 3D-modellen, vil treet automatisk åpne riktig mappe, scrolle ned og markere objektet for deg.

### 3. Arbeidsflyt og Status
Utvidelsen har flere verktøy for å holde oversikt over store modeller:
* 🎨 **Fargelegg (HHH):** Gir unike farger til objekter basert på deres 3-bokstavs RDS-gruppe.
* ✅ **Ferdig-markering:** Har du kontrollert et objekt? Marker det og trykk på **"✅ Ferdig"**. Det får en dus grønnfarge i treet, slik at du ser hvor langt du har kommet.
* 👁️ **Synk visning:** Hvis du skjuler eller isolerer lag i 3D-visningen, oppdaterer utvidelsen seg live. Skjulte objekter "duses ned" og blir grå i treet.
* 💾 **Lagre / Hent tre-status:** Trykk **"Lagre tre-status"** før du avslutter for dagen. Nettleseren husker da hvilke objekter som er grønne (Ferdig) og grå (Skjult). Neste gang du åpner modellen og bygger treet, trykker du bare **"Hent tre-status"** for å fortsette nøyaktig der du slapp!

### 4. Redigere egenskaper
1. Klikk på **blyant-ikonet (✏️)** ved siden av et objekt for å redigere det. 
2. For å **Batch-redigere** flere objekter samtidig, klikker du på blyanten ved siden av en *mappe*. Alle objektene i mappen får da de nye verdiene.
3. Du kan redigere eksisterende verdier, eller legge til helt nye ved å bruke feltet "Legg til manglende egenskap" nederst i vinduet.
4. Trykk **"Lagre i kø"**. Mappen/objektet markeres nå med "✏️ Endret" i rød tekst.

*Tips: For å raskt oppdatere løpenummer på tvers av mange objekter, kan du markere dem i 3D, skrive inn f.eks. `04` i tekstfeltet oppe til venstre, og trykke **"➕ Hurtigoppdater"**.*

### 5. Eksportere endringer
Når du er ferdig med å redigere, vil knappen **"💾 Eksporter"** vise hvor mange objekter som ligger i køen. 
* Trykk på knappen for å laste ned filen `update-properties.json`. Denne filen inneholder alle instruksjonene som trengs for å oppdatere IFC-filene.

---

## Del 2: Skrive endringene til IFC-filene (Desktop)

For at endringene du gjorde i nettleseren skal bli permanente, må de skrives inn i kildefilene (IFC-filene). Dette gjør du lokalt på din egen PC.

### Slik gjør du det:
1. Sørg for at du har lastet ned IFC-filene du skal oppdatere til en mappe på PCen din (eller at de er synkronisert via f.eks. Trimble Connect Sync / OneDrive).
2. Dobbeltklikk på programmet **`update-properties.exe`**.
3. Et fil-vindu spretter opp: Velg `update-properties.json`-filen du nettopp lastet ned fra Trimble Connect.
4. Et nytt vindu spretter opp: Velg mappen på PCen din som inneholder IFC-filene.
5. Programmet (en svart terminal) vil nå starte å lese filene og skrive inn endringene. Du kan følge med på fremdriften live i terminalen.
6. Når prosessen er ferdig, får du opp en suksessmelding som forteller hvor mange objekter som ble oppdatert.

**Viktig:** Programmet overskriver IFC-filene i mappen du velger. Sørg for at du har en backup eller bruker et versjonskontrollsystem dersom det er behov for det.

---
***Utviklet av** Vidar Metveit* ***for** Norconsult Norge AS.*