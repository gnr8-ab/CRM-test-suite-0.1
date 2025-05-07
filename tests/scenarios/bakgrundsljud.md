# Testscenario: Hantera bakgrundsprat vid inrapportering av möte

## Given
- Användaren vill rapportera in ett möte med en kontakt
- Det finns bakgrundsprat från andra personer i rummet
- Testdata:
     first name: "Maria"
     last name: "Jönsson"
     email: "maria.jonsson@vattenfall.se"
     company: "Vattenfall"
     role: "Projektledare"


## When
- Användaren säger: "Hej, jag vill rapportera in ett möte med Maria Jönsson på Vattenfall" samtidigt som en annan person i rummet säger "Jag tänker gå till restaurangen på hörnet för lunch"

## Then
- ALTERNATIV 1 (filtrering): Systemet ska svara: "Jag har noterat att du har träffat Maria Jönsson på Vattenfall. Vill du lägga till detaljer om mötet?"
- ALTERNATIV 2 (fråga): Systemet ska svara: "Jag uppfattade att du vill rapportera ett möte med Maria Jönsson på Vattenfall, men jag hörde också något om lunch. Var det något mer du ville rapportera om mötet?" 