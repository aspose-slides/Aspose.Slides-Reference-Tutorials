---
title: Organizza il layout del grafico Digita SmartArt utilizzando Java
linktitle: Organizza il layout del grafico Digita SmartArt utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Padroneggia i tipi di layout dei grafici organizzativi in SmartArt utilizzando Java con Aspose.Slides, migliorando facilmente le immagini della presentazione.
type: docs
weight: 13
url: /it/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---
## introduzione
In questo tutorial, esamineremo il processo di organizzazione del tipo di layout del grafico in SmartArt utilizzando Java, sfruttando in particolare la libreria Aspose.Slides. SmartArt nelle presentazioni può migliorare notevolmente l'attrattiva visiva e la chiarezza dei tuoi dati, rendendo essenziale padroneggiarne la manipolazione.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Libreria Aspose.Slides scaricata e configurata. Se non l'hai già fatto, scaricalo da[Qui](https://releases.aspose.com/slides/java/).
3. Conoscenza di base della programmazione Java.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari:
```java
import com.aspose.slides.*;
```
Suddividiamo l'esempio fornito in più passaggi:
## Passaggio 1: inizializzare l'oggetto di presentazione
```java
Presentation presentation = new Presentation();
```
Crea un nuovo oggetto di presentazione.
## Passaggio 2: aggiungi SmartArt alla diapositiva
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Aggiungi SmartArt alla diapositiva desiderata con dimensioni e tipo di layout specificati.
## Passaggio 3: imposta il layout dell'organigramma
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Imposta il tipo di layout dell'organigramma. In questo esempio, stiamo utilizzando il layout sospeso a sinistra.
## Passaggio 4: salva la presentazione
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Salva la presentazione con il layout del grafico organizzato.

## Conclusione
Padroneggiare l'organizzazione dei tipi di layout del grafico in SmartArt utilizzando Java ti consente di creare facilmente presentazioni visivamente accattivanti. Con Aspose.Slides, il processo diventa snello ed efficiente, permettendoti di concentrarti sulla creazione di contenuti di grande impatto.
## Domande frequenti
### Aspose.Slides è compatibile con diversi ambienti di sviluppo Java?
Sì, Aspose.Slides è compatibile con vari ambienti di sviluppo Java, garantendo flessibilità agli sviluppatori.
### Posso personalizzare l'aspetto degli elementi SmartArt utilizzando Aspose.Slides?
Assolutamente, Aspose.Slides offre ampie opzioni di personalizzazione per gli elementi SmartArt, consentendoti di adattarli alle tue esigenze specifiche.
### Aspose.Slides offre documentazione completa per gli sviluppatori?
Sì, gli sviluppatori possono fare riferimento alla documentazione dettagliata fornita da Aspose.Slides per Java, offrendo approfondimenti sulle sue funzionalità e utilizzo.
### È disponibile una versione di prova per Aspose.Slides?
Sì, puoi accedere a una versione di prova gratuita di Aspose.Slides per esplorarne le funzionalità prima di prendere una decisione di acquisto.
### Dove posso chiedere supporto per le domande relative ad Aspose.Slides?
 Per qualsiasi assistenza o domanda riguardante Aspose.Slides, è possibile visitare il forum di supporto[Qui](https://forum.aspose.com/c/slides/11).