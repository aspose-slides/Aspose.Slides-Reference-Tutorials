---
"description": "Leer hoe u de ClsId van de hoofddirectory instelt in Aspose.Slides voor Java-presentaties. Pas het gedrag van hyperlinks aan met CLSID."
"linktitle": "Hoofdmap ClsId in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Hoofdmap ClsId in Java-dia's"
"url": "/nl/java/media-controls/root-directory-clsid-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hoofdmap ClsId in Java-dia's


## Inleiding tot het instellen van de rootdirectory ClsId in Aspose.Slides voor Java

In Aspose.Slides voor Java kunt u de ClsId van de rootdirectory instellen. Dit is de CLSID (Class Identifier) die wordt gebruikt om de applicatie te specificeren die als rootdirectory moet worden gebruikt wanneer een hyperlink in uw presentatie wordt geactiveerd. In deze handleiding leggen we u stap voor stap uit hoe u dit kunt doen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java-bibliotheek toegevoegd aan uw project. U kunt deze downloaden van [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).
- Een code-editor of Integrated Development Environment (IDE) die is ingesteld voor Java-ontwikkeling.

## Stap 1: Een nieuwe presentatie maken

Laten we eerst een nieuwe presentatie maken met Aspose.Slides voor Java. In dit voorbeeld maken we een lege presentatie.

```java
// Naam van het uitvoerbestand
String resultPath = "your_output_path/pres.ppt"; // Vervang "your_output_path" door de gewenste uitvoermap.
Presentation pres = new Presentation();
```

In de bovenstaande code definiëren we het pad voor het uitvoerpresentatiebestand en maken we een nieuw `Presentation` voorwerp.

## Stap 2: Stel de ClsId van de hoofdmap in

Om de ClsId van de hoofddirectory in te stellen, moet u een exemplaar van `PptOptions` en stel de gewenste CLSID in. De CLSID vertegenwoordigt de applicatie die als root directory wordt gebruikt wanneer een hyperlink wordt geactiveerd.

```java
PptOptions pptOptions = new PptOptions();
// Stel CLSID in op 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

In de bovenstaande code maken we een `PptOptions` object en stel de CLSID in op 'Microsoft Powerpoint.Show.8'. U kunt dit vervangen door de CLSID van de applicatie die u als root directory wilt gebruiken.

## Stap 3: Sla de presentatie op

Laten we de presentatie nu opslaan met de Root Directory ClsId ingesteld.

```java
// Presentatie opslaan
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

In deze stap slaan we de presentatie op in de opgegeven `resultPath` met de `PptOptions` die we eerder hebben gemaakt.

## Stap 4: Opruimen

Vergeet niet om de `Presentation` bezwaar maken tegen het vrijgeven van toegewezen bronnen.

```java
if (pres != null) {
    pres.dispose();
}
```

## Volledige broncode voor rootdirectory ClsId in Java-dia's

```java
// Naam van het uitvoerbestand
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// Stel CLSID in op 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Presentatie opslaan
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusie

U hebt de ClsID voor de hoofdmap succesvol ingesteld in Aspose.Slides voor Java. Hiermee kunt u de applicatie specificeren die als hoofdmap wordt gebruikt wanneer hyperlinks in uw presentatie worden geactiveerd. U kunt de CLSID aanpassen aan uw specifieke wensen.

## Veelgestelde vragen

### Hoe vind ik de CLSID voor een specifieke toepassing?

Om de CLSID voor een specifieke toepassing te vinden, kunt u de documentatie of bronnen van de ontwikkelaar van de toepassing raadplegen. CLSID's zijn unieke identificatiecodes die aan COM-objecten worden toegewezen en zijn doorgaans specifiek voor elke toepassing.

### Kan ik een aangepaste CLSID instellen voor de hoofdmap?

Ja, u kunt een aangepaste CLSID voor de hoofdmap instellen door de gewenste CLSID-waarde op te geven met behulp van de `setRootDirectoryClsid` methode, zoals getoond in het codevoorbeeld. Hiermee kunt u een specifieke applicatie als rootdirectory gebruiken wanneer hyperlinks in uw presentatie worden geactiveerd.

### Wat gebeurt er als ik de Root Directory ClsId niet instel?

Als u de ClsId voor de hoofdmap niet instelt, is het standaardgedrag afhankelijk van de viewer of applicatie waarmee de presentatie wordt geopend. Het is mogelijk dat deze zijn eigen standaardapplicatie als hoofdmap gebruikt wanneer hyperlinks worden geactiveerd.

### Kan ik de Root Directory ClsId voor individuele hyperlinks wijzigen?

Nee, de ClsId van de rootdirectory wordt doorgaans ingesteld op presentatieniveau en is van toepassing op alle hyperlinks binnen de presentatie. Als u verschillende toepassingen voor afzonderlijke hyperlinks wilt opgeven, moet u deze hyperlinks mogelijk afzonderlijk in uw code verwerken.

### Zijn er beperkingen aan de CLSID's die ik kan gebruiken?

De CLSID's die u kunt gebruiken, worden doorgaans bepaald door de applicaties die op het systeem zijn geïnstalleerd. Gebruik CLSID's die overeenkomen met geldige applicaties die hyperlinks kunnen verwerken. Houd er rekening mee dat het gebruik van een ongeldige CLSID tot onverwacht gedrag kan leiden.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}