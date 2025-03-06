---
title: Crea oggetti compositi in forme geometriche
linktitle: Crea oggetti compositi in forme geometriche
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare oggetti compositi in forme geometriche utilizzando Aspose.Slides per Java con questo tutorial completo. Perfetto per gli sviluppatori Java.
weight: 20
url: /it/java/java-powerpoint-shape-formatting-geometry/create-composite-objects-geometry-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
Ehilà! Hai mai desiderato creare forme straordinarie e complesse nelle tue presentazioni PowerPoint utilizzando Java? Bene, sei nel posto giusto. In questo tutorial, approfondiremo la potente libreria Aspose.Slides per Java per creare oggetti compositi in forme geometriche. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida passo passo ti aiuterà a ottenere risultati straordinari in pochissimo tempo. Pronto per iniziare? Immergiamoci!
## Prerequisiti
Prima di addentrarci nel codice, ci sono alcune cose di cui avrai bisogno:
- Java Development Kit (JDK): assicurati di avere JDK 1.8 o versione successiva installata sul tuo computer.
- Ambiente di sviluppo integrato (IDE): un IDE come IntelliJ IDEA o Eclipse ti semplificherà la vita.
-  Aspose.Slides per Java: puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/) oppure usa Maven per includerlo nel tuo progetto.
- Conoscenza di base di Java: questo tutorial presuppone che tu abbia una conoscenza fondamentale di Java.
## Importa pacchetti
Per prima cosa, importiamo i pacchetti necessari per iniziare con Aspose.Slides per Java.
```java
import com.aspose.slides.*;

```

La creazione di oggetti compositi potrebbe sembrare complessa, ma suddividendola in passaggi gestibili, scoprirai che è più semplice di quanto pensi. Creeremo una presentazione PowerPoint, aggiungeremo una forma, quindi definiremo e applicheremo più percorsi geometrici per formare una forma composita.
## Passaggio 1: imposta il tuo progetto
 Prima di scrivere qualsiasi codice, imposta il tuo progetto Java. Crea un nuovo progetto nel tuo IDE e includi Aspose.Slides per Java. Puoi aggiungere la libreria utilizzando Maven o scaricare il file JAR dal file[Pagina di download di Aspose.Slides](https://releases.aspose.com/slides/java/).
### Aggiunta di Aspose.Slides al tuo progetto utilizzando Maven
 Se stai utilizzando Maven, aggiungi la seguente dipendenza al tuo file`pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace with the latest version -->
</dependency>
```
## Passaggio 2: inizializzare la presentazione
Ora creiamo una nuova presentazione di PowerPoint. Inizieremo inizializzando il file`Presentation` classe.
```java
// Nome del file di output
String resultPath = "Your Output Directory" +  "GeometryShapeCompositeObjects.pptx";
Presentation pres = new Presentation();
```
## Passaggio 3: crea una nuova forma
Successivamente, aggiungeremo una nuova forma rettangolare alla prima diapositiva della nostra presentazione.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Passaggio 4: definire il primo percorso geometrico
 Definiremo la prima parte della nostra forma composita creando a`GeometryPath` e aggiungendovi dei punti.
```java
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.moveTo(0, 0);
geometryPath0.lineTo(shape.getWidth(), 0);
geometryPath0.lineTo(shape.getWidth(), shape.getHeight() / 3);
geometryPath0.lineTo(0, shape.getHeight() / 3);
geometryPath0.closeFigure();
```
## Passaggio 5: definire il secondo percorso geometrico
Allo stesso modo, definisci la seconda parte della nostra forma composita.
```java
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.moveTo(0, shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight());
geometryPath1.lineTo(0, shape.getHeight());
geometryPath1.closeFigure();
```
## Passaggio 6: combina i percorsi geometrici
Combina i due percorsi geometrici e impostali sulla forma.
```java
shape.setGeometryPaths(new GeometryPath[]{geometryPath0, geometryPath1});
```
## Passaggio 7: salva la presentazione
Infine, salva la presentazione in un file.
```java
String resultPath = "Your Output Directory" + "GeometryShapeCompositeObjects.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## Passaggio 8: ripulire le risorse
Assicurati di rilasciare tutte le risorse utilizzate dalla presentazione.
```java
if (pres != null) pres.dispose();
```
## Conclusione
E il gioco è fatto! Hai creato con successo una forma composita utilizzando Aspose.Slides per Java. Suddividendo il processo in semplici passaggi, puoi creare facilmente forme complesse e migliorare le tue presentazioni. Continua a sperimentare diversi percorsi geometrici per creare design unici.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria per creare, manipolare e convertire presentazioni PowerPoint in Java.
### Come installo Aspose.Slides per Java?
 Puoi installarlo utilizzando Maven o scaricare il file JAR dal file[sito web](https://releases.aspose.com/slides/java/).
### Posso utilizzare Aspose.Slides per Java in progetti commerciali?
 Sì, ma dovrai acquistare una licenza. Puoi trovare maggiori dettagli su[pagina di acquisto](https://purchase.aspose.com/buy).
### È disponibile una prova gratuita?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso trovare ulteriore documentazione e supporto?
 Dai un'occhiata a[documentazione](https://reference.aspose.com/slides/java/) E[Forum di assistenza](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
