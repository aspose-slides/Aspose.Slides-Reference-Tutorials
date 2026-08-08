---
date: '2026-08-06'
description: Leer hoe u legend font color kunt wijzigen en chart legend text kunt
  aanpassen met Aspose.Slides for Java. Volg step‑by‑step instructies om chart legends
  snel te customize.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Leer hoe u legend font color kunt wijzigen en chart legend text kunt
  aanpassen met Aspose.Slides for Java. Deze gids toont u de exacte stappen en best
  practices.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Hoe de legend font color te wijzigen in Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Hoe de legend font color te wijzigen in Aspose.Slides for Java
url: /nl/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe de legendeletterkleur te wijzigen in Aspose.Slides voor Java

## Introductie
Als je de **legendeletterkleur** in een diagram moet wijzigen, biedt Aspose.Slides voor Java volledige controle over elk legende-item. Deze tutorial leidt je door het aanpassen van de tekststijlen van de legende, het toepassen van vet of cursief lettertype, en het instellen van effen kleuren zodat je diagrammen er precies uitzien zoals je wilt. Aan het einde van deze gids kun je de legendetekst van diagrammen zelfverzekerd aanpassen en de wijzigingen integreren in elke bestaande presentatie.

**Wat je zult leren**
- Hoe je **legendeletterkleur** programmatisch kunt wijzigen.
- Manieren om **diagramlegendetekst** te wijzigen, zoals vet, cursief en grootte.
- Tips voor het toepassen van de wijzigingen op meerdere diagrammen in één presentatie.
- Hoe je deze stappen kunt integreren in een grotere automatiseringsworkflow.

## Snelle antwoorden
- **Kan ik de kleur van één legende-item wijzigen?** Ja – krijg toegang tot het item via zijn index en stel het opvulformaat in op een effen kleur.  
- **Heb ik een licentie nodig om deze API's te gebruiken?** Een tijdelijke of betaalde licentie is vereist voor productie; een gratis proefversie werkt voor evaluatie.  
- **Welke Java‑versie wordt ondersteund?** Aspose.Slides voor Java 25.4+ werkt met JDK 16 en nieuwer.  
- **Zullen de wijzigingen andere diagramonderdelen beïnvloeden?** Nee, legendeopmaak staat los van de opmaak van de gegevensreeksen.  
- **Is batchverwerking mogelijk?** Absoluut – loop door dia's en diagrammen om dezelfde legende‑instellingen toe te passen op een volledige set.

## Wat is het wijzigen van de legendeletterkleur?
`change legend font color` verwijst naar de programmatische bewerking waarbij de tekstkleur van de legende‑items van een diagram wordt ingesteld via de Aspose.Slides‑API. Deze bewerking werkt het visuele uiterlijk van de legende bij zonder de onderliggende gegevens te wijzigen.

## Waarom diagramlegendes aanpassen?
Aspose.Slides ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** en kan presentaties met **meer dan 500 dia's** verwerken terwijl het geheugenverbruik onder de 200 MB blijft. Het aanpassen van legenden verbetert de leesbaarheid, versterkt merkkleuren en zorgt ervoor dat belangrijke gegevenspunten opvallen — vooral in zakelijke of educatieve presentaties waar visuele duidelijkheid beslissingen aandrijft.

## Vereisten
- **Aspose.Slides voor Java** bibliotheek (Versie 25.4 of later).  
- Java Development Kit (JDK) 16 of hoger.  
- Een IDE zoals IntelliJ IDEA, Eclipse of NetBeans.  
- Maven of Gradle voor afhankelijkheidsbeheer.  
- Basiskennis van Java‑programmeren.

## Aspose.Slides voor Java instellen
Om te beginnen met het aanpassen van je diagramlegenden, voeg je de bibliotheek toe aan je project met een van de onderstaande methoden.

### Maven
Voeg de volgende afhankelijkheid toe aan je `pom.xml`‑bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Voeg deze regel toe aan je `build.gradle`‑bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Directe download
Je kunt de nieuwste JAR ook downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Stappen voor licentie‑acquisitie
- **Gratis proefversie:** Begin met een gratis proefversie om de functies van Aspose.Slides te verkennen.  
- **Tijdelijke licentie:** Vraag een tijdelijke licentie aan voor een uitgebreide evaluatie.  
- **Aankoop:** Voor volledige toegang kun je een licentie kopen via [Aspose Purchase](https://purchase.aspose.com/buy).

#### Basisinitialisatie en -configuratie
Na het toevoegen van de bibliotheek aan je project:
1. Initialiseer Aspose.Slides in je Java‑applicatie.  
2. Laad een bestaande presentatie of maak een nieuwe aan.

## Hoe de legendeletterkleur wijzigen?
Om de legendeletterkleur te wijzigen, laad je de presentatie, haal je het diagramobject op, verkrijg je de legende, en wijzig je vervolgens het tekstformaat van elk legende-item door het opvultype in te stellen op effen en de gewenste kleur op te geven. Deze enkele bewerking werkt de legendetekstkleur direct bij zonder de hele dia opnieuw te hoeven tekenen. Voorbeeld: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Deze aanpak werkt voor elk diagramtype en vereist geen herrenderen van de volledige dia.

### Toegang tot en wijzigen van legendeteksteigenschappen

#### Definitie‑anker
De `IChart`‑interface vertegenwoordigt een diagramobject op een dia, en de methode `getLegend()` retourneert een `ILegend`‑object dat een verzameling `ILegendEntry`‑items bevat.

#### Een diagram toevoegen aan je presentatie
1. **Laad de presentatie:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Voeg een gegroepeerd kolomdiagram toe:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Lettertype‑eigenschappen aanpassen
3. **Toegang tot het tekstformaat van een legende-item:**  
   Hier is `legendEntry` een `ILegendEntry`‑object dat een enkel item in de diagramlegende vertegenwoordigt.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Stel vet‑ en cursief‑stijlen in met een specifieke hoogte:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Verander het opvultype naar een effen kleur voor betere zichtbaarheid:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### De presentatie opslaan
6. **Sla je wijzigingen op:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Veelvoorkomende valkuilen en probleemoplossing
- Controleer of de index van het legende-item overeenkomt met de volgorde van de reeksen in je diagram.  
- Zorg ervoor dat je een bibliotheekversie gebruikt die `setSolidFillColor` ondersteunt (beschikbaar sinds versie 20.9).  

## Praktische toepassingen
Het aanpassen van legendetekst is nuttig in veel praktische scenario's:

1. **Zakelijke presentaties:** Stem legende‑kleuren af op de huisstijl voor een verzorgde uitstraling.  
2. **Educatief materiaal:** Markeer belangrijke gegevensreeksen door contrasterende legende‑kleuren te gebruiken.  
3. **Marketingpresentaties:** Benadruk prestatiestatistieken met vetgedrukte, gekleurde legenden om de aandacht van belanghebbenden te trekken.  

Je kunt legende‑updates ook automatiseren door kleurwaarden uit een database of configuratiebestand te halen.

## Prestatie‑overwegingen
Houd bij het verwerken van grote presentaties deze tips in gedachten:

- **Efficiënt geheugenbeheer:** Roep `presentation.dispose()` aan na het opslaan om native bronnen vrij te geven.  
- **Laad alleen benodigde dia's:** Gebruik `Presentation.load(String path, LoadOptions options)` met `LoadOptions.setLoadOnlySlideIds()` als je een subset nodig hebt.  
- **Batchverwerking:** Groepeer legende‑updates per dia om het aantal API‑aanroepen te verminderen en de doorvoersnelheid te verbeteren.

## Conclusie
Je weet nu hoe je **legendeletterkleur** kunt **wijzigen** en **diagramlegendetekst** kunt **aanpassen** met Aspose.Slides voor Java. Deze aanpassingen verbeteren de visuele duidelijkheid en helpen je gegevens effectiever over te brengen. Experimenteer met verschillende lettertypen, groottes en kleuren om te voldoen aan de stijlgids van je presentatie, en verken andere diagram‑stijleigenschappen om echt professionele presentaties te maken.

**Volgende stappen**
- Probeer dezelfde legende‑stijl toe te passen op taart‑ en lijndiagrammen.  
- Combineer legende‑aanpassing met opmaak van gegevenslabels voor een volledig merk‑diagram.  

Klaar om je presentaties naar een hoger niveau te tillen? Implementeer de bovenstaande stappen en zie het verschil direct!

## Veelgestelde vragen
1. **Hoe wijzig ik de kleur van de tekst van een legende-item?**  
   Gebruik `getFillFormat().setFillType(FillType.Solid)` en vervolgens `setSolidFillColor(Color.YOUR_COLOR)` op het tekstformaat van het legende-item.

2. **Kan ik deze wijzigingen toepassen op alle legenden in een presentatie?**  
   Ja – loop door elke dia, zoek elk diagram, en werk de legende‑items bij binnen een lus.

3. **Is het mogelijk de lettergrootte dynamisch aan te passen op basis van de tekstlengte?**  
   Je kunt de benodigde grootte berekenen met `TextFrame.getTextFrameFormat().getFontHeight()` en instellen via `setFontHeight(double)`.

4. **Wat als ik problemen ondervind met de indexering van legende-items?**  
   Controleer dubbel of de index die je gebruikt overeenkomt met de volgorde van de reeksen; onthoud dat indexen nul‑gebaseerd zijn.

5. **Waar vind ik meer Aspose.Slides‑voorbeelden?**  
   Bekijk de [Aspose Documentation](https://reference.aspose.com/slides/java/) voor uitgebreide handleidingen en API‑referenties.

**Aanvullende V&A**

**V: Heeft het wijzigen van de legendeletterkleur invloed op geëxporteerde PDF‑bestanden?**  
A: Nee, de kleurwijziging wordt behouden in alle exportformaten die door Aspose.Slides worden ondersteund, inclusief PDF en PPTX.

**V: Kan ik een verloop gebruiken in plaats van een effen kleur?**  
A: Ja – stel `FillType.Gradient` in en configureer de verloopstops via `getGradientStyle()`.

**V: Hoeveel legende‑items kan een diagram hebben?**  
A: Een diagram kan tot 256 legende‑items hebben, alleen beperkt door het aantal gegevensreeksen dat je toevoegt.

## Bronnen
- **Documentatie:** Uitgebreide gids voor het gebruik van Aspose.Slides‑functies ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Toegang tot de nieuwste versie van Aspose.Slides voor Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Aankoop:** Koop een licentie om volledige functionaliteit te ontgrendelen ([Link](https://purchase.aspose.com/buy)).  
- **Gratis proefversie & tijdelijke licentie:** Begin met gratis proefversies en vraag tijdelijke licenties aan ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Ondersteuning:** Krijg hulp van de community op het supportforum van Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Laatst bijgewerkt:** 2026-08-06  
**Getest met:** Aspose.Slides voor Java 25.4  
**Auteur:** Aspose

## Gerelateerde tutorials
- [PowerPoint-diagrammen verbeteren: lettertype‑ en as‑aanpassing met Aspose.Slides voor Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides voor Java: Dynamische tekstframes & gids voor lettertype‑aanpassing](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Diagrammen animeren in PowerPoint met Aspose.Slides voor Java – Een stap‑voor‑stap‑gids](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}