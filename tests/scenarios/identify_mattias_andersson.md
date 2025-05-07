# Testscenario: Identifiera rätt person baserat på roll

## Given
- Testdata:
   - first name: "Mattias"
     last name: "Andersson"
     company: "Vattenfall"
     email: "mattias.andersson@vattenfall.se"
     role: "Project Manager"
   - first name: "Mattias"
     last name: "Andersson"
     company: "Vattenfall"
     email: "mattias.g.andersson@vattenfall.se"
     role: "Head of Development"

## When
- Användaren säger: "Jag har träffat Mattias Andersson på Vattenfall."
- Systemet frågar: "Jag ser att det finns flera Mattias Andersson på Vattenfall. Vilken roll har den Mattias som du menar?"
- Användaren svarar: "Han är chef för utveckling."

## Then
- Systemet ska svara: "Menar Mattias Andersson som är Head of Development på Vattenfall?" 