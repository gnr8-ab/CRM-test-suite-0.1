# Testscenario: Hantera ovanlig stavning vid sökning efter kontakt

## Given
- Användaren vill rapportera in ett möte med en kontakt som har ett namn med ovanlig stavning
- Testdata:
   - first name: "Billie"
     last name: "Johansson"
     company: "Volvo"
     email: "billie.johansson@volvo.se"
     role: "UX Designer"

## When
- Användaren säger: "Jag vill rapportera ett möte med Billy Johansson på Volvo"

## Then
- Systemet ska svara: "Jag har noterat att du har träffat Billie Johansson på Volvo. Vill du lägga till detaljer om mötet?" 
- must_contain:
    - "Billie"