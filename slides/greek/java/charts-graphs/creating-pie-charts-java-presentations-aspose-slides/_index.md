---
date: '2026-08-01'
description: Μάθετε πώς να χρησιμοποιείτε μια άδεια Aspose Slides για να δημιουργείτε
  και να προσαρμόζετε διαγράμματα πίτας σε παρουσιάσεις Java. Ακολουθήστε οδηγίες
  βήμα‑βήμα για να διαμορφώσετε τα δεδομένα του διαγράμματος πίτας και να προσθέτετε
  διαφάνειες διαγράμματος αποδοτικά.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Μάθετε πώς να χρησιμοποιείτε μια άδεια Aspose Slides για να δημιουργείτε
  και να προσαρμόζετε διαγράμματα πίτας σε παρουσιάσεις Java. Ακολουθήστε οδηγίες
  βήμα‑βήμα για να διαμορφώσετε τα δεδομένα του διαγράμματος πίτας και να προσθέτετε
  διαφάνειες διαγράμματος αποδοτικά.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Δημιουργία διαγραμμάτων πίτας σε Java με άδεια Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Δημιουργία διαγραμμάτων πίτας σε Java με άδεια Aspose Slides
url: /el/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε διαγράμματα πίτας σε παρουσιάσεις Java χρησιμοποιώντας το Aspose.Slides

## Εισαγωγή

Αν χρειάζεστε να δημιουργήσετε επαγγελματικές παρουσιάσεις, **an Aspose Slides license** σας δίνει τη δυνατότητα να δημιουργείτε και να μορφοποιείτε διαγράμματα προγραμματιστικά. Σε αυτόν τον οδηγό θα μάθετε πώς να δημιουργήσετε ένα διάγραμμα πίτας, να ρυθμίσετε τα δεδομένα του και να το ενσωματώσετε σε μια σειρά διαφανειών Java — χωρίς να εξαρτάστε από το Microsoft PowerPoint. Θα περάσουμε από τη ρύθμιση, τη ροή κώδικα και συμβουλές βέλτιστων πρακτικών ώστε να παραδίδετε επαγγελματικές οπτικές αναφορές σε λίγα λεπτά.

**Τι θα μάθετε:**
- Ρύθμιση του Aspose.Slides για Java με έγκυρη άδεια
- Βήματα για τη δημιουργία και προσαρμογή ενός διαγράμματος πίτας
- Πώς να ρυθμίσετε τα δεδομένα του διαγράμματος πίτας και να προσθέσετε διαφάνειες με διαγράμματα
- Κοινά προβλήματα και τεχνικές βελτιστοποίησης

Ας ξεκινήσουμε επιβεβαιώνοντας ότι το περιβάλλον σας είναι έτοιμο.

## Γρήγορες Απαντήσεις
- **Τι ενεργοποιεί η άδεια Aspose Slides;** Δημιουργία πλήρους λειτουργίας διαγραμμάτων, εξαγωγή σε PDF/HTML και αφαίρεση υδατογραφήματος.
- **Ποια έκδοση Java απαιτείται;** JDK 16 ή νεότερη.
- **Χρειάζομαι Maven ή Gradle;** Και τα δύο λειτουργούν· η βιβλιοθήκη είναι διαθέσιμη και μέσω των δύο.
- **Πόσες σημειακές τιμές μπορεί να περιέχει ένα διάγραμμα πίτας;** Έως 10 000 σημεία χωρίς προβλήματα μνήμης.
- **Μπορώ να εξάγω τη διαφάνεια ως εικόνα;** Ναι – υποστηρίζονται PNG, JPEG, SVG και άλλα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:
- **Απαιτούμενες βιβλιοθήκες:** Aspose.Slides for Java (έκδοση 25.4 ή νεότερη) – αυτή η έκδοση υποστηρίζει τις πιο πρόσφατες μορφές αρχείων και βελτιώσεις απόδοσης.
- **Ρύθμιση Περιβάλλοντος:** JDK 16+ εγκατεστημένο και ρυθμισμένο στο IDE ή στο σύστημα κατασκευής σας.
- **Βασικές Γνώσεις:** Εξοικείωση με Java, Maven ή Gradle, και έννοιες αντικειμενοστραφούς προγραμματισμού.

## Ρύθμιση του Aspose.Slides για Java

Για να χρησιμοποιήσετε το Aspose.Slides για Java, συμπεριλάβτε το στο έργο σας. Ακολουθεί πώς να προσθέσετε την εξάρτηση με τα πιο κοινά εργαλεία κατασκευής:

**Maven:**  
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

**Direct Download:** Μπορείτε επίσης να κατεβάσετε το τελευταίο JAR από [Αναφορές Aspose.Slides για Java](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας

Η Aspose προσφέρει δωρεάν δοκιμή που ξεκλειδώνει όλες τις λειτουργίες, αλλά μια **valid Aspose Slides license** απαιτείται για παραγωγική χρήση ώστε να αφαιρεθούν τα υδατογραφήματα αξιολόγησης και να κερδίσετε πλεονεκτήματα απόδοσης. Οι επιλογές αγοράς εμφανίζονται στη [purchase page](https://purchase.aspose.com/buy). Αφού αποκτήσετε το αρχείο άδειας, φορτώστε το μία φορά κατά την εκκίνηση της εφαρμογής:

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Οδηγός Υλοποίησης

### Δημιουργία και Προσθήκη Διαγράμματος Πίτας στην Παρουσίαση

#### Επισκόπηση
Αυτή η ενότητα εξηγεί πώς να δημιουργήσετε ένα διάγραμμα πίτας, να ρυθμίσετε τις σειρές δεδομένων του και να ενσωματώσετε το διάγραμμα σε μια διαφάνεια. Θα δείτε τη συνολική ροή από την αρχικοποίηση του αντικειμένου παρουσίασης μέχρι την αποθήκευση του τελικού αρχείου.

#### Βήμα 1: Αρχικοποίηση Παρουσίασης  
`Presentation` is Aspose.Slides' top‑level object that represents a PowerPoint file in memory. Creating an instance gives you a blank slide deck ready for modification.

```java
demo.Presentation pres = new demo.Presentation();
```  
Αυτή η γραμμή δημιουργεί μια νέα παρουσίαση όπου όλες οι επόμενες αλλαγές θα εφαρμοστούν.

#### Βήμα 2: Προσθήκη Διαγράμματος Πίτας στη Διαφάνεια  
`Chart` is the class that encapsulates chart objects, including pie charts. Adding a chart to a slide is a single method call that specifies position and size.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` και `yPosition` ορίζουν την πάνω‑αριστερή γωνία του διαγράμματος.  
- `width` και `height` καθορίζουν το οπτικό αποτύπωμα του διαγράμματος στη διαφάνεια.

#### Βήμα 3: Ρύθμιση Δεδομένων Διαγράμματος Πίτας  
`ChartData` holds the data series for a chart.  
**Πώς να ρυθμίσω τα δεδομένα του διαγράμματος πίτας;**  
Παρέχετε μια σύντομη απάντηση πρώτα: Χρησιμοποιήστε τη συλλογή `ChartData` για να προσθέσετε μια σειρά, στη συνέχεια γεμίστε αντικείμενα `ChartDataPoint` με αριθμητικές τιμές και ονόματα κατηγοριών. Αυτή η προσέγγιση σας επιτρέπει να εμφανίσετε έως 10 000 φέτες διατηρώντας τη μορφοποίηση ετικετών. Αφού ορίσετε τα δεδομένα, μπορείτε να προσαρμόσετε χρώματα, υπομνήματα και ετικέτες δεδομένων ώστε να ταιριάζουν με το εταιρικό στυλ.

Τώρα, εδώ είναι ο κώδικας που προσθέτει δύο κατηγορίες και εμφανίζει τις ετικέτες τους:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Το απόσπασμα δημιουργεί μια σειρά δεδομένων, εισάγει δύο σημεία και ενεργοποιεί τις ετικέτες κατηγοριών στο διάγραμμα.

#### Βήμα 4: Αποθήκευση Παρουσίασης  
Τέλος, αποθηκεύστε την παρουσίαση σε μορφή της επιλογής σας (PPTX, PDF ή PNG). Η μέθοδος `save` σέβεται την ενεργή άδεια, εξασφαλίζοντας ότι δεν εμφανίζονται υδατογραφήματα δοκιμής.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Συνηθισμένα Προβλήματα και Λύσεις
- **Missing License Error:** Βεβαιωθείτε ότι η διαδρομή του αρχείου άδειας είναι σωστή και ότι το αντικείμενο `License` έχει δημιουργηθεί πριν από οποιεσδήποτε κλήσεις Aspose.Slides.
- **Empty Chart:** Ελέγξτε ότι η σειρά `ChartData` περιέχει τουλάχιστον ένα `ChartDataPoint`. Μια κενή σειρά οδηγεί σε κενό χώρο διαγράμματος.
- **Performance Lag with Large Data Sets:** Χρησιμοποιήστε `presentation.getSlides().removeAt(index)` για να απορρίψετε αχρησιμοποίητες διαφάνειες και καλέστε `System.gc()` μετά από βαριά επεξεργασία.

## Πρακτικές Εφαρμογές
1. **Business Reports:** Οπτικοποιήστε το μερίδιο αγοράς ή τη διανομή εσόδων ανά περιοχή με ένα μόνο διάγραμμα πίτας.
2. **Academic Presentations:** Εμφανίστε αποτελέσματα ερευνών ή πειραμάτων με σαφή και εύπεπτο τρόπο.
3. **Project Dashboards:** Αντιπροσωπεύστε ποσοστά ολοκλήρωσης εργασιών ή κατανομή πόρων άμεσα σε μια διαφάνεια.

Μπορείτε επίσης να συνδυάσετε το Aspose.Slides με JDBC για να αντλήσετε ζωντανά δεδομένα από βάση, δημιουργώντας ενημερωμένα διαγράμματα για εβδομαδιαίες εκτελεστικές ενημερώσεις.

## Σκέψεις Απόδοσης
Όταν εργάζεστε με παρουσιάσεις που περιέχουν πολλές εικόνες υψηλής ανάλυσης ή μεγάλα σύνολα δεδομένων:
- Απελευθερώστε αντικείμενα άμεσα χρησιμοποιώντας `try‑with‑resources` ή ρητές κλήσεις `dispose()`.
- Ενεργοποιήστε τη lazy loading των πόρων διαφάνειας για να διατηρήσετε τη χρήση μνήμης χαμηλή.
- Για επεξεργασία σε παρτίδες, επαναχρησιμοποιήστε ένα μόνο αντικείμενο `Presentation` όπου είναι δυνατόν ώστε να μειώσετε το φορτίο JVM.

## Συμπέρασμα
Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή ροή εργασίας για τη δημιουργία διαγραμμάτων πίτας σε Java χρησιμοποιώντας μια **Aspose Slides license**. Πειραματιστείτε με πρόσθετους τύπους διαγραμμάτων — ράβδων, γραμμών ή δακτυλίου — για να εμπλουτίσετε περαιτέρω τις διαφάνειές σας. Στη συνέχεια, εξερευνήστε τις δυνατότητες εξαγωγής του API για αυτόματη δημιουργία PDF αναφορών ή PNG εικόνων.

## Συχνές Ερωτήσεις

**Q: Πώς μπορώ να προσθέσω πολλαπλά διαγράμματα σε μία διαφάνεια;**  
A: Καλέστε `slide.getShapes().addChart()` για κάθε διάγραμμα, παρέχοντας μοναδικές συντεταγμένες και διαστάσεις για κάθε περίπτωση.

**Q: Ποιες είναι μερικές εναλλακτικές λύσεις στο Aspose.Slides για Java;**  
A: Apache POI και JFreeChart είναι κοινές εναλλακτικές, αλλά δεν προσφέρουν τις ολοκληρωμένες επιλογές εξαγωγής και το μοντέλο αδειοδότησης του Aspose.

**Q: Μπορώ να μετατρέψω την παρουσίασή μου σε άλλες μορφές χρησιμοποιώντας το Aspose.Slides;**  
A: Ναι — εξαγωγή σε PDF, XPS, HTML, PNG, JPEG, SVG και άλλα με μία μόνο κλήση `save`.

**Q: Πώς διαχειρίζομαι την αδειοδότηση για μια μεγάλη ομάδα ανάπτυξης;**  
A: Αγοράστε εταιρική άδεια που καλύπτει πολλούς προγραμματιστές και διακομιστές· επικοινωνήστε με τις πωλήσεις της Aspose για εκπτώσεις όγκου.

**Q: Τι γίνεται αν τα δεδομένα του διαγράμματος ενημερώνονται συχνά;**  
A: Ενσωματώστε το Aspose.Slides με μια πηγή δεδομένων (π.χ. ερώτημα SQL) και ξαναδημιουργήστε το διάγραμμα σε χρόνο εκτέλεσης· το API υποστηρίζει δυναμική σύνδεση δεδομένων.

## Πόροι
- **Τεκμηρίωση:** [Αναφορά Aspose.Slides Java](https://reference.aspose.com/slides/java/)
- **Λήψη:** [Τελευταίες Εκδόσεις](https://releases.aspose.com/slides/java/)
- **Αγορά:** [Αγορά Άδειας](https://purchase.aspose.com/buy)
- **Δωρεάν Δοκιμή:** [Δοκιμάστε Aspose.Slides Δωρεάν](https://releases.aspose.com/slides/java/)
- **Προσωρινή Άδεια:** [Απόκτηση Προσωρινής Άδειας](https://purchase.aspose.com/temporary-license/)
- **Υποστήριξη:** [Φόρουμ Aspose](https://forum.aspose.com/c/slides/11)

---

**Τελευταία ενημέρωση:** 2026-08-01  
**Δοκιμάστηκε με:** Aspose.Slides for Java 25.4  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να Προσθέσετε και να Διαμορφώσετε Διαγράμματα σε Παρουσιάσεις Χρησιμοποιώντας Aspose.Slides για Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Δημιουργία και Προσαρμογή Διαγραμμάτων σε Παρουσιάσεις Java Χρησιμοποιώντας Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Πώς να Δημιουργήσετε και να Διαμορφώσετε Παρουσιάσεις με Aspose.Slides Java: Οδηγός Βήμα‑Βήμα](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}