---
"date": "2025-04-17"
"description": "Μάθετε πώς να δημιουργείτε, να προσαρμόζετε και να αποθηκεύετε γραφήματα με ετικέτες ποσοστών σε παρουσιάσεις Java χρησιμοποιώντας το Aspose.Slides. Βελτιώστε τις δεξιότητές σας στις παρουσιάσεις σήμερα!"
"title": "Δημιουργία και Προσαρμογή Γραφημάτων σε Παρουσιάσεις Java Χρησιμοποιώντας το Aspose.Slides"
"url": "/el/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργία και Προσαρμογή Γραφημάτων σε Παρουσιάσεις Java Χρησιμοποιώντας το Aspose.Slides

## Εισαγωγή
Η δημιουργία ελκυστικών παρουσιάσεων συχνά περιλαμβάνει περισσότερα από απλό κείμενο. Απαιτεί δυναμικά γραφήματα που μεταφέρουν πληροφορίες αποτελεσματικά. Αν θέλετε να βελτιώσετε τις παρουσιάσεις σας που βασίζονται σε Java με εξελιγμένες λειτουργίες γραφημάτων χρησιμοποιώντας το Aspose.Slides, αυτό το σεμινάριο είναι για εσάς. Θα σας καθοδηγήσουμε στη δημιουργία μιας παρουσίασης, στην προσθήκη και διαμόρφωση γραφημάτων, στον υπολογισμό συνόλων, στην εμφάνιση ετικετών ποσοστών και στην αποθήκευση της εργασίας σας—όλα σε λίγα μόνο εύκολα βήματα.

**Τι θα μάθετε:**
- Πώς να δημιουργήσετε και να προσαρμόσετε παρουσιάσεις με γραφήματα χρησιμοποιώντας το Aspose.Slides για Java
- Υπολογισμός συνόλων κατηγοριών σε γραφήματα
- Εμφάνιση δεδομένων ως ετικέτες ποσοστού σε γραφήματα
- Αποθήκευση παρουσιάσεων με βελτιωμένες λειτουργίες γραφημάτων

Ας δούμε αναλυτικά τις απαραίτητες προϋποθέσεις πριν ξεκινήσουμε.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:

- **Κιτ ανάπτυξης Java (JDK)**Έκδοση 8 ή νεότερη.
- **IDE**Όπως το IntelliJ IDEA, το Eclipse ή οποιοδήποτε IDE που υποστηρίζεται από Java.
- **Aspose.Slides για τη βιβλιοθήκη Java**Αυτό είναι κρίσιμο για τον χειρισμό των λειτουργιών παρουσίασης.

### Απαιτούμενες βιβλιοθήκες και εκδόσεις
Θα χρειαστείτε το Aspose.Slides για Java. Δείτε πώς μπορείτε να το συμπεριλάβετε στο έργο σας:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Βαθμός:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Εναλλακτικά, μπορείτε να κατεβάσετε απευθείας την τελευταία έκδοση από [Aspose.Slides για εκδόσεις Java](https://releases.aspose.com/slides/java/).

### Ρύθμιση περιβάλλοντος
Βεβαιωθείτε ότι το περιβάλλον ανάπτυξής σας έχει ρυθμιστεί ώστε να χρησιμοποιεί JDK 8 ή νεότερη έκδοση και ότι το IDE σας έχει ρυθμιστεί για τη διαχείριση εξαρτήσεων χρησιμοποιώντας το Maven ή το Gradle.

**Απόκτηση Άδειας:**
- **Δωρεάν δοκιμή**: Πρόσβαση σε βασικές λειτουργίες για σκοπούς δοκιμών.
- **Προσωρινή Άδεια**: Δοκιμή προηγμένων λειτουργιών χωρίς περιορισμούς αξιολόγησης.
- **Αγορά**Για μακροπρόθεσμη εμπορική χρήση, σκεφτείτε να αγοράσετε μια άδεια χρήσης.

## Ρύθμιση του Aspose.Slides για Java
Ξεκινήστε ρυθμίζοντας τη βιβλιοθήκη Aspose.Slides στο έργο Java σας. Δείτε πώς μπορείτε να την αρχικοποιήσετε και να την ρυθμίσετε:

1. Προσθέστε την εξάρτηση μέσω Maven ή Gradle όπως φαίνεται παραπάνω.
2. Εισαγάγετε τα απαραίτητα πακέτα Aspose.Slides:
   ```java
   import com.aspose.slides.*;
   ```

3. Αρχικοποίηση νέου `Presentation` παράδειγμα:
   ```java
   Presentation presentation = new Presentation();
   ```

Αυτή η ρύθμιση θα σας επιτρέψει να ξεκινήσετε τη δημιουργία παρουσιάσεων μέσω προγραμματισμού.

## Οδηγός Εφαρμογής

### Δημιουργήστε και προσαρμόστε γραφήματα στην παρουσίασή σας

#### Επισκόπηση
Η δημιουργία ενός γραφήματος περιλαμβάνει την αρχικοποίηση της παρουσίασής σας, την πρόσβαση σε διαφάνειες και την προσθήκη ενός γραφήματος με συγκεκριμένα χαρακτηριστικά όπως τύπος, θέση και μέγεθος.

**Βήματα:**
1. **Δημιουργία στιγμιότυπου παρουσίασης**: Ξεκινήστε δημιουργώντας μια παρουσία του `Presentation` τάξη.
2. **Πρόσβαση σε διαφάνεια**: Ανάκτηση της πρώτης διαφάνειας χρησιμοποιώντας `get_Item(0)`.
3. **Προσθήκη γραφήματος**: Χρήση `addChart()` για να προσθέσετε ένα γράφημα σωρευμένων στηλών σε καθορισμένες συντεταγμένες με καθορισμένες διαστάσεις.

```java
// Χαρακτηριστικό: Δημιουργία παρουσίασης με γράφημα
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Υπολογισμός συνόλων για κατηγορίες

#### Επισκόπηση
Ο υπολογισμός των συνόλων ανά κατηγορία περιλαμβάνει την επανάληψη κάθε σειράς στο γράφημα για την άθροιση τιμών ανά κατηγορία.

**Βήματα:**
1. **Αρχικοποίηση πίνακα**: Δημιουργήστε έναν πίνακα για να διατηρήσετε τις συνολικές τιμές.
2. **Επανάληψη μέσω κατηγοριών και σειρών**Χρησιμοποιήστε ένθετους βρόχους για να συγκεντρώσετε σύνολα για κάθε κατηγορία από όλες τις σειρές.

```java
// Λειτουργία: Υπολογισμός συνόλων για κατηγορίες σε ένα γράφημα
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Εμφάνιση δεδομένων ως ετικέτες ποσοστού σε ένα γράφημα

#### Επισκόπηση
Αυτή η λειτουργία εστιάζει στη διαμόρφωση ετικετών δεδομένων για την εμφάνιση τιμών ως ποσοστά, παρέχοντας σαφήνεια στην οπτικοποίηση.

**Βήματα:**
1. **Ρύθμιση παραμέτρων ετικετών σειράς**: Ορίστε ιδιότητες ετικέτας, όπως το μέγεθος γραμματοσειράς και την ορατότητα των πλήκτρων υπομνήματος.
2. **Υπολογισμός ποσοστών**: Υπολογισμός ποσοστού για κάθε σημείο δεδομένων με βάση τη συνολική τιμή της κατηγορίας.
3. **Ορισμός κειμένου ετικέτας**: Μορφοποίηση ετικετών για εμφάνιση ποσοστών με δύο δεκαδικά ψηφία.

```java
// Λειτουργία: Εμφάνιση δεδομένων ως ετικέτες ποσοστού σε ένα γράφημα
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Αποθήκευση παρουσίασης με γράφημα

#### Επισκόπηση
Τέλος, αποθηκεύστε την παρουσίασή σας σε μια καθορισμένη διαδρομή σε μορφή PPTX.

**Βήματα:**
1. **Μέθοδος Αποθήκευσης**: Χρησιμοποιήστε το `save()` μέθοδος στο `Presentation` παράδειγμα.
2. **Απόρριψη πόρων**: Βεβαιωθείτε ότι οι πόροι απελευθερώνονται μετά την αποθήκευση.

```java
// Χαρακτηριστικό: Αποθήκευση παρουσίασης με γράφημα
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Πρακτικές Εφαρμογές

1. **Οικονομική Αναφορά**Χρησιμοποιήστε γραφήματα για να εμφανίσετε τα ποσοστά αύξησης εσόδων σε όλα τα τμήματα.
2. **Ανάλυση Δεδομένων Πωλήσεων**: Οπτικοποιήστε τα δεδομένα πωλήσεων ανά περιοχή με ετικέτες ποσοστών για πιο σαφή εικόνα.
3. **Εκπαιδευτικές Παρουσιάσεις**Βελτιώστε τις ακαδημαϊκές παρουσιάσεις με οπτικά στατιστικά στοιχεία.
4. **Καμπάνιες μάρκετινγκ**: Εμφάνιση μετρήσεων απόδοσης καμπάνιας ως ελκυστικά γραφικά.
5. **Συναντήσεις Επιχειρηματικής Στρατηγικής**Χρησιμοποιήστε γραφήματα για να μεταφέρετε σύνθετα δεδομένα σε συζητήσεις στρατηγικού σχεδιασμού.

## Παράγοντες Απόδοσης
- **Διαχείριση μνήμης**: Απορρίψτε `Presentation` αντικείμενα άμεσα για να ελευθερωθούν πόροι.
- **Βελτιστοποίηση φόρτωσης γραφήματος**Φορτώστε μόνο τα απαραίτητα στοιχεία του γραφήματος στη μνήμη, εάν είναι δυνατόν.
- **Μαζική επεξεργασία**Κατά την επεξεργασία πολλαπλών παρουσιάσεων, εξετάστε το ενδεχόμενο χειρισμού τους σε παρτίδες για αποτελεσματική διαχείριση της κατανάλωσης πόρων.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}