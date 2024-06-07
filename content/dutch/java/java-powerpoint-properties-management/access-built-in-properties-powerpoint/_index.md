---
title: Toegang tot ingebouwde eigenschappen in PowerPoint
linktitle: Toegang tot ingebouwde eigenschappen in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u toegang krijgt tot ingebouwde eigenschappen in PowerPoint met behulp van Aspose.Slides voor Java. Deze tutorial begeleidt u bij het ophalen van de auteur, de aanmaakdatum en meer.
type: docs
weight: 10
url: /nl/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u toegang krijgt tot ingebouwde eigenschappen in PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Aspose.Slides is een krachtige bibliotheek waarmee Java-ontwikkelaars programmatisch met PowerPoint-presentaties kunnen werken, waardoor taken zoals het lezen en wijzigen van eigenschappen naadloos mogelijk worden.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd. Je kunt het downloaden van[hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides voor Java: Download en installeer Aspose.Slides voor Java van[deze link](https://releases.aspose.com/slides/java/).

## Pakketten importeren
Eerst moet u de benodigde pakketten in uw Java-project importeren. Voeg de volgende importinstructie toe aan het begin van uw Java-bestand:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
```
## Stap 1: Stel het presentatieobject in
Begin met het instellen van het Presentatie-object om de PowerPoint-presentatie weer te geven waarmee u wilt werken. Hier ziet u hoe u het kunt doen:
```java
// Het pad naar de map met het presentatiebestand
String dataDir = "path_to_your_presentation_directory/";
// Instantieer de klasse Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Stap 2: Open de documenteigenschappen
Nadat u het Presentation-object hebt ingesteld, heeft u toegang tot de ingebouwde eigenschappen van de presentatie via de IDocumentProperties-interface. Zo kunt u verschillende eigenschappen ophalen:
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
### Leidinggevende
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Aangepaste datum
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
In deze zelfstudie hebben we geleerd hoe u toegang krijgt tot ingebouwde eigenschappen in PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Door de hierboven beschreven stappen te volgen, kunt u eenvoudig programmatisch verschillende eigenschappen ophalen, zoals auteur, aanmaakdatum en titel.
## Veelgestelde vragen
### Kan ik deze ingebouwde eigenschappen wijzigen met Aspose.Slides voor Java?
Ja, u kunt deze eigenschappen wijzigen met Aspose.Slides. Gebruik eenvoudigweg de juiste instelmethoden die worden geboden door de IDocumentProperties-interface.
### Is Aspose.Slides compatibel met verschillende versies van PowerPoint?
Aspose.Slides ondersteunt een breed scala aan PowerPoint-versies, waardoor compatibiliteit tussen verschillende platforms wordt gegarandeerd.
### Kan ik ook aangepaste eigenschappen ophalen?
Ja, naast de ingebouwde eigenschappen kunt u ook aangepaste eigenschappen ophalen en wijzigen met Aspose.Slides voor Java.
### Biedt Aspose.Slides documentatie en ondersteuning?
 Ja, u kunt uitgebreide documentatie vinden en toegang krijgen tot ondersteuningsforums op de website[Aspose-website](https://reference.aspose.com/slides/java/).
### Is er een proefversie beschikbaar voor Aspose.Slides voor Java?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).