---
"description": "Scopri come impostare il CLSID della directory principale in Aspose.Slides per le presentazioni Java. Personalizza il comportamento dei collegamenti ipertestuali con il CLSID."
"linktitle": "Directory radice ClsId in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Directory radice ClsId in Java Slides"
"url": "/it/java/media-controls/root-directory-clsid-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Directory radice ClsId in Java Slides


## Introduzione all'impostazione del ClsId della directory radice in Aspose.Slides per Java

In Aspose.Slides per Java, è possibile impostare il CLSID della directory principale, ovvero il CLSID (Class Identifier) utilizzato per specificare l'applicazione da utilizzare come directory principale quando viene attivato un collegamento ipertestuale nella presentazione. In questa guida, vi guideremo passo dopo passo nella procedura.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

- Java Development Kit (JDK) installato sul sistema.
- La libreria Aspose.Slides per Java è stata aggiunta al tuo progetto. Puoi scaricarla da [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/).
- Un editor di codice o un ambiente di sviluppo integrato (IDE) configurato per lo sviluppo Java.

## Passaggio 1: creare una nuova presentazione

Per prima cosa, creiamo una nuova presentazione utilizzando Aspose.Slides per Java. In questo esempio, creeremo una presentazione vuota.

```java
// Nome del file di output
String resultPath = "your_output_path/pres.ppt"; // Sostituisci "your_output_path" con la directory di output desiderata.
Presentation pres = new Presentation();
```

Nel codice sopra, definiamo il percorso per il file di presentazione di output e creiamo un nuovo `Presentation` oggetto.

## Passaggio 2: impostare ClsId della directory radice

Per impostare il ClsId della directory radice, è necessario creare un'istanza di `PptOptions` e impostare il CLSID desiderato. Il CLSID rappresenta l'applicazione che verrà utilizzata come directory principale quando viene attivato un collegamento ipertestuale.

```java
PptOptions pptOptions = new PptOptions();
// Imposta CLSID su 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

Nel codice sopra, creiamo un `PptOptions` e imposta il CLSID su "Microsoft Powerpoint.Show.8". Puoi sostituirlo con il CLSID dell'applicazione che desideri utilizzare come directory radice.

## Passaggio 3: salva la presentazione

Salviamo ora la presentazione con il ClsId della directory radice impostato.

```java
// Salva la presentazione
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

In questo passaggio salviamo la presentazione nel percorso specificato `resultPath` con il `PptOptions` che abbiamo creato in precedenza.

## Fase 4: Pulizia

Non dimenticare di smaltire il `Presentation` oggetto per rilasciare le risorse assegnate.

```java
if (pres != null) {
    pres.dispose();
}
```

## Codice sorgente completo per ClsId della directory radice in Java Slides

```java
// Nome del file di output
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// imposta CLSID su 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Salva la presentazione
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusione

Hai impostato correttamente il CLSID della directory principale in Aspose.Slides per Java. Questo ti consente di specificare l'applicazione che verrà utilizzata come directory principale quando vengono attivati i collegamenti ipertestuali nella presentazione. Puoi personalizzare il CLSID in base alle tue esigenze specifiche.

## Domande frequenti

### Come faccio a trovare il CLSID di un'applicazione specifica?

Per trovare il CLSID di un'applicazione specifica, è possibile fare riferimento alla documentazione o alle risorse fornite dallo sviluppatore dell'applicazione. I CLSID sono identificatori univoci assegnati agli oggetti COM e sono in genere specifici per ciascuna applicazione.

### Posso impostare un CLSID personalizzato per la directory radice?

Sì, è possibile impostare un CLSID personalizzato per la directory principale specificando il valore CLSID desiderato utilizzando `setRootDirectoryClsid` metodo, come mostrato nell'esempio di codice. Questo consente di utilizzare un'applicazione specifica come directory principale quando vengono attivati i collegamenti ipertestuali nella presentazione.

### Cosa succede se non imposto il ClsId della directory radice?

Se non si imposta il ClsId della directory radice, il comportamento predefinito dipenderà dal visualizzatore o dall'applicazione utilizzata per aprire la presentazione. Potrebbe utilizzare la propria applicazione predefinita come directory radice quando vengono attivati i collegamenti ipertestuali.

### Posso modificare il ClsId della directory radice per singoli collegamenti ipertestuali?

No, il ClsId della directory radice viene in genere impostato a livello di presentazione e si applica a tutti i collegamenti ipertestuali al suo interno. Se è necessario specificare applicazioni diverse per i singoli collegamenti ipertestuali, potrebbe essere necessario gestire tali collegamenti separatamente nel codice.

### Ci sono delle limitazioni sui CLSID che posso utilizzare?

CLSID utilizzabili sono in genere determinati dalle applicazioni installate sul sistema. È consigliabile utilizzare CLSID che corrispondano ad applicazioni valide in grado di gestire collegamenti ipertestuali. Tenere presente che l'utilizzo di un CLSID non valido potrebbe causare comportamenti imprevisti.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}