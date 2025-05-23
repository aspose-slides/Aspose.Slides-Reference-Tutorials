---
"date": "2025-04-18"
"description": "Scopri come migliorare le tue presentazioni personalizzando i punti elenco SmartArt con immagini utilizzando Aspose.Slides per Java. Segui questa guida passo passo per ottenere un aspetto professionale."
"title": "Come personalizzare i punti elenco SmartArt con immagini utilizzando Aspose.Slides per Java | Guida passo passo"
"url": "/it/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come personalizzare i punti elenco SmartArt con le immagini utilizzando Aspose.Slides per Java

## Introduzione

Creare presentazioni visivamente accattivanti è fondamentale per catturare l'attenzione del pubblico e comunicare efficacemente il proprio messaggio. Una sfida comune nella progettazione di diapositive è l'ottimizzazione degli elenchi puntati all'interno della grafica SmartArt utilizzando immagini personalizzate. Questo tutorial vi guiderà nell'impostazione di un'immagine come formato di riempimento dei punti elenco nei nodi SmartArt con Aspose.Slides per Java, consentendovi di migliorare le vostre presentazioni in modo professionale.

**Cosa imparerai:**
- Configurazione e utilizzo di Aspose.Slides per Java
- Personalizzazione dei punti elenco con immagini nella grafica SmartArt
- Applicazioni pratiche di questa personalizzazione
- Risoluzione dei problemi comuni

Prima di passare all'implementazione, assicurati che tutto sia pronto.

## Prerequisiti

Per seguire questo tutorial, assicurati di soddisfare i seguenti prerequisiti:

1. **Librerie e dipendenze**Avrai bisogno della libreria Aspose.Slides per Java versione 25.4 o successiva.
2. **Configurazione dell'ambiente**:
   - Un IDE compatibile come IntelliJ IDEA o Eclipse
   - JDK 16 installato sulla tua macchina
3. **Prerequisiti di conoscenza**: Familiarità con la programmazione Java e con la struttura base delle presentazioni PowerPoint.

## Impostazione di Aspose.Slides per Java

Per iniziare, includi la libreria Aspose.Slides nel tuo progetto utilizzando uno dei seguenti metodi:

### Esperto

Aggiungi questa dipendenza al tuo `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Includi questo nel tuo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download diretto

In alternativa, scarica la libreria direttamente da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

**Fasi di acquisizione della licenza**: Aspose offre una licenza di prova gratuita, perfetta per testarne le funzionalità. È possibile richiedere una licenza temporanea o acquistarne una per rimuovere le limitazioni di valutazione.

Per inizializzare e configurare il tuo ambiente, crea un'istanza di `Presentation` classe come mostrato:

```java
Presentation presentation = new Presentation();
```

## Guida all'implementazione

Questa sezione suddividerà il processo in passaggi gestibili, spiegando come ottenere la funzionalità desiderata.

### Aggiunta di SmartArt con riempimento proiettile personalizzato

#### Panoramica

Inizieremo aggiungendo una forma SmartArt alla diapositiva e personalizzandone i punti elenco utilizzando un riempimento immagine.

#### Istruzioni passo passo

**1. Inizializzare l'oggetto di presentazione**

```java
Presentation presentation = new Presentation();
```

*Scopo*: Inizializza una nuova istanza di presentazione in cui aggiungerai la grafica SmartArt.

**2. Aggiungi forma SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Spiegazione*: Questa riga aggiunge una nuova forma SmartArt alla prima diapositiva nella posizione (x=10, y=10) con dimensioni di 500x400 pixel. `VerticalPictureList` layout viene utilizzato per l'allineamento verticale.

**3. Accedi e personalizza il riempimento dei proiettili**

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

*Scopo*: Controlla se il nodo ha un `BulletFillFormat` proprietà. In tal caso, carica un'immagine e la imposta come riempimento per i punti elenco.
*Parametri*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: Percorso del file immagine.
  - `PictureFillMode.Stretch`: Garantisce che l'immagine riempia completamente l'area del proiettile.

**4. Salva la tua presentazione**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}