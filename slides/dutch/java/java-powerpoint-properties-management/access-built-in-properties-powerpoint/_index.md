---
"description": "Leer hoe je toegang krijgt tot ingebouwde eigenschappen in PowerPoint met Aspose.Slides voor Java. Deze tutorial begeleidt je bij het ophalen van de auteur, aanmaakdatum en meer."
"linktitle": "Toegang tot ingebouwde eigenschappen in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Toegang tot ingebouwde eigenschappen in PowerPoint"
"url": "/nl/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Toegang tot ingebouwde eigenschappen in PowerPoint

## Invoering
In deze tutorial onderzoeken we hoe je toegang krijgt tot ingebouwde eigenschappen in PowerPoint-presentaties met Aspose.Slides voor Java. Aspose.Slides is een krachtige bibliotheek waarmee Java-ontwikkelaars programmatisch met PowerPoint-presentaties kunnen werken, waardoor taken zoals het lezen en wijzigen van eigenschappen naadloos verlopen.
## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat de JDK op uw systeem is geïnstalleerd. U kunt deze downloaden van [hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides voor Java: Download en installeer Aspose.Slides voor Java van [deze link](https://releases.aspose.com/slides/java/).

## Pakketten importeren
Eerst moet u de benodigde pakketten importeren naar uw Java-project. Voeg de volgende import-instructie toe aan het begin van uw Java-bestand:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Stap 1: Het presentatieobject instellen
Begin met het instellen van het presentatieobject om de PowerPoint-presentatie weer te geven waarmee u wilt werken. Zo doet u dat:
```java
// Het pad naar de map met het presentatiebestand
String dataDir = "path_to_your_presentation_directory/";
// Instantieer de presentatieklasse
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Stap 2: Toegang tot de documenteigenschappen
Nadat u het presentatieobject hebt ingesteld, hebt u toegang tot de ingebouwde eigenschappen van de presentatie via de interface IDocumentProperties. Zo kunt u verschillende eigenschappen ophalen:
### Categorie
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Huidige status
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Aanmaakdatum
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Auteur
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Beschrijving
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Trefwoorden
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Laatst gewijzigd door
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Toezichthouder
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Gewijzigde datum
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Presentatieformaat
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Laatste afdrukdatum
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Gedeeld tussen producenten
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Onderwerp
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Titel
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Conclusie
In deze tutorial hebben we geleerd hoe je toegang krijgt tot ingebouwde eigenschappen in PowerPoint-presentaties met Aspose.Slides voor Java. Door de bovenstaande stappen te volgen, kun je eenvoudig verschillende eigenschappen, zoals auteur, aanmaakdatum en titel, programmatisch ophalen.
## Veelgestelde vragen
### Kan ik deze ingebouwde eigenschappen wijzigen met Aspose.Slides voor Java?
Ja, u kunt deze eigenschappen wijzigen met Aspose.Slides. Gebruik hiervoor de juiste setter-methoden die beschikbaar zijn in de IDocumentProperties-interface.
### Is Aspose.Slides compatibel met verschillende versies van PowerPoint?
Aspose.Slides ondersteunt een breed scala aan PowerPoint-versies en garandeert compatibiliteit op verschillende platforms.
### Kan ik ook aangepaste eigenschappen ophalen?
Ja, naast ingebouwde eigenschappen kunt u met Aspose.Slides voor Java ook aangepaste eigenschappen ophalen en wijzigen.
### Biedt Aspose.Slides documentatie en ondersteuning?
Ja, u kunt uitgebreide documentatie vinden en toegang krijgen tot ondersteuningsforums op de [Aspose-website](https://reference.aspose.com/slides/java/).
### Is er een proefversie beschikbaar voor Aspose.Slides voor Java?
Ja, u kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}