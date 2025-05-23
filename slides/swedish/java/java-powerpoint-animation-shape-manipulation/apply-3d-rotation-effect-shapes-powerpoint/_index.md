---
"description": "Lär dig hur du använder 3D-rotationseffekter på former i PowerPoint med Aspose.Slides för Java med den här omfattande steg-för-steg-handledningen."
"linktitle": "Använd 3D-rotationseffekt på former i PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Använd 3D-rotationseffekt på former i PowerPoint"
"url": "/sv/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Använd 3D-rotationseffekt på former i PowerPoint

## Introduktion
Är du redo att ta dina PowerPoint-presentationer till nästa nivå? Att lägga till 3D-rotationseffekter kan göra dina bilder mer dynamiska och engagerande. Oavsett om du är en erfaren utvecklare eller precis har börjat, visar den här steg-för-steg-handledningen hur du tillämpar 3D-rotationseffekter på former i PowerPoint med Aspose.Slides för Java. Nu kör vi!
## Förkunskapskrav
Innan vi börjar, se till att du har följande på plats:
1. Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner det från [Oracles webbplats](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides för Java: Ladda ner den senaste versionen av Aspose.Slides för Java från [nedladdningslänk](https://releases.aspose.com/slides/java/).
3. Integrerad utvecklingsmiljö (IDE): Använd en IDE som IntelliJ IDEA eller Eclipse för kodning.
4. Giltigt körkort: Om du inte har körkort kan du få ett [tillfällig licens](https://purchase.aspose.com/temporary-license/) att testa funktionerna.
## Importera paket
Först ska vi importera de nödvändiga paketen till ditt Java-projekt. Dessa importer hjälper dig att hantera presentationer och former med Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Steg 1: Konfigurera ditt projekt
Innan du går in i koden, konfigurera din projektmiljö. Se till att du har lagt till Aspose.Slides för Java i projektets beroenden.
Lägg till Aspose.Slides i ditt projekt:
1. Ladda ner Aspose.Slides JAR-filerna från [nedladdningssida](https://releases.aspose.com/slides/java/).
2. Lägg till dessa JAR-filer i ditt projekts byggsökväg.
## Steg 2: Skapa en ny PowerPoint-presentation
I det här steget skapar vi en ny PowerPoint-presentation.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av Presentation-klassen
Presentation pres = new Presentation();
```
Det här kodavsnittet initierar ett nytt presentationsobjekt där vi lägger till våra former.
## Steg 3: Lägg till en rektangelform
Nästa steg är att lägga till en rektangelform på den första bilden.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Den här koden lägger till en rektangelform på den angivna positionen och storleken på den första bilden.
## Steg 4: Använd 3D-rotation på rektangeln
Nu ska vi tillämpa en 3D-rotationseffekt på rektangelformen.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Här ställer vi in djup, kamerans rotationsvinklar, kameratyp och ljustyp för att ge vår rektangel ett 3D-utseende.
## Steg 5: Lägg till en linjeform
Låt oss lägga till en annan form, den här gången en linje, på bilden.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Den här koden placerar en linjeform på bilden.
## Steg 6: Använd 3D-rotation på linjen
Slutligen kommer vi att tillämpa en 3D-rotationseffekt på linjeformen.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
I likhet med rektangeln ställer vi in 3D-egenskaperna för linjeformen.
## Steg 7: Spara presentationen
Spara presentationen när du har lagt till och konfigurerat dina former.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Den här koden sparar din presentation med det angivna filnamnet i önskat format.
## Slutsats
Grattis! Du har framgångsrikt tillämpat 3D-rotationseffekter på former i en PowerPoint-presentation med Aspose.Slides för Java. Genom att följa dessa steg kan du skapa visuellt tilltalande och dynamiska presentationer. För ytterligare anpassning och mer avancerade funktioner, se [Aspose.Slides-dokumentation](https://reference.aspose.com/slides/java/).
## Vanliga frågor
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt API för att skapa, modifiera och manipulera PowerPoint-presentationer programmatiskt.
### Kan jag prova Aspose.Slides för Java gratis?
Ja, du kan få en [gratis provperiod](https://releases.aspose.com/) eller en [tillfällig licens](https://purchase.aspose.com/temporary-license/) för att testa funktionerna.
### Vilka typer av former kan jag lägga till 3D-effekter i Aspose.Slides?
Du kan lägga till 3D-effekter på olika former som rektanglar, linjer, ellipser och anpassade former.
### Hur får jag stöd för Aspose.Slides för Java?
Du kan besöka [supportforum](https://forum.aspose.com/c/slides/11) för hjälp och för att diskutera eventuella problem.
### Kan jag använda Aspose.Slides för Java i kommersiella projekt?
Ja, men du måste köpa en licens. Du kan köpa en från [köpsida](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}