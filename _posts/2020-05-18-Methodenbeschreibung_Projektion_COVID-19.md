---
author: Edgar
title: Methodenbeschreibung Zi COVID-19-Projektion
excerpt: "Wie wir unsere Projektionen für das KV-System berechnen."
categories: [reports] # Pleaser choose from [news,presentations,articles,projects,reports]
tags:
  - covid19
layout: single
author_profile: true
read_time: false
comments: false
share: false
related: false
---

Dr. Lars Eric Kroll, Dr. Edgar Steiger, Dr. Mandy Schulz

  - [Stand](#stand)
  - [Zusammenfassung](#zusammenfassung)
  - [Methoden](#methoden)
      - [Projektion der inzidenten
        Fälle](#projektion-der-inzidenten-fälle)
      - [Drei Szenarien für die weitere Entwicklung der inzidenten
        Fälle](#drei-szenarien-für-die-weitere-entwicklung-der-inzidenten-fälle)
      - [Projektion des stationären
        Behandlungsbedarfs](#projektion-des-stationären-behandlungsbedarfs)
      - [Daten und Projektion des ambulanten
        Behandlungsbedarfs](#daten-und-projektion-des-ambulanten-behandlungsbedarfs)
  - [Aktuelle Daten](#aktuelle-daten)
      - [Modellierung](#modellierung)
      - [Zusammenfassung](#zusammenfassung-1)
  - [Anhang](#anhang)
      - [A Berechnung des Ansteckungsrisikos: Die zeitlich variierende
        Reproduktionszahl](#a-berechnung-des-ansteckungsrisikos-die-zeitlich-variierende-reproduktionszahl)
      - [B Prognose der Infektionszahlen: Das
        SIR-Modell](#b-prognose-der-infektionszahlen-das-sir-modell)
  - [Literatur](#literatur)

# Stand

Diese Datei hat den Stand: 20.05.2020.

# Zusammenfassung

Wir haben auf Basis der aktuellen verfügbaren Fallzahlen für
Deutschland, der aktuellen Bevölkerung sowie der Intensiv-Bettenzahl
(ICU) in Deutschland, die für die Versorgung von COVID-19-Patienten zur
Verfügung steht, die Zahl der inzidenten und prävalenten Patienten
fortgeschrieben und abgeschätzt, wie sich diese Entwicklung auf den
ambulanten und stationären Leistungsbedarf auswirkt.

# Methoden

## Projektion der inzidenten Fälle

Die Entwicklung der inzidenten Fälle wurde empirisch auf Basis der
Fallzahlentwicklung der bisherigen Entwicklung geschätzt. Hier war die
einzig eingehende Annahme die Dauer der Infektion, diese wurde mit 14
Tagen pro Patient angesetzt. Das RKI modelliert mit 10 Tagen
Infektionsdauer (Heiden und Buchholz [2020](#ref-rkimodellierung)), geht
dafür aber vom angesetzten Erkrankungsbeginn statt Meldedatum aus. Vor
Erkrankungsbeginn sind mehrere Tage Inkubationszeit anzusetzen, ebenso
entstehen Probleme durch eventuelle Nachmeldungen. Zur Modellierung der
Infektionsentwicklung wurde zunächst eine Schätzung der zeitlich
variierenden Reproduktionszahl durchgeführt (Thompson u. a.
[2019](#ref-thompson2019improved)) und anschließend ein SIR-Modell für
die Projektion verwendet (Kermack und McKendrick
[1991](#ref-kermack1991contributions)). Die zeitlich variierende
Reproduktionszahl $$R_t$$ beschreibt die Dynamik der Übertragbarkeit
einer Infektion **während** einer Epidemie (als Erweiterung der
Basis-Reproduktionszahl $$R_0$$, die für eine bestimmte Infektion
konstant ist und die Übertragbarkeit nur zu Beginn der Epidemie
beschreibt). Das SIR-Modell ist ein klassisches Modell der
mathematischen Epidemiologie zur dynamischen Modellierung von
Infektionskrankheiten. Die Bevölkerung wird in drei Gruppen aufgeteilt:
$$S$$ (“susceptibles”, nicht Infizierte), $$I$$ (“infectious”, infiziert
& ansteckend), sowie $$R$$ (“removed”, Genesene und Gestorbene, nicht
mehr ansteckend). Auf der Basis von gemeldeten historischen Daten (für
Deutschland: Robert Koch-Institut “RKI”, <https://corona.rki.de/>,
international: Johns Hopkins University “JHU”,
<https://coronavirus.jhu.edu/>) und einer angenommenen Verweildauer im
Status $$I$$ sowie den berechneten $$R_t$$ können damit Modellierungen
über die Größe der drei Gruppen durchgeführt werden.

## Drei Szenarien für die weitere Entwicklung der inzidenten Fälle

International und national zeigt sich, dass Maßnahmen zur Eindämmung der
Übertragung Erfolg haben. Wir haben darum in unseren Szenarien die
Effekte der aktuellen Maßnahmen in Deutschland mit einbezogen. Weiterhin
lässt sich die beobachtete Entwicklung der zeitlich variierenden
Reproduktionszahl $$R_t$$ als Trend fortschreiben.

### Szenario 1 “Trend lokal”

In Szenario 1 (“Trend lokal”) berechnen wir für jeden Landkreis, jedes
Bundesland, Gesamtdeutschland sowie auch internationale Vergleichsländer
einen eigenen Trend aus den lokalen historischen Daten. Dies bedeutet,
dass wir die vergangene Entwicklung der zeitlich variierenden
Reproduktionszahl $$R_t$$ berücksichtigen und projizieren auf dieser
Basis die zukünftige Entwicklung von $$R_t$$ und damit der Fallzahlen.
Ist das derzeitige $$R_t$$ größer als $$0{,}7$$, wird der Trend bis zu
diesem Wert fortgeschrieben und danach konstant gehalten. Sollte $$R_t$$
derzeit bereits kleiner als $$0{,}7$$ sein, wird es konstant auf dem
derzeitigen Niveau gehalten, da dies bereits ein sehr günstiges Szenario
darstellt.

### Szenario 2 “Trend Bund”

In Szenario 2 (“Trend Bund”) nehmen wir den “lokalen Trend” von
Gesamtdeutschland und setzen diesen als Maßstab insbesondere für die
Landkreise an. Da in den Landkreisen die Fallzahlen deutlich kleiner
sind als auf höheren Aggregationsebenen, können die Parameterschätzungen
des lokalen Trends instabil sein, sodass die Verwendung des
bundesdeutschen Trends sinnvoller erscheint. Für Landkreise mit derzeit
ungünstiger Entwicklung bedeutet die Anwendung des bundesdeutschen
Trends eventuell ein “Best Case”-Szenario, da sich die Ansteckungsrate
in Deutschland derzeit sehr positiv darstellt.

### Szenario 3 “Worst Case $$R_t$$=1,3”

In Szenario 3 modellieren wir ein “Worst Case”-Szenario, bei dem die
derzeitige Reproduktionszahl $$R_t$$ innerhalb von 7 Tagen ein Niveau
von $$1{,}3$$ anstrebt und dann dort verharrt. Dies bedeutet ein
erneutes exponentielles Wachstum der Fallzahlen. Wir versuchen damit die
schwer abschätzbaren Folgen einer zu umfassenden Lockerung der
Eindämmungsmaßnahmen zu modellieren.

## Projektion des stationären Behandlungsbedarfs

Eingehende Annahmen der Modellierung im Hinblick auf die stationäre
Versorgung betreffen den Anteil der Intensiv-Betten in Deutschland sowie
den Anteil der Patienten, die intensivmedizinisch versorgt werden
müssen. Wir gehen in unserer Projektion davon aus, dass ca. 6% der
inzidenten Patienten eine ICU-Versorgung benötigen, auf Basis
internationaler Zahlen aus China und Südkorea könnte der Anteil
allerdings auch höher sein: Anhand der Daten von 1.099 Patienten mit
bestätigter COVID-19-Infektion aus 552 Krankenhäusern in China berichten
Guan u. a. ([2020](#ref-guan2020clinical)) eine Einweisungsrate in eine
Intensive Care Unit (ICU) von 5,0% und von einer Beatmungsrate 2,3%.
China CDC Weekly berichtet von 14% schweren Fällen, die eine
Hospitalisierung und Beatmung erforderlich machen sowie ebenfalls von
einer ICU-Einweisungsrate von 5% (The NCPERE Team
[2020](#ref-novel2020epidemiological)). Verity u. a.
([2020](#ref-verity2020estimates)) berichten eine ähnliche Rate von
13,8% Hospitalisierung und 6,1% ICU-Einweisungen. Demgegenüber steht der
Report aus der Lombardei in Italien, wo innerhalb der ersten 2 Wochen
ICU-Einweisungsraten zwischen 12% (relativ zu allen bestätigten Fällen)
und 16% (relativ zu allen hospitalisierten Fällen) beobachtet wurden
(Grasselli u. a. [2020](#ref-grasselli2020critical)). Hier besteht also
derzeit eine gewisse Unsicherheit in der Modellierung. Die für die
Versorgung von COVID-19-Patienten potentiell zur Verfügung stehende
Bettenzahl wird seit 16. April 2020 verpflichtend von den Krankenhäusern
an die Deutsche interdisziplinäre Vereinigung für Intensiv- und
Notfallmedizin (DIVI) gemeldet (Intensivregister,
<https://www.intensivregister.de/>). Wir gehen von 25% der gemeldeten
Kapazität aus, da auch weiterhin andere Intensivfälle behandelt werden
müssen.

In unseren Modellierungen berücksichtigen wir eine Rate von 13,8%
Hospitalisierungen, sowie davon 50% ICU-Notwendigkeit (analog zu WHO
Team ([2020](#ref-who2020report)) und Verity u. a.
([2020](#ref-verity2020estimates))). Darüber hinaus gehen wir von einer
Liegezeit von 15 Tagen in der ICU-Versorgung aus (DGEpi
[2020](#ref-dgepi2020stellungnahme)), wobei die Hospitalisierung 6 Tage
und die ICU-Notwendigkeit sich nach weiteren 2 Tagen nach der Infektion
ergibt (Heiden und Buchholz [2020](#ref-rkimodellierung)).

## Daten und Projektion des ambulanten Behandlungsbedarfs

Für den ambulanten Behandlungsbedarf von COVID-19 durch Vertragsärzte
sind insbesondere die Dauer und die Anzahl der erkrankten Patienten
relevant. Die Betreuung der Patienten wird sicher in ihrem Umfang
variieren, wir setzen hier lediglich Durchschnittswerte für den
Behandlungsaufwand von drei Patientengruppen an.

In der Modellgruppe $$I$$ sind dies einerseits **Patienten mit niedrigem
Behandlungsbedarf** (infiziert und symptomatisch, etwa 56,5 Prozent der
Infizierten), die in unserem Modell etwa 5 Minuten pro Konsultation alle
2 Tage benötigen, andererseits **Patienten mit erhöhtem
Behandlungsbedarf** (Risikogruppe, aber keine Hospitalisierung, etwa 33
Prozent der Infizierten), die etwa 20 Minuten pro Konsultation pro Tag
benötigen. Bei weiteren 13,8% der Infizierten wird Krankenhaus-Betreuung
angesetzt, zu 100 fehlende Prozent sind infiziert aber asymptomatisch
(ohne Behandlung).

Darüber hinaus benötigen bestimmte Patienten in $$R$$ ambulante
Betreuung, wenn sie in Krankenhaus/ICU-Behandlung waren (**Patienten in
der Nachsorge**, etwa 66 Prozent der ehemals ICU-behandelten sowie alle
übrigen Krankenhaus-Behandelten): 20 Minuten pro Konsultation alle 10
Tage für ehemalige ICU-Fälle und 15 Minuten alle 10 Tage für
hospitalisierte Patienten.

Die notwendige Arztzeit pro Tag ergibt sich durch die summierten
durchschnittlichen Konsultationsdauern. Diesen Wert haben wir durch eine
mittlere Tagesarbeitszeit von 8 Stunden dividiert um zu einem Schätzwert
für die täglich benötigte Versorgungsleistung in VZÄ zu gelangen.

Nicht berücksichtigt haben wir den Bedarf, der durch (verunsicherte)
nicht-infizierte Patienten (in $$S$$) entsteht, die ärztliche Zeit in
Anspruch nehmen (z.B. Anrufe bei leichten Erkältungssymptomen oder
Durchführen von SARS-CoV-2-Tests, die sich als negativ herausstellen).

# Aktuelle Daten

Die offiziellen deutschen Fallzahlen zu COVID-19-Erkrankungen werden vom
RKI täglich aktualisiert und entsprechen den von den jeweiligen
Gesundheitsämtern übermittelten Fällen. Dabei kommt es jedoch teilweise
zu Meldeverzügen, so dass in diesen offiziellen Zahlen unterschieden
werden muss zwischen Meldedatum und Übermittlungsdatum, insbesondere bei
den Zahlen des letzten Tages: Die am aktuellen Tag vom RKI kommunizierte
Zahl ist nicht endgültig. Weiterhin erschwerend kommt hinzu, dass
generell Meldedatum und Infektionsereignis der Person nicht
übereinstimmen. So hat die Infektion in der Regel bereits ein paar Tage
vor der Meldung stattgefunden. Eine Meldung erfolgt erst nach
bestätigtem Laborbefund.

![](/assets/posts/Methodenbeschreibung_Projektion_COVID-19_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

## Modellierung

Die Ergebnisse der Prognose hängen entscheidend von den Annahmen zur
weiteren Inzidenzentwicklung ab. Hier wird das Szenario laufend an den
aktuellen Erkenntnisstand angepasst.

Die aktuelle Modellierung basiert auf den bis zum 19.05.2020 um 23.59
Uhr beim RKI eingegangenen Meldungen. Insgesamt wurden 175.963 Fälle
gemeldet.

### Zeitlich variierende Reproduktionszahl $$R_t$$

Zur Berechnung von $$R_t$$ auf den historischen Daten wurde das R-Paket
“EpiEstim” verwendet (Thompson u. a.
[2019](#ref-thompson2019improved); Cori u. a. [2013](#ref-cori2013r0)).
Für 7-Tages-Fenster wird ein rollender Mittelwert der Reproduktionszahl
mit einem bayesschen Schätzverfahren bestimmt. Da sich bei der
Übermittlung der Infektionszahlen an das RKI Meldeverzüge ergeben,
schließen wir die letzten 3 Tage aus der Berechnung von $$R_t$$ aus (der
Großteil der Meldeverzüge verteilt sich auf die letzten drei Tage).
Ausgehend von diesem Stichtag berechnen wir einen linearen Trend von
$$R_t$$ innerhalb der letzten 5 Tage (wegen des rollenden Mittelwerts
entspricht dies dem Trend der letzten 12 Tage). Dieser Trend wird in
Szenario 1 und 2 fortgeschrieben bis zu einem Niveau von $$0{,}7$$ (und
danach konstant), falls er negativ ist, bei positivem Trend wird bis zu
einer Reproduktionszahl von $$2{,}5$$ fortgeschrieben. Szenario 3
beschreibt einen linearen Trend vom derzeitigen Niveau bis zum Niveau
$$1{,}3$$ innerhalb von 7 Tagen (und danach konstant).

Nähere Informationen zur Bestimmung der zeitlich variierenden
Reproduktionszahl finden sich im Appendix.

### SIR-Modell

Das zur Projektion verwendete SIR-Modell wird im Appendix beschrieben.
In unserem Modell wird der Ansteckungsparameter $$\beta$$ von den
empirischen Werten $$R_0$$ bzw. $$R_t$$ abgeleitet, weiterhin wird der
Infektionsdauerparameter $$\gamma$$ konstant gesetzt als das Inverse der
Infektionsdauer: $$\gamma=1/14$$.

### Andere Ansätze

Das hier verwendete SIR-Modell hat den Vorteil, dass es mit wenig
Parametern und wenig strukturierten historischen Daten bereits
angemessene Vorhersagen für die Zukunft erlaubt. Das Modell kann um
weitere Patientengruppen (z.B. $$E$$ für nicht-ansteckende Infizierte,
$$D$$ für Verstorbene, etc.) erweitert werden und außerdem können
saisonale Effekte berücksichtigt werden. Dies bedeutet aber auch immer
zusätzliche Parameter, die geschätzt oder belegt werden müssen.

Das RKI (Heiden und Buchholz [2020](#ref-rkimodellierung)) verwendet ein
SEIR-Modell, erweitert um unterschiedlich starke saisonale Effekte und
unterschiedliche $$R_0$$ in Abhängigkeit von potentiellen Erfolgen der
Mitigationsmaßnahmen. Mögliche Projektionen für den stationären
Behandlungsbedarf werden abgegeben, aber keine Auswirkungen auf den
ambulanten Sektor benannt. Ebenso bleibt offen, was das
wahrscheinlichste Szenario für die zukünftige Entwicklung ist.

Magal und Webb ([2020](#ref-magal2020predicting)) erweitern in ihrem
technischen Paper das SIR-Modell, indem $$I$$ in drei Gruppen
aufgespaltet wird: asymptomatische Infizierte, sowie symptomatische
identifizierte Infizierte und symptomatische unidentifizierte
Infizierte. Für Deutschland prognostizieren sie auf Basis der gemeldeten
Zahlen eine weiter exponentiell steigende Zahl von Infizierten,
berücksichtigen aber keine Mitigationsmaßnahmen, da es in dieser
Veröffentlichung vor allem um die Modell\), die Parameterschätzungen
basieren derzeit lediglich auf den historischen Daten aus China bzw.
Fachveröffentlichungen und Prognosen für verschiedene Länder werden
damit basierend auf den chinesischen Erfahrungen gemacht.

Ferguson u. a. ([2020](#ref-ferguson2020impact)) sowie Walker u. a.
([2020](#ref-walker2020global)) benutzen als Alternative zu den
differentialgleichungsbasierten Modellen Simulationsansätze
(“agent-based”), bei denen stochastisch die Ansteckung von einzelnen
Individuen über einen Zeitraum simuliert wird. Die Parameter verhalten
sich bei diesen Ansätzen ähnlich wie im SIR-Modell und seinen
Erweiterungen. Allerdings werden hier besser alltägliche
Infektionssituationen (Haushalt, Schule, soziale Zusammenkünfte)
abgebildet und modelliert. Insbesondere Ferguson u. a.
([2020](#ref-ferguson2020impact)) heben stark die Bedeutung und den
Einfluss von verschiedenen Mitigationsmaßnahmen hervor.

### Limitationen und Ausbau des Zi-Mode\)erschiedenen Szenarien.

Eine Limitation fast aller Prognosemodelle ist die Dunkelziffer der
(eventuell asymptomatischen) Infizierten, die nicht getestet und
identifiziert werden, aber die Infektion weitergeben können. Eine
Möglichkeit wäre, zusätzlich zu den Fallzahlen die Todesfälle $$D$$ mit
zu berücksichtigen und auch eine Patientengruppe $$U$$ (nicht
identifiziert, aber infiziert) zu modellieren, da die Todesfälle mit
großer Sicherheit richtig identifiziert sind und eine konstante
Todesrate bei Infektion angenommen werden kann (Lachmann
[2020](#ref-lachmann2020correcting); Murray und IHME COVID-19 Health
Service Utilization Forecasting Team [2020](#ref-ihme2020forecasting)).

#### Sicherheit der Projektion

Um die Güte unserer Projektionen durch das Zi zu evaluieren, berechnen
wir Modelle für historische Zeitpunkte und vergleichen deren Vorhersagen
mit den tatsächlich nach diesem Zeitpunkt gemeldeten Zahlen. Folgende
Aussagen lassen sich treffen:

  - Auf Bundesebene gelingen die Vorhersagen bisher sehr gut;
  - auf Bundeslandebene annehmbar gut für einen begrenzten Zeithorizont;
  - auf Kreisebene sind die Fallzahlen zum Teil so gering und volatil,
    dass nicht in jedem Kreis verlässliche Vorhersagen getroffen werden
    können.

Generell sind Projektionen mit einem Horizont von mehr als vier Wochen
nicht verlässlich zu erstellen, da das Ausbreitungsgeschehen stark durch
gesellschaftliche Entwicklungen beeinflusst wird. Ebenso können
Einzelereignisse, wie Großveranstaltungen oder Infektionsherde in
Einrichtungen, auftreten und zu massiven Trendwenden (Zeitpunkt und
Qualität) führen.

In der nachstehenden Grafik sind die prognostizierten Fallzahlen für
Deutschland unseres Modells (“Trend lokal”) auf Basis des Stands der
Daten vom Stichtag 20.4.2020 abgetragen, mit den tatsächlichen
gemeldeten Fallzahlen seitdem und der weiteren Projektion. Die
schattierte Fläche beschreibt ein 95%-Konfidenzintervall für die
Projektion, das für die Zeit seit dem Stichtag auf Basis der
prognostizierten und tatsächlichen Fallzahlen der Bundesländer berechnet
und für den erweiterten Horizont linear fortgeschrieben wurde.

![](/assets/posts/Methodenbeschreibung_Projektion_COVID-19_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

<!-- Die Zi-Modellierung erfasst derzeit fast alle Kreise in Deutschland. Lediglich Kreise, für die eine hinreichende Fallzahl vorliegt, werden ausgewiesen. Derzeit können für folgende Ebenen Projektionen erstellt werden: -->

<!-- ```{r} -->

<!-- prognosedata %>% filter(Szenario=="Italien") %>% group_by(ebene,name) %>% count() %>% group_by(ebene) %>% count(name="n") %>% ungroup() %>% select("Raumebene"=ebene,"Regionen"=n) %>% ggplot(aes(x=Raumebene,y=Regionen)) + geom_bar(stat="identity",  fill=zi_cols("ziblue")) + geom_text(aes(label=Regionen),nudge_y = 25 )  + scale_y_continuous(limit=c(0,430)) + labs(x="",y="Modelle für Regionen", title="Erfasste Regionen") + theme_zi() -->

<!-- ``` -->

<!-- Aufgrund des dynamischen Geschehens ist die Entwicklung der nächsten Zeit sehr unsicher. Wir nutzen darum zwei Szenarien in unseren Modellen (siehe oben). Die Modelle sollen den wahrscheinlichen Korridor der zukünftigen Entwicklung skizzieren. Die nachfolgende Abbildung vergleicht diesen Prognosekorridor mit der Situation in den einzelnen Bundesländern. Sie stellt dadurch dar, welchem modellierten Szenario das jeweilige Land aktuell näher ist. -->

<!-- **Abb. 5 Vergleich zwischen RKI Zahlen und Zi-Prognosemodell des Vortages** -->

<!-- ```{r} -->

<!-- # Vergleich RKI aktuell mit Modell gestern -->

<!-- rki_aktuell <- load_mydb(mydatapath,name="rki") %>% as_tibble() %>% group_by(name) %>% -->

<!--   arrange(name,-as.numeric(date)) %>% filter(row_number()==1) %>% -->

<!--   rename(Name=name) -->

<!-- modell_vortag <-  read_excel(paste0("../../data/results/allresults_",date(now()-days(1)),".xlsx")) %>% -->

<!--   filter(Ebene=="Land" | Ebene=="Bund" ) %>% -->

<!--   select(Tag="Tag der Prognose",Name,Szenario,Faelle=`jemals Infizierte (= Fallzahl RKI)`) %>% -->

<!--   filter(Tag==2) %>% select(-Tag) %>% spread(Szenario,Faelle) -->

<!-- vergleich_rki_zi_szenario <- left_join(rki_aktuell %>% select(-todesfaelle,-date,-statusdate),modell_vortag,by="Name") -->

<!-- vergleich_rki_zi_szenario %>% filter(Name!="Gesamt") %>% rename(hart="Harte Maßnahmen",mittel="Mittlere Maßnahmen") %>% ggplot(aes(x=fct_reorder(Name,faelle))) + theme_minimal() + coord_flip() + labs(x="",y="Fälle laut RKI") +   geom_linerange(aes(ymin=hart,ymax=mittel),color=zi_cols("ziblue")) + scale_y_log10() + geom_point(aes(y=faelle, color=faelle>((hart+mittel)/2)),size=3,show.legend = F) + scale_color_zi("greenred") -->

<!-- ``` -->

## Zusammenfassung

So lange das Ansteckungsrisiko so groß ist, dass jede infizierte Person
mehr als eine weitere Person ansteckt (mathematisch: $$R_t>1$$), gibt es
ein exponentielles Wachstum der Infektionszahlen und innerhalb kurzer
Zeit so viele Infizierte und Erkrankte, dass das Gesundheitssystem
überlastet wird. Nur ein $$R_t<1$$ kann dies verhindern oder diese
Situation wieder beseitigen. Der internationale Vergleich zeigt, dass
dies in Ländern wie Südkorea oder China gelungen ist, während in einigen
Ländern noch exponentielles Wachstum vorliegt, aber sich zum Teil
günstige Trends abzeichnen. Deustchland steht derzeit mit einer
günstigen Reproduktionszahl $$<1$$ da. Zukunftsprognosen sind
schwierig, da nur begrenzt Aussagen über den Einfluss von
Mitigationsmaßnahmen auf $$R_t$$ bzw. das Ansteckungsrisiko
quantifiziert werden können. Falls sich der aktuelle Trend fortsetzt und
ein günstiges Reproduktionsniveau $$<1$$ dauerhaft gehalten werden
könnte, sind nach unseren Prognosen die ambulanten und stationären
Ressourcen ausreichend. Es ist aber nicht auszuschließen, dass sich
dieser Trend verändert, auf einem Niveau $$>1$$ einfriert oder sogar
umkehrt, wenn zu umfassende Lockerungen der Eindämmungsmaßnahmen
beschlossen werden.

# Anhang

## A Berechnung des Ansteckungsrisikos: Die zeitlich variierende Reproduktionszahl

Im Unterschied zur Basisreproduktionszahl $$R_0$$ berücksichtigt die
zeitlich variierende Reproduktionszahl bzw. Nettoreproduktionszahl
$$R_t$$ auch die fortschreitende Immunisierung der Bevölkerung (nach
durchstandener Infektion) und Kontrollmaßnahmen. $$R_t$$ kann geschätzt
werden als das Verhältnis von neuen Infektionen zu einem Zeitpunkt $$t$$
und der Gesamtinfektiösität aller bereits infizierten Individuen zur
Zeit $$t$$ (Cori u. a. [2013](#ref-cori2013r0)). Das Maß für die
Infektiösität eines Individuums ist die sogenannte Verteilung des
seriellen Intervalls (“serial interval distribution”). Basierend auf der
Literatur wird hier für diese Verteilung eine Gamma-Verteilung
($$\Gamma$$) mit Mittelwertsparameter $$5$$ und
Standardabweichungsparameter $$4$$ angenommen (Du u. a.
[2020](#ref-du2020serial); Nishiura u. a.
[2020](#ref-nishiura2020serial)). Die Verteilung beschreibt den
zufälligen Prozess, wann eine infizierte Person eine andere Person
ansteckt, und deckt sich für die gewählten Parameter mit der Annahme,
dass die Infektionsdauer in etwa 10 Tage beträgt, da das maßgebliche
Gewicht der Veteilung auf den ersten 10 Tagen liegt. Weitere
Modellannahmen sind, dass die Zahl der Neuinfizierten einer
Poissonverteilung folgt und dass die Reproduktionszahl rollend konstant
geschätzt wird für ein fixes Zeitintervall (hier: 7 Tage). Das
ermöglicht, $$R_t$$ mit bayesschen Verfahren zu schätzen, Details
finden sich bei Thompson u. a. ([2019](#ref-thompson2019improved)).

## B Prognose der Infektionszahlen: Das SIR-Modell

Beim SIR-Modell zur Modellierung von Infektionskrankheiten werden drei
Gruppen unterschieden:

  - $$S$$: “Susceptibles”, nicht infizierte Personen,

  - $$I$$: “Infected”, (frisch) infizierte & ansteckende Personen,

  - $$R$$: “Removed”, nicht mehr ansteckende Personen (genesen oder
    gestorben).

Folgende wichtige Annahmen beinhaltet das Modell:

  - die Reihenfolge der Zustände ist $$S\rightarrow I \rightarrow R$$,
    das heißt jede Person kann nur einmal erkranken und genest/stirbt
    letztendlich,
\)
  - die Bevölkerungszahl $$N$$ wird für den Modellierungshorizont als
    konstant angenommen ($$S+I+R=N$$, Geburten werden nicht
    berücksichtigt),

  - Personen in $$I$$ sind mit konstanter Rate $$\beta$$ ansteckend,

  - Personen in $$I$$ verlassen diesen Zustand mit konstanter Rate
    $$\gamma$$ (genesen oder versterben),

  - Personen in den drei Gruppen interagieren auf gleiche Weise
    miteinander.

Unter diesen Annahmen kann die zeitliche Entwicklung der
Infektionsausbreitung mit einem Differentialgleichungssystem modelliert
werden:

  - $$\frac{dS}{dt} = -\frac{\beta}{N} \cdot I \cdot S,$$

  - $$\frac{dI}{dt} = \frac{\beta}{N} \cdot I \cdot S - \gamma \cdot I,$$

  - $$\frac{dR}{dt} = \gamma \cdot I.$$

Weiterhin gilt, dass die Ansteckungsrate $$R_0$$ aus den Parametern des
Differentialgleichungssystems geschätzt werden kann:

$$R_0 = \frac{\beta}{\gamma}.$$

Umgekehrt kann auch aus bekanntem $$R_0$$ und fixem $$\gamma$$ der
Parameter $$\beta$$ geschätzt werden.

Mit den ermittelten Parametern können Prognosen für die zukünftige
Verteilung der drei Gruppen abgegeben werden. Ebenso lässt sich bei
Konstanthaltung von $$\gamma$$ mit Variierung von $$R_0$$ bzw. $$\beta$$
der zukünftige Einfluss von ansteckungsverhindernden Maßnahmen
modellieren.

# Literatur

<div id="ref-neher2020covid"></div>


AKSAMENTOV, Ivan u. a., 2020. *COVID-10 Scenarios* \[online\]. 2020.
Verfügbar unter: <https://neherlab.org/covid19/>


<div id="ref-cori2013r0"></div>

CORI, Anne u. a., 2013. A New Framework and Software to Estimate
Time-Varying Reproduction Numbers During Epidemics. *American Journal of
Epidemiology*. September 2013. Bd. 178, Nr. 9, S. 1505–1512.
DOI [10.1093/aje/kwt133](https://doi.org/10.1093/aje/kwt133)



<div id="ref-dgepi2020stellungnahme"></div>

DGEPI, 2020. *Stellungnahme der Deutschen Gesellschaft für Epidemiologie
(DGEpi) zur Verbreitung des neuen Coronavirus (SARS-CoV-2)* \[online\].
2020. Verfügbar unter:
<https://www.dgepi.de/assets/Stellungnahmen/Stellungnahme2020Corona_DGEpi-21032020-v2.pdf>



<div id="ref-du2020serial"></div>

DU, Zhanwei u. a., 2020. The serial interval of COVID-19 from publicly
reported confirmed cases. *medRxiv*. 2020.
DOI [10.1101/2020.02.19.20025452](https://doi.org/10.1101/2020.02.19.20025452)



<div id="ref-ferguson2020impact"></div>

FERGUSON, Neil M u. a., 2020. Impact of non-pharmaceutical interventions
(NPIs) to reduce COVID-19 mortality and healthcare demand.. 2020.
DOI [10.25561/77482](https://doi.org/10.25561/77482)



<div id="ref-grasselli2020critical"></div>

GRASSELLI, Giacomo u. a., 2020. Critical Care Utilization for the
COVID-19 Outbreak in Lombardy, Italy: Early Experience and Forecast
During an Emergency Response. *JAMA*. März 2020.
DOI [10.1001/jama.2020.4031](https://doi.org/10.1001/jama.2020.4031)



<div id="ref-guan2020clinical"></div>

GUAN, Wei-jie u. a., 2020. Clinical Characteristics of Coronavirus
Disease 2019 in China. *New England Journal of Medicine*. 2020.
DOI [10.1056/NEJMoa2002032](https://doi.org/10.1056/NEJMoa2002032)



<div id="ref-rkimodellierung"></div>

HEIDEN, Matthias an der und Udo BUCHHOLZ, 2020. Modellierung von
Beispielszenarien der SARS-CoV-2-Epidemie 2020 in Deutschland.. 2020.
DOI [10.25646/6571.2](https://doi.org/10.25646/6571.2)

<div id="ref-kermack1991contributions"></div>


KERMACK, William O und Anderson G MCKENDRICK, 1991. Contributions to the
mathematical theory of epidemics–I. 1927. *Bulletin of mathematical
biology*. 1991. Bd. 53, Nr. 1-2, S. 33—55.
DOI [10.1007/bf02464423](https://doi.org/10.1007/bf02464423)


<div id="ref-lachmann2020correcting"></div>


LACHMANN, Alexander, 2020. Correcting under-reported COVID-19 case
numbers. *medRxiv*. 2020.
DOI [10.1101/2020.03.14.20036178](https://doi.org/10.1101/2020.03.14.20036178)


<div id="ref-magal2020predicting"></div>


MAGAL, Pierre und Glenn WEBB, 2020. Predicting the number of reported
and unreported cases for the COVID-19 epidemic in South Korea, Italy,
France and Germany. *medRxiv*. 2020.
DOI [10.1101/2020.03.21.20040154](https://doi.org/10.1101/2020.03.21.20040154)


<div id="ref-ihme2020forecasting"></div>


MURRAY, Christopher JL und IHME COVID-19 HEALTH SERVICE UTILIZATION
FORECASTING TEAM, 2020. Forecasting COVID-19 impact on hospital
bed-days, ICU-days, ventilator-days and deaths by US state in the next 4
months. *medRxiv*. 2020.
DOI [10.1101/2020.03.27.20043752](https://doi.org/10.1101/2020.03.27.20043752)

<div id="ref-nishiura2020serial"></div>


NISHIURA, Hiroshi u. a., 2020. Serial interval of novel coronavirus
(COVID-19) infections. *International Journal of Infectious Diseases*.
2020.
DOI [10.1016/j.ijid.2020.02.060](https://doi.org/10.1016/j.ijid.2020.02.060)


<div id="ref-novel2020epidemiological"></div>


THE NCPERE TEAM, 2020. The epidemiological characteristics of an
outbreak of 2019 novel coronavirus diseases (COVID-19) in China. *CCDC
Weekly*. 2020. Bd. 2, Nr. 8, S. 113–122.
DOI [10.3760/cma.j.issn.0254-6450.2020.02.003](https://doi.org/10.3760/cma.j.issn.0254-6450.2020.02.003)


<div id="ref-thompson2019improved"></div>

THOMPSON, R. N. u. a., 2019. Improved inference of time-varying
reproduction numbers during infectious disease outbreaks. *Epidemics*.
2019. Bd. 29, S. 100356.
DOI [https://doi.org/10.1016/j.epidem.2019.100356](https://doi.org/https://doi.org/10.1016/j.epidem.2019.100356)

<div id="ref-verity2020estimates"></div>

VERITY, Robert u. a., 2020. Estimates of the severity of coronavirus
disease 2019: a model-based analysis. *The Lancet infectious diseases*.
2020.
DOI [10.1016/S1473-3099(20)30243-7](https://doi.org/10.1016/S1473-3099$$20$$30243-7)


<div id="ref-walker2020global"></div>

WALKER, Patrick GT u. a., 2020. The Global Impact of COVID-19 and
Strategies for Mitigation and Suppression.. 2020.
DOI [10.25561/77482](https://doi.org/10.25561/77482)

<div id="ref-who2020report"></div>

WHO TEAM, 2020. *Report of the WHO-China Joint Mission on Coronavirus
Disease 2019 (COVID-19)* \[online\]. 2020. Verfügbar unter:
<https://www.who.int/publications-detail/report-of-the-who-china-joint-mission-on-coronavirus-disease-2019-(covid-19)>
