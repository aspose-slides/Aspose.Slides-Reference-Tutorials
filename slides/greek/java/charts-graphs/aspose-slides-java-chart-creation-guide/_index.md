---
date: '2026-01-14'
description: Μάθετε πώς να δημιουργήσετε ένα συγκεντρωτικό ραβδόγραμμα σε Java χρησιμοποιώντας
  το Aspose.Slides. Οδηγός βήμα‑προς‑βήμα που καλύπτει κενή παρουσίαση, προσθήκη γραφήματος
  στην παρουσίαση και διαχείριση σειρών.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Πώς να δημιουργήσετε ομαδοποιημένο γράφημα στηλών σε Java με το Aspose.Slides
url: /el/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Εξοικείωση με τη Δημιουργία Διαγραμμάτων σε Java με το Aspose.Slides

## Πώς να Δημιουργήσετε και να Διαχειριστείτε Διαγράμματα Χρησιμοποιώντας το Aspose.Slides for Java

### Εισαγωγή
Η δημιουργία δυναμικών παρουσιάσεων συχνά περιλαμβάνει την οπτικοποίηση δεδομένων μέσω διαγραμμάτων. Με το **Aspose.Slides for Java**, μπορείτε εύκολα **να δημιουργήσετε ένα συγκεντρωτικό διάγραμμα στήλης** και να διαχειριστείτε διάφορους τύπους διαγραμμάτων, βελτιώνοντας τόσο την σαφήνεια όσο και την επίδραση. Αυτό το εκπαιδευτικό υλικό θα σας καθοδηγήσει στη δημιουργία μιας κενής παρουσίασης, στην προσθήκη ενός συγκεντρωτικού διαγράμματος στήλης, στη διαχείριση σειρών και στην προσαρμογή της αντιστροφής σημείων δεδομένων—όλα με το Aspose.Slides for Java.

**Τι Θα Μάθετε:**
- Πώς να ρυθμίσετε το Aspose.Slides for Java.
- Βήματα για **δημιουργία κενής παρουσίασης** και προσθήκη διαγράμματος στην παρουσίαση.
- Τεχνικές για αποτελεσματική διαχείριση σειρών διαγράμματος και σημείων δεδομένων.
- Μεθόδους για υπό όρους αντιστροφή αρνητικών σημείων δεδομένων για καλύτερη οπτικοποίηση.
- Πώς να αποθηκεύσετε την παρουσίαση με ασφάλεια.

Ας δούμε τις προαπαιτούμενες πληροφορίες πριν ξεκινήσουμε.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για εκκίνηση;** `Presentation` από το `com.aspose.slides`.
- **Ποιος τύπος διαγράμματος δημιουργεί ένα συγκεντρωτικό διάγραμμα στήλης;** `ChartType.ClusteredColumn`.
- **Πώς προσθέτετε ένα διάγραμμα σε μια διαφάνεια;** Χρησιμοποιήστε `addChart()` στη συλλογή σχήματος της διαφάνειας.
- **Μπορείτε να αντιστρέψετε αρνητικές τιμές;** Ναι, με `invertIfNegative(true)` σε ένα σημείο δεδομένων.
- **Ποια έκδοση απαιτείται;** Aspose.Slides for Java 25.4 ή νεότερη.

## Τι είναι ένα συγκεντρωτικό διάγραμμα στήλης;
Ένα συγκεντρωτικό διάγραμμα στήλης εμφανίζει πολλαπλές σειρές δεδομένων πλάι‑πλάι για κάθε κατηγορία, καθιστώντας το ιδανικό για σύγκριση τιμών μεταξύ ομάδων. Το Aspose.Slides σας επιτρέπει να δημιουργήσετε αυτό το διάγραμμα προγραμματιστικά χωρίς να ανοίξετε το PowerPoint.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides for Java για προσθήκη διαγράμματος στην παρουσίαση;
- **Πλήρης έλεγχος** πάνω στα δεδομένα, την εμφάνιση και τη διάταξη του διαγράμματος.
- **Δεν απαιτείται εγκατάσταση Office** στον διακομιστή.
- **Υποστηρίζει όλους τους κύριους τύπους διαγραμμάτων**, συμπεριλαμβανομένων των συγκεντρωτικών διαγραμμάτων στήλης.
- **Εύκολη ενσωμάτωση** με Maven/Gradle builds.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

1. **Απαιτούμενες Βιβλιοθήκες:**
   - Aspose.Slides for Java (έκδοση 25.4 ή νεότερη).

2. **Απαιτήσεις Περιβάλλοντος:**
   - Συμβατική έκδοση JDK (π.χ., JDK 16).
   - Maven ή Gradle εγκατεστημένα εάν προτιμάτε διαχείριση εξαρτήσεων.

3. **Γνώσεις Προαπαιτούμενων:**
   - Βασική κατανόηση του προγραμματισμού Java.
   - Εξοικείωση με τη διαχείριση εξαρτήσεων στο περιβάλλον ανάπτυξης.

## Ρύθμιση του Aspose.Slides for Java
Για να αρχίσετε να χρησιμοποιείτε το Aspose.Slides, ακολουθήστε τα παρακάτω βήματα:

**Εγκατάσταση μέσω Maven:**  
Προσθέστε την ακόλουθη εξάρτηση στο αρχείο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Εγκατάσταση μέσω Gradle:**  
Προσθέστε την ακόλουθη γραμμή στο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Άμεση Λήψη:**  
Εναλλακτικά, κατεβάστε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
- **Δωρεάν Δοκιμή:** Μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμή για να εξερευνήσετε τις δυνατότητες.  
- **Προσωρινή Άδεια:** Αποκτήστε μια προσωρινή άδεια για πλήρη πρόσβαση κατά τη διάρκεια της αξιολόγησής σας.  
- **Αγορά:** Σκεφτείτε την αγορά εάν θεωρείτε ότι καλύπτει τις μακροπρόθεσμες ανάγκες σας.

### Βασική Αρχικοποίηση
Ακολουθεί ο ελάχιστος κώδικας που απαιτείται για τη δημιουργία μιας νέας παρουσίας:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Οδηγός Υλοποίησης
Τώρα, ας διασπάσουμε κάθε δυνατότητα σε διαχειρίσιμα βήματα.

### Δημιουργία Παρουσίασης με Συγκεντρωτικό Διάγραμμα Στήλης
#### Επισκόπηση
Αυτή η ενότητα δείχνει πώς να **δημιουργήσετε μια κενή παρουσίαση**, να προσθέσετε ένα **συγκεντρωτικό διάγραμμα στήλης** και να το τοποθετήσετε στην πρώτη διαφάνεια.

**Βήματα:**
1. **Αρχικοποίηση του Αντικειμένου Presentation** – δημιουργήστε ένα νέο `Presentation`.
2. **Προσθήκη Συγκεντρωτικού Διαγράμματος Στήλης** – καλέστε `addChart()` με τον κατάλληλο τύπο και διαστάσεις.

**Παράδειγμα Κώδικα:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Διαχείριση Σειρών Διαγράμματος
#### Επισκόπηση
Μάθετε πώς να διαγράψετε τυχόν προεπιλεγμένες σειρές, να προσθέσετε μια νέα σειρά και να την γεμίσετε με θετικές και αρνητικές τιμές.

**Βήματα:**
1. **Καθαρισμός Υπάρχουσας Σειράς** – αφαιρέστε τυχόν προ‑συμπληρωμένα δεδομένα.
2. **Προσθήκη Νέας Σειράς** – χρησιμοποιήστε το κελί του βιβλίου εργασίας ως όνομα σειράς.
3. **Εισαγωγή Σημείων Δεδομένων** – προσθέστε τιμές, συμπεριλαμβανομένων των αρνητικών, για να δείξετε την αντιστροφή αργότερα.

**Παράδειγμα Κώδικα:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Αντιστροφή Σημείων Δεδομένων Σειράς βάσει Συνθηκών
#### Επισκόπηση
Από προεπιλογή, το Aspose.Slides μπορεί να αντιστρέψει αρνητικές τιμές. Μπορείτε να ελέγξετε αυτή τη συμπεριφορά παγκοσμίως και ανά σημείο δεδομένων.

**Βήματα:**
1. **Ορισμός Παγκόσμιας Αντιστροφής** – απενεργοποιήστε την αυτόματη αντιστροφή για ολόκληρη τη σειρά.
2. **Εφαρμογή Υπό Όρους Αντιστροφής** – ενεργοποιήστε την αντιστροφή μόνο για συγκεκριμένα αρνητικά σημεία.

**Παράδειγμα Κώδικα:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| Το διάγραμμα εμφανίζεται κενό | Βεβαιωθείτε ότι ο δείκτης διαφάνειας (`0`) υπάρχει και ότι οι διαστάσεις του διαγράμματος είναι εντός των ορίων της διαφάνειας. |
| Οι αρνητικές τιμές δεν αντιστρέφονται | Επαληθεύστε ότι το `invertIfNegative(false)` έχει οριστεί στη σειρά και το `invertIfNegative(true)` στο συγκεκριμένο σημείο δεδομένων. |
| Εξαίρεση άδειας | Εφαρμόστε μια έγκυρη άδεια Aspose πριν δημιουργήσετε το αντικείμενο `Presentation`. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να προσθέσω άλλους τύπους διαγραμμάτων εκτός του συγκεντρωτικού στήλης;**  
Α: Ναι, το Aspose.Slides υποστηρίζει γραμμικά, πίτες, ράβδους, περιοχές και πολλούς άλλους τύπους διαγραμμάτων.

**Ε: Χρειάζομαι άδεια για ανάπτυξη;**  
Α: Η δωρεάν δοκιμή λειτουργεί για αξιολόγηση, αλλά απαιτείται εμπορική άδεια για χρήση σε παραγωγή.

**Ε: Πώς εξάγω το διάγραμμα ως εικόνα;**  
Α: Χρησιμοποιήστε `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` μετά το rendering.

**Ε: Είναι δυνατόν να μορφοποιήσω το διάγραμμα (χρώματα, γραμματοσειρές);**  
Α: Απόλυτα. Κάθε `IChartSeries` και `IChartDataPoint` παρέχει ιδιότητες μορφοποίησης.

**Ε: Τι γίνεται αν θέλω να προσθέσω διάγραμμα σε υπάρχον αρχείο PPTX;**  
Α: Φορτώστε το αρχείο με `new Presentation("existing.pptx")`, στη συνέχεια προσθέστε το διάγραμμα στη ζητούμενη διαφάνεια.

## Συμπέρασμα
Σε αυτό το εκπαιδευτικό υλικό, μάθατε πώς να **δημιουργήσετε ένα συγκεντρωτικό διάγραμμα στήλης** σε Java, να διαχειριστείτε σειρές και να αντιστρέψετε υπό όρους αρνητικά σημεία δεδομένων χρησιμοποιώντας το Aspose.Slides. Με αυτές τις τεχνικές, μπορείτε να δημιουργήσετε ελκυστικές, δεδομενο‑προσανατολισμένες παρουσιάσεις προγραμματιστικά.

**Επόμενα Βήματα:**
- Πειραματιστείτε με άλλους τύπους διαγραμμάτων που προσφέρει το Aspose.Slides for Java.  
- Εμβαθύνετε σε προχωρημένες επιλογές μορφοποίησης όπως προσαρμοσμένα χρώματα, ετικέτες δεδομένων και μορφοποίηση αξόνων.  
- Ενσωματώστε τη δημιουργία διαγραμμάτων στις διαδικασίες αναφοράς ή ανάλυσης σας.

---

**Τελευταία Ενημέρωση:** 2026-01-14  
**Δοκιμασμένο Με:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}