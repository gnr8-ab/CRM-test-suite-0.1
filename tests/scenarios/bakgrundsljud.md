# Testscenario: Hantera bakgrundsprat vid inrapportering av möte

## Given
- Användaren vill rapportera in ett möte med en kontakt
- Det finns bakgrundsprat från andra personer i rummet
- Testdata:
   - first name: "Maria"
     last name: "Jönsson"
     company: "Vattenfall"
     email: "maria.jonsson@vattenfall.se"
     role: "Projektledare"


## When
- Användaren säger: "Hej, jag vill rapportera in ett möte med Maria Jönsson på Vattenfall" samtidigt som en annan person i rummet säger "Jag tänker gå till restaurangen på hörnet för lunch"

## Then
- ALTERNATIV 1 (filtrering): Systemet ska svara: "Jag har noterat att du har träffat Maria Jönsson på Vattenfall. Vill du lägga till detaljer om mötet?"
  - must_not_contain:
    - "lunch"
    - "restaurang"
    - "hörn"
  - must_contain:
    - "Maria"
    - "Jönsson"
    - "Vattenfall"
- ALTERNATIV 2 (fråga): Systemet ska svara: "Nu hörde jag en del saker som jag inte tror är en del av rapporteringen. Kan du säga det igen?"