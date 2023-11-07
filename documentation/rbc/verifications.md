# Hantering av meddelanden RBC

Här dokumenterar vi de verifikationer vi gör av inkomna meddelanden samt beskriver den process som förhandsgranskningen av ansökningar följer.

## Om verifikationer

Verifikationer av inkommande meddelanden görs utifrån två principielt skilda perspektiv och med lite olka utfall. 

Till att börja med görs en validering av meddelandets "format", mycket på samma sätt som man normalt verifierar XML eller JSON med deklarerade schemata. Vi använder detta repository som källa för de scheman som används och använder verktyget [medeia-validator](https://github.com/worldturner/medeia-validator)

Fel som upptäcks av schema-validering har i allmänhet tekniska orsaker och leder inte till tillstånd som med enkelhet kan hanteras automatiskt. Utgångspunkten är därför att dessa resulterar i ett tekniskt felmeddelande som skickas till Läkemedelsverket via mail. Typfall av infomration finns listade i apendix A.

Utöver de fel som har med format att göra finns problem som relaterar till det innehålls som strukturen har och även dessa kan klassificeras i två övergripande kategorier; dels sådana som gör att meddelandet inte är internt konsekvent och dels sådana som som inte är konsekventa i relation till det tillstånd som berört ärende har i vårt mottagande system. Ett exempel på det förra är ett meddelande där "MessageReasonType" säger att det är en notis om en ny initial ansökan men "CaseType" säger att det är en ändringsansökan, eller att listade dokument inte finns med i zip-filen. Exempel på det senare är fall där vi får en begäran om preliminär granskning för ett ärende där vi redan har skickat ett uttalade. 

Till sist har vi även regler som definierats av den process vi satt upp för granskningen. Den innebär exempelvis att ett antal handlingar med nödvändighet måste vara tillgängliga för våra utredare när en granskning genomförs. Vi kan med andra ord inte påbörja en förhandsgranskning om vi inte har fått erfoderligt underlag från sponsor, vilket även det är ett fall där tillståndet för ärendet gör att vi inte kan ta emot en begäran om förhandsgranskning.

Även dessa fall kommer att hanteras genom att felmeddelande skickas till Läkemedelsverket, men det finns således en sannolikhet att felets orsak snarare är en fråga om handläggarnas arbete än rena tekniska fel. Rutinen för att avhjälpa fel behöver därför anpassas baserat på innehåll.

Nedan listas de konsistensverifikationer som görs visavi meddelandets interna innehåll och visavi de eventuella tillstånd vi har för prövningen som helhet och för aktuell ansökan. I och med att tillstånden i första hand är kopplade till vilken meddelandetyp som skickas organiseras dokumentationen baserat på meddelandetyp.

## Meddelande

### Notis: Initial ansökan del I och II

### Notis: Initial ansökan del I

### Notis: Initial ansökan del II

### Notis: Ändringsansökan

### Notis: Valid ansökan

### Notis: Validerings-RFI till sponsor

### Begäran: Preliminär granskning del I

### Begäran: Preliminär granskning del II

### Svar: Preliminär granskning del I

### Svar: Preliminär granskning del II

### Notis: Bedömnings-RFI del I till sponsor

### Notis: Bedömnings-RFI del II till sponsor

### Notis: Komplettering från sponsor del I

### Notis: Komplettering från sponsor del II

### Notis: AR och slutsats del I

### Notis: AR och slutsats del II

### Notis: Ansökan dragits tillbaka

### Notis: Ansökan förfallen

### Notis: Ansökan tyst godkännande

### Notis: Beslut för ansökan

### Notis: Informell RFI

### Notis: Beslut för överflyttad prövning
