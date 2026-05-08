# Testdata-generator

Webbsida som genererar fiktiva svenska person-poster (personnummer, namn, adress, postadress, telefonnummer) — slumpade från inbäddade källistor. Allt körs i webbläsaren via [PyScript](https://pyscript.net/); inget backend, ingen build.

## Person-post

```json
{
    "personnummer": "198502182382",
    "first_name": "Linnea",
    "last_name": "Malmberg",
    "adress": "Konstnärvägen",
    "gatunummer": "33",
    "postadress": "624 53 Lärbro",
    "telefonnummer": "0387661966"
}
```

Se `instructions.md` för fullständig specifikation.

## Användning

1. Öppna sidan.
2. Ange antal personer (1–1000, default 10).
3. Klicka **Generera** — förhandsgranskning visar de första 20 posterna.
4. Klicka **Ladda ner JSON** för att spara hela resultatet som `testdata.json`.

## Köra lokalt

PyScript måste servas över HTTP (inte `file://`):

```bash
python3 -m http.server 8000
# öppna http://localhost:8000/
```

## Deploy
### GitHub pages
Deployas till [GitHub pages](https://oskardrenske.github.io/testdatacreator-web/) vid push till `main`branch

### Annan webserver
Ladda upp `docs/index.html` till valfri statisk webbserver (t.ex. via SFTP). Det är den enda filen som behövs — all data är inbäddad.
