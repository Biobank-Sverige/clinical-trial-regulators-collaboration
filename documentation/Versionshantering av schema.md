Versionshantering av schema
===========================

I princip använder vi bara en version av schemat för kommunikation. Den version som används ska alltid ha en tagg.

Vi vill dock versionshantera schemat av två anledningar:

- Kunna kommunicera framtida schema i ett verktyg (git)
- RBC behöver kunna läsa in tidigare meddelanden vid t.ex. migrering och behöver därför veta med vilken schemaversion de är skickade.

GIT
---

Vi använder git (https://github.com/Biobank-Sverige/clinical-trial-regulators-collaboration) för versionshantering.

Grenen main är den vi jobbar i, den kommer i praktiken alltid att ha X-SNAPHSOT som version (t.ex. 4-SNAPSHOT när vi releaseat 3.X)

Ändringar föreslås i egna grenar med pull-request tillbaka till main.

För att föreslå en framtida ändring
-----------------------------------

- Se till att du checkat ut senaste main.
- Skapa en gren med ett namn som beskriver ändringen.
- Gör ändringen på din gren.
- Skapa pull-request tillbaka till main.

För att föreslå en ändring som behöver ske direkt ("buggfix")
-------------------------------------------------------------

- Se till att du checkat ut senaste (aktuell) tag.
- Skapa en gren med ett namn som beskriver ändringen.
- Gör ändringen på din gren.
- Meddela övriga om ändringen (obs, ingen pull request).
- När alla är överens om ändringen:
	- Sätt rätt versionsnummer i schemat
	- Tagga committen
	- pusha
	- mergea grenen tillbaka till main (om ändringen även ska vara med i nästa version)
