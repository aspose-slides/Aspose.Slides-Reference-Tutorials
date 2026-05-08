---
date: '2026-02-17'
description: Leer hoe u taartdiagrammen aan PowerPoint‑presentaties kunt toevoegen
  met Aspose.Slides voor Java. Volg deze stapsgewijze handleiding om professionele
  taartdiagrammen te maken en aan te passen.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Hoe voeg je een cirkeldiagram toe aan PowerPoint met Aspose.Slides voor Java
url: /nl/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak en pas taartdiagrammen aan in PowerPoint met Aspose.Slides voor Java

## Inleiding

Heb je moeite om gegevens effectief te visualiseren in je PowerPoint‑presentaties? **Een taartdiagram PowerPoint**‑dia toevoegen kan ruwe cijfers meteen omzetten in een duidelijk visueel verhaal. Met Aspose.Slides voor Java kun je programmatisch **een taartdiagram PowerPoint**‑bestanden toevoegen, waardoor je volledige controle hebt over ontwerp en data zonder PowerPoint handmatig te openen. In deze tutorial lopen we het volledige proces door — van het instellen van de bibliotheek tot het aanpassen van individuele datapunten — zodat je in enkele minuten gepolijste, data‑gedreven dia's kunt leveren.

### Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.Slides voor Java (nieuwste versie).  
- **Kan ik een diagram maken zonder PowerPoint geïnstalleerd?** Ja, de API werkt volledig offline.  
- **Welke Java‑versie is vereist?** JDK 16 of later wordt aanbevolen.  
- **Hoe wijzig ik de kleur van een partitie?** Gebruik de `setFillType` en `setSolidFillColor` methoden op het datapunten.  
- **Is een licentie verplicht?** Een proefversie werkt voor ontwikkeling; een permanente licentie verwijdert evaluatielimieten.

### Wat je zult leren
- Hoe je programmatisch **een taartdiagram PowerPoint** toevoegt met Java.  
- Manieren om partitie‑explosie, kleuren en andere visuele eigenschappen aan te passen.  
- Best practices voor resource‑beheer en prestaties bij het verwerken van grote presentaties.

## Waarom een taartdiagram PowerPoint toevoegen met Aspose.Slides voor Java?
Een taartdiagram direct vanuit code insluiten stelt je in staat up‑to‑date rapporten te genereren, maandelijkse dashboards te automatiseren of gepersonaliseerde presentaties on‑the‑fly te maken. Het elimineert handmatige copy‑paste‑fouten, zorgt voor consistentie tussen presentaties en integreert soepel met bestaande Java‑back‑ends.

## Vereisten

Zorg ervoor dat je het volgende hebt:

- **Aspose.Slides voor Java‑bibliotheek** – de tutorial verwijst naar versie 25.4 (de nieuwste release op het moment van schrijven).  
- Een compatibele **Java Development Kit (JDK)** – JDK 16+ heeft de voorkeur.  
- Basiskennis van **Maven** of **Gradle** voor dependency‑beheer.  

## Aspose.Slides voor Java instellen

Om te beginnen, voeg je de Aspose.Slides‑bibliotheek toe aan je project.

### Maven
Voeg deze afhankelijkheid toe aan je `pom.xml`‑bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Neem het volgende op in je `build.gradle`‑bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Download de nieuwste versie rechtstreeks van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licenties
Om Aspose.Slides zonder beperkingen te gebruiken:

- Begin met een **gratis proefversie** om de API te evalueren.  
- Vraag een **tijdelijke licentie** aan voor uitgebreid testen op de [Temporary License](https://purchase.aspose.com/temporary-license/) pagina.  
- Koop een volledige abonnement via de [Purchase page](https://purchase.aspose.com/buy).

## Hoe een taartdiagram PowerPoint toevoegen met Aspose.Slides voor Java

Hieronder vind je een stap‑voor‑stap‑gids die precies laat zien hoe je een taartdiagram maakt en aanpast.

### Stap 1: Initialiseer de presentatie
Maak eerst een nieuw `Presentation`‑object aan. Dit vertegenwoordigt een lege PowerPoint‑file.
```java
Presentation pres = new Presentation();
```

### Stap 2: Voeg het taartdiagram toe
Voeg een taartdiagram toe aan de eerste dia. De coördinaten (50, 50) en grootte (600 × 400) werken goed voor een standaard 16:9‑dia.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Stap 3: Sla de presentatie op
Schrijf de presentatie naar schijf. Vervang `YOUR_OUTPUT_DIRECTORY` door de map waarin je het bestand wilt opslaan.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Stap 4: Ruim bronnen op
Dispose het `Presentation`‑object om native bronnen vrij te geven.
```java
if (pres != null) pres.dispose();
```

## Aanpassen van explosie en kleur van datapunten

Het aanpassen van individuele partities maakt je diagram beter leesbaar, vooral wanneer je een specifieke waarde wilt benadrukken.

### Stap 1: Laad een bestaande presentatie (of hergebruik de zojuist gemaakte)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Stap 2: Toegang tot het diagram en doel‑datapunt
Hier halen we het tweede datapunt (index 1) op uit de eerste serie.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Stap 3: Pas explosie en kleur toe
Schep de partitie visueel uit en wijzig de vulkleur naar blauw.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Stap 4: Opslaan en disposen
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Praktische toepassingen
- **Verkooprapporten:** Markeer best verkopende producten met uitgepofte partities.  
- **Budgetanalyse:** Wijs verschillende kleuren toe aan afdelingen voor snelle visuele vergelijking.  
- **Educatieve dia's:** Splits complexe concepten op in gemakkelijk verteerbare diagramsegmenten.

## Prestatie‑overwegingen
- **Dispose objecten** onmiddellijk om geheugenlekken te voorkomen, vooral bij het genereren van veel dia's in een lus.  
- **Monitor heap‑gebruik** voor grote presentaties; overweeg streaming‑output met `Save`‑overloads die een `OutputStream` accepteren.  
- Blijf bij **JDK 16+** om te profiteren van de nieuwste garbage‑collection‑verbeteringen.

## Conclusie
Je hebt nu een volledige, productie‑klare workflow om **een taartdiagram PowerPoint**‑bestanden te maken met Aspose.Slides voor Java. Experimenteer met verschillende explosie‑afstanden, kleuren en datasets om bij je branding te passen. Wanneer je er klaar voor bent, verken dan andere diagramtypen — staaf, lijn of spreiding — om een volledige analytics‑dashboard binnen PowerPoint te bouwen.

## FAQ‑sectie
1. **Wat is het belangrijkste voordeel van het gebruik van Aspose.Slides voor Java?**  
   - Het vereenvoudigt het programmatisch maken en manipuleren van PowerPoint‑bestanden en biedt een breed scala aan functies.  
2. **Kan ik andere diagramtypen aanpassen met Aspose.Slides?**  
   - Absoluut! Aspose.Slides ondersteunt diverse diagramtypen zoals staaf-, lijn‑ en spreidingsdiagrammen.  
3. **Hoe ga ik om met meerdere dia's bij het maken van diagrammen?**  
   - Toegang tot elke dia via de index met de `get_Item()`‑methode om wijzigingen over verschillende dia's toe te passen.  
4. **Wat als mijn taartdiagram niet correct wordt weergegeven na aanpassing?**  
   - Controleer de coördinaten en afmetingen die in `addChart()` worden gebruikt, zodat ze binnen je dia‑lay-out passen.  
5. **Waar vind ik meer geavanceerde functies voor Aspose.Slides?**  
   - Bekijk de [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) voor extra functionaliteiten en opties.

## Bronnen
- **Documentatie:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Bibliotheek downloaden:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Licentie kopen:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Gratis proefversie:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Tijdelijke licentie:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Supportforum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Laatst bijgewerkt:** 2026-02-17  
**Getest met:** Aspose.Slides voor Java 25.4 (JDK 16 classifier)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}