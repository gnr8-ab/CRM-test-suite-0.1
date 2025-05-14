# Testscenario: Koppla samman flera kontakter från olika företag i samma möte

## Given
- Användaren vill rapportera ett möte där flera kontakter från olika företag deltog
- Testdata:
   - Kontakter i systemet:
     - first name: "Johanna"
       last name: "Bergström"
       company: "Skanska"
       email: "johanna.bergstrom@skanska.se"
       role: "Projektchef"
     - first name: "Anders"
       last name: "Lindqvist"
       company: "NCC"
       email: "anders.lindqvist@ncc.se"
       role: "Byggchef"
     - first name: "Maria"
       last name: "Öberg"
       company: "Peab"
       email: "maria.oberg@peab.se"
       role: "Hållbarhetschef"
   - Organisationer i systemet:
     - name: "Skanska"
       website: "www.skanska.se"
       industry: "Bygg"
     - name: "NCC"
       website: "www.ncc.se"
       industry: "Bygg"
     - name: "Peab"
       website: "www.peab.se"
       industry: "Bygg"

## When
- Användaren säger: "Jag vill registrera ett projektmöte med Johanna på Skanska, Anders från NCC och Maria på Peab från igår"
- Användaren svarar på eventuell följdfråga: "Ja, alla tre var med på mötet, det handlade om samarbetet för det nya sjukhusbygget"

## Then
- Systemet ska identifiera alla tre kontakter från olika företag
- Systemet ska förstå att alla tre var deltagare i samma möte
- Systemet ska korrekt registrera ett möte med kopplingar till alla tre kontakter och deras respektive organisationer