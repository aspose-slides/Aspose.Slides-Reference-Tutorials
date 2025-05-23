---
"date": "2025-04-17"
"description": "Scopri come personalizzare i formati data per gli assi delle categorie utilizzando Aspose.Slides per Java. Migliora i tuoi grafici con una presentazione dati personalizzata, perfetta per report annuali e altro ancora."
"title": "Come impostare un formato data personalizzato sull'asse delle categorie in Aspose.Slides Java | Guida alla visualizzazione dei dati"
"url": "/it/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come impostare un formato data personalizzato sull'asse delle categorie in Aspose.Slides Java | Guida alla visualizzazione dei dati

Nell'attuale mondo basato sui dati, presentare le informazioni in modo chiaro è fondamentale per un processo decisionale efficace. Quando si creano grafici con Aspose.Slides per Java, la personalizzazione del formato data sull'asse delle categorie può migliorare notevolmente sia la comprensione che la qualità della presentazione. Questa guida vi guiderà nell'impostazione di un formato data personalizzato in Aspose.Slides per migliorare l'aspetto visivo delle vostre diapositive e la chiarezza dei dati.

**Cosa imparerai:**
- Impostazione di Aspose.Slides per Java
- Implementazione di formati di data personalizzati sull'asse delle categorie
- Conversione delle date del calendario gregoriano nel formato data di automazione OLE
- Applicazioni pratiche di queste funzionalità in scenari reali

Scopriamo insieme come puoi raggiungere questo obiettivo con facilità!

## Prerequisiti

Prima di iniziare, assicurati di aver soddisfatto i seguenti prerequisiti:

### Librerie e versioni richieste:
- **Aspose.Slides per Java**: Avrai bisogno della versione 25.4 o successiva.

### Requisiti di configurazione dell'ambiente:
- Un ambiente di sviluppo in grado di eseguire codice Java (come IntelliJ IDEA, Eclipse o NetBeans).
- Maven o Gradle configurati nel tuo progetto per gestire le dipendenze.

### Prerequisiti di conoscenza:
- Conoscenza di base della programmazione Java.
- Familiarità con l'utilizzo dei componenti dei grafici nelle presentazioni.

## Impostazione di Aspose.Slides per Java

Per utilizzare Aspose.Slides per Java, includilo come dipendenza nel tuo progetto. Di seguito sono riportate le istruzioni di installazione:

**Esperto:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

In alternativa, puoi [scarica l'ultima versione](https://releases.aspose.com/slides/java/) direttamente dal sito ufficiale di Aspose.

### Acquisizione della licenza:
- **Prova gratuita**: Inizia con una prova gratuita per esplorare le funzionalità.
- **Licenza temporanea**: Richiedi una licenza temporanea per test estesi.
- **Acquistare**: Per un utilizzo a lungo termine, si consiglia di acquistare un abbonamento. Visita [Acquisto Aspose](https://purchase.aspose.com/buy) per maggiori dettagli.

### Inizializzazione di base:

Ecco come puoi inizializzare Aspose.Slides nel tuo progetto:
```java
import com.aspose.slides.Presentation;
// Crea un'istanza di un oggetto Presentation che rappresenta un file di presentazione
Presentation pres = new Presentation();
```

Passiamo ora al nocciolo della guida!

## Guida all'implementazione

### Impostazione del formato data per l'asse delle categorie

Questa funzione consente di personalizzare la visualizzazione delle date sull'asse delle categorie del grafico. Di seguito una guida dettagliata:

#### 1. Crea una nuova presentazione e un nuovo grafico
Inizia creando un'istanza di `Presentation` e aggiungendo un nuovo grafico ad area.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // Inizializza la presentazione
        Presentation pres = new Presentation();
        
        try {
            // Aggiungere un grafico ad area alla prima diapositiva nella posizione e dimensione specificate
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // Cartella di lavoro dei dati del grafico di Access per la manipolazione dei dati del grafico
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // Cancella tutti i dati esistenti nel grafico

            // Rimuovi tutte le categorie e le serie preesistenti
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // Aggiungere date all'asse delle categorie utilizzando le date OLE Automation convertite
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // Crea una nuova serie e aggiungivi punti dati
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // Imposta il tipo di asse della categoria su Data e configura il suo formato numerico
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // Formatta le date solo come anno

            // Salva la presentazione in una directory specificata
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Data di base per la conversione dell'automazione OLE
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // Converti in data OLE Automation
        return String.valueOf(oaDate);
    }
}
```

#### 2. Conversione della data del calendario gregoriano nel formato data di automazione OLE

Aspose.Slides richiede date nel formato OLE Automation, un formato data standard di Excel. Ecco come convertire le date Java. `GregorianCalendar` date:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 15 gennaio 2021
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Data base di Excel per l'automazione OLE
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### Suggerimenti per la risoluzione dei problemi:
- Assicurare la data di base per la conversione (`30 Dec 1899`) è analizzato correttamente.
- Verifica che il tuo ambiente Java supporti le librerie e le classi necessarie.
- In caso di problemi, verificare la disponibilità di aggiornamenti o patch per Aspose.Slides.

### Applicazioni pratiche

La personalizzazione dei formati delle date può essere particolarmente utile in scenari quali:
- **Relazioni annuali:** Visualizzazione chiara delle tendenze dei dati annuali.
- **Grafici finanziari:** Presentazione accurata dei periodi fiscali.
- **Tempistiche del progetto:** Evidenziare intervalli di tempo o traguardi specifici.

Seguendo questa guida, potrai migliorare le tue presentazioni con formati di data precisi e visivamente accattivanti utilizzando Aspose.Slides per Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}