---
title: Ottieni porzione di rettangolo in PowerPoint con Java
linktitle: Ottieni porzione di rettangolo in PowerPoint con Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come ottenere il rettangolo della porzione in PowerPoint utilizzando Aspose.Slides per Java con questo tutorial dettagliato passo dopo passo. Perfetto per gli sviluppatori Java.
type: docs
weight: 12
url: /it/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---
## introduzione
Creare presentazioni dinamiche in Java è un gioco da ragazzi con Aspose.Slides per Java. In questo tutorial, ci immergeremo nel nocciolo della questione per ottenere il rettangolo della porzione in PowerPoint utilizzando Aspose.Slides. Copriremo tutto, dalla configurazione del tuo ambiente alla scomposizione del codice passo dopo passo. Quindi iniziamo!
## Prerequisiti
Prima di addentrarci nel codice, assicuriamoci di avere tutto ciò di cui hai bisogno per seguire senza problemi:
1. Java Development Kit (JDK): assicurati di avere JDK 8 o versione successiva installata sul tuo computer.
2.  Aspose.Slides per Java: scarica l'ultima versione da[Qui](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): Eclipse, IntelliJ IDEA o qualsiasi altro IDE Java di tua scelta.
4. Conoscenza di base di Java: la comprensione della programmazione Java è essenziale.
## Importa pacchetti
Per prima cosa importiamo i pacchetti necessari. Ciò includerà Aspose.Slides e alcuni altri per gestire il nostro compito in modo efficiente.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Passaggio 1: impostazione della presentazione
Il primo passo è creare una nuova presentazione. Questa sarà la nostra tela su cui lavorare.
```java
Presentation pres = new Presentation();
```
## Passaggio 2: creazione di una tabella
Ora aggiungiamo una tabella alla prima diapositiva della nostra presentazione. Questa tabella conterrà le celle in cui aggiungeremo il nostro testo.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Passaggio 3: aggiunta di paragrafi alle celle
Successivamente, creeremo paragrafi e li aggiungeremo a una cella specifica nella tabella. Ciò comporta la cancellazione di qualsiasi testo esistente e l'aggiunta di nuovi paragrafi.
```java
// Crea paragrafi
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Aggiungi testo nella cella della tabella
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Passaggio 4: aggiunta di una cornice di testo a una forma automatica
Per rendere la nostra presentazione più dinamica, aggiungeremo una cornice di testo a una forma e ne imposteremo l'allineamento.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Passaggio 5: calcolo delle coordinate
Dobbiamo ottenere le coordinate dell'angolo in alto a sinistra della cella della tabella. Questo ci aiuterà a posizionare le forme in modo accurato.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Passaggio 6: aggiunta di cornici a paragrafi e porzioni
 Usando il`IParagraph.getRect()` E`IPortion.getRect()`metodi, possiamo aggiungere cornici ai nostri paragrafi e porzioni. Ciò comporta l'iterazione dei paragrafi e delle parti, la creazione di forme attorno ad essi e la personalizzazione del loro aspetto.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Passaggio 7: aggiunta di cornici ai paragrafi di forma automatica
Allo stesso modo, aggiungeremo cornici ai paragrafi nella nostra forma automatica, migliorando l'attrattiva visiva della presentazione.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Passaggio 8: salvataggio della presentazione
Infine, salveremo la nostra presentazione in un percorso specificato.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Passaggio 9: pulizia
È buona norma smaltire l'oggetto di presentazione per liberare risorse.
```java
if (pres != null) pres.dispose();
```
## Conclusione
Congratulazioni! Hai imparato con successo come ottenere il rettangolo della porzione in PowerPoint utilizzando Aspose.Slides per Java. Questa potente libreria apre un mondo di possibilità per creare a livello di codice presentazioni dinamiche e visivamente accattivanti. Immergiti più a fondo in Aspose.Slides ed esplora più funzionalità per migliorare ulteriormente le tue presentazioni.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare le presentazioni di PowerPoint a livello di codice.
### Posso utilizzare Aspose.Slides per Java in progetti commerciali?
 Sì, Aspose.Slides per Java può essere utilizzato in progetti commerciali. È possibile acquistare una licenza da[Qui](https://purchase.aspose.com/buy).
### È disponibile una prova gratuita per Aspose.Slides per Java?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
 La documentazione è disponibile[Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto per Aspose.Slides per Java?
 Puoi ottenere supporto dal forum Aspose[Qui](https://forum.aspose.com/c/slides/11).