# Hosting?

Hosts sind das Fundament des Sia-Netzwerks, sie sind essenziell für das Sia-Ökosystem. Hosts stellen Speicherplatz und Bandbreite im Austausch für Siacoin bereit. Ohne Hosts können Nutzer (Renter) keine Daten speichern und Skynet würde nicht funktionieren.

Hosten setzt ein einfaches technisches Verständnis voraus. Basics wie Port-Forwarding, Firewall-Regeln, Datenträgermanagement und das für Sia einzigartige, dezentralisierte Speicherkonzept gilt es zu beherrschen und zu verstehen.

## Uptime
Hosten ist ein verbindliches Engagement. Hosts sind idealerweise 24/7 online, kurze Downtimes sind jedoch akzeptabel. Eine Uptime von über 85 Prozent ist für die meisten Renter akzeptabel. Es ist nicht nur für die Bezahlung wichtig für Hosts, eine konsistente Verfügbarkeit der Nutzerdaten zur Verfügung zu stellen. Lassen sich Hosting-Verbindlichkeiten nicht erfüllen, kann dies zu Verlust von Siacoin führen.

## Hardwarevoraussetzungen
Die Sia-Software läuft auf verschiedenen Geräten, Architekturen und Betriebssystemen. Es stehen offizielle Releases für Windows, Mac und Linux bereit. Es gibt Hosts, die auf Geräten mit geringem Stromverbrauch laufen – wie etwa ein Raspberry Pi – oder gar auf ausgewachsenen High-End-Server-Racks.

**Minimale Anforderungen**
- Dualcore-CPU
- 4GB Arbeitsspeicher
- 60GB SSD
- 4TB HDD

**Empfohlene Anforderungen**
- Quadcore-CPU
- 8GB Arbeitsspeicher
- 256GB SSD
- 4TB HDD
- Linux

Im Idealfall speicherst Du Sias Blockchain (20GB+) und die Metadaten auf einer SSD, um die beste Performance zu erhalten. Nutzerdaten lassen sich auf HDD-Magnetfestplatten speichern, um den besten Kompromiss aus Speicherplatz und Kosten zu erzielen. Sia ist optimiert für Linux, andere Systeme funktionieren, können aber typische Probleme oder Risiken mitbringen.

## Wallet-Bilanz
Hosts müssen ihre Wallet mit Siacoin füllen, um neue Contracts (Verträge) annehmen und Nachweise für sicher hinterlegte Nutzerdaten erbringen zu können. Das Bezahlungssystem für Verträge führt dazu, dass Hoster mehr Sicherheit (Collateral) hinterlegen als sie einnehmen. Es kann bis zu einem Jahr dauern, bis ein Hosting-Server für das Sia-Netzwerk lediglich von den Einnahmen unterhalten werden kann.

„10 US-Dollar in Siacoin sind in der Regel genug für neue Hoster, um zu starten. Der Betrag hängt von den gewählten Preisen und der hinterlegten Sicherheit ab.“

## Einnahmen erzielen
Host generieren Einnahmen, indem Sie Rentern Speicherplatz und Bandbreite zur Verfügung stellen. Renter bezahlen dafür in Siacoin. Am Ende einer Vertragslaufzeit werden die Kosten für den Nutzer (Allowance) an die Wallet des Hosts gesendet. Ein Vertrag über drei Monate bedeutet, dass der Host erst nach dieser Zeit bezahlt wird.

„Derzeit gibt es zwei Bugs, die die Nachverfolgung der Einnahmen erschwert. Host-Einnahmen erscheinen in Sias Transaktionsliste nicht und werden in der Anzeige für Host-Einnahmen ungenau angezeigt. Da die hinterlegte Sicherheit oft die Einnahmen übersteigt, macht es die Kombination beider Bugs sehr schwer, die Einnahmen nachvollziehen zu können.“

## Collateral als Garantie
Um sicherzustellen, dass Hosts Nutzerdaten langfristig zur Verfügung stellen, bieten sie Collateral als Sicherheitsgarantie an. Wenn ein Host nicht belegen kann, dass er Daten wie vereinbart gesichert hat, werden das Collateral und die potenziellen Einnahmen vernichtet. Collateral gilt als Anreiz für ein sicheres und verantwortungsvolles Hosten.

## Storage Proofs
Zum Ende einer Vertragslaufzeit hat der Host die Möglichkeit, einen Beleg für die hinterlegten Daten einzureichen (Storage Proof). Dies belegt, dass der Host Nutzerdaten über den vereinbarten Zeitraum gespeichert hat. Nach Ablauf eines Vertrags stehen als Zeitfenster für den Beleg (proof-window) 24 Stunden (144 Blöcke) zur Verfügung. Kommt der Host dem nicht nach, werden die vom Host hinterlegte Sicherheit und die vom Nutzer hinterlegte Zahlung verbrannt.

„In den meisten Fällen ist es im Interesse des Hosts, einen Beweis für die gespeicherten Daten zu erbringen. Es gibt jedoch Fälle, in denen dies keinen Sinn ergibt: etwa wenn die Kosten für den Beweis den Verlust wegen eines mangelnden Belegs übersteigen.“

## Verträge
Verträge erzeugen einen direkten Zahlungskanal zwischen Host und Renter, um schnell für Speicherplatz und Bandbreite zahlen zu können. Verträge sind Blockchain-gesicherte Vereinbarungen, die automatisch enden, wenn die Vertragslaufzeit ausläuft. So läuft das ganze System transparent und ehrlich.

Hoster und Renter hinterlegen jeweils Siacoin für die gesamte Vertragslaufzeit. Bei der Erstellung eines Vertrags einigen sich Hoster und Renter jeweils auf die Beträge für Collateral sowie Allowance und die Laufzeit ihres Vertrags. Die Sicherheit, zu viel eingezahlte Allowance und die Einnahmen gehen nach Vertragsende automatisch an den rechtmäßigen Eigentümer.

Der Host hat Möglichkeiten, unattraktive Verträge abzulehnen. Der Renter bestimmt die Dauer des Vertrags und wie viel Sicherheit der Host zurücklegen muss. Der Host kann jedoch begrenzen, wie hoch das Collateral für einen einzigen Vertrag und wie lange die Laufzeit maximal sein dürfen. 

**Max Duration** ist die maximale Dauer für einen Vertrag und wird für gewöhnlich in Monaten berechnet: im Durchschnitt drei Monate. Hosts werden nur am Ende einer Vertragslaufzeit bezahlt. Verpflichtet sich ein Host für sechs Monate und kann keinen Beweis für die Speicherung erbringen, werden Einnahmen und das Collateral verbrannt.

**Max Collateral** ist der maximale Betrag, den ein Host als Sicherheit für einen Vertag hinterlegen möchte. Große Vertragsvolumen können die Performance beeinflussen und zu hohe Sicherheiten können die Anzahl der möglichen Verträge beschränken.

**Collateral Budget** ist der Gesamtbetrag in Siacoin für eine Vertragserstellung. Hier gibt es derzeit Bugs, sodass das Budget steigen kann, obwohl noch keine Sicherheit hinterlegt wurde. Diese Einstellung unabhängig von der Wallet-Bilanz zu erhöhen, kann unnötige Neustarts reduzieren.

## Preise
Hoster legen ihre eigenen Preise fest. Der Marktplatz dient dem freien und offenen Wettbewerb zwischen Hostern, um Rentern den bestmöglichen Nutzwert bieten zu können. Historisch bedingt, gab es immer ein Hoster-Überangebot, deswegen sind die Einnahmen vergleichsweise niedrig. Das schließt profitables Hosting jedoch nicht aus. Gut angebundene und reputable Hosts können auch bei höheren Kosten in der Nutzergunst steigen.

**Storage Price** sind die Kosten, um Daten auf einem Host abzulegen. Berechnet werden sie in Siacoin pro Terabyte pro Monat. Zwischen **1 und 2 US-Dollar pro Terabyte** sind ein guter Einstiegspreis. 

**Download Bandwidth Price** sind die Kosten, um Daten von einem Host herunterzuladen – auch bekannt als „egress“. Berechnet werden sie in Siacoin pro Terabyte. Zwischen **1 und 5 US-Dollar pro Terabyte** sind ein guter Einstiegspreis. Mit steigendem Wettbewerb kann es sinnvoll sein, die Preise zu erhöhen – gerade bei einer Gigabit-Anbindung ohne Volumenbegrenzung oder in Regionen mit wenig Hosts.

**Upload Bandwidth Price** sind die Kosten, um Daten auf einen Host hochzuladen – auch bekannt als „ingress“. Berechnet werden sie in Siacoin pro Terabyte. Das Aufnehmen von Daten ist der wichtigste Part beim Hosten. Der Preis sollte niedrig sein oder gar 0 betragen, um möglichst viele Daten aufnehmen zu können.

**Collateral** ist die Höhe der Sicherheit, die ein Host pro Terabyte riskieren muss. Ein guter Anfang sind die **ein- bis zweifache Menge des Storage Price**.

**Contract Price** sind die Kosten, um einen Vertrag mit dem Host zu erstellen. Diese sollten nicht mehr als **1 SC** betragen. Der Contract Price dient dazu, Kosten für Transaktionen oder für Speicherbelege zu decken. Die Standardeinstellung **0,15 SC** reicht im Regelfall. Das Belegen von gesicherten Daten kostet weniger als 0,01 SC.

## Ankündigung
Hosts müssen entweder eine IP- oder eine DNS-Adresse mitteilen, unter der Renter sich mit Hosts verbinden können. Die Ankündigung enthält vier Bestandteile: die IP/Domain, der Port, der öffentliche Schlüssel des Hosts und eine Signatur. Das erleichtert Rentern die Übersicht und die Verbindung zu neuen und Updates für bestehende Hosts. 

Die Ankündigung einer DNS-Adresse wie myhost.hosting.com:9982 antelle einer IP-Adresse hilft Hosts mit dynamischen IPs, multiple Ankündigungen zu vermeiden.

## Ranking
Renter filtern Hosts nach eigenen Vorlieben. Es gibt kein zentrales Ranking-System für Hosts. Das Ranking findet beim Renter nach verschiedenen, eigenen Kriterien statt. In vielen Fällen kann die Bewertung eines Hosts für verschiedene Renter unterschiedlich sein. 

Das ursprüngliche Ranking basierte auf Alter, Preisen, Collateral-Ratio, verfügbarem Speicherplatz und geschätzter Uptime. Wählen Renter einen Host aus, geschieht dies nicht unbedingt nur nach dem Rang. Deswegen sollte der Rang für Hoster keine wichtige Maßgabe sein. Um in die Top 50 zu kommen, müssten Hosts den Großteil ihres Einnahmepotenzials opfern. Es gibt auch Ranking-Systeme, die Transfergeschwindgkeit, Verfügbarkeit und Latenz über den Preis stellen.

## Nützliche Tools für Hoster
- **[SiaStats](https://siastats.info/hosts) / host** | Monitoring und Benchmarks aller Hosts im Netzwerk.
- **[Sia Central](https://troubleshoot.siacentral.com/)** | Problemlösungsübersicht für  Portweiterleitungen, DNS-Auflösung und Verbindungsprobleme.
- **[Sia Host Manager](https://siacentral.com/host-manager)** | Alternative zu Sia-UI mit einem besseren Finanz-Tracking und Fiat-Preisbindung.

## Was nun?
Wenn du als Host starten möchtest, ist es sinnvoll mehr über Renter zu erfahren. Unser Guide führt Dich durch alle Punkte, die du [vor dem Start wissen](https://skynetwiki.tech/before-you-start/) solltest.
