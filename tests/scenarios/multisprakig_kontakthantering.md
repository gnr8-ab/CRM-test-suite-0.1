# Testscenario: Hantera multispråkig kontakthantering vid röstinmatning

## Given
- Användaren vill rapportera ett möte med en kontakt som har ett utländskt namn
- Testdata:
   - Kontakt i systemet:
     first name: "François"
     last name: "Müller-Jørgensen"
     company: "Schneider Electric"
     email: "francois.muller-jorgensen@schneider-electric.com"
     role: "Head of Business Development"
   - Organisation i systemet:
     name: "Schneider Electric"
     website: "www.schneider-electric.com"
     industry: "Energi"

## When
- Användaren säger: "Jag vill registrera ett möte med Fransoa Muller-Jorgensen på Schneider"
- Användaren svarar på eventuell följdfråga: "Ja, det är François med ç och Müller med ü"

## Then
- Systemet ska identifiera att kontaktens namn innehåller specialtecken/diakritiska tecken som kan missuppfattas vid röstinmatning
- Systemet ska föreslå matchande kontakter med korrekt stavning av namnen
- Systemet ska efter bekräftelse använda den korrekta stavningen av kontaktens namn i sin registrering
- must_contain:
  - "François"
  - "Müller-Jørgensen"
  - "Schneider Electric"
- must_not_contain:
  - "Fransoa"
  - "Muller" utan diakritiska tecken
  - "Jorgensen" utan diakritiska tecken