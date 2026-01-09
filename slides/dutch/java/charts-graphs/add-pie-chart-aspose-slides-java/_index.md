---
date: '2026-01-09'
description: Ontdek hoe je Aspose Slides Maven kunt gebruiken om een diagram aan een
  dia toe te voegen en een taartdiagram aan te passen in Java‑presentaties. Stapsgewijze
  installatie, code en praktijkvoorbeelden.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven: Voeg een cirkeldiagram toe aan een presentatie'
url: /nl/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe een cirkeldiagram toe te voegen aan een presentatie met Aspose.Slides Java

## Introductie
Het maken van visueel aantrekkelijke presentaties is cruciaal voor het effectief overbrengen van informatie, vooral wanneer datavisualisatie een belangrijke rol speelt. Als je dit proces wilt automatiseren met **aspose slides maven**, ben je hier op het juiste adres. In deze tutorial leer je hoe je **add chart to slide** — specifiek een cirkeldiagram — gebruikt Aspose.Slides voor Java, en zie je hoe je het kunt aanpassen voor real‑world scenario's.

### Wat je zult leren
- Hoe je een presentatie‑object initialiseert in Java.  
- Stappen om **add a pie chart java** op de eerste dia van een presentatie toe te voegen.  
- Toegang krijgen tot chart‑data workbooks en de worksheets daarin opsommen.  

Laten we duiken in hoe je Aspose.Slides Java kunt benutten om je presentaties te verrijken met dynamische diagrammen!

## Snelle antwoorden
- **Welke bibliotheek voegt diagrammen toe via Maven?** aspose slides maven  
- **Welk diagramtype wordt gedemonstreerd?** Pie chart (add chart to slide)  
- **Minimale Java‑versie vereist?** JDK 16 of later  
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie werkt; productie vereist een licentie  
- **Waar vind ik de Maven‑dependency?** In de setup‑sectie hieronder  

## Wat is Aspose Slides Maven?
Aspose.Slides voor Java is een krachtige API waarmee ontwikkelaars programmatic PowerPoint‑bestanden kunnen maken, wijzigen en renderen. Het Maven‑pakket (`aspose-slides`) vereenvoudigt dependency‑beheer, zodat je je kunt concentreren op het bouwen en aanpassen van dia's—zoals het toevoegen van een cirkeldiagram—zonder je bezig te houden met low‑level bestandsafhandeling.

## Waarom Aspose.Slides Maven gebruiken om een diagram aan een dia toe te voegen?
- **Automatisering:** Genereer rapporten en dashboards automatisch.  
- **Precisie:** Volledige controle over diagramtypen, data en styling.  
- **Cross‑Platform:** Werkt in elke Java‑compatibele omgeving.  

## Vereisten
- **Aspose.Slides for Java** versie 25.4 of later (Maven/Gradle).  
- JDK 16+ geïnstalleerd.  
- Een IDE (IntelliJ IDEA, Eclipse, enz.).  
- Basiskennis van Java en vertrouwdheid met Maven of Gradle.

## Aspose.Slides voor Java installeren
Voeg eerst Aspose.Slides toe aan je project via Maven of Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Of je kunt de [latest release downloaden](https://releases.aspose.com/slides/java/) rechtstreeks van de website van Aspose.

### Licentie‑acquisitie
Aspose.Slides for Java biedt een gratis proefversie met een tijdelijke licentie voor testdoeleinden. Voor onbeperkt productiegebruik koop je een licentie via de [purchase page](https://purchase.aspose.com/buy).

## Implementatie‑gids
Hieronder splitsen we de oplossing op in twee onderdelen: een cirkeldiagram toevoegen en toegang krijgen tot het data‑workbook.

### Onderdeel 1: Een presentatie maken en een diagram toevoegen
#### Overzicht
Dit gedeelte laat zien hoe je een nieuwe presentatie maakt en **add a pie chart** aan de eerste dia toevoegt.

#### Stap‑voor‑stap

**Stap 1: Initialiseert een nieuw Presentation‑object**  
```java
Presentation pres = new Presentation();
```
*Creëert de `Presentation`‑instantie die alle dia's zal bevatten.*

**Stap 2: Voeg een cirkeldiagram toe**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Plaatst een cirkeldiagram op coördinaten (50, 50) met een breedte van 400 en een hoogte van 500. De `ChartType.Pie`‑enum vertelt Aspose een cirkeldiagram te renderen.*

**Stap 3: Ruim bronnen op**  
```java
if (pres != null) pres.dispose();
```
*Vrijgeven van native resources; roep altijd `dispose()` aan wanneer je klaar bent.*

### Onderdeel 2: Toegang tot chart‑data workbook en worksheets
#### Overzicht
Leer hoe je het onderliggende workbook dat de diagramdata opslaat bereikt en door de worksheets iterereert.

#### Stap‑voor‑stap

**Stap 1: (Herbruik) Initialiseert een nieuw Presentation‑object**  
*Zelfde als Onderdeel 1, Stap 1.*

**Stap 2: (Herbruik) Voeg een cirkeldiagram toe**  
*Zelfde als Onderdeel 1, Stap 2.*

**Stap 3: Haal het chart‑data workbook op**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Haal het `IChartDataWorkbook` op dat aan het diagram gekoppeld is.*

**Stap 4: Itereer door worksheets**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Print de naam van elketructuur kunt verifiëren.*

**Stap 5: Ruim bronnen op**  
*Zelfde als Onderdeel 1, Stap 3.*

## Praktische toepassingen
- **Data‑rapportage:** Auto‑genereer slide‑decks met up‑to‑date metrics voor business intelligence.  
- **Academische presentaties:** Visualiseer onderzoeksresultaten zonder handmatig diagrammen te maken.  
- **Marketingmateriaal:** Toon productprestaties of enquête‑resultaten direct.

## Prestatie‑overwegingen
- Houd het aantal dia's en diagrammen redelijk; elk verbruikt geheugen.  
- Roep altijd `dispose()` aan om native resources vrij te geven.  
- Optimaliseer workbook‑data‑verwerking—vermijd het laden van enorme datasets in één diagram.

## Conclusie
We hebben behandeld hoe **aspose slides maven** je in staat stelt **add chart to slide** programmatically te doen en hoe je met het data‑workbook van het diagram werkt. Met deze bouwblokken kun je elke rapportage‑workflow automatiseren die een gepolijste PowerPoint‑output vereist.

### Volgende stappen
- Verken diagram‑stylingopties (kleuren, legenda’s, data‑labels).  
- Verbind met externe databronnen (CSV, databases) om diagrammen dynamisch te vullen.  
- Combineer meerdere diagramtypen in één presentatie voor rijkere storytelling.

## Veelgestelde vragen

**Q: Hoe installeer ik Aspose.Slides voor Java?**  
A: Gebruik de Maven‑ of Gradle‑dependency die hierboven wordt getoond, of download de bibliotheek van de releases‑pagina.

**Q: Wat zijn de systeemvereisten voor Aspose.Slides?**  
A: JDK 16 of later; de bibliotheek is platform‑onafhankelijk.

**Q: Kan ik andere diagramtypen toevoegen naast cirkeldiagrammen?**  
A: Ja, Aspose.Slides ondersteunt bar, line, scatter en vele andere diagramtypen.

**Q: Hoe moet ik grote presentaties efficiënt verwerken?**  
A: Ruim objecten tijdig op, beperk het aantal high‑resolution afbeeldingen, en hergebruik diagram‑templates waar mogelijk.

**Q: Waar vind ik meer details over de functies van Aspose.Slides?**  
A: Bezoek de [Aspose documentation](https://reference.aspose.com/slides/java/) voor een volledige API‑referentie.

**Q: Is een licentie vereist voor commercieel gebruik?**  
A: Een geldige licentie is vereist voor productie; een gratis proefversie is beschikbaar voor evaluatie.

**Q: Bevat het Maven‑pakket alle diagramfunctionaliteiten?**  
A: Ja, het `aspose-slides` Maven‑artifact bevat de volledige diagramengine.

---  

**Laatst bijgewerkt:** 2026-01-09  
**Getest met:** Aspose.Slides 25.4 for Java (jdk16)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## Resources
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)