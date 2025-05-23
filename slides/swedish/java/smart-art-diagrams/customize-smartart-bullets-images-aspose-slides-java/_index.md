---
"date": "2025-04-18"
"description": "Lär dig hur du kan förbättra dina presentationer genom att anpassa SmartArt-punkter med bilder med Aspose.Slides för Java. Följ den här steg-för-steg-guiden för ett professionellt utseende."
"title": "Hur man anpassar SmartArt-punkter med bilder med Aspose.Slides för Java | Steg-för-steg-guide"
"url": "/sv/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man anpassar SmartArt-punkter med bilder med hjälp av Aspose.Slides för Java

## Introduktion

Att skapa visuellt tilltalande presentationer är avgörande för att fånga publikens uppmärksamhet och effektivt kommunicera ditt budskap. En vanlig utmaning vid design av bilder är att förbättra punktlistor i SmartArt-grafik med hjälp av anpassade bilder. Den här handledningen guidar dig genom att ställa in en bild som punktformat i SmartArt-noder med Aspose.Slides för Java, så att du kan höja dina presentationer professionellt.

**Vad du kommer att lära dig:**
- Konfigurera och använda Aspose.Slides för Java
- Anpassa punktlistor med bilder i SmartArt-grafik
- Praktiska tillämpningar av denna anpassning
- Felsökning av vanliga problem

Innan vi går in i implementeringen, se till att du har allt klart.

## Förkunskapskrav

För att följa den här handledningen, se till att du uppfyller följande krav:

1. **Bibliotek och beroenden**Du behöver Aspose.Slides för Java-biblioteket version 25.4 eller senare.
2. **Miljöinställningar**:
   - En kompatibel IDE som IntelliJ IDEA eller Eclipse
   - JDK 16 installerat på din maskin
3. **Kunskapsförkunskaper**Bekantskap med Java-programmering och grundläggande struktur för PowerPoint-presentationer.

## Konfigurera Aspose.Slides för Java

Börja med att inkludera Aspose.Slides-biblioteket i ditt projekt med någon av följande metoder:

### Maven

Lägg till detta beroende till din `pom.xml` fil:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Inkludera detta i din `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning

Alternativt kan du ladda ner biblioteket direkt från [Aspose.Slides för Java-versioner](https://releases.aspose.com/slides/java/).

**Steg för att förvärva licens**Aspose erbjuder en gratis provlicens som är perfekt för att testa dess funktioner. Du kan begära en tillfällig licens eller köpa en för att ta bort utvärderingsbegränsningar.

För att initiera och konfigurera din miljö, skapa en instans av `Presentation` klass som visas:

```java
Presentation presentation = new Presentation();
```

## Implementeringsguide

Det här avsnittet kommer att dela upp processen i hanterbara steg och förklara hur man uppnår önskad funktionalitet.

### Lägga till SmartArt med anpassad punktfyllning

#### Översikt

Vi börjar med att lägga till en SmartArt-form i din bild och anpassa dess punktlistor med hjälp av en bildfyllning.

#### Steg-för-steg-instruktioner

**1. Initiera presentationsobjekt**

```java
Presentation presentation = new Presentation();
```

*Ändamål*Initierar en ny presentationsinstans där du lägger till SmartArt-grafiken.

**2. Lägg till SmartArt-form**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Förklaring*Den här raden lägger till en ny SmartArt-form till den första bilden vid position (x=10, y=10) med måtten 500x400 pixlar. `VerticalPictureList` layout används för vertikal justering.

**3. Åtkomst till och anpassa punktfyllning**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Ändamål*Kontrollerar om noden har en `BulletFillFormat` egenskap. Om så är fallet laddas en bild och anges som fyllnad för punkter.
*Parametrar*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`Sökvägen till din bildfil.
  - `PictureFillMode.Stretch`: Säkerställer att bilden fyller punktlistan helt.

**4. Spara din presentation**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}