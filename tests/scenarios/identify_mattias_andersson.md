# Testscenario: Identifiera rätt person baserat på roll

## Given
- En testdatamängd med flera personer som heter "Mattias Andersson" på Vattenfall, med olika roller (t.ex. "Projektledare", "Utvecklingschef", "Analytiker").

## When
- Användaren säger: "Jag har träffat Mattias Andersson på Vattenfall."
- Systemet frågar: "Vilken roll har han som du söker?"
- Användaren svarar: "Han är chef för utveckling."

## Then
- Systemet ska svara: "Du menar Mattias Andersson som är Head of Development på Vattenfall." 