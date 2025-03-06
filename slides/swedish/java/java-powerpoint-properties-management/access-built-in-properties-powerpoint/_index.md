---
title: Få åtkomst till inbyggda egenskaper i PowerPoint
linktitle: Få åtkomst till inbyggda egenskaper i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du kommer åt inbyggda egenskaper i PowerPoint med Aspose.Slides för Java. Denna handledning guidar dig genom att hämta författare, skapandedatum och mer.
weight: 10
url: /sv/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
I den här handledningen kommer vi att undersöka hur du kommer åt inbyggda egenskaper i PowerPoint-presentationer med Aspose.Slides för Java. Aspose.Slides är ett kraftfullt bibliotek som låter Java-utvecklare arbeta med PowerPoint-presentationer programmatiskt, vilket möjliggör uppgifter som att läsa och ändra egenskaper sömlöst.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner den från[här](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från[den här länken](https://releases.aspose.com/slides/java/).

## Importera paket
Först måste du importera de nödvändiga paketen till ditt Java-projekt. Lägg till följande importsats i början av din Java-fil:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Steg 1: Ställ in presentationsobjektet
Börja med att ställa in Presentation-objektet så att det representerar den PowerPoint-presentation du vill arbeta med. Så här kan du göra det:
```java
// Sökvägen till katalogen som innehåller presentationsfilen
String dataDir = "path_to_your_presentation_directory/";
// Instantiera presentationsklassen
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Steg 2: Öppna dokumentegenskaperna
Efter att ha ställt in Presentation-objektet kan du komma åt presentationens inbyggda egenskaper med hjälp av IDocumentProperties-gränssnittet. Så här kan du hämta olika egenskaper:
### Kategori
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Nuvarande status
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Skapelsedagen
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Författare
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Beskrivning
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Nyckelord
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Senast ändrad av
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Handledare
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Ändrat datum
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Presentationsformat
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Senaste utskriftsdatum
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Delas mellan producenter
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Ämne
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Titel
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Slutsats
den här handledningen lärde vi oss hur man kommer åt inbyggda egenskaper i PowerPoint-presentationer med Aspose.Slides för Java. Genom att följa stegen som beskrivs ovan kan du enkelt hämta olika egenskaper som författare, skapelsedatum och titel programmatiskt.
## FAQ's
### Kan jag ändra dessa inbyggda egenskaper med Aspose.Slides för Java?
Ja, du kan ändra dessa egenskaper med Aspose.Slides. Använd helt enkelt lämpliga sättermetoder som tillhandahålls av IDocumentProperties-gränssnittet.
### Är Aspose.Slides kompatibel med olika versioner av PowerPoint?
Aspose.Slides stöder ett brett utbud av PowerPoint-versioner, vilket säkerställer kompatibilitet mellan olika plattformar.
### Kan jag hämta anpassade egenskaper också?
Ja, förutom inbyggda egenskaper kan du också hämta och ändra anpassade egenskaper med Aspose.Slides för Java.
### Erbjuder Aspose.Slides dokumentation och support?
 Ja, du kan hitta omfattande dokumentation och få tillgång till supportforum på[Aspose hemsida](https://reference.aspose.com/slides/java/).
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
