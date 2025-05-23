---
"description": "Scopri come ottenere il rettangolo di porzione in PowerPoint utilizzando Aspose.Slides per Java con questo tutorial dettagliato e passo dopo passo. Perfetto per gli sviluppatori Java."
"linktitle": "Ottieni una porzione rettangolare in PowerPoint con Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Ottieni una porzione rettangolare in PowerPoint con Java"
"url": "/it/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ottieni una porzione rettangolare in PowerPoint con Java

## Introduzione
Creare presentazioni dinamiche in Java è un gioco da ragazzi con Aspose.Slides per Java. In questo tutorial, approfondiremo i dettagli per ottenere il rettangolo di porzione in PowerPoint usando Aspose.Slides. Parleremo di tutto, dalla configurazione dell'ambiente all'analisi passo passo del codice. Iniziamo!
## Prerequisiti
Prima di passare al codice, assicuriamoci di avere tutto il necessario per seguirlo senza problemi:
1. Java Development Kit (JDK): assicurati di avere installato sul tuo computer la versione JDK 8 o superiore.
2. Aspose.Slides per Java: scarica l'ultima versione da [Qui](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): Eclipse, IntelliJ IDEA o qualsiasi altro IDE Java di tua scelta.
4. Conoscenza di base di Java: è essenziale comprendere la programmazione Java.
## Importa pacchetti
Per prima cosa, importiamo i pacchetti necessari. Tra questi, Aspose.Slides e alcuni altri, utili per gestire il nostro compito in modo efficiente.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Fase 1: Impostazione della presentazione
Il primo passo è creare una nuova presentazione. Questa sarà la nostra tela su cui lavorare.
```java
Presentation pres = new Presentation();
```
## Passaggio 2: creazione di una tabella
Ora aggiungiamo una tabella alla prima diapositiva della nostra presentazione. Questa tabella conterrà le celle in cui aggiungeremo il testo.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Passaggio 3: aggiunta di paragrafi alle celle
Successivamente, creeremo dei paragrafi e li aggiungeremo a una cella specifica della tabella. Questo comporta la cancellazione del testo esistente e l'aggiunta di nuovi paragrafi.
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
Per rendere più dinamica la nostra presentazione, aggiungeremo una cornice di testo a una forma e ne imposteremo l'allineamento.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Passaggio 5: calcolo delle coordinate
Dobbiamo ottenere le coordinate dell'angolo in alto a sinistra della cella della tabella. Questo ci aiuterà a posizionare le forme con precisione.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Fase 6: Aggiunta di cornici a paragrafi e porzioni
Utilizzando il `IParagraph.getRect()` E `IPortion.getRect()` Con i metodi, possiamo aggiungere cornici ai nostri paragrafi e alle nostre porzioni. Questo significa iterare attraverso i paragrafi e le porzioni, creare forme attorno ad essi e personalizzarne l'aspetto.
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
## Passaggio 7: aggiunta di cornici ai paragrafi di AutoShape
Allo stesso modo, aggiungeremo cornici ai paragrafi nella nostra AutoShape, migliorando l'aspetto visivo della presentazione.
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
## Fase 9: Pulizia
È buona norma eliminare l'oggetto presentazione per liberare risorse.
```java
if (pres != null) pres.dispose();
```
## Conclusione
Congratulazioni! Hai imparato come ottenere il rettangolo di porzione in PowerPoint utilizzando Aspose.Slides per Java. Questa potente libreria apre un mondo di possibilità per creare presentazioni dinamiche e visivamente accattivanti a livello di programmazione. Approfondisci Aspose.Slides ed esplora altre funzionalità per migliorare ulteriormente le tue presentazioni.
## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare le presentazioni di PowerPoint a livello di programmazione.
### Posso utilizzare Aspose.Slides per Java in progetti commerciali?
Sì, Aspose.Slides per Java può essere utilizzato in progetti commerciali. È possibile acquistare una licenza da [Qui](https://purchase.aspose.com/buy).
### È disponibile una versione di prova gratuita di Aspose.Slides per Java?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
La documentazione è disponibile [Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto per Aspose.Slides per Java?
Puoi ottenere supporto dal forum Aspose [Qui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}