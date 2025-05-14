# Testscenario: Komplettera historisk information i CRM-systemet

## Given
- Användaren har tidigare registrerat ett möte med felaktig information
- Testdata:
   - Tidigare registrerad aktivitet i systemet:
     type: "möte"
     date: "2025-05-13, 13:00"
     contact: "Johan Svensson"
     company: "Ericsson"
     notes: "Diskussioner om AI inom produktutvecklingen, uppföljning efter sommaren"
   - Kontakt i systemet:
     first name: "Johan"
     last name: "Svensson"
     company: "Ericsson"
     email: "johan.svensson@ericsson.com"
     role: "Produktchef"
   - Organisation i systemet:
     name: "Ericsson"
     website: "www.ericsson.com"
     industry: "Telekom"

## When
- Användaren säger: "Jag behöver uppdatera anteckningarna för mötet med Johan på Ericsson som jag registrerade igår"
- Användaren svarar på följdfråga om vilket möte: "Det var AI-mötet igår klockan ett"
- Användaren svarar på följdfråga om ändringen: "Lägg till att Johan är tillbaka från sin semester den tionde augusti"

## Then
- Systemet ska identifiera det specifika mötet baserat på kontaktperson, företag och tidpunkt
- Systemet ska bekräfta det aktuella mötet innan ändring sker
- Systemet ska uppdatera anteckningarna genom att lägga till den nya informationen utan att ta bort befintliga anteckningar
- Systemet ska bekräfta att ändringen har genomförts