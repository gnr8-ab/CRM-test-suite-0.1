# Testscenario: Hantera ljudliknande företagsnamn vid röstinmatning

## Given
- Användaren vill rapportera ett möte med en kontakt på ett företag vars namn kan missuppfattas vid röstinmatning
- Testdata:
   - Organisationer i systemet:
     - name: "Åhléns"
       website: "www.ahlens.se"
       industry: "Detaljhandel"
     - name: "Ålands Hotell"
       website: "www.alandshotell.se"
       industry: "Hotell & Restaurang"
   - Kontakt i systemet:
     - first name: "Kristina"
       last name: "Bergman"
       company: "Åhléns"
       email: "kristina.bergman@ahlens.se"
       role: "Inköpschef"
     - first name: "Kristina"
       last name: "Berglund"
       company: "Ålands Hotell"
       email: "kristina.berglund@alandshotell.se"
       role: "Hotelldirektör"

## When
- Användaren säger: "Jag vill rapportera ett möte med Kristina på Olens"
- Användaren svarar på följdfråga om företag: "Nej, hon jobbar på Åhléns, varuhuset"

## Then
- Systemet ska identifiera att "Olens" är en fonetisk missuppfattning och föreslå alternativen "Åhléns" eller "Ålands Hotell"
- Systemet ska efter klargörandet registrera rätt företag baserat på användarens förtydligande
- must_contain:
  - "Åhléns"
  - "Kristina Bergman"
  - något av: ["varuhuset", "detaljhandel"]
- must_not_contain:
  - "Ålands Hotell"
  - "Kristina Berglund"
  - "Olens"