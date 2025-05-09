# Testscenario: Hantera saknad organisation vid inrapportering av telefonsamtal

## Given
- Användaren vill rapportera in ett telefonsamtal med en kontakt på en organisation som inte finns i systemet
- Testdata:
   - Organisationer i systemet:
     - name: "Volvo"
       website: "www.volvo.se"
       industry: "Fordonsindustri"
     - name: "Vattenfall"
       website: "www.vattenfall.se"
       industry: "Energi"
     - name: "IKEA"
       website: "www.ikea.se"
       industry: "Detaljhandel"
   - Kontakt (finns ej i systemet):
     first name: "Sofia"
     last name: "Eriksson"
     phone: "070-123 45 67"
     email: "sofia.eriksson@nyaforetaget.se"
     role: "Marknadschef"
   - Organisation (finns ej i systemet):
     name: "Nya Företaget AB"
     website: "www.nyaforetaget.se"
     industry: "Detaljhandel"

## When
- Användaren säger: "Jag vill rapportera ett telefonsamtal med Sofia Eriksson på Nya Företaget AB"
- Användaren svarar på eventuell följdfråga: "Ja, lägg till både organisationen och kontakten"

## Then
- Systemet ska identifiera att organisationen "Nya Företaget AB" inte finns i systemet och fråga om den ska läggas till
- Systemet ska även identifiera att kontakten "Sofia Eriksson" inte finns och fråga om denna ska läggas till
- Systemet ska därefter fortsätta att lägga in informationen om telefonsamtalet.