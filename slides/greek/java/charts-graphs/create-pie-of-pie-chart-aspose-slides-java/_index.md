---
date: '2026-07-17'
description: Μάθετε πώς να προσθέσετε chart στο PowerPoint δημιουργώντας ένα Pie of
  Pie chart χρησιμοποιώντας Aspose.Slides for Java. Περιλαμβάνει setup, code, customization,
  και saving ως PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Προσθήκη chart στο PowerPoint με Aspose.Slides for Java. Αυτός ο οδηγός
  δείχνει πώς να δημιουργήσετε, να προσαρμόσετε και να αποθηκεύσετε ένα Pie of Pie
  chart ως PPTX σε λίγα λεπτά.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Προσθήκη Chart στο PowerPoint – Δημιουργία Pie of Pie Chart σε Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Προσθήκη Chart στο PowerPoint – Δημιουργία Pie of Pie Chart σε Java με Aspose.Slides
url: /el/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Προσθήκη Διαγράμματος στο PowerPoint – Δημιουργία Διαγράμματος Πίτας Πίτας σε Java με Aspose.Slides

## Διαγράμματα & Γραφήματα

### Εισαγωγή

Στις σύγχρονες παρουσιάσεις που βασίζονται σε δεδομένα, η **προσθήκη διαγράμματος στο PowerPoint** είναι συχνά ο ταχύτερος τρόπος για να μετατρέψετε ακατέργαστους αριθμούς σε οπτική κατανόηση. Ένα κανονικό διάγραμμα πίτας λειτουργεί καλά για λίγες κατηγορίες, αλλά όταν μερικές φέτες είναι πολύ μικρές γίνονται ακατανόητες. Ένα διάγραμμα *Pie of Pie* λύνει αυτό το πρόβλημα εξάγοντας αυτές τις μικρές φέτες σε μια δευτερεύουσα πίτα, διατηρώντας το κύριο διάγραμμα καθαρό και τις λεπτομέρειες προσβάσιμες.

Σε αυτό το σεμινάριο θα μάθετε πώς να **προσθέσετε διάγραμμα στο PowerPoint** δημιουργώντας ένα διάγραμμα Pie of Pie με το Aspose.Slides for Java. Θα περάσουμε από τη ρύθμιση του περιβάλλοντος, τη δημιουργία του διαγράμματος, την προσαρμογή των ετικετών, τη ρύθμιση της θέσης διαχωρισμού και, τέλος, την αποθήκευση της παρουσίασης ως αρχείο PPTX. Στο τέλος θα είστε έτοιμοι να ενσωματώσετε σύνθετα διαγράμματα σε οποιοδήποτε σύνολο διαφανειών.

## Γρήγορες Απαντήσεις
Στο Aspose.Slides, το `Presentation` αντιπροσωπεύει ένα αρχείο PPTX, το `ChartType.PieOfPie` επιλέγει το διάγραμμα Pie of Pie, το `setShowValue(true)` εμφανίζει τις τιμές στις ετικέτες, και το `save` γράφει το αρχείο.

- **Ποια είναι η κύρια κλάση για τη διαχείριση PowerPoint;** `Presentation` – αντιπροσωπεύει ένα ολόκληρο αρχείο PPTX στη μνήμη.  
- **Ποιος τύπος διαγράμματος δημιουργεί μια δευτερεύουσα πίτα για μικρές φέτες;** `ChartType.PieOfPie`.  
- **Πώς εμφανίζετε τις τιμές σε κάθε φέτα;** Ορίστε `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Μπορείτε να αποθηκεύσετε το αρχείο απευθείας ως PPTX;** Ναι – καλέστε `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Χρειάζεστε άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή 30 ημερών λειτουργεί για δοκιμές· μια μόνιμη άδεια αφαιρεί τα υδατογραφήματα αξιολόγησης.

## Τι είναι ένα Διάγραμμα Pie of Pie;
Ένα **διάγραμμα Pie of Pie** είναι μια οπτικοποίηση πίτας δύο επιπέδων που απομονώνει μία ή περισσότερες μικρές φέτες σε μια ξεχωριστή, συνδεδεμένη πίτα, καθιστώντας τες πιο ευανάγνωστες. Το Aspose.Slides υποστηρίζει αυτόν τον τύπο διαγράμματος έτοιμο προς χρήση, επιτρέποντάς σας να ελέγχετε το μέγεθος διαχωρισμού, τη θέση και τη μορφοποίηση των ετικετών.

## Γιατί να προσθέσετε διάγραμμα στο PowerPoint με το Aspose.Slides;
Το Aspose.Slides μπορεί να δημιουργεί, να επεξεργάζεται και να αποδίδει αρχεία PowerPoint χωρίς εγκατεστημένο το Microsoft Office. Υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου**, επεξεργάζεται παρουσιάσεις με **έως 500 διαφάνειες** σε λιγότερο από ένα δευτερόλεπτο σε τυπικό εξοπλισμό διακομιστή, και παρέχει **πλήρη έλεγχο API** πάνω στο στυλ των διαγραμμάτων, τις ετικέτες δεδομένων και τη διάταξη—ιδανικό για αυτοματοποιημένες ροές αναφοράς.

## Προαπαιτούμενα

- **Java Development Kit (JDK) 16+** εγκατεστημένο.
- Ένα IDE όπως το **IntelliJ IDEA**, **Eclipse**, ή **NetBeans**.
- Maven ή Gradle για διαχείριση εξαρτήσεων (δείτε τις ενότητες παρακάτω).
- Βασικές γνώσεις Java και εξοικείωση με τη δημιουργία έργων.

## Ρύθμιση Aspose.Slides για Java

### Πληροφορίες Εγκατάστασης

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

**Άμεση Λήψη:** Μπορείτε να κατεβάσετε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Βήματα Απόκτησης Άδειας
- **Δωρεάν Δοκιμή:** Ξεκινήστε με δοκιμή 30 ημερών για να εξερευνήσετε όλες τις δυνατότητες.  
- **Προσωρινή Άδεια:** Ζητήστε ένα προσωρινό κλειδί για εκτεταμένη αξιολόγηση.  
- **Αγορά:** Αποκτήστε μόνιμη άδεια για παραγωγική χρήση ώστε να αφαιρεθούν τα υδατογραφήματα αξιολόγησης.

### Βασική Αρχικοποίηση και Ρύθμιση
`Presentation` είναι το κύριο αντικείμενο για τη δημιουργία αρχείων PowerPoint, και `Chart` αντιπροσωπεύει ένα σχήμα διαγράμματος μέσα σε μια διαφάνεια.

```java
Presentation presentation = new Presentation();
```  

Αυτό δημιουργεί μια κενή παρουσίαση έτοιμη για διαφάνειες και διαγράμματα.

## Οδηγός Υλοποίησης

### Πώς προσθέτετε διάγραμμα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java;
Φορτώστε μια νέα `Presentation`, προσθέστε μια διαφάνεια και εισάγετε ένα `Chart` τύπου `PieOfPie`. Η αλυσίδα κλήσεων API είναι σύντομη: δημιουργήστε το διάγραμμα, γεμίστε τα δεδομένα της σειράς, προσαρμόστε την ορατότητα των ετικετών, διαμορφώστε το μέγεθος της δευτερεύουσας πίτας και, τέλος, αποθηκεύστε. Η ολόκληρη διαδικασία τυπικά χωράει σε λιγότερο από 20 γραμμές κώδικα, καθιστώντας την ιδανική για αυτοματοποιημένη δημιουργία αναφορών.

### Δημιουργία Διαγράμματος 'Pie of Pie'

#### Επισκόπηση
Θα δημιουργήσουμε ένα διάγραμμα Pie of Pie στην πρώτη διαφάνεια, θα διαχωρίσουμε τις μικρότερες φέτες και θα ετικετοποιήσουμε κάθε τμήμα με την τιμή του.

#### Βήμα 1: Δημιουργία Αντικειμένου της Κλάσης Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Αυτό αρχικοποιεί το κοντέινερ για όλες τις επόμενες διαφάνειες και διαγράμματα.

#### Βήμα 2: Προσθήκη Διαγράμματος 'Pie of Pie' στην Πρώτη Διαφάνεια
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Εδώ καθορίζουμε το `ChartType.PieOfPie` και ορίζουμε τη θέση του διαγράμματος (X, Y) και το μέγεθός του (πλάτος, ύψος) στον καμβά της διαφάνειας.

#### Βήμα 3: Ορισμός Ετικετών Δεδομένων για Εμφάνιση Τιμών στη Σειρά
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Η ενεργοποίηση του `showValue` κάνει κάθε φέτα να εμφανίζει την αριθμητική της τιμή, κάτι που είναι απαραίτητο για γρήγορη ερμηνεία των δεδομένων.

#### Βήμα 4: Διαμόρφωση Μεγέθους Δεύτερης Πίτας και Διαχωρισμού κατά Ποσοστό
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Αυτές οι επιλογές σας επιτρέπουν να αποφασίσετε πόσο του διαγράμματος θα διατεθεί στη δευτερεύουσα πίτα και ποιες φέτες θα μετακινηθούν βάσει ενός ορίου ποσοστού.

#### Βήμα 5: Αποθήκευση της Παρουσίασης στο Δίσκο σε Μορφή PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Συμβουλή:** Χρησιμοποιήστε απόλυτη διαδρομή ή το `Paths.get()` της Java για να αποφύγετε διαχωριστές ειδικούς για την πλατφόρμα.

## Συχνά Προβλήματα και Λύσεις

Η κλάση `License` φορτώνει ένα αρχείο άδειας για να αφαιρέσει τους περιορισμούς αξιολόγησης.

- **Προειδοποίηση έλλειψης άδειας:** Εάν δείτε “Evaluation Only” στο διάγραμμα, βεβαιωθείτε ότι έχετε εφαρμόσει ένα έγκυρο αρχείο άδειας μέσω `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **Λανθασμένος διαχωρισμός φέτας:** Ελέγξτε ότι η ιδιότητα `splitBy` είναι ορισμένη σε `SplitBy.Percentage` και ότι το `secondPieSize` είναι μια τιμή μεταξύ 0 και 100.
- **Μη εμφάνιση δεδομένων:** Επιβεβαιώστε ότι η σειρά του διαγράμματος περιέχει τουλάχιστον ένα σημείο δεδομένων· διαφορετικά το διάγραμμα θα εμφανιστεί κενό.

## Συχνές Ερωτήσεις

`IChart` αντιπροσωπεύει ένα αντικείμενο διαγράμματος που μπορεί να προστεθεί σε μια διαφάνεια.

**Ε: Μπορώ να δημιουργήσω πολλαπλά διαγράμματα σε μία παρουσίαση;**  
Α: Ναι, δημιουργήστε ένα νέο `IChart` για κάθε διαφάνεια ή θέση· το API επιτρέπει απεριόριστα αντικείμενα διαγράμματος ανά αρχείο.

`SaveFormat.Pdf` καθορίζει τη μορφή εξόδου PDF για αποθήκευση.

**Ε: Υποστηρίζει το Aspose.Slides την αποθήκευση ως PDF επίσης;**  
Α: Απόλυτα – καλέστε `presentation.save("output.pdf", SaveFormat.Pdf)` για να εξάγετε το ίδιο σύνολο διαφανειών σε PDF.

`IPortion` αντιπροσωπεύει μια μεμονωμένη φέτα ενός διαγράμματος πίτας.

**Ε: Ποιος είναι ο μέγιστος αριθμός σημείων δεδομένων που μπορεί να διαχειριστεί ένα διάγραμμα Pie of Pie;**  
Α: Η βιβλιοθήκη υποστηρίζει έως **10.000** σημεία δεδομένων ανά σειρά, περιορισμένο μόνο από τη διαθέσιμη μνήμη.

**Ε: Είναι δυνατόν να προσαρμόσετε τα χρώματα των μεμονωμένων φετών;**  
Α: Ναι, προσπελάστε κάθε `IPortion` μέσω `chart.getChartData().getSeries().get_Item(0).getPortions()` και ορίστε `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Ε: Πώς ενσωματώνω το παραγόμενο PPTX σε μια web εφαρμογή;**  
Α: Μετά την αποθήκευση του αρχείου, ρέξτε το απευθείας στον πελάτη χρησιμοποιώντας `HttpServletResponse` με `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Συμπέρασμα

Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή συνταγή για **προσθήκη διαγράμματος στο PowerPoint** δημιουργώντας ένα διάγραμμα Pie of Pie με το Aspose.Slides for Java. Πειραματιστείτε με διαφορετικά όρια διαχωρισμού, μορφές ετικετών και χρωματικά σχήματα για να ταιριάζουν με τις οδηγίες της μάρκας σας. Στη συνέχεια, εξερευνήστε άλλους τύπους διαγραμμάτων—όπως στοίβαξη μπαρ ή ραντάρ—για να εμπλουτίσετε περαιτέρω τις αυτοματοποιημένες διαφάνειές σας.

---

**Τελευταία Ενημέρωση:** 2026-07-17  
**Δοκιμή Με:** Aspose.Slides for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά Σεμινάρια

- [Δημιουργία Δυναμικού Διαγράμματος Java – Μαθήματα Διαγραμμάτων PowerPoint για Aspose.Slides](/slides/java/charts-graphs/)
- [Πώς να προσθέσετε διάγραμμα πίτας στο PowerPoint με Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Πώς να Προσθέσετε Διαγράμματα στο PowerPoint Χρησιμοποιώντας το Aspose.Slides για Java: Οδηγός Βήμα‑Βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}