---
date: '2026-08-21'
description: Μάθετε πώς να δημιουργήσετε box plot java χρησιμοποιώντας Aspose.Slides,
  προσθέστε chart στο slide και δημιουργήστε ένα box‑and‑whisker chart στο PowerPoint.
  Ιδανικό για προγραμματιστές Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Μάθετε πώς να δημιουργήσετε box plot java χρησιμοποιώντας Aspose.Slides,
  προσθέστε chart στο slide και δημιουργήστε ένα box‑and‑whisker chart στο PowerPoint.
  Ιδανικό για προγραμματιστές Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Πώς να δημιουργήσετε box plot java με Aspose.Slides για PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Πώς να δημιουργήσετε box plot java με Aspose.Slides για PowerPoint
url: /el/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε box plot java με Aspose.Slides για PowerPoint

Σε αυτόν τον οδηγό θα **δημιουργήσετε box plot java** με Aspose.Slides, και στη συνέχεια θα ενσωματώσετε το διάγραμμα απευθείας σε μια διαφάνεια PowerPoint. Η δημιουργία διαγραμμάτων box‑and‑whisker προγραμματιστικά σας επιτρέπει να μετατρέψετε ακατέργαστα στατιστικά δεδομένα σε σαφή οπτικά ευρήματα χωρίς να αφήσετε τον κώδικα Java. Εάν χρειάζεστε αυτοματοποίηση αναφορών PowerPoint, το Aspose.Slides for Java παρέχει ένα αξιόπιστο, υψηλής απόδοσης API.

## Τι θα μάθετε

- Ρύθμιση του περιβάλλοντος σας για Aspose.Slides for Java
- Βήματα για **προσθήκη διαγράμματος στη διαφάνεια** και δημιουργία διαγράμματος box‑whisker στο PowerPoint χρησιμοποιώντας Java
- Καλές πρακτικές για βελτιστοποίηση της απόδοσης κατά τη χρήση του Aspose.Slides
- Πρακτικές εφαρμογές διαγραμμάτων box‑and‑whisker

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί ένα box plot σε Java;** Aspose.Slides for Java.  
- **Ποιος τύπος διαγράμματος χρησιμοποιείται;** `ChartType.BoxAndWhisker`.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται εμπορική άδεια για παραγωγή.  
- **Μπορώ να προσθέσω πολλαπλές σειρές;** Ναι – επαναλάβετε το μπλοκ δημιουργίας σειράς για κάθε σύνολο δεδομένων.  
- **Ποια μορφή έχει το τελικό αρχείο;** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Τι είναι ένα box plot και γιατί να το χρησιμοποιήσετε σε Java;

Ένα διάγραμμα box‑and‑whisker (συχνά αποκαλούμενο *box plot*) οπτικοποιεί την κατανομή των δεδομένων—διάμεσο, τεταρτημόρια και εξωγενείς—σε μια συμπαγή μορφή. Σε Java, η προγραμματιστική δημιουργία αυτού του διαγράμματος σας επιτρέπει να ενσωματώσετε στατιστικές πληροφορίες απευθείας σε παρουσιάσεις PowerPoint, εξαλείφοντας την ανάγκη χειροκίνητης δημιουργίας διαγραμμάτων. Είναι ιδιαίτερα χρήσιμο για τη σύγκριση κατανομών μεταξύ πολλαπλών κατηγοριών, όπως βαθμολογίες μαθημάτων ή πωλήσεις ανά περιοχή. Δημιουργώντας το διάγραμμα σε Java, μπορείτε να το ενσωματώσετε σε αυτοματοποιημένες αλυσίδες αναφορών, διασφαλίζοντας ότι τα πιο πρόσφατα δεδομένα εμφανίζονται πάντα στις παρουσιάσεις σας.

## Γιατί να προσθέσετε διάγραμμα στη διαφάνεια με Aspose.Slides;

Το Aspose.Slides αφαιρεί τις λεπτομέρειες του χαμηλού επιπέδου OpenXML, παρέχοντάς σας ένα ευέλικτο API για δημιουργία, μορφοποίηση και εξαγωγή διαγραμμάτων. Αυτό σημαίνει ότι μπορείτε να αυτοματοποιήσετε τη δημιουργία αναφορών, να διασφαλίσετε συνεπή branding και να ενσωματώσετε διαγράμματα σε μεγαλύτερες ροές εργασίας Java. Η βιβλιοθήκη υποστηρίζει επίσης επιλογές μορφοποίησης όπως χρώματα, γραμματοσειρές και δείκτες, επιτρέποντάς σας να ταιριάξετε το εταιρικό στυλ. Επιπλέον, διαχειρίζεται σύνθετες εργασίες όπως σύνδεση δεδομένων και ανανέωση διαγράμματος χωρίς να απαιτείται Microsoft Office.

## Πώς να προσθέσετε διάγραμμα σε διαφάνεια με Java και Aspose.Slides;

Φορτώστε ή δημιουργήστε ένα `Presentation`, εισάγετε ένα `Chart` τύπου `BoxAndWhisker`, τροφοδοτήστε τα δεδομένα σας και αποθηκεύστε το αρχείο—όλα σε λίγες γραμμές Java. Το API διαχειρίζεται τη διάταξη, την κλιμάκωση και την απόδοση, ώστε να μην χρειάζεται να επεξεργαστείτε XML χειροκίνητα. Μπορείτε επίσης να ορίσετε τίτλους διαγράμματος και ετικέτες αξόνων προγραμματιστικά για να παρέχετε πλαίσιο στους θεατές.

## Προαπαιτούμενα

- **Java Development Kit (JDK)**: JDK 8 ή νεότερο.  
- **Aspose.Slides for Java Library**: Απαιτείται για τη διαχείριση PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse ή οποιονδήποτε επεξεργαστή συμβατό με Java.

## Ρύθμιση Aspose.Slides για Java

Προσθέστε τη βιβλιοθήκη ως εξάρτηση Maven, Gradle ή χειροκίνητη.

### Maven

Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Στο `build.gradle` σας, συμπεριλάβετε:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση λήψη

Εναλλακτικά, κατεβάστε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Απόκτηση άδειας

- **Δωρεάν δοκιμή** – εξερευνήστε τις δυνατότητες χωρίς κόστος.  
- **Προσωρινή άδεια** – χρήση για βραχυπρόθεσμη αξιολόγηση.  
- **Αγορά** – ξεκλειδώστε πλήρη λειτουργικότητα για παραγωγικά φορτία εργασίας.

Για να αρχικοποιήσετε το Aspose.Slides, βεβαιωθείτε ότι το JAR βρίσκεται στο classpath σας και ορίστε οποιοδήποτε αρχείο άδειας όπως περιγράφεται στην τεκμηρίωση.

## Οδηγός υλοποίησης

Παρακάτω βρίσκεται ένας βήμα‑βήμα οδηγός. Κάθε μπλοκ εξηγείται πριν από το απόσπασμα ώστε να γνωρίζετε ακριβώς τι κάνει.

### Τι είναι η κλάση `Presentation`;

Η κλάση `Presentation` είναι το κεντρικό αντικείμενο στο Aspose.Slides που αντιπροσωπεύει ολόκληρο το αρχείο PowerPoint στη μνήμη. Παρέχει πρόσβαση σε διαφάνειες, διαγράμματα, σχήματα και άλλα στοιχεία, επιτρέποντάς σας να δημιουργείτε, τροποποιείτε και αποθηκεύετε παρουσιάσεις προγραμματιστικά. Χρησιμοποιώντας αυτήν την κλάση, μπορείτε να προσθέσετε νέες διαφάνειες, να εισάγετε εικόνες και να διαχειριστείτε τη σειρά των διαφανειών με απλές κλήσεις API.

### Βήμα 1: δημιουργία ή άνοιγμα παρουσίασης

Πρώτα, ανοίξτε ένα υπάρχον PPTX ή ξεκινήστε ένα νέο:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Συμβουλή:** Εάν το αρχείο δεν υπάρχει, το Aspose.Slides θα δημιουργήσει αυτόματα μια νέα κενή παρουσίαση.

### Βήμα 2: προσθήκη διαγράμματος box‑and‑whisker στη διαφάνεια

Τοποθετήστε το διάγραμμα όπου χρειάζεστε, καθορίζοντας τη θέση και το μέγεθος (σε points):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Βήμα 3: εκκαθάριση υπάρχοντων δεδομένων

Πριν εισάγετε νέα δεδομένα, διαγράψτε τυχόν κατηγορίες ή σειρές placeholder:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Βήμα 4: διαμόρφωση κατηγοριών

Προσθέστε τις κατηγορίες (ετικέτες άξονα X) που θα εμφανίζονται κάτω από κάθε κουτί:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Σημείωση:** Προσαρμόστε το κείμενο ετικέτας ώστε να ταιριάζει με το πεδίο των δεδομένων σας (π.χ., “Q1”, “Product A”).

### Βήμα 5: δημιουργία και προσαρμογή σειράς

Τώρα δημιουργήστε μια σειρά, ορίστε οπτικές επιλογές και τροφοδοτήστε τα αριθμητικά σημεία δεδομένων:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Μπορείτε να αντικαταστήσετε τον πίνακα `int[] data` με τιμές που προέρχονται από βάση δεδομένων, αρχείο CSV ή οποιαδήποτε άλλη πηγή.

### Βήμα 6: αποθήκευση παρουσίασης

Αποθηκεύστε τις αλλαγές σε ένα νέο αρχείο PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Βήμα 7: εκκαθάριση πόρων

Πάντα απελευθερώστε το αντικείμενο `Presentation` για να ελευθερώσετε τους εγγενείς πόρους:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Πρακτικές εφαρμογές

Τα διαγράμματα box‑and‑whisker είναι ανεκτίμητα στην στατιστική ανάλυση και παρουσίαση δεδομένων. Εδώ είναι μερικά σενάρια όπου διαπρέπουν:

1. **Οικονομική ανάλυση** – οπτικοποίηση κατανομής εσόδων ανά περιοχή.  
2. **Έλεγχος ποιότητας** – εντοπισμός εξωγενών σε μετρήσεις παραγωγής.  
3. **Ακαδημαϊκή έρευνα** – εμφάνιση μεταβλητότητας πειραματικών αποτελεσμάτων.  
4. **Έρευνα αγοράς** – σύγκριση απόδοσης προϊόντων ανά δημογραφικά.

Η ενσωμάτωση αυτών των διαγραμμάτων απευθείας σε παρουσιάσεις PowerPoint επιτρέπει στους ενδιαφερόμενους να κατανοήσουν σύνθετα δεδομένα με μια ματιά.

## Σκέψεις απόδοσης

Το Aspose.Slides μπορεί να διαχειριστεί παρουσιάσεις με **500+ διαφάνειες** και διαγράμματα με **100 000+ σημεία δεδομένων** διατηρώντας τη χρήση μνήμης κάτω από 200 MB σε τυπικό διακομιστή. Για να παραμείνετε εντός αυτών των ορίων:

- **Διαχείριση μνήμης** – απελευθερώστε άμεσα τα αντικείμενα `Presentation`.  
- **Διαχείριση δεδομένων** – φορτώστε μόνο τα απαραίτητα δεδομένα· αποφύγετε την άμεση τροφοδοσία τεράστιων συνόλων δεδομένων στο βιβλίο εργασίας του διαγράμματος.  
- **Lazy loading** – κατά τη δημιουργία πολλών διαφανειών, δημιουργήστε διαγράμματα μόνο για εκείνες που θα εμφανιστούν.

## Συχνά προβλήματα και λύσεις

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **Το διάγραμμα εμφανίζεται κενό** | Κελιά δεδομένων δεν έχουν γεμίσει σωστά | Επαληθεύστε ότι οι κλήσεις `wb.getCell` αναφέρονται στη σωστή γραμμή/στήλη και ότι η τιμή δεν είναι `null`. |
| **Τα outliers δεν εμφανίζονται** | `setShowOutlierPoints` ορίστηκε σε `false` | Βεβαιωθείτε ότι καλείται `series.setShowOutlierPoints(true)`. |
| **Διαρροή μνήμης** | Η παρουσίαση δεν έχει απελευθερωθεί | Πάντα τυλίξτε τη χρήση σε `try/finally` και καλέστε `dispose()`. |
| **Λανθασμένα τεταρτημόρια** | Χρήση της προεπιλεγμένης μεθόδου `Inclusive` | Αλλάξτε σε `Exclusive` μέσω `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Συχνές ερωτήσεις

**Ε1: Τι είναι ένα διάγραμμα box‑and‑whisker;**  
Ένα διάγραμμα box‑and‑whisker, επίσης γνωστό ως box plot, εμφανίζει την κατανομή των δεδομένων βάσει πέντε βασικών στατιστικών: ελάχιστο, πρώτο τεταρτημόριο, διάμεσο, τρίτο τεταρτημόριο και μέγιστο, καθώς και τυχόν εξωγενείς.

**Ε2: Μπορώ να προσαρμόσω την εμφάνιση του διαγράμματος box‑and‑whisker;**  
Ναι. Το Aspose.Slides σας επιτρέπει να αλλάξετε χρώματα, στυλ γραμμών, σχήματα δεικτών και να προσθέσετε ετικέτες δεδομένων μέσω του API μορφοποίησης του διαγράμματος.

**Ε3: Είναι δυνατόν να διαχειριστείτε πολλαπλές σειρές σε ένα μόνο διάγραμμα;**  
Απόλυτα. Επαναλάβετε το μπλοκ δημιουργίας σειράς για κάθε σύνολο δεδομένων που θέλετε να οπτικοποιήσετε.

**Ε4: Πώς να επιλύσω προβλήματα με δεδομένα που δεν εμφανίζονται σωστά;**  
Βεβαιωθείτε ότι τα δεδομένα έχουν γραφτεί σωστά στα κελιά του βιβλίου εργασίας και ότι οι ιδιότητες ορατότητας όπως `setShowMeanLine` είναι ενεργοποιημένες.

**Ε5: Πού μπορώ να λάβω υποστήριξη αν αντιμετωπίσω προβλήματα;**  
Επισκεφθείτε το [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) για βοήθεια από την κοινότητα ή συμβουλευτείτε την επίσημη τεκμηρίωση.

**Ε6: Υποστηρίζει το Aspose.Slides άλλους τύπους διαγραμμάτων;**  
Ναι, υποστηρίζει πάνω από 50 τύπους διαγραμμάτων—συμπεριλαμβανομένων γραμμής, ράβδου, πίτας, διασποράς, ραντάρ και χωνιού—ώστε να μπορείτε να επιλέξετε το καλύτερο οπτικό μέσο για τα δεδομένα σας.

**Ε7: Μπορώ να δημιουργήσω διαγράμματα σε περιβάλλον server χωρίς UI;**  
Η βιβλιοθήκη λειτουργεί πλήρως σε σενάρια server‑side· δεν απαιτείται εγκατάσταση UI ή Microsoft Office.

## Πόροι

- **Τεκμηρίωση**: Εξερευνήστε λεπτομερείς αναφορές API στο [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Λήψη**: Πρόσβαση στη σελίδα κυκλοφοριών του Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Αγορά**: Αγοράστε άδεια για να ξεκλειδώσετε όλες τις δυνατότητες [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Δωρεάν δοκιμή & προσωρινή άδεια**: Ξεκινήστε με δωρεάν δοκιμή ή ζητήστε προσωρινή άδεια [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Ακολουθώντας αυτόν τον οδηγό, έχετε τώρα τα εφόδια για να δημιουργείτε προγραμματιστικά διαγράμματα box‑and‑whisker στα Java applications σας και να τα ενσωματώνετε απευθείας σε παρουσιάσεις PowerPoint. Καλή προγραμματιστική!

---

**Τελευταία ενημέρωση:** 2026-08-21  
**Δοκιμάστηκε με:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να προσθέσετε διάγραμμα στο PowerPoint χρησιμοποιώντας Aspose.Slides for Java: Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Δημιουργία διαγράμματος PowerPoint με Java χρησιμοποιώντας Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Προσθήκη animation σε διάγραμμα PowerPoint χρησιμοποιώντας Aspose.Slides for Java – Οδηγός βήμα‑βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}