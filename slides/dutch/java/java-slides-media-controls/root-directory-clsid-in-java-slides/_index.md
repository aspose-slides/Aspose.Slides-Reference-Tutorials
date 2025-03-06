---
title: Root Directory ClsId in Java-dia's
linktitle: Root Directory ClsId in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u Root Directory ClsId in Aspose.Slides instelt voor Java-presentaties. Pas het hyperlinkgedrag aan met CLSID.
weight: 10
url: /nl/java/media-controls/root-directory-clsid-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Inleiding tot het instellen van rootdirectory ClsId in Aspose.Slides voor Java

In Aspose.Slides voor Java kunt u de Root Directory ClsId instellen. Dit is de CLSID (Class Identifier) die wordt gebruikt om de toepassing op te geven die als hoofdmap moet worden gebruikt wanneer een hyperlink in uw presentatie wordt geactiveerd. In deze handleiding leggen we u stap voor stap uit hoe u dit kunt doen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Slides voor Java-bibliotheek toegevoegd aan uw project. Je kunt het downloaden van[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).
- Een code-editor of Integrated Development Environment (IDE) opgezet voor Java-ontwikkeling.

## Stap 1: Maak een nieuwe presentatie

Laten we eerst een nieuwe presentatie maken met Aspose.Slides voor Java. In dit voorbeeld maken we een lege presentatie.

```java
// Naam van uitvoerbestand
String resultPath = "your_output_path/pres.ppt"; // Vervang "your_output_path" door de gewenste uitvoermap.
Presentation pres = new Presentation();
```

In de bovenstaande code definiëren we het pad voor het uitvoerpresentatiebestand en maken we een nieuw`Presentation` voorwerp.

## Stap 2: Stel de rootdirectory ClsId in

 Om de Root Directory ClsId in te stellen, moet u een exemplaar van maken`PptOptions` en stel de gewenste CLSID in. De CLSID vertegenwoordigt de applicatie die zal worden gebruikt als de hoofdmap wanneer een hyperlink wordt geactiveerd.

```java
PptOptions pptOptions = new PptOptions();
// Stel CLSID in op 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 In de bovenstaande code maken we een`PptOptions` object en stel de CLSID in op 'Microsoft Powerpoint.Show.8'. U kunt deze vervangen door de CLSID van de toepassing die u als hoofdmap wilt gebruiken.

## Stap 3: Sla de presentatie op

Laten we nu de presentatie opslaan met de Root Directory ClsId-set.

```java
// Presentatie opslaan
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 In deze stap slaan we de presentatie op in het opgegeven bestand`resultPath` met de`PptOptions` die we eerder hebben gemaakt.

## Stap 4: Opruimen

 Vergeet niet om de`Presentation` bezwaar maken tegen het vrijgeven van toegewezen middelen.

```java
if (pres != null) {
    pres.dispose();
}
```

## Volledige broncode voor rootdirectory ClsId in Java-dia's

```java
// Naam van uitvoerbestand
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//stel CLSID in op 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Presentatie opslaan
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusie

U hebt met succes de Root Directory ClsId ingesteld in Aspose.Slides voor Java. Hiermee kunt u de toepassing opgeven die als hoofdmap wordt gebruikt wanneer hyperlinks in uw presentatie worden geactiveerd. U kunt de CLSID aanpassen aan uw specifieke vereisten.

## Veelgestelde vragen

### Hoe vind ik de CLSID voor een specifieke toepassing?

Om de CLSID voor een specifieke toepassing te vinden, kunt u de documentatie of bronnen raadplegen die door de ontwikkelaar van de toepassing zijn geleverd. CLSID's zijn unieke ID's die aan COM-objecten worden toegewezen en zijn doorgaans specifiek voor elke toepassing.

### Kan ik een aangepaste CLSID instellen voor de hoofdmap?

 Ja, u kunt een aangepaste CLSID instellen voor de hoofdmap door de gewenste CLSID-waarde op te geven met behulp van de`setRootDirectoryClsid` methode, zoals weergegeven in het codevoorbeeld. Hierdoor kunt u een specifieke applicatie als hoofdmap gebruiken wanneer hyperlinks in uw presentatie worden geactiveerd.

### Wat gebeurt er als ik de Root Directory ClsId niet instel?

Als u de Root Directory ClsId niet instelt, is het standaardgedrag afhankelijk van de viewer of toepassing die wordt gebruikt om de presentatie te openen. Het kan zijn eigen standaardapplicatie gebruiken als hoofdmap wanneer hyperlinks worden geactiveerd.

### Kan ik de Root Directory ClsId voor individuele hyperlinks wijzigen?

Nee, de Root Directory ClsId wordt doorgaans ingesteld op presentatieniveau en is van toepassing op alle hyperlinks binnen de presentatie. Als u verschillende toepassingen voor afzonderlijke hyperlinks moet opgeven, moet u deze hyperlinks mogelijk afzonderlijk in uw code verwerken.

### Zijn er beperkingen op de CLSID's die ik kan gebruiken?

De CLSID's die u kunt gebruiken, worden doorgaans bepaald door de toepassingen die op het systeem zijn geïnstalleerd. U moet CLSID's gebruiken die overeenkomen met geldige toepassingen die hyperlinks kunnen verwerken. Houd er rekening mee dat het gebruik van een ongeldige CLSID tot onverwacht gedrag kan leiden.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
