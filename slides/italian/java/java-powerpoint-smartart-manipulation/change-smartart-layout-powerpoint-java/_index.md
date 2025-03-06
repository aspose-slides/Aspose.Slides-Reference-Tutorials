---
title: Modifica il layout SmartArt in PowerPoint con Java
linktitle: Modifica il layout SmartArt in PowerPoint con Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come manipolare i layout SmartArt nelle presentazioni PowerPoint utilizzando Java con Aspose.Slides per Java.
weight: 19
url: /it/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
In questo tutorial esploreremo come manipolare i layout SmartArt nelle presentazioni PowerPoint utilizzando Java. SmartArt è una potente funzionalità di PowerPoint che consente agli utenti di creare grafica visivamente accattivante per vari scopi, come illustrare processi, gerarchie, relazioni e altro.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
1. Ambiente di sviluppo Java: assicurati di avere Java Development Kit (JDK) installato sul tuo sistema.
2.  Libreria Aspose.Slides: scarica e installa la libreria Aspose.Slides per Java da[Qui](https://releases.aspose.com/slides/java/).
3. Comprensione di base di Java: sarà utile avere familiarità con i fondamenti del linguaggio di programmazione Java.
4. Ambiente di sviluppo integrato (IDE): scegli un IDE di tua preferenza, come Eclipse o IntelliJ IDEA.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Passaggio 1: configura l'ambiente del tuo progetto Java
Assicurati che il tuo progetto Java sia configurato correttamente nell'IDE scelto. Crea un nuovo progetto Java e includi la libreria Aspose.Slides nelle dipendenze del tuo progetto.
## Passaggio 2: crea una nuova presentazione
Creare un'istanza di un nuovo oggetto Presentazione per creare una nuova presentazione di PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Passaggio 3: aggiungi grafica SmartArt
Aggiungi un elemento grafico SmartArt alla tua presentazione. Specificare la posizione e le dimensioni dell'elemento grafico SmartArt sulla diapositiva.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Passaggio 4: modifica il layout SmartArt
Modificare il layout dell'elemento grafico SmartArt nel tipo di layout desiderato.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Passaggio 5: salva la presentazione
Salva la presentazione modificata in una directory specificata sul tuo sistema.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Manipolare i layout SmartArt nelle presentazioni PowerPoint utilizzando Java è un processo semplice con Aspose.Slides per Java. Seguendo questo tutorial, puoi modificare facilmente la grafica SmartArt per adattarla alle tue esigenze di presentazione.
## Domande frequenti
### Posso personalizzare l'aspetto della grafica SmartArt utilizzando Aspose.Slides per Java?
Sì, puoi personalizzare vari aspetti della grafica SmartArt, come colori, stili ed effetti.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Aspose.Slides supporta presentazioni PowerPoint create in varie versioni di PowerPoint, garantendo la compatibilità tra diverse piattaforme.
### Aspose.Slides offre supporto per altri linguaggi di programmazione?
Sì, Aspose.Slides è disponibile per più linguaggi di programmazione, inclusi .NET, Python e JavaScript.
### Posso creare grafica SmartArt da zero utilizzando Aspose.Slides?
Assolutamente, puoi creare grafica SmartArt a livello di codice o modificare quelli esistenti per soddisfare le tue esigenze.
### Esiste un forum della community in cui posso chiedere aiuto riguardo ad Aspose.Slides?
 Sì, puoi visitare il forum Aspose.Slides[Qui](https://forum.aspose.com/c/slides/11) porre domande e interagire con la comunità.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
