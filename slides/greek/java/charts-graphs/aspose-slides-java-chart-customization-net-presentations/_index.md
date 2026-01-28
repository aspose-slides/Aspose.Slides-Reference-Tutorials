---
date: '2026-01-17'
description: Μάθετε πώς να προσθέτετε σειρές σε γράφημα και να προσαρμόζετε τα στοιβαγμένα
  διαγράμματα στήλης σε παρουσιάσεις .NET χρησιμοποιώντας το Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Προσθήκη σειράς σε διάγραμμα με το Aspose.Slides for Java στο .NET
url: /el/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Κατάκτηση της Προσαρμογής Διαγραμμάτων σε Παρουσιάσεις .NET με τη χρήση του Aspose.Slides για Java

## Εισαγωγή
Στον κόσμο των παρουσιάσεων που βασίζονται σε δεδομένα, τα διαγράμματα είναι απαραίτητα εργαλεία που μετατρέπουν ακατέργαστους αριθμούς σε συναρπαστικές οπτικές ιστορίες. Όταν χρειάζεται να **προσθήκη σειράς στο γράφημα** προγραμματιστικά, ειδικά μέσα σε αρχεία παρουσίασης .NET, η εργασία μπορεί να φαίνεται δύσκολη. Ευτυχώς, το **Aspose.Slides for Java** προσφέρει ένα ισχυρό, γλώσσα‑ανεξάρτητο API που κάνει τη δημιουργία και προσαρμογή διαγραμμάτων απλής—ακόμη και όταν ο στόχος σας είναι ένα .NETPPTX.

Σε αυτό το σεμινάριο θα ανακαλύψετε πώς να **προσθήκη σειράς στο γράφημα**, πώς να **προσθήκη γραφήματος** τύπου stacked column, και πώς να ρυθμίσετε λεπτομερείς οπτικές παραμέτρους όπως το πλάτος του χάσματος. Στο τέλος, μπορείτε να δημιουργήσετε δυναμικές, πλούσιες σε δεδομένα διαφάνειες που φαίνονται επαγγελματικές και καλοσχεδιασμένες.

**Τι θα μάθετε**
- Πώς να δημιουργήσετε μια κενή παρουσίαση χρησιμοποιώντας το Aspose.Slides
- Πώς να **add stacked column chart** σε μια διαφάνεια
- Πώς να **προσθήκη σειράς στο γράφημα** και να ορίσετε κατηγορίες
- Πώς να γεμίσετε σημεία δεδομένων και να προσαρμόσετε οπτικές ρυθμίσεις

Ας ετοιμάσουμε το περιβάλλον ανάπτυξής σας.

## Γρήγορες απαντήσεις
- **Ποια είναι η κύρια κλάση για την έναρξη μιας παρουσίασης;** `Presentation`
- **Ποια μέθοδος προσθέτει ένα γράφημα σε μια διαφάνεια;** `slide.getShapes().addChart(...)`
- **Πώς προσθέτετε μια νέα σειρά;** `chart.getChartData().getSeries().add(...)`
- **Μπορείτε να αλλάξετε το πλάτος του κενού μεταξύ των γραμμών;** Ναι, χρησιμοποιώντας το `setGapWidth()` στην ομάδα σειρών
- **Χρειάζομαι άδεια χρήσης για παραγωγή;** Ναι, απαιτείται μια έγκυρη άδεια χρήσης Aspose.Slides για Java

## Τι είναι η "προσθήκη σειράς σε γράφημα";
Η προσθήκη σε ένα διάγραμμα σημαίνει την εισαγωγή μιας νέας συλλογής δεδομένων που το διάγραμμα θα αποτυπώσει ως ξεχωριστό οπτικό στοιχείο (π.χ. μια νέα ράβδο, γραμμή ή φέτα). Κάθε σειρά μπορεί να έχει το δικό της σύνολο τιμών, χρωμάτων και μορφοποίησης, επιτρέποντάς σας να συγκρίνετε πολλαπλά σύνολα δεδομένων πλάι‑πλάι.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για Java για να τροποποιήσετε παρουσιάσεις .NET;
- **Cross‑platform**: Γράψτε κώδικα Java μία φορά και στοχευμένα αρχεία PPTX που αναφέρονται από εφαρμογές .NET.
- **No COM or Office dependencies**: Λειτουργεί σε διακομιστές, CI pipelines και containers.
- **API εμπλουτισμένου γραφήματος**: Υποστηρίζει πάνω από 50 τύπους διαγραμμάτων, συμπεριλαμβανομένων των γραφημάτων στοιβαγμένων στηλών.

## Προαπαιτούμενα
1. **Aspose.Slides for Java** βιβλιοθήκη (έκδοση25.4 ή νεότερη).
2. Maven ή Gradle εργαλείο κατασκευής, ή χειροκίνητη λήψη JAR.
3. Βασικές γνώσεις Java και εξοικείωση με τη δομή PPTX.

## Ρύθμιση Aspose.Slides για Java
### Εγκατάσταση Maven
Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Εγκατάσταση Gradle
Συμπεριλάβετε αυτή τη γραμμή στο αρχείο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση λήψη
Εναλλακτικά, κατεβάστε το τελευταίο JAR από τη σελίδα κυκλοφορίας: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Απόκτηση Άδειας Χρήσης**
Ξεκινήστε με μια δωρεάν δοκιμή κατεβάζοντας μια προσωρινή άδεια από [εδώ](https://purchase.aspose.com/temporary-license/). Για παραγωγική χρήση, αγοράστε πλήρη άδεια για να ξεκλειδώσετε όλες τις δυνατότητες.

## Οδηγός υλοποίησης βήμα προς βήμα
Κάτω από κάθε βήμα θα βρείτε ένα συνοπτικό απόσπασμα κώδικα (αμετάβλητο από τον αρχικό οδηγό) ακολουθούμενο από μια επεξήγηση του τι κάνει.

### Βήμα 1: Δημιουργήστε μια κενή παρουσίαση

```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*Ξεκινάμε με ένα καθαρό αρχείο PPTX, το οποίο μας παρέχει έναν καμβά για την προσθήκη διαγραμμάτων.*

### Βήμα 2: Προσθήκη γραφήματος με στοίβες στηλών στη διαφάνεια
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Η μέθοδος `addChart` δημιουργεί ένα **add stacked column chart** και το τοποθετεί στην πάνω‑αριστερή γωνία της διαφάνειας.*

### Βήμα 3: Προσθήκη σειράς στο γράφημα (Κύριος στόχος)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Εδώ **add series to chart** – κάθε κλήση δημιουργεί μια νέα σειρά δεδομένων που θα εμφανιστεί ως ξεχωριστή ομάδα στηλών.*

### Βήμα 4: Προσθήκη κατηγοριών στο γράφημα
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Οι κατηγορίες λειτουργούν ως ετικέτες του άξονα X, δίνοντας νόημα σε κάθε στήλη.*

### Βήμα 5: Συμπλήρωση δεδομένων σειράς
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Τα σημεία δεδομένων δίνουν σε κάθε σειρά τις αριθμητικές της τιμές, τις οποίες το διάγραμμα θα αποδώσει ως ύψος ράβδων.*

### Βήμα 6: Ορισμός πλάτους κενού για την ομάδα σειρών γραφήματος
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Η ρύθμιση του πλάτους του κενού βελτιώνει την αναγνωσιμότητα, ειδικά όταν υπάρχουν πολλές κατηγορίες.*

## Συνήθεις περιπτώσεις χρήσης
- **Financial reporting** – σύγκριση τριμηνιαίων εσόδων ανά επιχειρησιακή μονάδα.
- **Project dashboards** – εμφάνιση ποσοστών ολοκλήρωσης εργασιών ανά ομάδα.
- **Marketing analytics** – οπτικοποίηση απόδοσης εκστρατειών πλάι‑πλάι.

## Συμβουλές απόδοσης
- **Reuse the `Presentation` object** όταν δημιουργείτε πολλά διαγράμματα για να μειώσετε την κατανάλωση μνήμης.
- **Περιορίστε τον αριθμό των σημείων δεδομένων** στα απαραίτητα για την οπτική ιστορία.
- **Dispose of objects** (`presentation.dispose()`) μετά την αποθήκευση για απελευθέρωση πόρων.

## Συχνές Ερωτήσεις
**Ε: Μπορώ να προσθέσω άλλους τύπους γραφημάτων εκτός από τη στοιβαγμένη στήλη;**
Α: Ναι, το Aspose.Slides υποστηρίζει γραμμή, πίτα, περιοχή και πολλούς άλλους τύπους γραφημάτων.

**Ε: Χρειάζομαι ξεχωριστή άδεια χρήσης για την έξοδο .NET;**
Α: Όχι, η ίδια άδεια χρήσης Java λειτουργεί για όλες τις μορφές εξόδου, συμπεριλαμβανομένων των αρχείων .NET PPTX.

**Ε: Πώς μπορώ να αλλάξω την παλέτα χρωμάτων του γραφήματος;**
Α: Χρησιμοποιήστε την εντολή `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` και ορίστε το επιθυμητό `Color`.

**Ε: Είναι δυνατή η προσθήκη ετικετών δεδομένων μέσω προγραμματισμού;**
Α: Απολύτως. Καλέστε την εντολή `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` για να εμφανίσετε τιμές.

**Ε: Τι γίνεται αν χρειαστεί να ενημερώσω μια υπάρχουσα παρουσίαση;**
Α: Φορτώστε το αρχείο με την εντολή `new Presentation("existing.pptx")`, τροποποιήστε το γράφημα και αποθηκεύστε το ξανά.

## Συμπέρασμα
Τώρα έχετε έναν πλήρη οδηγό από την αρχή μέχρι το τέλος για το πώς να **add series to chart**, να δημιουργήσετε ένα **stacked column chart**, και να ρυθμίσετε την εμφάνιση του σε παρουσιάσεις .NET χρησιμοποιώντας το Aspose.Slides for Java. Πειραματιστείτε με διαφορετικούς τύπους διαγραμμάτων, χρώματα και πηγές για να δημιουργήσετε εντυπωσιακές οπτικές αναφορές που θα εντυπωσιάσουν τα ενδιαφερόμενα μέρη.

---

**Τελευταία ενημέρωση: ** 17-01-2026
**Δοκιμασμένο με:** Aspose.Slides για Java 25.4 (jdk16)
**Συγγραφέας:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
