# Auto Onderhoud

Simpele tracker voor onderhoud van je auto (datum, km-stand, type onderhoud, status, info).
Twee versies in deze map:

1. **`auto_onderhoud.xlsx`** — los Excel-bestand, lokaal te gebruiken. Kolom "Onderhoud" en
   "Uitgevoerd" hebben een klikbare keuzelijst (dropdown).
2. **`index.html`** — webpagina die je via GitHub Pages kunt hosten. Nieuwe onderhoudsbeurten
   worden automatisch weggeschreven naar een bestand `onderhoud.json` in je eigen repository.

## De webversie (`index.html`) opzetten

1. Maak een **nieuwe GitHub repository** aan (bv. `auto-onderhoud`), publiek of privé.
2. Zet `index.html` in de root van die repository (commit + push, of upload via de GitHub website).
3. Ga naar **Settings → Pages** van de repo, kies branch `main` en map `/ (root)`. Na een paar
   minuten is de pagina bereikbaar op `https://<gebruikersnaam>.github.io/<repo-naam>/`.
4. Maak een **Personal Access Token**:
   - Ga naar github.com → **Settings → Developer settings → Personal access tokens →
     Fine-grained tokens**.
   - Beperk het token tot **alleen deze ene repository**.
   - Geef alleen **"Contents: Read and write"** rechten.
5. Open je gehoste pagina, klap "⚙️ Instellingen" open, vul je GitHub-gebruikersnaam,
   repo-naam en token in en klik "Opslaan & verbinden".
6. Voeg onderhoud toe via het formulier — dit wordt automatisch gecommit naar
   `onderhoud.json` in je repository. Elke wijziging is dus terug te vinden in de
   commit-geschiedenis van de repo.

### Exporteren naar Excel of PDF
Boven het overzicht staan twee knoppen: **"⬇ Excel (.xlsx)"** en **"⬇ PDF"**. Deze zetten de
data die op dat moment geladen is (dus alles uit `onderhoud.json`) direct om naar een
gedownload bestand — geen extra stap nodig, werkt volledig in de browser.

### Let op
- Het token staat alleen lokaal in de browser (localStorage) opgeslagen — het wordt nergens
  anders naartoe gestuurd dan naar de GitHub API zelf. Gebruik toch altijd een
  fine-grained token beperkt tot één repo, nooit een token met volledige account-rechten.
- Werkt het beste op één repo per auto/gebruiker; bij meerdere gebruikers tegelijk kan de
  laatste opslag de vorige overschrijven (geen samenvoeg-logica).
- Wil je liever geen token in de browser? Dan is de Excel-versie de veiligere/simpelere keuze.

#### openen app
om app te openen: https://MitchMolenaar.github.io/auto_onderhoud/
