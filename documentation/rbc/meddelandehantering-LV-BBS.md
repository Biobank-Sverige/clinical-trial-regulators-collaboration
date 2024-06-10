Meddelandehantering Läkemedelsverket - Biobank Sverige
======================================================

Terminologi
-----------

Meddelande:

Paket av information skickat vid en tidpunkt

Ansökan:

En ansökan är samma sak som *case* och defineras av alla meddelanden med samma diarienummer hos Läkemedelsverket.
En ansökan har en orsak (*caseType*) som defineras vid första meddelandet.

Bedömning:

En bedömning är samma sak som *asessment* och görs inom ramen för en ansökan. Kan innehålla
del I, del II eller del I och II.

Meddelandetyper
---------------

Kommunikationen bygger på fasta meddelandetyper som defineras av *messageReasonType* och *caseType*

Följande kombinationer av dessa accepteras när LV skickar meddelanden till BBS:

- Notis: Initial ansökan del I
    - KP-ansökan, multinationell, initialt del I
    - KP-ansökan, mononationell, initialt del I
- Notis: Initial ansökan del I och II
    - KP-ansökan, multinationell, initialt komplett
    - KP-ansökan, mononationell, initialt komplett
    - KP-ansökan, Tillägg av SE som MSC
- Notis: Ändringsansökan
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, mononationell, del I och del II
    - Ändring, nationell, del II
- Notis: Beslut för överflyttad prövning
    - KP-ansökan, multinationell, transitional
    - KP-ansökan, mononationell, transitional
- Notis: Initial ansökan del II
    - Samma som första meddelandet i ansökan
- Notis: Valid ansökan
    - Samma som första meddelandet i ansökan
- Notis: Validerings-RFI till sponsor
    - Samma som första meddelandet i ansökan
- Begäran: Preliminär granskning del I
    - Samma som första meddelandet i ansökan
- Begäran: Preliminär granskning del II
    - Samma som första meddelandet i ansökan
- Notis: Bedömnings-RFI del I till sponsor
    - Samma som första meddelandet i ansökan
- Notis: Bedömnings-RFI del II till sponsor
    - Samma som första meddelandet i ansökan
- Notis: Komplettering från sponsor del I
    - Samma som första meddelandet i ansökan
- Notis: Komplettering från sponsor del II
    - Samma som första meddelandet i ansökan
- Notis: AR och slutsats del I
    - Samma som första meddelandet i ansökan
- Notis: AR och slutsats del II
    - Samma som första meddelandet i ansökan
- Notis: Ansökan dragits tillbaka
    - Samma som första meddelandet i ansökan
- Notis: Ansökan förfallen
    - Samma som första meddelandet i ansökan
- Notis: Ansökan tyst godkännande
    - Samma som första meddelandet i ansökan
- Notis: Beslut för ansökan
    - Samma som första meddelandet i ansökan
- Notis: Informell RFI
    - Samma som första meddelandet i ansökan
- Notis: Beslut för överflyttad prövning
    - KP-ansökan, multinationell, transitional ?
    - KP-ansökan, mononationell, transitiona ?

Följande kombinationer av dessa accepteras när BBS skickar meddelanden till LV:

Dokumenttyper
-------------

Lista över dokumenttyper finns på 
[enumerations](https://github.com/Biobank-Sverige/clinical-trial-regulators-collaboration/blob/main/documentation/common/Enumerationer.md)

Meddelanden som innehåller dokument av typ som inte RBC efterfrågade (markerade med -) kommer att generera en varning i mail till avsändaren, men meddelandet kommer att accepteras.

Meddelanden som innehåller dokument av typ som inte är listad ovan kommer att betraktas som felaktiga (alltså inte tas emot och generera ett felmeddelande)


Processbeskrivning
------------------

För detaljer kring vad som utgör ett korrekt meddelande, se [verifications](verifications.md).

### Livscykel studie

Som första meddelande för en ny studie från LV till BBS accepteras:

- Notis: Initial ansökan del I
    - KP-ansökan, multinationell, initialt del I
    - KP-ansökan, mononationell, initialt del I
- Notis: Initial ansökan del I och II
    - KP-ansökan, multinationell, initialt komplett
    - KP-ansökan, mononationell, initialt komplett
    - KP-ansökan, Tillägg av SE som MSC
- Notis: Beslut för överflyttad prövning
    - KP-ansökan, multinationell, transitional
- Notis: Ansökan tyst godkännande
    - KP-ansökan, multinationell, initialt del I
    - KP-ansökan, multinationell, initialt komplett
    - KP-ansökan, mononationell, initialt del I
    - KP-ansökan, mononationell, initialt komplett
    - KP-ansökan, Tillägg av SE som MSC
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, monongodkännandeationell, del I och del II
    - Ändring, nationell, del II

När ett sådant meddelande är mottaget startas en studie och en ansökan (*case*) och en eller två bedömning(ar) (
*asessment(s)*)

En studie kan inte avslutas.

### Livscykel ansökan

Ansökan skapas i samband med att studien startar (se ovan).

En ansökan kan också skapas med

- Notis: Ändringsansökan
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, mononationell, del I och del II
    - Ändring, nationell, del II

Detta förutsätter att det inte finns någon pågående ansökan för studien.

En ansökan kan innehålla noll eller en bedömning del I och noll eller en bedömning del II.

När ett sådant meddelande är mottaget startas en (ändrings)ansökan (*case*) och en eller två bedömning (ar) (
*assessment(s)*)

Ansökan avslutas med något av:

- Notis: Ansökan dragits tillbaka
- Notis: Ansökan förfallen
- Notis: Ansökan tyst godkännande
- Notis: Beslut för ansökan

### Livscykel bedömning del I

Bedömning del I startar alltid i samband med

- Notis: Initial ansökan del I
- Notis: Initial ansökan del I och II
- Notis: Ändringsansökan
    - Ändring, multinationell, del I
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I
    - Ändring, mononationell, del I och del II
    - KP-ansökan, Tillägg av SE som MSC

Bedömning del I avslutas vid meddelande:

- Notis: AR och slutsats del I
- Notis: Beslut för ansökan
- Notis: Ansökan dragits tillbaka
- Notis: Ansökan förfallen
- Notis: Ansökan tyst godkännande

Övriga meddelanden rörande en bedömning kan bara tas emot när ansökan är aktiv (startad men inte avslutad)

Dessa är:

- Notis: Valid ansökan
- Notis: Validerings-RFI till sponsor
- Begäran: Preliminär granskning del I
- Notis: Bedömnings-RFI del I till sponsor
- Notis: Komplettering från sponsor del I
- Notis: Informell RFI

### Livscykel bedömning del II

Bedömning del II startar alltid i samband med

- Notis: Initial ansökan del II
- Notis: Initial ansökan del I och II
- Notis: Ändringsansökan
    - Ändring, multinationell, del I och del II
    - Ändring, mononationell, del I och del II
    - Ändring, nationell, del II
    - KP-ansökan, Tillägg av SE som MSC

Bedömning del II avslutas vid meddelande:

- Notis: AR och slutsats del II
- Notis: Beslut för ansökan
- Notis: Ansökan dragits tillbaka
- Notis: Ansökan förfallen
- Notis: Ansökan tyst godkännande

Övriga meddelanden rörande en bedömning kan bara tas emot när ansökan är aktiv (startad men inte avslutad)

Dessa är:

- Notis: Valid ansökan
- Notis: Validerings-RFI till sponsor
- Begäran: Preliminär granskning del II
- Notis: Bedömnings-RFI del II till sponsor
- Notis: Komplettering från sponsor del II
- Notis: Informell RFI
