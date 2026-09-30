# Jousaali-broneering
Liikmed broneerivad treeninguaega, treener näeb broneeringute nimekirja.
Tegijad: [Nikita Popovych], [Nikita Kirejev] Grupp [NPTV24]

## Kasutajad ja nõuded

Süsteemil on kaks rolli: liige ja treener. Kuus kasutajalugu on GitHubi Issues all ning tähtsamad nõuded on märgitud must sildiga. 

# Arendusmudel

Valisime inkrementaalse mudeli, sest nii saab süsteemi teha osade kaupa. Kõigepealt teeme vabade aegade vaatamise ja treeningu broneerimise. Seejärel lisame broneeringute tühistamise ja treenerile registreerunud liikmete nimekirja. Nii saab iga osa eraldi kontrollida ja süsteemi järk-järgult parandada. Kosemudel meile ei sobi, sest arendamise käigus võivad tekkida muudatused ja uued nõuded.

## Diagrammid

![Kasutusjuhud](diagramm/Diagramm.png)

![Klassid](diagramm/2Diagramm.png)

# Inkrementaalselt või iteratiivselt ja miks
Tegime maketi inkrementaalselt, sest nii saime ühe ekraani valmis teha ja kontrollida enne teise ekraani tegemist.

# Kuidas me töötasime

Tahvli alguse ja lõpu pildid asuvad kaustas protsess/.

Kõige paremini läks ülesannete jagamine ja koos töötamine. Kõige raskem oli GitHubi harude ja pull requestide kasutamine. Järgmisel korral planeeriksime töö etapid varem ja jagaksime ülesanded täpsemalt.


# Mermaid Class Diagramm CODE
```mermaid
classDiagram
    class Klient {
        -liikmeID: int
        -nimi: String
        -email: String
        +vaataBroneeringuid()
        +broneeriAeg()
        +tühistaBroneering()
    }
    class Broneering {
        -int broneeringuId
        -Date kuupäev
        -String staatus
        +looBroneering()
        +tühista()
        +kinnita()
    }
    class TreeninguAeg{
        -treeninguID: int
        -kuupäev: Date
        -vaba: Boolean
        -kellaaeg: Time
        +muudaAega()
        +kontrolliSaadavust()
        +kuvaRegistreerunudLiikmed()
    }
    class Treener{
        -treenerID: int
        -nimi: String
        -email: String
        +muudaTreeninguAeg()
        +vaataRegistreerinuid()

    }
    Klient  -->  Broneering
    Broneering --> TreeninguAeg
    TreeninguAeg <-- Treener
```
# Diff
Diff näitab, millised read ja muudatused lisati, kustutati või muudeti kahe versiooni vahel.

## Vahendid
Meie süsteemi jaoks valime draw.io, sest see on tasuta ja seda on lihtne kasutada. Me ei vali Mermaidit, sest selle õppimine on keerulisem ja koostöö on piiratum. Kui meeskond oleks suurem, valiksime samuti draw.io, sest seal on mugav koos diagramme luua.
