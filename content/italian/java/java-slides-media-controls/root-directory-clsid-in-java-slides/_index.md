---
title: ClsId della directory principale nelle diapositive Java
linktitle: ClsId della directory principale nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare ClsId della directory principale in Aspose.Slides per presentazioni Java. Personalizza il comportamento del collegamento ipertestuale con CLSID.
type: docs
weight: 10
url: /it/java/media-controls/root-directory-clsid-in-java-slides/
---

## Introduzione all'impostazione del ClsId della directory principale in Aspose.Slides per Java

In Aspose.Slides per Java, è possibile impostare il ClsId della directory principale, che è il CLSID (identificatore di classe) utilizzato per specificare l'applicazione da utilizzare come directory principale quando viene attivato un collegamento ipertestuale nella presentazione. In questa guida ti spiegheremo come eseguire questa operazione passo dopo passo.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Libreria Aspose.Slides per Java aggiunta al tuo progetto. Puoi scaricarlo da[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).
- Un editor di codice o un ambiente di sviluppo integrato (IDE) configurato per lo sviluppo Java.

## Passaggio 1: crea una nuova presentazione

Innanzitutto, creiamo una nuova presentazione utilizzando Aspose.Slides per Java. In questo esempio creeremo una presentazione vuota.

```java
// Nome del file di output
String resultPath = "your_output_path/pres.ppt"; // Sostituisci "your_output_path" con la directory di output desiderata.
Presentation pres = new Presentation();
```

 Nel codice sopra, definiamo il percorso per il file di presentazione di output e ne creiamo uno nuovo`Presentation` oggetto.

## Passaggio 2: impostare il ClsId della directory principale

 Per impostare il ClsId della directory principale, è necessario creare un'istanza di`PptOptions` impostare il CLSID desiderato. Il CLSID rappresenta l'applicazione che verrà utilizzata come directory principale quando viene attivato un collegamento ipertestuale.

```java
PptOptions pptOptions = new PptOptions();
// Imposta CLSID su "Microsoft Powerpoint.Show.8"
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 Nel codice sopra, creiamo a`PptOptions` oggetto e impostare il CLSID su "Microsoft Powerpoint.Show.8". Puoi sostituirlo con il CLSID dell'applicazione che desideri utilizzare come directory root.

## Passaggio 3: salva la presentazione

Ora salviamo la presentazione con il set Root Directory ClsId.

```java
// Salva presentazione
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 In questo passaggio, salviamo la presentazione nel formato specificato`resultPath` con il`PptOptions` abbiamo creato in precedenza.

## Passaggio 4: pulizia

 Non dimenticare di smaltire il`Presentation` oggetto di rilasciare eventuali risorse assegnate.

```java
if (pres != null) {
    pres.dispose();
}
```

## Codice sorgente completo per ClsId della directory principale nelle diapositive Java

```java
// Nome del file di output
String resultPath = RunExamples.getOutPath() + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// imposta CLSID su "Microsoft Powerpoint.Show.8"
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Salva presentazione
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusione

Hai impostato correttamente il ClsId della directory principale in Aspose.Slides per Java. Ciò ti consente di specificare l'applicazione che verrà utilizzata come directory principale quando i collegamenti ipertestuali vengono attivati nella presentazione. È possibile personalizzare il CLSID in base ai propri requisiti specifici.

## Domande frequenti

### Come posso trovare il CLSID per un'applicazione specifica?

Per trovare il CLSID per un'applicazione specifica, puoi fare riferimento alla documentazione o alle risorse fornite dallo sviluppatore dell'applicazione. I CLSID sono identificatori univoci assegnati agli oggetti COM e sono in genere specifici per ciascuna applicazione.

### Posso impostare un CLSID personalizzato per la directory principale?

 Sì, puoi impostare un CLSID personalizzato per la directory root specificando il valore CLSID desiderato utilizzando il file`setRootDirectoryClsid` metodo, come mostrato nell'esempio di codice. Ciò consente di utilizzare un'applicazione specifica come directory principale quando i collegamenti ipertestuali vengono attivati nella presentazione.

### Cosa succede se non imposto il ClsId della directory principale?

Se non imposti il ClsId della directory principale, il comportamento predefinito dipenderà dal visualizzatore o dall'applicazione utilizzata per aprire la presentazione. Può utilizzare la propria applicazione predefinita come directory principale quando vengono attivati i collegamenti ipertestuali.

### Posso modificare il ClsId della directory principale per i singoli collegamenti ipertestuali?

No, il ClsId della directory principale viene generalmente impostato a livello di presentazione e si applica a tutti i collegamenti ipertestuali all'interno della presentazione. Se è necessario specificare applicazioni diverse per singoli collegamenti ipertestuali, potrebbe essere necessario gestire tali collegamenti separatamente nel codice.

### Esistono limitazioni sui CLSID che posso utilizzare?

I CLSID che è possibile utilizzare sono generalmente determinati dalle applicazioni installate nel sistema. È necessario utilizzare CLSID che corrispondano ad applicazioni valide in grado di gestire i collegamenti ipertestuali. Tieni presente che l'utilizzo di un CLSID non valido può provocare un comportamento imprevisto.