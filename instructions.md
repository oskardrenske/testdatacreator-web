# Skapa testdata 


## Skapa fiktiva personer med data valt slumpmässigt från fil.

### Personpost
En person-post ser ut så här:


| benämning   | datatyp               |   Källa i katalogen data                                                                                   |
|-------------|-------------------------------------------------------------------------------------------------------------------|
| `first_name`   |  string            | 
| `last_name`   |  string             | 
| `adress`   |  string               |  Slumpade värden: "<adress_prefix.txt> <adress_suffix.txt>" 
| `gatunummer`   |  string               | 1-150
| `postadress`   |  string             | Slumpat från postadress.txt
| `personnummer`   |  str              | slumpat från personnummer.txt
| `telefonnummer`   |  str               | slumpat "0" + 9 siffor

### Exempel:
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

## Input
Antal testpersoner som skall skapas

## Skapande
Skapa så många testpersoner som angetts

## Output
En websida som erbjuder val hur många testpersoner som skall skapas. 
Möjlighet att ladda ned resultatet som en json-fil


## Teknik
PyScript på webbsidan
Single Page Application
Datafiler kan finnas på webservern (kan göras om till något annat format än text, t.ex json om det underlättar)



