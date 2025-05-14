# Testscenario: Hantera företagsnamn som uttalas annorlunda än de stavas

## Given
- Användaren vill rapportera ett möte med en kontakt på ett företag vars namn uttalas annorlunda än det stavas
- Systemet har tidigare inte lärt sig att "Hennes och Mauritz" är samma som "H&M"
- Testdata:
   - Organisationer i systemet:
     - name: "H&M"
       website: "www.hm.com"
       industry: "Detaljhandel"
   - Kontakt i systemet:
     - first name: "Emma"
       last name: "Lindberg"
       company: "H&M"
       email: "emma.lindberg@hm.com"
       role: "Hållbarhetschef"

## When
- Användaren säger: "Jag vill registrera ett möte med Emma Lindberg på Hennes och Mauritz"
- Användaren svarar på följdfråga om företag: "Jag menar H&M, det kan stå som H&M i systemet"

## Then
- Systemet ska inte automatiskt känna igen "Hennes och Mauritz" som "H&M" i den första interaktionen
- Systemet ska efter användarens förtydligande koppla samman "Hennes och Mauritz" med "H&M" och lagra denna koppling
- Systemet ska sedan använda denna information för att registrera mötet korrekt
- Systemet ska lära sig kopplingen för framtida interaktioner
