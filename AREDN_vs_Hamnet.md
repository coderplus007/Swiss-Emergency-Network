# Vergleich AREDN vs. HAMNET -- Technische Vor- und Nachteile

**Einleitung:** AREDN (*Amateur Radio Emergency Data Network*) und
HAMNET (*Highspeed Amateurradio Multimedia NETwork*) sind zwei
Hochgeschwindigkeits-Datennetzwerke im Amateurfunk. Beide ermöglichen
IP-basierte Kommunikation über Funk, unterscheiden sich jedoch in
Architektur und Einsatzschwerpunkt. Im Folgenden werden die Vor- und
Nachteile beider Systeme hinsichtlich **(1)** Notfallkommunikation,
**(2)** Datenübertragung, **(3)** Hardwarekompatibilität und **(4)**
Bandbreite technisch gegenübergestellt.

# Übersicht der Unterschiede

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Aspekt**                   **AREDN (Notfunk-Mesh-Netz)**                                                                                                                                                           **HAMNET (stationärer Backbone)**
  ---------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Notfallkommunikation**     *Vorteile:* Schneller ad-hoc Aufbau („Plug-and-Play"), vermaschtes **Mesh-Netz** mit automatischer Routenfindung und Ausfallsicherheit                                                  *Vorteile:* **Festes Netzwerk** mit geplanten Linkstrecken; oft bereits vorab installiert und durch USV stromausfallsicher ([HAMNET --
  *(Zuverlässigkeit & Einsatz  ([AREDN](https://uska.ch/aredn/?lang=de#:~:text=Furthermore%2C%20the%20network%20is%20designed,fails%2C%20an%20alternative%20is%20routed)). Unabhängig von vorhandener Infrastruktur,   Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=erm%C3%B6glichen.%20,kommerziellen%20Netzen%20durch%20%2031)). Hohe Reichweiten durch Richtfunk; sofort
  in Krisen)*                  flexible Einsetzbarkeit vor Ort (tragbare Knoten mit Akku). *Nachteile:* Begrenzte Reichweite pro Funkstrecke (Line-of-Sight nötig); bei wenigen Knoten ggf. einzelne Ausfallpunkte.    nutzbar, sofern im Krisengebiet vorhanden. *Nachteile:* Aufbau neuer Verbindungen erfordert Planung (Ausrichten von Antennen, IP-Koordination). Bei Ausfall von Knoten
                               Gesamtleistung sinkt bei vielen Teilnehmern auf einem Kanal.                                                                                                                            ohne Redundanz können Teilnetze isoliert werden (weniger selbstheilend als Mesh).

  **Datenübertragung**         **Datenraten:** Typ. bis \~10--30 Mbit/s effektiv (je nach Kanalbreite) ([Einführung in HAMNET - Datennetz für                                                                          **Datenraten:** Pro Richtfunk-Link bis zu \~65 Mbit/s brutto möglich ([HAMNET --
  *(Datenraten, Protokolle,    HAMs](https://www.darc.de/fileadmin/filemounts/distrikte/p/ortsverbaende/18/Hamnet/Einfuehrung_in_HAMNET_2016-02-05_e.pdf#:~:text=%E2%80%A2%20Effektive%20Datenrate%20ca.%2050,11n)),   Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=k%C3%B6nnen%20bestimmte%20handels%C3%BCbliche%2C%20aber%20in,kann%20bis%20zu%2065%C2%A0MBit%2Fs%20betragen))
  Stabilität)*                 maximal \~54 Mbit/s (802.11n, 20 MHz) pro Link ([AREDN](https://uska.ch/aredn/?lang=de#:~:text=AREDN%20is%20a%20meshed%20radio,alternative%20to%20conventional%20Internet%20access)).   (mit moderner 802.11-Technik, oft 5/10 MHz Kanäle für Reichweite). Durch dedizierte Links bleibt der Datendurchsatz über mehrere Hops hinweg hoch (jede Strecke nutzt
                               **Protokolle:** Vollständige IPv4/IPv6-Unterstützung; dynamisches Routing (OLSR) für Ad-hoc-Netze                                                                                       eigene Frequenz). **Protokolle:** Standard-IP-Netz (44.x.x.x-Adressraum ([HAMNET --
                               ([AREDN](https://uska.ch/aredn/?lang=de#:~:text=1,custom%20developments%20can%20be%20built)) ([AREDN](https://uska.ch/aredn/?lang=de#:~:text=2,hoc%20networks)). Unterstützt alle       Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=HAMNET%20arbeitet%20auf%20Basis%20der,4))); meist feste Routen oder Routingprotokolle (z.B. OSPF/BGP) zur
                               gängigen IP-Dienste (HTTP, FTP, VoIP, Video, E-Mail, Chat etc.) -- nahezu jede Internet-Anwendung ist möglich, sofern konform mit AFu-Regeln                                            Vernetzung. Trägt zahlreiche Anwendungen: von VoIP/EchoLink über Winlink-E-Mail bis hin zu Video (DATV) und APRS ([HAMNET --
                               ([AREDN](https://uska.ch/aredn/?lang=de#:~:text=emergency%20radio%20use%20of%20this,are%20easy%20to)) ([Beginner's Guide --- AREDN® Documentation latest                                Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=%C3%9Cber%20das%20Netzwerk%20werden%20eine,1)). **Stabilität:** Sehr stabile Punkt-zu-Punkt-Verbindungen dank
                               documentation](http://docs.arednmesh.org/en/latest/arednHow-toGuides/beginner-guide.html#:~:text=By%20loading%20the%20AREDN%C2%AE%20firmware,you%20can%20put%20on%20the)).              Richtantennen und exklusiver Frequenzen (wenig Störungen ([HAMNET -- Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Es%20werden%20im%20Rahmen%20von,6))).
                               **Stabilität:** Verbindungen stabil bei guter Funkstrecke; Mesh passt sich an Linkqualität an und wählt stets die beste Route                                                           Redundante Links müssen geplant werden; bei Single-Link-Ausfall ist kein automatisches Ausweichen möglich, sofern keine Alternativroute vordefiniert.
                               ([AREDN](https://uska.ch/aredn/?lang=de#:~:text=Furthermore%2C%20the%20network%20is%20designed,fails%2C%20an%20alternative%20is%20routed)). Mehrere Hops erhöhen Latenz und verringern  
                               Durchsatz (CSMA/CA-Funkzugriff).                                                                                                                                                        

  **Hardwarekompatibilität**   Setzt auf **COTS-WLAN-Hardware** (Ubiquiti, TP-Link, Mikrotik, GL-iNet etc.) mit AREDN-Firmware ([Selecting Radio Hardware --- AREDN® Documentation latest                              Nutzt **handelsübliche WLAN-Router/Hardware**, die auf Amateurfunk-Frequenzen umgestellt werden können ([HAMNET --
  *(Nutzbare Hardware &        documentation](http://docs.arednmesh.org/en/latest/arednGettingStarted/selecting_devices.html#:~:text=One%20of%20the%20best%20sources,LINK%2C%20and%20Ubiquiti%20Networks)). Viele      Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Die%20Daten%20sollen%20haupts%C3%A4chlich%20per,kann%20bis%20zu%2065%C2%A0MBit%2Fs%20betragen)) (z.B.
  Flexibilität)*               outdoor WLAN-Router (2,4/5 GHz) lassen sich flashen und als Knoten einsetzen. Sehr flexibel: kostengünstige Geräte (\< €100) können spontan ins Netz gebracht werden; integrierte oder  Mikrotik, Ubiquiti mit angepasster Config oder Firmware). Typischerweise werden Richtfunkstrecken mit Outdoor-Geräten (Routerboard, Rocket, LHG usw.) aufgebaut, die
                               externe Antennen je nach Bedarf. Firmware bietet Web-UI und automatische IP-Konfiguration, wodurch keine manuelle Rollenverteilung (AP/Client) nötig ist                                fest installiert sind. Flexibilität durch Vielfalt an Geräten, aber Einrichtung erfordert Fachkenntnis (zentrale IP-Vergabe, Router-Konfiguration). Integration
                               ([AREDN](https://uska.ch/aredn/?lang=de#:~:text=Classic%20Hamnet%3A%20Routes%20are%20planned%2C,and%20which%20as%20a%20station)).                                                       kabelgebundener Links und Internet-Gateways möglich (Hybridnetz). Keine einheitliche Firmware -- dafür Anpassung an Standorte optimiert (z.B. proprietäre TDMA-Modi
                                                                                                                                                                                                                       wie AirMax/NV2 zur Leistungssteigerung auf einzelnen Links).

  **Bandbreite**               Verwendet Amateurfunk-Bänder im **2,4 GHz**, **3,4 GHz** und **5,6--5,8 GHz** Bereich (je nach Region) ([Beginner's Guide --- AREDN® Documentation latest                               Amateur Radio Emergency Data Network\](<https://www.arednmesh.org/content/max-throughput#:~:text=The%20max%20data%20rate%20,is%20802>)). In Praxis meist 10 MHz für
  *(Frequenzspektrum &         documentation](http://docs.arednmesh.org/en/latest/arednHow-toGuides/beginner-guide.html#:~:text=By%20loading%20the%20AREDN%C2%AE%20firmware,you%20can%20put%20on%20the)). Optional     gutes Verhältnis von Reichweite und Datenrate. **Netzkapazität:** Alle Knoten teilen sich einen Kanal -- ideal für Mesh-Broadcast (jeder sieht jeden), aber begrenzte
  nutzbare Kanalbreite)*       auch 900 MHz (33 cm-Band, USA) für spezielle Anwendungen. Kanalbandbreiten flexibel einstellbar: 5, 10 oder 20 MHz üblich (neuere Geräte auch 40 MHz). Dadurch Anpassung von Reichweite Gesamtkapazität bei hohem Datenaufkommen. Für bandbreitenintensive Dienste (HD-Video etc.) nur auf kurzen Distanzen oder separaten Links (z.B. 5 GHz) geeignet.
                               vs. Durchsatz: z.B. \~130 Mbit/s brutto \@20 MHz vs. 32 Mbit/s \@5 MHz (\[Max throughput?                                                                                               
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Notfallkommunikation (Zuverlässigkeit & Geschwindigkeit in Krisen)

**AREDN:** Der Schwerpunkt von AREDN liegt auf schneller
**Notfallkommunikation**. Die Knoten bilden ein vermaschtes Ad-hoc-Netz,
in dem sich alle Stationen auf einer gemeinsamen Frequenz automatisch
verbinden und erkennen. Ein optimiertes Routing-Protokoll (OLSR)
ermittelt ständig die beste Route zwischen den Knoten und wechselt bei
Ausfall einer Verbindung selbstständig auf alternative Pfade
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=Furthermore%2C%20the%20network%20is%20designed,fails%2C%20an%20alternative%20is%20routed)).
Dadurch ist im Krisenfall ein äußerst zügiger Netzaufbau möglich --
**„anschließen und loslegen"** ohne zentrale Koordination
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=For%20use%20in%20emergency%20radio%2C,network%20and%20are%20immediately%20accessible)).
Jede Node kann binnen Minuten in Betrieb gehen, etwa um vor Ort
Einsatzkräfte zu vernetzen, selbst wenn Internet und Telefon ausgefallen
sind
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=AREDN%20is%20a%20meshed%20radio,alternative%20to%20conventional%20Internet%20access)).
Die Mesh-Struktur erhöht die Zuverlässigkeit: Fällt ein Knoten aus, kann
der Datenverkehr über andere Wege geleitet werden, sofern vorhanden.
Nachteil dieser One-Frequency-Mesh-Topologie ist allerdings, dass das
Netz auf ausreichende Funkabdeckung angewiesen ist -- einzelne
Funkstrecken (z.B. über größere Distanzen) können zum **Single Point of
Failure** werden, wenn keine alternativen Routen existieren. Insgesamt
bietet AREDN in Notfällen eine hohe Ausfallsicherheit und sofortige
Einsetzbarkeit auch in abgelegenen Gebieten, solange genügend Knoten und
Sichtverbindungen vorhanden sind.

**HAMNET:** HAMNET wurde als **Backbone-Infrastruktur** konzipiert, die
in Notlagen als Rückfallebene dienen kann ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=erm%C3%B6glichen.%20,kommerziellen%20Netzen%20durch%20%2031)).
Vorteile ergeben sich vor allem dort, wo das HAMNET bereits ausgebaut
ist: Durch fest installierte **Richtfunkstrecken** auf hohen Standorten
(z.B. Amateurfunk-Relais auf Bergen oder Türmen) können weite Gebiete
abgedeckt werden. Ist diese Infrastruktur intakt, stehen den
Einsatzkräften sofort **hochkapazitäre Datenverbindungen** zur Verfügung
-- unabhängig von kommerziellen Netzen ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=erm%C3%B6glichen.%20,kommerziellen%20Netzen%20durch%20%2031)).
Viele Knotenpunkte sind mit Notstrom (USV) ausgestattet, sodass sie auch
bei Stromausfall weiterlaufen ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=erm%C3%B6glichen.%20,kommerziellen%20Netzen%20durch%20%2031)).
Die Zuverlässigkeit der Links ist hoch, da sie in der Regel auf
bewährter Technik und festen Antenneninstallationen beruhen. Allerdings
ist HAMNET weniger „mobil": Einen neuen Standort ad-hoc anzubinden
erfordert zunächst Kenntnis über nahe HAMNET-Knoten und das Ausrichten
einer Richtfunkantenne dorthin. Ebenso müssen IP-Adressen und Routen
koordiniert werden, was in der **Akutphase** Zeit und Expertise
verlangt. Bei Ausfall einzelner Backbone-Strecken hängt die
Kommunikationsfähigkeit davon ab, ob alternative Routen (durch
redundante Links oder Umwege) vorgesehen sind. In gut geplanten
HAMNET-Regionen existieren Ringstrukturen oder mehrere Pfade zwischen
Knoten, sodass der Ausfall eines Links kompensiert werden kann -- dies
muss jedoch im Voraus eingerichtet sein (automatisches Meshing wie bei
AREDN erfolgt nicht). Zusammengefasst ist HAMNET in Krisensituationen
sehr leistungsfähig und **schnell einsatzbereit, wo vorhanden**, jedoch
weniger flexibel bei der spontanen Erweiterung ins Katastrophengebiet
hinein.

# Datenübertragung (Datenraten, unterstützte Protokolle, Verbindungsstabilität)

**AREDN:** AREDN-Knoten nutzen modifizierte WLAN-Technik und erreichen
je nach Hardware und Kanalbandbreite typische **Durchsatzraten** im
zweistelligen Mbit/s-Bereich. Unter optimalen Bedingungen (z.B. 20 MHz
Kanal, MIMO) sind bis zu \~54 Mbit/s netto realisierbar
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=AREDN%20is%20a%20meshed%20radio,alternative%20to%20conventional%20Internet%20access))
-- entsprechende Tests mit 802.11n zeigen \~130 Mbit/s brutto pro Link
und etwa 20--30 % Nutzdaten-Durchsatz ([Max throughput? \| Amateur Radio
Emergency Data
Network](https://www.arednmesh.org/content/max-throughput#:~:text=The%20max%20data%20rate%20,is%20802)).
In der Praxis wird oft mit 5 oder 10 MHz Bandbreite gearbeitet, was
Reichweite und Störsicherheit erhöht, aber ca. proportional geringere
Bitraten ergibt (z.B. \>10 Mbit/s effektiv bei 10 MHz) ([Einführung in
HAMNET - Datennetz für
HAMs](https://www.darc.de/fileadmin/filemounts/distrikte/p/ortsverbaende/18/Hamnet/Einfuehrung_in_HAMNET_2016-02-05_e.pdf#:~:text=%E2%80%A2%20Effektive%20Datenrate%20ca.%2050,11n)).
Diese Geschwindigkeiten sind für die meisten Notfunk-Anwendungen
ausreichend (E-Mail, VoIP, Web, moderate Videoübertragung).
**Netzwerkprotokolle:** AREDN ist vollständig IP-basiert
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=1,custom%20developments%20can%20be%20built)).
Jeder Knoten läuft unter einer angepassten OpenWRT-Linux-Firmware mit
Routing-Daemon (OLSR), der die IP-Pakete im Mesh weiterleitet.
Unterstützt werden IPv4 (und experimentell IPv6) sowie alle gängigen
Transportprotokolle (TCP, UDP etc.). Damit können praktisch **alle
Dienste** betrieben werden, die man aus normalen Netzwerken kennt -- von
Webservern über Chat und Datenübertragung bis hin zu Video-Streams und
Telefonie
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=emergency%20radio%20use%20of%20this,are%20easy%20to))
([Beginner's Guide --- AREDN® Documentation latest
documentation](http://docs.arednmesh.org/en/latest/arednHow-toGuides/beginner-guide.html#:~:text=By%20loading%20the%20AREDN%C2%AE%20firmware,you%20can%20put%20on%20the)).
Beispielsweise lassen sich VoIP-Telefonanlagen, Webcam-Feeds oder
Winlink-E-Mail-Knoten ins AREDN-Netz integrieren. Die einzige
Einschränkung kommt von den gesetzlichen Auflagen des Amateurfunks (kein
verschlüsselter Verkehr außer zur Steuerung, Rufzeichenkennzeichnung
etc.), was jedoch durch entsprechende Konfiguration (z.B.
unverschlüsselte Dienste) berücksichtigt wird. **Stabilität:** Aufgrund
der Verwendung von lizenzierten AFu-Frequenzen außerhalb der
überlaufenen WLAN-Kanäle treten weniger Störungen durch Fremdnetzwerke
auf ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Es%20werden%20im%20Rahmen%20von,6)).
Die Verbindungen sind stabil, solange ausreichendes
Signal-Rausch-Verhältnis besteht; die Firmware passt die Modulation bei
schwächerem Signal automatisch an, um die Verbindung aufrechtzuhalten.
In einem Mesh teilen sich alle Nodes das Medium per CSMA/CA (ähnlich
WLAN), daher können bei vielen aktiven Knoten Kollisionen und Overhead
(z.B. Routing-Updates) den nutzbaren Durchsatz pro Knoten verringern.
Insgesamt bietet AREDN jedoch robuste **Link-Adaption** und Ausgleich
von Einzelstrecken-Schwächen durch seine Mehrwegefähigkeit.

**HAMNET:** Das HAMNET nutzt ebenfalls WLAN-Datenfunk, allerdings meist
in Form von **dedizierten Punkt-zu-Punkt oder Punkt-zu-Mehrpunkt
Verbindungen**. Jede Funkstrecke kann daher nahe an ihrer individuellen
Maximalrate betrieben werden, ohne dass gleichzeitiger Kanalbetrieb
mehrerer Stationen diese Rate teilt. Übliche Installationen verwenden
802.11a/n Technik mit **Brutto-Datenraten** bis 54 Mbit/s (802.11a) bzw.
höher mit 802.11n/ac. Die Wikipedia gibt eine Datenübertragungsrate bis
zu **65 MBit/s** pro Verbindung an ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=k%C3%B6nnen%20bestimmte%20handels%C3%BCbliche%2C%20aber%20in,kann%20bis%20zu%2065%C2%A0MBit%2Fs%20betragen))
-- dies entspricht einem 20 MHz breiten 802.11n-Kanal mit einer
MIMO-Antenne. Effektiv sind auf einer 10 MHz-Strecke typisch
\>10--20 Mbit/s Nutzdatendurchsatz erreichbar ([Einführung in HAMNET -
Datennetz für
HAMs](https://www.darc.de/fileadmin/filemounts/distrikte/p/ortsverbaende/18/Hamnet/Einfuehrung_in_HAMNET_2016-02-05_e.pdf#:~:text=%E2%80%A2%20Effektive%20Datenrate%20ca.%2050,11n)),
was für breitbandige Anwendungen im Amateurfunk (z.B. ATV-Übertragungen)
ausreichend ist. **Protokolle:** HAMNET ist ein vollwertiges IP-Netzwerk
(sowohl IPv4 als auch zunehmend IPv6) und integriert sich in den
globalen Amateurfunk-**AMPRNet**-Adressraum 44.0.0.0/8 ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=HAMNET%20arbeitet%20auf%20Basis%20der,4)).
Zwischen den Knoten kommen oft Routing-Protokolle wie OSPF oder BGP zum
Einsatz, um die Vielzahl von festen Links zu einem zusammenhängenden
Netzwerk zu verbinden (HAMNET wird teils als autonomes System betrieben
([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=HAMNET%20stellt%20ein%20Netzwerk%20zwischen,Anwendungen%20und%20Nutzer%20entstehen%20kann))).
Für Benutzer bedeutet das, dass **ähnliche Dienste wie im Internet** zur
Verfügung stehen. Tatsächlich werden im HAMNET zahlreiche Anwendungen
realisiert, u.a. **EchoLink**-VoIP für Relaisanbindungen,
**Winlink2000** für E-Mail über Funk, Instant Messaging/Chat-Server,
VoIP-Telefonie, **DATV/IP-TV**-Streaming und APRS-Gateways ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=%C3%9Cber%20das%20Netzwerk%20werden%20eine,1)).
Im Grunde kann jede IP-Anwendung eingesetzt werden, solange sie den
Amateurfunk-Richtlinien entspricht. **Stabilität:** Dank fester
Richtfunkverbindungen auf exklusiven Frequenzen (oft knapp außerhalb der
WLAN-Bereiche) sind HAMNET-Links in der Regel sehr stabil und über Jahre
in Betrieb. Weder konkurrierende WLANs noch viele Nutzer auf dem
gleichen Kanal stören die Verbindung ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Es%20werden%20im%20Rahmen%20von,6)).
Die Latenzzeiten bleiben niedrig, da jedes Paket nur wenige Hops über
definierte Strecken nimmt, und es gibt keinen unnötigen Mesh-Overhead.
Bei extremen Wetterbedingungen (Regen, Schnee) können sehr hochfrequente
Links (5 GHz) in der Reichweite etwas beeinträchtigt werden, was durch
Link-Budget-Reserven und adaptive Modulation ausgeglichen wird. Sollte
dennoch ein Link ausfallen (Hardwaredefekt, Sturm, Stromausfall ohne
Backup), hängt die Netzstabilität von vorhandenen Ausweichrouten ab. In
vielen HAMNET-Regionen werden kritische Standorte mit **Redundanz**
(zweiten Link zu anderem Knoten) geplant, sodass der Verkehr umgeleitet
werden kann. Wo das nicht der Fall ist, führt ein Ausfall allerdings zum
Abbruch der Verbindung für die abhängigen Teilnehmer -- hier zeigt sich
der Nachteil, dass HAMNET nicht von selbst neue Routen „findet", sondern
auf vordefinierte Infrastruktur angewiesen ist.

# Hardwarekompatibilität (verfügbare Hardware & Flexibilität der Systeme)

**AREDN:** Ein großer Vorteil von AREDN ist die Nutzung
**kostengünstiger, handelsüblicher Hardware**. Das Projekt stellt
Firmware bereit, die auf dutzende Modelle von WLAN-Geräten aufgespielt
werden kann ([Selecting Radio Hardware --- AREDN® Documentation latest
documentation](http://docs.arednmesh.org/en/latest/arednGettingStarted/selecting_devices.html#:~:text=One%20of%20the%20best%20sources,LINK%2C%20and%20Ubiquiti%20Networks)).
Darunter sind Outdoor-Router und Access Points verschiedener Hersteller
(z.B. Ubiquiti NanoStation/Bullet, TP-Link CPEs, Mikrotik hAP/SXT und
sogar kleine GL-iNet Router) -- also Geräte, die eigentlich für WLAN
oder WISP-Betrieb gedacht sind. Durch das Flashen der AREDN-Firmware
werden sie in vollwertige Mesh-Knoten im Amateurfunkband verwandelt. Die
Hardwareanforderungen sind relativ gering (schon 400 MHz CPU, 64 MB RAM
genügen oft), was den Einsatz auch älterer oder stromsparender Geräte
ermöglicht. **Flexibilität:** AREDN-Knoten arbeiten alle auf der
gleichen Frequenz und mit dem gleichen Protokoll, was die Kompatibilität
vereinfacht -- *"jeder Knoten sieht jeden"* im Funknetz
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=Advantage%3A%20Everyone%20sees%20everyone)).
Es muss nicht festgelegt werden, welcher Knoten z.B. Access Point oder
Client ist; alle sind gleichberechtigt und handeln die Verbindungen
automatisch aus. Dies erlaubt es, spontan zusätzliche Knoten ins Netz zu
bringen, ohne Konfigurations-Marathon -- Firmware aufspielen, Standort
aufbauen, und der Node integriert sich selbstständig (MAC-basierte
IP-Zuweisung inklusive)
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=Classic%20Hamnet%3A%20Routes%20are%20planned%2C,and%20which%20as%20a%20station)).
Für portable Notfunk-Einsätze bedeutet das maximale Einfachheit:
Funkamateure können vorprogrammierte Router mitnehmen und bei Bedarf an
Masten, Gebäuden oder Fahrzeugen montieren, um das Mesh zu erweitern.
Aufgrund der Standardisierung auf wenigen Frequenzen kann es bei sehr
vielen Knoten in einem Gebiet nötig sein, manuell auf eine alternative
Mesh-Frequenz auszuweichen (z.B. wenn zwei unabhängige Mesh-Netze sich
gegenseitig stören würden). Insgesamt ist die Hardwareauswahl bei AREDN
**sehr groß und offen** -- neue Geräte können oft durch
Community-Anpassung integriert werden, solange sie von OpenWRT
unterstützt werden.

**HAMNET:** Das HAMNET schreibt keine spezielle Firmware vor, sondern
setzt auf **konfigurierbare Standard-Hardware** im Amateurfunkbetrieb.
Typischerweise kommen professionelle WLAN-Systeme zum Einsatz, die
Frequenzen außerhalb der üblichen WLAN-Kanäle beherrschen oder
modifizierbar sind ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Die%20Daten%20sollen%20haupts%C3%A4chlich%20per,kann%20bis%20zu%2065%C2%A0MBit%2Fs%20betragen)).
Beliebt sind z.B. Mikrotik RouterBoards und Ubiquiti-Geräte (Rocket M5,
AirFiber, NanoBridge etc.), da diese vom Hersteller bereits
Frequenzbänder wie 2300--2400 MHz oder 5650--5850 MHz unterstützen (oft
durch Auswahl spezieller Ländereinstellungen oder mit Labor-Firmware).
Auch selbstgebaute Lösungen oder Umbauten sind möglich -- etwa das
Anpassen von WLAN-Karten mit externen Oberwellenfiltern, um sie im
2,3 GHz-Band zu betreiben. **Flexibilität & Betrieb:** Da jeder Link
separat eingerichtet wird, können unterschiedliche Technologien
koexistieren. Ein Linkpaar kann z.B. mit Ubiquiti-Hardware im
proprietären AirMax-Modus (TDMA) betrieben werden, um die Effizienz zu
steigern, während ein anderer Link Mikrotik mit NV2 oder sogar
klassische 802.11 nutzt -- **Interoperabilität** besteht über die
IP-Schicht (die Router an den Endpunkten verbinden die Netze). Diese
Vielfalt erlaubt Optimierung pro Strecke, erschwert aber die spontane
Erweiterung: Neue Knoten müssen erst in das IP-Adresskonzept
(44er-Adressen) eingebunden und mit den Nachbarn abgestimmt werden.
Meist gibt es regionale Koordinatoren, die Frequenzen und Adressen
zuteilen, um Störungen zu vermeiden. Auf der **User-Seite** (Einstieg
ins HAMNET) kann neben Richtfunk auch ein einfacher Zugangspunkt im
2,4 GHz-Band eingerichtet werden -- z.B. stellen manche Knoten lokal
einen WLAN-Hotspot auf Amateurfrequenz bereit, in den sich User-Devices
einloggen können. In Summe ist HAMNET hardwareseitig **vielfältig, aber
weniger einheitlich**: Man nutzt kommerzielle Technik, die jedoch oft
fest installiert und spezialisiert ist. Für den Aufbau eines eigenen
HAMNET-Knotens ist mehr initialer Aufwand nötig (Auswahl kompatibler
Hardware, Installation von Antennen, Konfiguration von Routing), was
aber durch sehr **optimierte Leistungsdaten** pro Link belohnt wird.

# Bandbreite (genutztes Frequenzspektrum & effiziente Nutzung für Netzwerkdienste)

**AREDN:** AREDN operiert auf mehreren Amateurfunk-Frequenzbändern, vor
allem **2,4 GHz (13 cm)**, **3,4 GHz (9 cm)** und **5,6/5,8 GHz (6 cm)**
([Beginner's Guide --- AREDN® Documentation latest
documentation](http://docs.arednmesh.org/en/latest/arednHow-toGuides/beginner-guide.html#:~:text=By%20loading%20the%20AREDN%C2%AE%20firmware,you%20can%20put%20on%20the)).
Diese liegen teils direkt neben den WLAN-Bändern, sind aber dem
Amateurfunk zugewiesen -- dadurch kann AREDN Frequenzen nutzen, die für
gewöhnliche WLAN-Nutzer tabu sind, was Interferenz verringert ([HAMNET
--
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Es%20werden%20im%20Rahmen%20von,6)).
In den USA wird zudem das 900 MHz-Band (33 cm) von einigen AREDN-Netzen
verwendet, um Hindernisse besser zu durchdringen (auf Kosten von
Datenrate und Antennengröße). Ein großer Vorteil von AREDN ist die
**variable Kanalbandbreite**: je nach Bedarf können 5 MHz, 10 MHz oder
20 MHz breite Kanäle eingestellt werden. Schmalbandigere Kanäle bieten
höhere Reichweite/Empfindlichkeit und belegen weniger Spektrum -- ideal,
um mit geringer Sendeleistung weit zu kommen oder mehrere Netze
nebeneinander zu betreiben. Breitbandige Kanäle liefern mehr Durchsatz,
was für datenintensive Anwendungen relevant ist. So lässt sich z.B. in
einem lokal begrenzten Mesh für Videoübertragung ein 20 MHz-Kanal
wählen, der theoretisch \~130 Mbit/s brutto ermöglicht ([Max throughput?
\| Amateur Radio Emergency Data
Network](https://www.arednmesh.org/content/max-throughput#:~:text=The%20max%20data%20rate%20,is%20802)),
während für einen Weitstrecken-Link ggf. 5 MHz sinnvoll sind, um mit
minimalem Rauschen eine stabile Verbindung aufzubauen. In der Praxis
sind 10 MHz ein gängiger Kompromiss, der ausreichend **Bandbreite für
typische Netzwerk-Anwendungen** (Telefonie, Web, Telemetrie) bietet und
zugleich mehrere Links im 2,3/5,8 GHz-Band nebeneinander erlaubt. Da in
einem AREDN-Mesh *alle* Teilnehmer auf dem selben Kanal funken, teilt
sich die verfügbare Bandbreite auf alle Datenströme auf, die simultan
laufen. Für die Nutzung bedeutet das: Ein einzelner Datenstrom kann die
Funkkanal-Kapazität nahezu ausschöpfen (z.B. Videostream mit 5 Mbit/s),
aber mehrere gleichzeitige Streams müssen sich diese Kapazität teilen.
**Netzwerkanwendungen** lassen sich dennoch gut realisieren, weil
Dienste im Notfunk meist zeitkritischer sind als datenmengenintensiv --
z.B. Sprache, Kurznachrichten, Einsatzdaten. Größere Datenmengen
(hochauflösende Videos, große Dateitransfers) sind über wenige Hops
hinweg eingeschränkt möglich, aber nicht die Primärdomäne von AREDN.
Hier kann man ggf. durch **Aufsplitten des Netzes auf verschiedene
Frequenzen** (z.B. 5 GHz für Video-Feed, 2,4 GHz für Steuerdaten) mehr
Gesamtbandbreite erzielen. Zu beachten ist, dass Amateurfunk ein
geteilter Primärnutz(er)-Status hat -- Koordination mit anderen Nutzern
(Militär, Satellit) kann erforderlich sein. Insgesamt bietet AREDN
genügend Bandbreite, um ein **breites Spektrum an Anwendungen** im
Katastropheneinsatz zu unterstützen, von VoIP-Telefonkonferenzen über
Livebilder bis zu Datenbanken, solange die Belastung innerhalb der
Funkkapazität bleibt.

**HAMNET:** Im HAMNET wird das verfügbare **Frequenzspektrum**
strategisch aufgeteilt, um maximale Abdeckung und Datendurchsatz zu
erzielen. In Zentraleuropa sind vor allem zwei Bereiche in Verwendung:
das **13 cm-Band um 2,3 GHz** (typisch 2320--2400 MHz) für Zugangs- und
Nahbereichsverbindungen und das **6 cm-Band um 5,7 GHz** für
Weitverkehrs-Richtfunk ([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Als%20Frequenzbereiche%20f%C3%BCr%20die%20Richtfunkverbindungen,6)).
Zusätzlich kommt stellenweise das 9 cm-Band (\~3,4 GHz) zum Einsatz,
soweit verfügbar. Diese Frequenzen liegen neben bzw. über den üblichen
WLAN-Kanälen -- z.B. 5,7 GHz ist knapp oberhalb des WLAN-UNII-Bands, so
dass paralleler Betrieb ohne gegenseitige Störung möglich ist ([HAMNET
--
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=Es%20werden%20im%20Rahmen%20von,6)).
Regulativ ist in Deutschland für Datenübertragung im Amateurfunk (außer
Fernsehumsetzer) eine maximale **Signalbandbreite von 10 MHz**
vorgesehen ([Einführung in HAMNET - Datennetz für
HAMs](https://www.darc.de/fileadmin/filemounts/distrikte/p/ortsverbaende/18/Hamnet/Einfuehrung_in_HAMNET_2016-02-05_e.pdf#:~:text=%E2%80%A2%20In%20DL%20max,2015%20Holger%20Riethm%C3%BCller%20DL8SCU%207)).
Daher sind viele HAMNET-Links auf 5 MHz oder 10 MHz Kanalbreite
festgelegt. Dies begrenzt zwar den Spitzen-Durchsatz pro Link, erlaubt
aber die **gleichzeitige Nutzung mehrerer Kanäle** innerhalb des Bandes
und verbessert die Reichweite. So wurden für das 5,7 GHz-Band z.B.
Center-Frequenzen 5805, 5815, 5825 MHz mit je 10 MHz Abstand koordiniert
([Einführung in HAMNET - Datennetz für
HAMs](https://www.darc.de/fileadmin/filemounts/distrikte/p/ortsverbaende/18/Hamnet/Einfuehrung_in_HAMNET_2016-02-05_e.pdf#:~:text=5805%2C5815%2C5825%20MHz%2C%2010MHz%20Bandbreite%2013cm,Nutzer%20nicht%20eingezeichnet%2C%20au%C3%9Fer%20BOS)),
was drei parallele 10 MHz-Kanäle ermöglicht. Jeder Link hat somit eine
feste zugewiesene Bandbreite. Für Anwendungen, die mehr Datendurchsatz
benötigen (z.B. ATV-Streams), können spezielle breitere Kanäle genutzt
werden, sofern die Bandplane es zulässt -- in einigen Ländern oder in
Absprache sind auch 20 MHz-Kanäle mit 802.11ac-Technik realisiert
worden, um über 100 Mbit/s zu übertragen. **Effizienz für
Netzwerkanwendungen:** Durch die Trennung der Verbindungen kann das
HAMNET insgesamt ein deutlich höheres Datenvolumen tragen als ein
einzelnes Frequenz-Mesh. Beispielsweise könnte ein Knotenpunkt auf
5,7 GHz gleichzeitig Daten von drei entfernten Stationen empfangen, ohne
dass diese sich gegenseitig die Bandbreite streitig machen -- jede
Strecke hat ihren eigenen „Kanal". Dienste wie live Videoübertragung,
große Dateiserver oder dauerhafte Datenströme lassen sich so eher ins
Netz integrieren, da die Netzkapazität skalierbar ist (hinzugefügte
Linkstrecken erhöhen das Gesamtdatenvolumen linear, solange genug
Frequenzen verfügbar sind). Der Nachteil ist der **Aufwand der
Koordination**: Frequenznutzung muss geplant werden, um Überschneidungen
zu vermeiden. Während AREDN spontan einen freien Kanal nutzen kann,
erfordert HAMNET eine Abstimmung mit Nachbarn (ähnlich der
Frequenzplanung bei klassischen Relais). In der Summe stellt HAMNET aber
**reichlich Bandbreite pro Benutzer** bereit -- typische Anwendungen
laufen flüssig und mit geringer Latenz, da jeder Backbone-Link dediziert
ist. Für den Endnutzer in einem HAMNET-Hotspot bedeutet die hohe
Backbone-Bandbreite, dass auch mehrere Benutzer zugleich (z.B. auf einem
Fieldday) Dienste wie Websurfen auf internen Servern, Voice-Chats oder
Videostreams nutzen können, ohne das Netz zu überlasten. Die tatsächlich
nutzbare Bandbreite hängt letztlich von der **Kaskade der Links** ab:
Ist irgendwo ein Engpass (z.B. ein alter 2 Mbit/s Packet-Radio-Link als
Übergang), bestimmt dieser den Durchfluss. Solche Schmalband-Strecken
sind jedoch selten, da HAMNET gerade als Ersatz für das altmodische
Packet-Radio gedacht ist und dieses fast überall abgelöst hat ([HAMNET
--


**Fazit:** Zusammenfassend richtet sich **AREDN** eher an den flexiblen,
lokalen Einsatz im Notfunk mit schnell aufbaubaren Mesh-Netzen,
wohingegen **HAMNET** ein leistungsfähiges, festes Amateurfunk-Datennetz
für breite Anwendungen darstellt. AREDN punktet mit einfacher
Handhabung, Selbstkonfiguration und bewährt sich insbesondere dort, wo
Infrastruktur zerstört ist und unmittelbar ein Ersatznetz geschaffen
werden muss. HAMNET hingegen bietet hohe stabile Datenraten und weite
Vernetzung als Rückgrat -- ideal, um bereits im Vorfeld Regionen zu
vernetzen und im Krisenfall als **Backbone** zu dienen, jedoch weniger
agil im spontanen Aufbau. Beide Systeme ergänzen sich potentiell: So
kann ein lokal aufgebautes AREDN-Mesh an das überregionale HAMNET
angebunden werden, um das Beste aus beiden Welten zu nutzen (schnelle
lokale Vernetzung + Weitverkehrsanbindung). Technisch sind sowohl AREDN
als auch HAMNET hervorragende Beispiele dafür, wie Funkamateure
**modernste Datenübertragung** im Dienste der Notfallkommunikation und
der Gemeinschaft einsetzen können.
([AREDN](https://uska.ch/aredn/?lang=de#:~:text=Furthermore%2C%20the%20network%20is%20designed,fails%2C%20an%20alternative%20is%20routed))
([HAMNET --
Wikipedia](https://de.wikipedia.org/wiki/HAMNET#:~:text=erm%C3%B6glichen.%20,kommerziellen%20Netzen%20durch%20%2031))


21.01.2025 
Beat Meier, HB9MQB