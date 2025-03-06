---
title: Pas Outer Shadow toe in PowerPoint met Java
linktitle: Pas Outer Shadow toe in PowerPoint met Java
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u het buitenste schaduweffect in PowerPoint kunt toepassen met behulp van Java met Aspose.Slides. Verbeter uw presentaties met diepte en visuele aantrekkingskracht.
weight: 13
url: /nl/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pas Outer Shadow toe in PowerPoint met Java

## Invoering
Het maken van visueel aantrekkelijke PowerPoint-presentaties omvat vaak het toevoegen van verschillende effecten aan vormen en tekst. Eén zo'n effect is de buitenste schaduw, waardoor elementen kunnen opvallen en diepte aan uw dia's kan worden toegevoegd. In deze zelfstudie leert u hoe u een buitenschaduweffect op een vorm in PowerPoint kunt toepassen met behulp van Java met Aspose.Slides.
## Vereisten

Voordat u met deze zelfstudie begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd. U kunt de nieuwste versie van JDK downloaden en installeren vanaf de Oracle-website.

2.  Aspose.Slides voor Java: Download en installeer Aspose.Slides voor Java vanaf de[downloadpagina](https://releases.aspose.com/slides/java/).

3. Integrated Development Environment (IDE): Kies uw favoriete Java IDE, zoals Eclipse, IntelliJ IDEA of NetBeans, voor het coderen en uitvoeren van Java-applicaties.

4. Basiskennis van Java: Bekendheid met de grondbeginselen van de Java-programmeertaal en objectgeoriënteerde concepten zal nuttig zijn voor het begrijpen van de codevoorbeelden.

## Pakketten importeren

Importeer eerst de benodigde pakketten voor het werken met Aspose.Slides en gerelateerde functionaliteiten in uw Java-project:

```java
import com.aspose.slides.*;
```

Laten we nu de voorbeeldcode opsplitsen in meerdere stappen om het buitenste schaduweffect toe te passen op een vorm in PowerPoint met behulp van Java met Aspose.Slides:

## Stap 1: Richt uw projectomgeving in

Maak een nieuw Java-project in de IDE van uw voorkeur en voeg de Aspose.Slides voor Java-bibliotheek toe aan het buildpad van uw project.

## Stap 2: Initialiseer het presentatieobject

 Maak een exemplaar van de`Presentation` klasse, die een PowerPoint-presentatiebestand vertegenwoordigt.

```java
Presentation presentation = new Presentation();
```

## Stap 3: Voeg een dia en vorm toe

Haal een verwijzing op naar de dia waaraan u de vorm wilt toevoegen en voeg vervolgens een AutoVorm (bijvoorbeeld een rechthoek) toe aan de dia.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Stap 4: Pas de vorm aan

Stel het vultype van de vorm in op 'Geen opvulling' en voeg tekst toe aan de vorm.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Stap 5: Pas de tekst aan

Krijg toegang tot de teksteigenschappen van de vorm en pas de lettergrootte aan.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Stap 6: Schakel het effect Buitenschaduw in

Schakel het buitenste schaduweffect in voor het tekstgedeelte.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Stap 7: Stel schaduwparameters in

Definieer de parameters voor het buitenste schaduweffect, zoals vervagingsradius, richting, afstand en schaduwkleur.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Stap 8: Sla de presentatie op

Sla de gewijzigde presentatie op met het buitenste schaduweffect toegepast op de vorm.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Conclusie

Gefeliciteerd! U hebt met succes een buitenschaduweffect op een vorm in PowerPoint toegepast met behulp van Java met Aspose.Slides. Experimenteer met verschillende parameters om de gewenste visuele effecten in uw presentaties te bereiken.

## Veelgestelde vragen

### Kan ik het buitenste schaduweffect op andere vormen dan rechthoeken toepassen?
Ja, u kunt het buitenste schaduweffect toepassen op verschillende vormen die worden ondersteund door Aspose.Slides, zoals cirkels, driehoeken en aangepaste vormen.

### Is het mogelijk om de kleur en intensiteit van de schaduw aan te passen?
Absoluut! U hebt volledige controle over de schaduwparameters, inclusief kleur, vervagingsradius, richting en afstand.

### Kan ik meerdere effecten op dezelfde vorm toepassen?
Ja, u kunt meerdere effecten combineren, zoals buitenschaduw, binnenschaduw, gloed en reflectie, om de visuele aantrekkingskracht van vormen en tekst in uw presentaties te vergroten.

### Ondersteunt Aspose.Slides het toepassen van effecten op tekstelementen?
Ja, u kunt niet alleen effecten op vormen toepassen, maar ook op afzonderlijke tekstgedeelten binnen vormen, waardoor u uitgebreide flexibiliteit krijgt bij het ontwerpen van uw dia's.

### Waar kan ik meer bronnen en ondersteuning vinden voor Aspose.Slides?
 U kunt verwijzen naar de[documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde API-referenties en verken de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor gemeenschapsondersteuning en discussies.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
