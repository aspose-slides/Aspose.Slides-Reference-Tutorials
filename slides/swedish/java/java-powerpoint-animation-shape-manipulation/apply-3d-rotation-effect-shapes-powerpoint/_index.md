---
title: Använd 3D-rotationseffekt på former i PowerPoint
linktitle: Använd 3D-rotationseffekt på former i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du applicerar 3D-rotationseffekter på former i PowerPoint med Aspose.Slides för Java med denna omfattande, steg-för-steg handledning.
weight: 12
url: /sv/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Använd 3D-rotationseffekt på former i PowerPoint

## Introduktion
Är du redo att ta dina PowerPoint-presentationer till nästa nivå? Att lägga till 3D-rotationseffekter kan göra dina bilder mer dynamiska och engagerande. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer denna steg-för-steg-handledning att visa dig hur du applicerar 3D-rotationseffekter på former i PowerPoint med Aspose.Slides för Java. Låt oss dyka direkt in!
## Förutsättningar
Innan vi börjar, se till att du har följande på plats:
1.  Java Development Kit (JDK): Se till att du har JDK installerat på ditt system. Du kan ladda ner den från[Oracle hemsida](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Ladda ner den senaste versionen av Aspose.Slides for Java från[nedladdningslänk](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Använd en IDE som IntelliJ IDEA eller Eclipse för kodning.
4.  En giltig licens: Om du inte har en licens kan du få en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för att prova funktionerna.
## Importera paket
Låt oss först importera de nödvändiga paketen i ditt Java-projekt. Dessa importer hjälper dig att hantera presentationer och former med Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Steg 1: Konfigurera ditt projekt
Innan du dyker in i koden, ställ in din projektmiljö. Se till att du har lagt till Aspose.Slides för Java till ditt projekts beroenden.
Lägg till Aspose.Slides till ditt projekt:
1.  Ladda ner Aspose.Slides JAR-filerna från[nedladdningssida](https://releases.aspose.com/slides/java/).
2. Lägg till dessa JAR-filer till ditt projekts byggväg.
## Steg 2: Skapa en ny PowerPoint-presentation
I det här steget kommer vi att skapa en ny PowerPoint-presentation.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapa en instans av presentationsklassen
Presentation pres = new Presentation();
```
Det här kodavsnittet initierar ett nytt presentationsobjekt där vi lägger till våra former.
## Steg 3: Lägg till en rektangelform
Låt oss sedan lägga till en rektangelform till den första bilden.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Denna kod lägger till en rektangelform vid den angivna positionen och storleken på den första bilden.
## Steg 4: Använd 3D-rotation på rektangeln
Låt oss nu tillämpa en 3D-rotationseffekt på rektangelformen.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Här ställer vi in djup, kamerarotationsvinklar, kameratyp och belysningstyp för att ge vår rektangel ett 3D-utseende.
## Steg 5: Lägg till en linjeform
Låt oss lägga till en annan form, den här gången en linje, till bilden.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Denna kod placerar en linjeform på bilden.
## Steg 6: Applicera 3D-rotation på linjen
Slutligen kommer vi att tillämpa en 3D-rotationseffekt på linjeformen.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
I likhet med rektangeln ställer vi in 3D-egenskaperna för linjeformen.
## Steg 7: Spara presentationen
När du har lagt till och konfigurerat dina former, spara presentationen.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Denna kod sparar din presentation med det angivna filnamnet i önskat format.
## Slutsats
 Grattis! Du har framgångsrikt tillämpat 3D-rotationseffekter på former i en PowerPoint-presentation med Aspose.Slides för Java. Genom att följa dessa steg kan du skapa visuellt tilltalande och dynamiska presentationer. För ytterligare anpassning och mer avancerade funktioner, se[Aspose.Slides dokumentation](https://reference.aspose.com/slides/java/).
## FAQ's
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt API för att skapa, ändra och manipulera PowerPoint-presentationer programmatiskt.
### Kan jag prova Aspose.Slides för Java gratis?
 Ja, du kan få en[gratis provperiod](https://releases.aspose.com/) eller a[tillfällig licens](https://purchase.aspose.com/temporary-license/) för att testa funktionerna.
### Vilka typer av former kan jag lägga till 3D-effekter i i Aspose.Slides?
Du kan lägga till 3D-effekter till olika former som rektanglar, linjer, ellipser och anpassade former.
### Hur får jag support för Aspose.Slides för Java?
 Du kan besöka[supportforum](https://forum.aspose.com/c/slides/11) för hjälp och för att diskutera eventuella frågor.
### Kan jag använda Aspose.Slides för Java i kommersiella projekt?
 Ja, men du måste köpa en licens. Du kan köpa en från[köpsidan](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
