---
"description": "Lär dig hur du får åtkomst till inbyggda egenskaper i PowerPoint med Aspose.Slides för Java. Den här handledningen guidar dig genom att hämta författare, skapandedatum och mer."
"linktitle": "Åtkomst till inbyggda egenskaper i PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Åtkomst till inbyggda egenskaper i PowerPoint"
"url": "/sv/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Åtkomst till inbyggda egenskaper i PowerPoint

## Introduktion
den här handledningen ska vi utforska hur man får åtkomst till inbyggda egenskaper i PowerPoint-presentationer med hjälp av Aspose.Slides för Java. Aspose.Slides är ett kraftfullt bibliotek som gör det möjligt för Java-utvecklare att arbeta med PowerPoint-presentationer programmatiskt, vilket möjliggör uppgifter som att läsa och ändra egenskaper sömlöst.
## Förkunskapskrav
Innan vi börjar, se till att du har följande förutsättningar:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner det från [här](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från [den här länken](https://releases.aspose.com/slides/java/).

## Importera paket
Först måste du importera de nödvändiga paketen till ditt Java-projekt. Lägg till följande import-sats i början av din Java-fil:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Steg 1: Konfigurera presentationsobjektet
Börja med att konfigurera presentationsobjektet så att det representerar PowerPoint-presentationen du vill arbeta med. Så här gör du:
```java
// Sökvägen till katalogen som innehåller presentationsfilen
String dataDir = "path_to_your_presentation_directory/";
// Instansiera Presentation-klassen
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Steg 2: Åtkomst till dokumentegenskaperna
Efter att du har konfigurerat presentationsobjektet kan du komma åt presentationens inbyggda egenskaper med hjälp av gränssnittet IDocumentProperties. Så här kan du hämta olika egenskaper:
### Kategori
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Nuvarande status
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Skapandedatum
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
### Delat mellan producenter
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
I den här handledningen lärde vi oss hur man får åtkomst till inbyggda egenskaper i PowerPoint-presentationer med hjälp av Aspose.Slides för Java. Genom att följa stegen som beskrivs ovan kan du enkelt hämta olika egenskaper som författare, skapandedatum och titel programmatiskt.
## Vanliga frågor
### Kan jag ändra dessa inbyggda egenskaper med hjälp av Aspose.Slides för Java?
Ja, du kan ändra dessa egenskaper med Aspose.Slides. Använd helt enkelt lämpliga setter-metoder som tillhandahålls av IDocumentProperties-gränssnittet.
### Är Aspose.Slides kompatibelt med olika versioner av PowerPoint?
Aspose.Slides stöder en mängd olika PowerPoint-versioner, vilket säkerställer kompatibilitet mellan olika plattformar.
### Kan jag även hämta anpassade egenskaper?
Ja, förutom inbyggda egenskaper kan du även hämta och ändra anpassade egenskaper med hjälp av Aspose.Slides för Java.
### Erbjuder Aspose.Slides dokumentation och support?
Ja, du kan hitta omfattande dokumentation och få tillgång till supportforum på [Asposes webbplats](https://reference.aspose.com/slides/java/).
### Finns det en testversion tillgänglig för Aspose.Slides för Java?
Ja, du kan ladda ner en gratis testversion från [här](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}