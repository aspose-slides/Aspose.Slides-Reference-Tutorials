---
"description": "Scopri come aggiungere elenchi puntati ai paragrafi nelle diapositive di PowerPoint utilizzando Aspose.Slides per Java. Questo tutorial ti guiderà passo dopo passo con esempi di codice."
"linktitle": "Aggiungere elenchi puntati di paragrafo in PowerPoint utilizzando Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere elenchi puntati di paragrafo in PowerPoint utilizzando Java"
"url": "/it/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere elenchi puntati di paragrafo in PowerPoint utilizzando Java

## Introduzione
L'aggiunta di elenchi puntati ai paragrafi migliora la leggibilità e la struttura delle presentazioni di PowerPoint. Aspose.Slides per Java offre strumenti robusti per la gestione delle presentazioni a livello di codice, inclusa la possibilità di formattare il testo con diversi stili di elenco puntato. In questo tutorial, imparerai come integrare gli elenchi puntati nelle diapositive di PowerPoint utilizzando codice Java, sfruttando Aspose.Slides.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza di base della programmazione Java.
- JDK (Java Development Kit) installato sul sistema.
- Libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, importa i pacchetti Aspose.Slides necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Passaggio 1: imposta il tuo progetto
Per prima cosa, crea un nuovo progetto Java e aggiungi la libreria Aspose.Slides per Java al percorso di build del progetto.
## Passaggio 2: inizializzare una presentazione
Inizializza un oggetto di presentazione (`Presentation`) per iniziare a lavorare con le diapositive.
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di un'istanza di presentazione
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla diapositiva e alla cornice di testo
Accedi alla diapositiva (`ISlide`) e la sua cornice di testo (`ITextFrame`) in cui vuoi aggiungere i punti elenco.
```java
// Accesso alla prima diapositiva
ISlide slide = pres.getSlides().get_Item(0);
// Aggiunta e accesso ad Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Accesso alla cornice di testo della forma automatica creata
ITextFrame txtFrm = aShp.getTextFrame();
```
## Passaggio 4: creare e formattare paragrafi con elenchi puntati
Crea paragrafi (`Paragraph`) e impostare gli stili dei punti elenco, i rientri e il testo.
```java
// Creare un paragrafo
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Creazione di un altro paragrafo
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Passaggio 5: Salva la presentazione
Salvare la presentazione modificata in un file PowerPoint (`PPTX`).
```java
// Scrivere la presentazione come file PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Passaggio 6: pulizia delle risorse
Eliminare l'oggetto presentazione per liberare risorse.
```java
// Eliminare l'oggetto di presentazione
if (pres != null) {
    pres.dispose();
}
```

## Conclusione
Aggiungere elenchi puntati ai paragrafi in PowerPoint utilizzando Aspose.Slides per Java è semplicissimo grazie agli esempi di codice forniti. Personalizza stili e formattazione dei punti elenco in base alle tue esigenze di presentazione.

## Domande frequenti
### Posso personalizzare i colori dei punti elenco?
Sì, puoi impostare colori personalizzati per i punti elenco utilizzando l'API Aspose.Slides.
### Come faccio ad aggiungere elenchi puntati annidati?
L'annidamento dei punti elenco consiste nell'aggiungere paragrafi all'interno di paragrafi, regolando di conseguenza il rientro.
### Posso creare stili di elenco puntato diversi per diapositive diverse?
Sì, è possibile applicare stili di elenco puntato unici a diverse diapositive tramite programmazione.
### Aspose.Slides è compatibile con Java 11?
Sì, Aspose.Slides supporta Java 11 e versioni successive.
### Dove posso trovare altri esempi e documentazione?
Visita [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/) per guide ed esempi completi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}