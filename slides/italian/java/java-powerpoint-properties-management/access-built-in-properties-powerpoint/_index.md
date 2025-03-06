---
title: Accedi alle proprietà integrate in PowerPoint
linktitle: Accedi alle proprietà integrate in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come accedere alle proprietà integrate in PowerPoint utilizzando Aspose.Slides per Java. Questo tutorial ti guida nel recupero dell'autore, della data di creazione e altro ancora.
type: docs
weight: 10
url: /it/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---
## introduzione
In questo tutorial esploreremo come accedere alle proprietà integrate nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Aspose.Slides è una potente libreria che consente agli sviluppatori Java di lavorare con presentazioni PowerPoint a livello di codice, abilitando attività come la lettura e la modifica delle proprietà senza problemi.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. Puoi scaricarlo da[Qui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides per Java: scarica e installa Aspose.Slides per Java da[questo link](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari nel tuo progetto Java. Aggiungi la seguente istruzione di importazione all'inizio del tuo file Java:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Passaggio 1: impostare l'oggetto di presentazione
Inizia impostando l'oggetto Presentazione per rappresentare la presentazione di PowerPoint con cui vuoi lavorare. Ecco come puoi farlo:
```java
// Il percorso della directory contenente il file di presentazione
String dataDir = "path_to_your_presentation_directory/";
// Istanziare la classe Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Passaggio 2: accedere alle proprietà del documento
Dopo aver configurato l'oggetto Presentation, puoi accedere alle proprietà integrate della presentazione utilizzando l'interfaccia IDocumentProperties. Ecco come è possibile recuperare varie proprietà:
### Categoria
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Stato attuale
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Data di creazione
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Autore
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Descrizione
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Parole chiave
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Ultima modifica di
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Supervisore
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Data modificata
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Formato di presentazione
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Data dell'ultima stampa
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Condiviso tra i produttori
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Soggetto
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Titolo
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Conclusione
In questo tutorial, abbiamo imparato come accedere alle proprietà integrate nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Seguendo i passaggi descritti sopra, puoi facilmente recuperare varie proprietà come autore, data di creazione e titolo a livello di codice.
## Domande frequenti
### Posso modificare queste proprietà integrate utilizzando Aspose.Slides per Java?
Sì, puoi modificare queste proprietà utilizzando Aspose.Slides. È sufficiente utilizzare i metodi setter appropriati forniti dall'interfaccia IDocumentProperties.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Aspose.Slides supporta un'ampia gamma di versioni di PowerPoint, garantendo la compatibilità su varie piattaforme.
### Posso recuperare anche le proprietà personalizzate?
Sì, oltre alle proprietà integrate, puoi anche recuperare e modificare proprietà personalizzate utilizzando Aspose.Slides per Java.
### Aspose.Slides offre documentazione e supporto?
 Sì, puoi trovare la documentazione completa e accedere ai forum di supporto su[Sito web Aspose](https://reference.aspose.com/slides/java/).
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).