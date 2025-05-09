# Testscenario: Hantera dubbletter av organisationer

## Given
- Det finns två organisationsposter i systemet som representerar samma företag
- Testdata:
   - organisation: "Ericsson AB"
     id: 1001
     created_date: "2022-01-15"
     contacts: 
       - first_name: "Johan"
         last_name: "Svensson"
         email: "johan.svensson@ericsson.com"
         role: "Inköpschef"
       - first_name: "Anna"
         last_name: "Lindberg"
         email: "anna.lindberg@ericsson.com"
         role: "Projektledare"
     activities: 
       - type: "möte"
         date: "2023-04-12"
       - type: "samtal"
         date: "2023-06-28"
   - organisation: "Ericsson"
     id: 1458
     created_date: [DATUM_3_MÅNADER_SEDAN]
     contacts:
       - first_name: "Maria"
         last_name: "Bergström"
         email: "maria.bergstrom@ericsson.com"
         role: "UX Designer"
     activities: []

## When
- Användaren säger: "Jag vill registrera ett möte med Ericsson från igår"
- Användaren svarar på följdfråga om sammanslagning: "Ja, slå ihop dem"

## Then
- Systemet ska informera användaren om att det finns flera organisationer som matchar "Ericsson"
- Systemet ska också föreslå sammanslagning eftersom följande tre kriterier uppfylls
    - Den nyare organisationen är skapad för mindre än 90 dagar sedan.
    - Den nyare organisationen har högst en kontakt registrerad.
    - Den nyare organisationen har inga händelser (möten, anteckningar, samtal eller meddelanden) registrerade
- Systemet ska överföra kontakten med förnamnet "Maria" och efternamnet "Bergström" från organisationen "Ericsson" med id "1458" till organisationen "Ericsson AB" med id "1001".
- Systemet ska ta bort organisationen "Ericsson" med id "1458"
- Efter sammanslagning ska systemet fortsätta med den ursprungliga uppgiften att registrera mötesinformationen.