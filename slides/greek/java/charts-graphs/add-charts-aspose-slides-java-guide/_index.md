---
date: '2026-06-03'
description: Μάθετε πώς να προσθέτετε charts με το aspose slides maven dependency,
  να διαμορφώνετε data labels και να δημιουργείτε δυναμικά charts σε παρουσιάσεις
  Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Προσθήκη και Διαμόρφωση charts σε παρουσιάσεις
  χρησιμοποιώντας Aspose.Slides for Java'
url: /el/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Προσθήκη και Διαμόρφωση Διαγραμμάτων σε Παρουσιάσεις Χρησιμοποιώντας το Aspose.Slides για Java

## Εισαγωγή
Το **aspose slides maven dependency** επιτρέπει στους προγραμματιστές Java να δημιουργούν, τροποποιούν και εμπλουτίζουν αρχεία PowerPoint προγραμματιστικά, χωρίς ποτέ να ανοίγουν το PowerPoint. Σε πολλές επιχειρηματικές και ακαδημαϊκές περιπτώσεις, η χειροκίνητη εισαγωγή διαγραμμάτων είναι χρονοβόρα και επιρρεπής σε σφάλματα. Αυτό το εκπαιδευτικό υλικό σας δείχνει βήμα‑βήμα πώς να προσθέσετε ένα Bubble Chart, να συνδέσετε ετικέτες δεδομένων με κελιά φύλλου εργασίας και να αποθηκεύσετε το αποτέλεσμα—χρησιμοποιώντας το aspose slides maven dependency με καθαρό, επαναλαμβανόμενο τρόπο.

**Τι Θα Μάθετε**
- Πώς να προσθέσετε διαγράμματα με το aspose slides maven dependency
- Ρύθμιση ενός έργου Java χρησιμοποιώντας Maven ή Gradle
- Φόρτωση υπάρχουσας παρουσίασης και εισαγωγή Bubble Chart
- Διαμόρφωση ετικετών δεδομένων χρησιμοποιώντας αναφορές κελιών (add data labels chart)
- Αποθήκευση του ενημερωμένου αρχείου για μελλοντική διανομή
- Πραγματικές περιπτώσεις χρήσης όπως η δυναμική δημιουργία διαγραμμάτων και η δημιουργία ροών εργασίας διαγραμμάτων παρουσίασης

## Σύντομες Απαντήσεις
- **Ποιο Maven artifact προσθέτει δυνατότητες διαγράμματος;** `com.aspose:aspose-slides:25.4` (ή το τελευταίο)  
- **Μπορώ να συνδέσω ετικέτες δεδομένων με κελιά τύπου Excel;** Ναι – χρησιμοποιήστε `ChartDataLabel` με `setDataLabelFormat` και αναφορές κελιών.  
- **Απαιτείται άδεια για παραγωγή;** Μια πλήρης άδεια αφαιρεί το υδατογράφημα αξιολόγησης και ξεκλειδώνει όλες τις λειτουργίες.  
- **Θα λειτουργήσει σε Java 11+;** Απόλυτα· η βιβλιοθήκη είναι συμβατή με Java 8 έως Java 21.  
- **Πόσοι τύποι διαγραμμάτων υποστηρίζονται;** Πάνω από 70 διαφορετικούς τύπους διαγραμμάτων, συμπεριλαμβανομένων των Bubble, Radar και Stock.

## Τι είναι το aspose slides maven dependency;
Το **aspose slides maven dependency** είναι ένα πακέτο συμβατό με Maven που παρέχει ένα πλήρες API για τη δημιουργία και επεξεργασία αρχείων PowerPoint (PPTX, PPT, ODP) σε Java. Προσθέτοντας αυτήν την εξάρτηση στο `pom.xml` ή `build.gradle`, αποκτάτε πρόσβαση σε πάνω από 70 τύπους διαγραμμάτων, 150+ διατάξεις διαφανειών και τη δυνατότητα διαχείρισης σχημάτων, animations και μεταδεδομένων χωρίς εγκατεστημένο Office.

## Γιατί να χρησιμοποιήσετε το aspose slides maven dependency για αυτοματοποίηση διαγραμμάτων;
Το Aspose.Slides επεξεργάζεται χιλιάδες διαφάνειες σε κάτω από ένα δευτερόλεπτο σε τυπικό εξοπλισμό διακομιστή, υποστηρίζει **70+ τύπους διαγραμμάτων** και μπορεί να αποδώσει παρουσιάσεις έως **10.000 διαφάνειες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Αυτές οι ποσοτικοποιημένες δυνατότητες το καθιστούν ιδανικό για επιχειρησιακή δυναμική δημιουργία διαγραμμάτων, όπου η απόδοση και η κλιμακωσιμότητα είναι αδιαπραγμάτευτες.

## Προαπαιτούμενα
- **Java Development Kit (JDK)** 8 ή νεότερο (συνιστάται Java 11+).  
- **Maven** 3.6+ ή **Gradle** 6+.  
- **Aspose.Slides for Java** library (το aspose slides maven dependency, έκδοση 25.4 ή νεότερη).  
- Βασική εξοικείωση με συλλογές Java και file I/O.  
- Αρχείο αξιολόγησης ή πλήρους άδειας (`license.json`) εάν σκοπεύετε να εκτελέσετε τον κώδικα μετά την περίοδο δοκιμής.

## Πώς να προσθέσετε διάγραμμα σε διαφάνεια χρησιμοποιώντας το Aspose.Slides;
Φορτώστε την παρουσίαση-στόχο, δημιουργήστε ένα νέο σχήμα διαγράμματος στη ζητούμενη διαφάνεια και ορίστε τον τύπο διαγράμματος (Bubble σε αυτό το παράδειγμα). Η ολοκληρωμένη λειτουργία μπορεί να εκτελεστεί σε **τρεις συνοπτικές γραμμές κώδικα** μόλις η βιβλιοθήκη αναφερθεί, καθιστώντας την ιδανική για γρήγορη πρωτοτυποποίηση και παραγωγικές γραμμές εργασίας.

### Βήμα 1: Προσθήκη του aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Αυτά τα αποσπάσματα αντλούν ολόκληρο το API του Aspose.Slides—συμπεριλαμβανομένης της υποστήριξης διαγραμμάτων—απευθείας από το Maven Central.

### Βήμα 2: Φόρτωση της παρουσίασης και εισαγωγή Bubble Chart
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Βήμα 3: Διαμόρφωση της σειράς δεδομένων και των ετικετών του διαγράμματος
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Βήμα 4: Αποθήκευση της τροποποιημένης παρουσίασης
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Πώς να διαμορφώσετε ετικέτες δεδομένων χρησιμοποιώντας αναφορές κελιών;
Οι ετικέτες δεδομένων μπορούν να συνδεθούν με εξωτερικές τιμές κελιών, μιμούμενες τη λειτουργία “Link to Cell” του Excel. Αυτή η προσέγγιση εξαλείφει τις σκληρά κωδικοποιημένες τιμές και επιτρέπει **δυναμική δημιουργία διαγραμμάτων** όπου το περιεχόμενο των ετικετών ενημερώνεται αυτόματα καθώς τα υποκείμενα δεδομένα αλλάζουν. Συνδέοντας κάθε ετικέτα με ένα συγκεκριμένο κελί του βιβλίου εργασίας, διασφαλίζετε ότι οποιαδήποτε τροποποίηση των πηγών δεδομένων αντικατοπτρίζεται αμέσως στην παρουσίαση, μειώνοντας το κόστος συντήρησης και τον κίνδυνο παλαιών πληροφοριών.

### Άμεση Απάντηση
Καλέστε `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` και περάστε ένα `DataLabelFormat` που αναφέρεται σε διεύθυνση κελιού όπως `"Sheet1!A2"`. Το Aspose.Slides επιλύει την αναφορά κατά το χρόνο εκτέλεσης, ενσωματώνοντας την τρέχουσα τιμή του κελιού στην ετικέτα του διαγράμματος.

### Βήμα‑βήμα
1. Εντοπίστε τη σειρά που θέλετε να επισημάνετε.  
2. Ανακτήστε το αντικείμενο `IDataLabel` για κάθε σημείο δεδομένων.  
3. Χρησιμοποιήστε `setDataLabelFormat` με `DataLabelFormat` ρυθμισμένο για `CellReference`.  
4. Προαιρετικά προσαρμόστε τη γραμματοσειρά, το χρώμα και τις επιλογές εμφάνισης.

## Πώς να αποθηκεύσετε την τροποποιημένη παρουσίαση;
Η αποθήκευση είναι μια κλήση μεθόδου που γράφει το αντικείμενο `Presentation` στη μνήμη σε διαδρομή αρχείου ή ροή εξόδου. Μπορείτε επίσης να επιλέξετε τη μορφή εξόδου (PPTX, PDF, ODP) περνώντας το αντίστοιχο enum `SaveFormat`. Η λειτουργία αυτή ρέει το αποτέλεσμα απευθείας στο δίσκο, απελευθερώνοντας όλους τους εγγενείς πόρους αυτόματα όταν το αντικείμενο `Presentation` κλείσει ή βγει εκτός εμβέλειας, βοηθώντας στη διατήρηση χαμηλής χρήσης μνήμης ακόμη και για μεγάλες παρουσιάσεις.

### Άμεση Απάντηση
Κλήση `presentation.save("output.pptx", SaveFormat.Pptx)`· η βιβλιοθήκη ρέει το αποτέλεσμα απευθείας στο δίσκο, απελευθερώνοντας όλους τους εγγενείς πόρους αυτόματα όταν το αντικείμενο `Presentation` κλείσει ή βγει εκτός εμβέλειας.

## Πρακτικές Εφαρμογές
1. **Επιχειρηματικές Αναφορές:** Δημιουργία τριμηνιαίων διαγραμμάτων πωλήσεων αυτόματα από εξαγωγή βάσης δεδομένων.  
2. **Ακαδημαϊκές Διαλέξεις:** Ανάκτηση ζωντανών ερευνητικών δεδομένων σε διαφάνειες διαλέξεων για κάθε μάθημα.  
3. **Προωθήσεις Πωλήσεων:** Δημιουργία προσαρμοσμένων ταμπλό απόδοσης για πελάτες σε πραγματικό χρόνο.  
4. **Διαχείριση Έργων:** Οπτικοποίηση χρονοδιαγραμμάτων τύπου Gantt με δυναμικές ετικέτες δεδομένων.  
5. **Αναλύσεις Μάρκετινγκ:** Ενσωμάτωση KPI καμπάνιας σε παρουσιάσεις που ενημερώνονται καθώς έρχονται νέες μετρήσεις.

## Σκέψεις Απόδοσης
- **Διαχείριση Μνήμης:** Χρησιμοποιήστε try‑with‑resources ή ρητή κλήση `presentation.dispose()` για άμεση απελευθέρωση της εγγενούς μνήμης.  
- **Μεγάλα Σύνολα Δεδομένων:** Όταν διαχειρίζεστε πάνω από 10.000 σημεία δεδομένων, γεμίστε τα δεδομένα του διαγράμματος μέσω `ChartDataWorkbook` για να αποφύγετε τη φόρτωση ολόκληρου του συνόλου σε αντικείμενα Java.  
- **Ασφάλεια Νήματος:** Κάθε νήμα πρέπει να εργάζεται με το δικό του αντικείμενο `Presentation`; το API δεν είναι thread‑safe για κοινόχρηστα αντικείμενα.  

## Συνηθισμένα Προβλήματα και Λύσεις
- **Issue:** “License file not found.”  
  **Solution:** Τοποθετήστε το `license.json` στο classpath και καλέστε `License license = new License(); license.setLicense("license.json");` πριν από οποιαδήποτε χρήση του API.  
- **Issue:** Chart appears blank after saving.  
  **Solution:** Βεβαιωθείτε ότι το βιβλίο εργασίας δεδομένων του διαγράμματος αποθηκεύεται με την παρουσίαση (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Issue:** Data labels show “#REF!” errors.  
  **Solution:** Επαληθεύστε ότι η συμβολοσειρά αναφοράς κελιού ταιριάζει ακριβώς με το όνομα φύλλου και τη διεύθυνση, και ότι το σχετικό βιβλίο εργασίας είναι συνδεδεμένο με το διάγραμμα.  

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσθέσω άλλους τύπους διαγραμμάτων εκτός από Bubble;**  
A: Ναι, η απαρίθμηση `ChartType` περιλαμβάνει line, bar, pie, radar, stock και πάνω από 70 επιπλέον τύπους.

**Q: Το aspose slides maven dependency λειτουργεί με OpenJDK;**  
A: Απόλυτα· είναι πλήρως συμβατό με OpenJDK 8‑21 και λειτουργεί σε όλα τα κύρια λειτουργικά συστήματα.

**Q: Πώς ενσωματώνω διάγραμμα από υπάρχον αρχείο Excel;**  
A: Φορτώστε το βιβλίο εργασίας Excel με `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, έπειτα συνδέστε το `ChartDataWorkbook` του διαγράμματος με το βιβλίο εργασίας πριν ορίσετε τις αναφορές κελιών.

**Q: Υπάρχει όριο στον αριθμό διαγραμμάτων ανά διαφάνεια;**  
A: Σ πρακτικό επίπεδο όχι—το Aspose.Slides μπορεί να διαχειριστεί δεκάδες διαγράμματα ανά διαφάνεια, περιορισμένο μόνο από τη διαθέσιμη μνήμη.

**Q: Σε ποιες μορφές μπορώ να εξάγω την τελική παρουσίαση;**  
A: Υποστηρίζονται PPTX, PPT, ODP, PDF, XPS, HTML και ακόμη μορφές εικόνας όπως PNG και JPEG.

## Πόροι
- [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) – κατεβάστε τα πιο πρόσφατα δυαδικά της βιβλιοθήκης.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – ολοκληρωμένη αναφορά API και οδηγούς.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – άμεση σελίδα λήψης για τα πακέτα Maven/Gradle.  
- [Purchase a License](https://purchase.aspose.com/buy) – αποκτήστε πλήρη εμπορική άδεια.  
- [Free Trial](https://releases.aspose.com/slides/java/) – ξεκινήστε με δοκιμαστική έκδοση για αξιολόγηση των λειτουργιών.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – ζητήστε προσωρινό κλειδί για εκτεταμένη αξιολόγηση.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – λάβετε βοήθεια από την κοινότητα και τους μηχανικούς της Aspose.

## Συμπέρασμα
Τώρα έχετε έναν πλήρη οδηγό βήμα‑βήμα για τη χρήση του **aspose slides maven dependency** ώστε να προσθέτετε, διαμορφώνετε και αποθηκεύετε διαγράμματα σε παρουσιάσεις Java. Ακολουθώντας τα παραπάνω βήματα μπορείτε να αυτοματοποιήσετε τη δημιουργία διαγραμμάτων, να συνδέσετε ετικέτες δεδομένων με ζωντανές τιμές κελιών και να παράγετε επαγγελματικές παρουσιάσεις σε κλίμακα. Δοκιμάστε άλλους τύπους διαγραμμάτων, εξερευνήστε τις APIs animation και ενσωματώστε αυτή τη ροή εργασίας στις διαδικασίες αναφοράς σας για μέγιστο αντίκτυπο.

---  
**Τελευταία Ενημέρωση:** 2026-06-03  
**Δοκιμή Με:** Aspose.Slides for Java 25.4  
**Συγγραφέας:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε και να Διαμορφώσετε Παρουσιάσεις με Aspose.Slides Java: Οδηγός Βήμα‑Βήμα](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Δημιουργία PPTX Java με Aspose.Slides Maven – Οδηγός Αυτοματοποίησης](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Πώς να Δημιουργήσετε Διάγραμμα σε Java με Aspose.Slides: Αναλυτικός Οδηγός](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}