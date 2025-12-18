# Processfel

### Vi förväntade oss ett öppet ärende, men ärendet är avslutat.

### Vi förväntade oss ett avslutat ärende, men ärendet är öppet.

### Vi förväntade oss ett godkänt ärende, men ärendet är avslaget.

### Vi förväntade oss ett avslaget ärende, men ärendet är godkänt.

### Vi förväntade oss inte ett redan aktivt ärende, men har hittat ett pågående ärende.

### Vi förväntade oss ett redan aktivt ärende, men hittade inget ärende.

### Den existerande ärendetypen: {actual.caseType} är inte det densamma som meddelandets ärendetyp: {expected.caseType}.

### Existerande LV-diarienummer: {actual.lvDiaryNumber} är inte detsamma som meddelandets LV-diarienummer: {expected.lvDiaryNumber}.

### Vi förväntade oss inte en begäran om granskning av del I på detta ärende.

### Vi förväntade oss inte en begäran om granskning av del II på detta ärende.

### Vi har inte tidigare notifierats om en del I på detta ärende.

### Vi förväntade oss att del I skulle vara avslutad för detta ärende.

### Vi förväntade oss inte att del I skulle vara avslutad för detta ärende.

### Vi har inte tidigare notifierats om en del II på detta ärende.

### Vi förväntade oss att del II skulle vara avslutad för detta ärende.

### Vi förväntade oss inte att del II skulle vara avslutad för detta ärende.

### Ingen bedömnings RFI för del I har mottagits. Således förväntades inte meddelandet.

### Ingen bedömnings RFI för del II har mottagits. Således förväntades inte meddelandet.

### RBC har anmält att vi inte ska granska detta ärende, och tar därför inte emot meddelanden i ärendet.

### Inget dokument av någon av typerna: {docTypes.joinToString { "{it.docType}: {it.name}" }} är inkommet men behövs för uppdrag {action.name}. De typer som är inkomna är " + joinToString { "{it.typeCode}: {it.displayName}

### Alla dokument av typerna: {docTypes.joinToString { "{it.docType}: {it.name}" }} är inte inkomna men behövs för uppdrag {action.name}. De typer som är inkomna är " + joinToString { "{it.typeCode}: {it.displayName}

### Fel antal dokument av typen: {docType.docType}: {docType.name}  har inkommit för uppdrag {action.name}. Vi förväntade oss ett och endast ett (1) dokument men fick $count.

# Tekniska fel schema version 6 och 7
- Could not parse header->version in message.json
    - Json-filen innehåller inte fältet för schemaversion på rätt sätt
- $versionString is not a recognized schema version
    - Json-filen innehåller inte någon av de överenskomna schema versionerna i fältet för schemaversion
- Error parsing schema version from message.json: ${e.message}
    - Generellt fel i JSON tillsammans med detaljerad felinformation från ramverket som läser JSON.
- Sponsor cannot be null
    - Sponsor är null vilket den inte får vara enligt överenskommelse
- Schema validation failed: ${schemaFailure.clearTextDescription}
    - JSON-filen stämmer inte överens med schemat som bestämmer formatet tillsammans med felmeddelande från ramverket som granskar mot schemat
- Failed to decode message.json: ${exception.message}.
    - Generellt fel i filen message.json som är så allvarligt att vi inte ens kan försöka tolka den
- Document '{doc.filename}' has unknown document type code '${doc.documentType.code}'
    - Det finns minst en bifogad fil som har en dokumenttyp som aldrig kommunicerats.
- 'decision' is empty
    - Det saknas värde för beslut, något som alltid ska finnas när det är ett beslut
- 'decisionDetail' is empty
    - Det saknas detaljer för beslut, något som alltid ska finnas när det är ett beslut
- 'caseData/caseType' {message.caseData.specificCaseData.caseType} is invalid for {message.header.messageReasonType.text}
    - Kombinationen av CaseType och MessageReasonType är ogiltig
- Timetable does not contain planned end date for validation notification (TIMETABLE_VALIDATION_NOTIFICATION)
    - Tidtabellen innehåller inte information om datum för när LV ska få påminnelse.