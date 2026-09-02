---
date: '2026-09-02'
description: Μάθετε πώς να δημιουργήσετε χωνικό διάγραμμα στο PowerPoint χρησιμοποιώντας
  το Aspose.Slides for Java. Αυτός ο οδηγός βήμα προς βήμα καλύπτει τη ρύθμιση των
  δεδομένων του διαγράμματος, την προσαρμογή χρωμάτων και την εξαγωγή της παρουσίασης.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Μάθετε πώς να δημιουργήσετε χωνικό διάγραμμα στο PowerPoint χρησιμοποιώντας
  το Aspose.Slides for Java. Αυτός ο οδηγός σας καθοδηγεί στη ρύθμιση των δεδομένων,
  την προσαρμογή χρωμάτων και την εξαγωγή της τελικής παρουσίασης.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Δημιουργία χωνικού διαγράμματος στο PowerPoint με Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Δημιουργία χωνικού διαγράμματος στο PowerPoint με Aspose.Slides for Java
url: /el/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Κατάκτηση της δημιουργίας διαγράμματος χωνιού στο PowerPoint με το Aspose.Slides for Java

## Εισαγωγή
Η δημιουργία εντυπωσιακών παρουσιάσεων είναι μια τέχνη που συνδυάζει οπτικοποίηση δεδομένων, σχεδιασμό και αφήγηση. Ένα ισχυρό οπτικό στοιχείο που διευκρινίζει αμέσως μια πολυεπίπεδη διαδικασία είναι το διάγραμμα χωνιού. Είτε χρειάζεστε να απεικονίσετε μια αλυσίδα πωλήσεων, μια ροή μετατροπής ή ένα σημείο συμφόρησης στην παραγωγή, ένα καλά σχεδιασμένο διάγραμμα χωνιού μετατρέπει ακατέργαστους αριθμούς σε μια διαισθητική αφήγηση. Σε αυτό το σεμινάριο θα μάθετε πώς να **δημιουργήσετε διάγραμμα χωνιού** στο PowerPoint προγραμματιστικά χρησιμοποιώντας το Aspose.Slides for Java, να διαμορφώσετε τα δεδομένα του, να προσαρμόσετε το χρώμα κάθε τμήματος και να εξάγετε το τελικό αρχείο.

**Τι θα μάθετε**
- Πώς να προσθέσετε το Aspose.Slides for Java σε ένα έργο Maven ή Gradle  
- Πώς να δημιουργήσετε ένα αντικείμενο `Presentation` και να έχετε πρόσβαση στις διαφάνειές του  
- Πώς να εισαγάγετε ένα διάγραμμα χωνιού, να ορίσετε κατηγορίες και να γεμίσετε τα δεδομένα σειράς  
- Πώς να μορφοποιήσετε κάθε τμήμα του χωνιού με συμπαγείς γεμίσματα ή χρώματα ειδικά για το brand  
- Πώς να αποθηκεύσετε την παρουσίαση ως αρχείο PPTX ή να εξάγετε μια διαφάνεια ως εικόνα  

## Σύντομες απαντήσεις
- **Ποια είναι η κύρια βιβλιοθήκη για οπτικοποίηση δεδομένων java;** Aspose.Slides for Java.  
- **Πώς δημιουργείτε ένα διάγραμμα χωνιού στο PowerPoint;** Call `slide.addChart(ChartType.Funnel, …)` on the target slide.  
- **Ποιο API ορίζει την πηγή δεδομένων του διαγράμματος;** Use `IChartDataWorkbook` together with `chart.getChartData()`.  
- **Μπορείτε να προσαρμόσετε τα χρώματα για κάθε τμήμα του χωνιού;** Yes—set `FillFormat.setFillType(FillType.Solid)` and assign a `java.awt.Color`.  
- **Χρειάζεστε άδεια για παραγωγική χρήση;** A purchased Aspose.Slides license is required for commercial deployments.

## Τι είναι η οπτικοποίηση δεδομένων Java;
Η οπτικοποίηση δεδομένων Java είναι η πρακτική μετατροπής ακατέργαστων δεδομένων σε γραφήματα, διαγράμματα ή διαδραστικά γραφικά απευθείας από εφαρμογές Java. Το Aspose.Slides for Java είναι μια κορυφαία βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν πάνω από 100 τύπους διαγραμμάτων —συμπεριλαμβανομένων των διαγραμμάτων χωνιού— χωρίς να ανοίγουν ποτέ το PowerPoint χειροκίνητα, υποστηρίζοντας παρουσιάσεις με έως και 500 διαφάνειες ενώ διατηρεί τη χρήση μνήμης χαμηλή.

## Γιατί να χρησιμοποιείτε διαγράμματα χωνιού στο PowerPoint;
Τα διαγράμματα χωνιού αποκαλύπτουν αμέσως τα ποσοστά απώλειας μεταξύ διαδοχικών σταδίων, καθιστώντας τα ιδανικά για αλυσίδες πωλήσεων, ανάλυση μετατροπών ή αξιολόγηση αποδοτικότητας διαδικασιών. Το Aspose.Slides σας δίνει έλεγχο pixel‑perfect πάνω στη διάταξη, τα χρώματα των τμημάτων και τις ετικέτες δεδομένων, ώστε να διατηρείτε τη συνέπεια του brand και να αποφεύγετε την χειροκίνητη επεξεργασία διαγραμμάτων στη διεπαφή του PowerPoint.

## Προαπαιτούμενα (H2)

### Απαιτούμενες βιβλιοθήκες, εκδόσεις και εξαρτήσεις
Για να ενσωματώσετε το Aspose.Slides for Java στο έργο σας, συμπεριλάβετε τις κατάλληλες συντεταγμένες Maven ή Gradle. Η βιβλιοθήκη λειτουργεί με Java 8‑21 και δεν απαιτεί εξωτερικές εγγενείς εξαρτήσεις.

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

Μπορείτε επίσης να κατεβάσετε το JAR απευθείας από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απαιτήσεις ρύθμισης περιβάλλοντος
Βεβαιωθείτε ότι έχετε εγκατεστημένο το JDK 8 ή νεότερο και ότι το `JAVA_HOME` δείχνει στον σωστό φάκελο του JDK. Το Aspose.Slides λειτουργεί σε οποιοδήποτε OS που υποστηρίζει το JDK, συμπεριλαμβανομένων των Windows, macOS και Linux.

### Προαπαιτούμενα γνώσης
Βασική εξοικείωση με τη σύνταξη Java, τον αντικειμενοστραφή προγραμματισμό και την έννοια ενός αρχείου παρουσίασης θα βοηθήσει, αλλά τα αποσπάσματα κώδικα εξηγούνται πλήρως για προγραμματιστές κάθε επιπέδου εμπειρίας.

## Ρύθμιση του Aspose.Slides for Java (H2)

1. **Προσθήκη της εξάρτησης** – Χρησιμοποιήστε το απόσπασμα Maven ή Gradle παραπάνω.  
2. **Απόκτηση άδειας** –  
   - **Δωρεάν δοκιμή** – Κατεβάστε μια προσωρινή άδεια από [Aspose's website](https://purchase.aspose.com/temporary-license/) για αξιολόγηση.  
   - **Πλήρης άδεια** – Αγοράστε μια παραγωγική άδεια μέσω της [purchase page](https://purchase.aspose.com/buy).  
3. **Βασική αρχικοποίηση** –  

`Presentation` είναι η κεντρική κλάση του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη. Παρέχει πρόσβαση σε διαφάνειες, σχήματα και αντικείμενα διαγραμμάτων.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Ο παραπάνω κώδικας δημιουργεί ένα νέο αντικείμενο `Presentation`, έτοιμο για επεξεργασία διαφανειών, και εξασφαλίζει ότι οι πόροι απελευθερώνονται με το `dispose()`.

## Οδηγός υλοποίησης

Θα περάσουμε βήμα-βήμα από κάθε δυνατότητα που απαιτείται για τη δημιουργία ενός πλήρους διαγράμματος χωνιού, προσθέτοντας σύντομο επεξηγηματικό κείμενο πριν από κάθε θέση κώδικα.

### Χαρακτηριστικό 1: δημιουργία παρουσίασης (H2)

#### Επισκόπηση
Ξεκινήστε δημιουργώντας μια παρουσίαση της κλάσης `Presentation`. Αυτό το αντικείμενο είναι το σημείο εισόδου για όλες τις επόμενες λειτουργίες.

`Presentation` είναι το κορυφαίο αντικείμενο του Aspose.Slides που κρατά τη συλλογή διαφανειών και τις παγκόσμιες ρυθμίσεις του εγγράφου.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Το απόσπασμα ανοίγει μια κενή παρουσίαση, την οποία μπορείτε αργότερα να αποθηκεύσετε ως αρχείο `.pptx`.

### Χαρακτηριστικό 2: προσθήκη διαγράμματος χωνιού σε διαφάνεια (H2)

#### Επισκόπηση
Εισάγετε ένα διάγραμμα χωνιού στην πρώτη διαφάνεια, ορίστε το μέγεθός του και καθορίστε τον τύπο διαγράμματος.

`ChartType.Funnel` λέει στο Aspose.Slides να αποδώσει μια οπτικοποίηση τύπου χωνιού αντί για ραβδόγραμμα ή γραμμικό διάγραμμα.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Η κλήση `addChart` δημιουργεί το σχήμα διαγράμματος, το τοποθετεί στο `(50, 50)` points και του δίνει πλάτος `500` και ύψος `400`.

### Χαρακτηριστικό 3: εκκαθάριση δεδομένων διαγράμματος (H2)

#### Επισκόπηση
Πριν γεμίσετε το διάγραμμα, διαγράψτε τυχόν κατηγορίες ή σειρές που μπορεί να περιέχει το πρότυπο.

`chart.getChartData().getCategories().clear()` αφαιρεί όλες τις υπάρχουσες κατηγορίες, ενώ `chart.getChartData().getSeries().clear()` αφαιρεί τυχόν προ‑συμπληρωμένες σειρές.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Αυτό εξασφαλίζει καθαρό καμβά ώστε τα προσαρμοσμένα σας δεδομένα να εμφανιστούν ακριβώς όπως θέλετε.

### Χαρακτηριστικό 4: ρύθμιση βιβλίου δεδομένων διαγράμματος (H2)

#### Επισκόπηση
Το αντικείμενο `IChartDataWorkbook` αποθηκεύει τις ακατέργαστες τιμές που τροφοδοτούν το διάγραμμα. Η αρχικοποίησή του σας επιτρέπει να γράψετε δεδομένα απευθείας σε κελιά.

`IChartDataWorkbook` είναι ένα ελαφρύ, ενσωματωμένο φύλλο υπολογισμού που το Aspose.Slides χρησιμοποιεί για την τροφοδοσία σειρών και κατηγοριών διαγράμματος.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Ο κώδικας διαγράφει τυχόν υπάρχοντα κελιά, προετοιμάζοντας το βιβλίο εργασίας για νέες εγγραφές.

### Χαρακτηριστικό 5: προσθήκη κατηγοριών σε διάγραμμα (H2)

#### Επισκόπηση
Ορίστε τις ετικέτες κειμένου που εμφανίζονται στην αριστερή πλευρά του χωνιού —αντιπροσωπεύουν κάθε στάδιο της διαδικασίας σας.

`chart.getChartData().getCategories().add()` δημιουργεί ένα νέο αντικείμενο κατηγορίας συνδεδεμένο με συγκεκριμένο κελί του βιβλίου εργασίας.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Εδώ προσθέτουμε τρία στάδια: “Prospects”, “Qualified Leads”, και “Closed Deals”.

### Χαρακτηριστικό 6: προσθήκη σειράς δεδομένων σε διάγραμμα (H2)

#### Επισκόπηση
Γεμίστε το χωνιό με αριθμητικές τιμές και προαιρετικά εκχωρήστε μοναδικό χρώμα σε κάθε τμήμα.

`IDataPoint` αντιπροσωπεύει ένα μεμονωμένο σημείο δεδομένων μέσα σε μια σειρά διαγράμματος.  

`chart.getChartData().getSeries().add()` δημιουργεί μια σειρά που κρατά τα αριθμητικά σημεία δεδομένων· κάθε `IDataPoint` μπορεί να λάβει το δικό του χρώμα γεμίσματος.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Ο βρόχος δείχνει πώς να ορίσετε συμπαγές γέμισμα για κάθε σημείο, χρησιμοποιώντας είτε σταθερές χρωμάτων `java.awt.Color` του brand είτε τυχαία χρώματα για οπτική ποικιλία.

## Συνηθισμένες περιπτώσεις χρήσης & συμβουλές (H2)

- **Αναφορά αλυσίδας πωλήσεων** – Δείξτε πόσες επαφές προχωρούν από προοπτική σε κλειστό‑κερδισμένο σε κάθε στάδιο.  
- **Ανάλυση αποδοτικότητας διαδικασίας** – Οπτικοποιήστε απώλειες υλικού ή καθυστερήσεις χρόνου μεταξύ βημάτων παραγωγής.  
- **Ανασκόπηση marketing funnel** – Συγκρίνετε τα ποσοστά μετατροπής μεταξύ καμπανιών ή πηγών κίνησης.  

**Pro tip:** Αντί για τυχαία χρώματα, χρησιμοποιήστε την παλέτα του brand σας (π.χ., `new Color(0, 112, 192)`) για να διατηρήσετε τη παρουσίαση συνεπή με άλλα marketing assets.

## Συχνές ερωτήσεις (H2)

**Q: Πώς αλλάζω τον προσανατολισμό του διαγράμματος χωνιού;**  
A: Ορίστε την ιδιότητα `ChartOrientation` στο αντικείμενο `IChart` σε `ChartOrientation.Vertical` ή `ChartOrientation.Horizontal`.

**Q: Μπορώ να εξάγω τη διαφάνεια ως εικόνα μετά την προσθήκη του διαγράμματος;**  
A: Ναι—καλέστε `pres.getSlides().get_Item(0).getThumbnail(1, 1)` και γράψτε το προκύπτον `java.awt.image.BufferedImage` σε αρχείο PNG ή JPEG.

**Q: Τι γίνεται αν χρειαστώ περισσότερες από τρεις κατηγορίες;**  
A: Απλώς προσθέστε επιπλέον κατηγορίες χρησιμοποιώντας `chart.getChartData().getCategories().add(...)` και παρέχετε αντίστοιχα σημεία δεδομένων για κάθε νέα κατηγορία.

**Q: Υπάρχει τρόπος να κρύψω το υπόμνημα (legend);**  
A: Χρησιμοποιήστε `chart.getChartTitle().setVisible(false)` και `chart.getLegend().setVisible(false)` για να αφαιρέσετε τόσο τον τίτλο όσο και το υπόμνημα από το οπτικό στοιχείο.

**Q: Χρειάζομαι άδεια για εκδόσεις ανάπτυξης;**  
A: Μια προσωρινή άδεια είναι επαρκής για αξιολόγηση· μια πλήρης εμπορική άδεια απαιτείται για παραγωγικές εγκαταστάσεις.

---

**Τελευταία ενημέρωση:** 2026-09-02  
**Δοκιμή με:** Aspose.Slides for Java 25.4 (jdk16)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να προσθέσετε διάγραμμα σε PowerPoint χρησιμοποιώντας Aspose.Slides for Java: Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Πώς να επεξεργαστείτε δεδομένα διαγράμματος PowerPoint χρησιμοποιώντας Aspose.Slides for Java: Αναλυτικός οδηγός](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Προσθήκη animation σε διάγραμμα PowerPoint χρησιμοποιώντας Aspose.Slides for Java – Οδηγός βήμα‑βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}