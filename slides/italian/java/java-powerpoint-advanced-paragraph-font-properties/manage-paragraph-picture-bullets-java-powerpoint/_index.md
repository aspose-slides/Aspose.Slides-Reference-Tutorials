---
title: Gestisci i punti elenco delle immagini dei paragrafi in Java PowerPoint
linktitle: Gestisci i punti elenco delle immagini dei paragrafi in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere elenchi puntati personalizzati alle diapositive di PowerPoint utilizzando Aspose.Slides per Java. Segui questa guida dettagliata passo dopo passo per un'integrazione perfetta.
type: docs
weight: 11
url: /it/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---
## introduzione
Creare presentazioni accattivanti e visivamente accattivanti è un'abilità cruciale nel mondo degli affari moderno. Gli sviluppatori Java possono sfruttare Aspose.Slides per migliorare le loro presentazioni con elenchi puntati personalizzati nelle diapositive di PowerPoint. Questo tutorial ti guiderà attraverso il processo passo dopo passo, assicurandoti di poter aggiungere con sicurezza elenchi puntati di immagini alle tue presentazioni.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Kit di sviluppo Java (JDK) installato
- Ambiente di sviluppo integrato (IDE) come Eclipse o IntelliJ IDEA
- Aspose.Slides per la libreria Java
- Conoscenza base della programmazione Java
- File immagine per l'immagine del proiettile
 Per scaricare la libreria Aspose.Slides per Java, visitare il sito[pagina di download](https://releases.aspose.com/slides/java/) . Per la documentazione consultare il[documentazione](https://reference.aspose.com/slides/java/).
## Importa pacchetti
Innanzitutto, assicurati di aver importato i pacchetti necessari per il tuo progetto. Aggiungi le seguenti importazioni all'inizio del tuo file Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Suddividiamo il processo in passaggi gestibili.
## Passaggio 1: imposta la directory del progetto
Crea una nuova directory per il tuo progetto. Questa directory conterrà il file Java, la libreria Aspose.Slides e il file immagine per il punto elenco.
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: inizializzare la presentazione
 Inizializza una nuova istanza di`Presentation` classe. Questo oggetto rappresenta la tua presentazione PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Passaggio 3: accedi alla prima diapositiva
Accedi alla prima diapositiva della presentazione. Le diapositive hanno indice zero, quindi la prima diapositiva ha indice 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 4: carica l'immagine del proiettile
Carica l'immagine che desideri utilizzare per i proiettili. Questa immagine dovrebbe essere inserita nella directory del tuo progetto.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Passaggio 5: aggiungi una forma alla diapositiva
Aggiungi una forma alla diapositiva. La forma conterrà il testo con i punti elenco personalizzati.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Passaggio 6: accedi alla cornice di testo
Accedi alla cornice di testo della forma per manipolarne i paragrafi.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Passaggio 7: rimuovere il paragrafo predefinito
Rimuovi il paragrafo predefinito che viene aggiunto automaticamente alla cornice di testo.
```java
textFrame.getParagraphs().removeAt(0);
```
## Passaggio 8: crea un nuovo paragrafo
Crea un nuovo paragrafo e imposta il suo testo. Questo paragrafo conterrà i punti elenco delle immagini personalizzate.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Passaggio 9: imposta lo stile e l'immagine del punto elenco
Imposta lo stile del punto elenco per utilizzare l'immagine personalizzata caricata in precedenza.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Passaggio 10: regolare l'altezza del proiettile
Imposta l'altezza del punto elenco per assicurarti che abbia un bell'aspetto nella presentazione.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Passaggio 11: aggiungi il paragrafo alla cornice di testo
Aggiungi il paragrafo appena creato alla cornice di testo della forma.
```java
textFrame.getParagraphs().add(paragraph);
```
## Passaggio 12: salva la presentazione
Infine, salva la presentazione sia come file PPTX che come file PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Conclusione
 E il gioco è fatto! Seguendo questi passaggi, puoi facilmente aggiungere elenchi puntati personalizzati alle tue presentazioni PowerPoint utilizzando Aspose.Slides per Java. Questa potente libreria offre un'ampia gamma di funzionalità per aiutarti a creare presentazioni professionali e visivamente accattivanti. Non dimenticare di esplorare il[documentazione](https://reference.aspose.com/slides/java/)per funzionalità più avanzate e opzioni di personalizzazione.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che consente agli sviluppatori Java di creare, modificare e manipolare le presentazioni PowerPoint a livello di codice.
### Posso utilizzare qualsiasi immagine per i punti elenco delle immagini?
Sì, puoi utilizzare qualsiasi immagine per i punti elenco purché sia accessibile dalla directory del progetto.
### Ho bisogno di una licenza per utilizzare Aspose.Slides per Java?
 Aspose.Slides per Java richiede una licenza per la piena funzionalità. È possibile ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/) o acquistare una licenza completa[Qui](https://purchase.aspose.com/buy).
### Posso aggiungere più paragrafi con stili di punti elenco diversi in una forma?
Sì, puoi aggiungere più paragrafi con stili di punti elenco diversi a una singola forma creando e configurando ogni paragrafo individualmente.
### Dove posso trovare ulteriori esempi e supporto?
 Puoi trovare altri esempi in[documentazione](https://reference.aspose.com/slides/java/) e ottieni supporto dalla comunità Aspose su[forum](https://forum.aspose.com/c/slides/11).