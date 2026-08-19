---
date: '2026-07-17'
description: Μάθετε πώς να προσθέσετε Sunburst Charts στο PowerPoint χρησιμοποιώντας
  Aspose Slides για Java. Ο οδηγός βήμα‑βήμα καλύπτει τη ρύθμιση, τη δημιουργία γραφήματος,
  την προσαρμογή και τις πραγματικές περιπτώσεις χρήσης.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Πώς να προσθέσετε Sunburst Charts στο PowerPoint χρησιμοποιώντας Aspose
  Slides για Java. Ακολουθήστε αυτό το tutorial για να ρυθμίσετε τη βιβλιοθήκη, να
  δημιουργήσετε ένα γράφημα, να προσαρμόσετε τα δεδομένα και να το εφαρμόσετε σε πραγματικά
  έργα.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Πώς να προσθέσετε Sunburst Charts στο PowerPoint με Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Πώς να προσθέσετε Sunburst Charts στο PowerPoint με Aspose (Java)
url: /el/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να Προσθέσετε Διαγράμματα Sunburst στο PowerPoint με το Aspose (Java)

## Εισαγωγή

Η προσθήκη ενός διαγράμματος sunburst σε μια παρουσίαση PowerPoint μπορεί αμέσως να μετατρέψει έναν επίπεδο πίνακα δεδομένων σε μια ελκυστική οπτική ιεραρχία. Σε αυτό το tutorial θα μάθετε **πώς να προσθέσετε sunburst** διαγράμματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides for Java, από τη ρύθμιση του περιβάλλοντος μέχρι την λεπτομερή ρύθμιση χρωμάτων και ετικετών. Είτε δημιουργείτε έναν πίνακα ελέγχου πωλήσεων, μια διάσπαση έργου‑εργασιών, ή μια εκπαιδευτική παρουσίαση, τα παρακάτω βήματα θα σας δώσουν μια λύση έτοιμη για παραγωγή.

**Τι Θα Μάθετε**
- Πώς να διαμορφώσετε το Aspose.Slides σε έργο Maven ή Gradle  
- Πώς να δημιουργήσετε μια νέα παρουσίαση και να εισάγετε ένα διάγραμμα sunburst  
- Πώς να προσαρμόσετε τα σημεία δεδομένων, τις ετικέτες και τα χρώματα γεμίσματος  
- Πραγματικά σενάρια όπου τα διαγράμματα sunburst ξεχωρίζουν  

Ας ξεκινήσουμε και ας δούμε πόσο εύκολο είναι να μετατρέψετε ακατέργαστα ιεραρχικά δεδομένα σε ένα επεξεργασμένο οπτικό στοιχείο PowerPoint.

## Γρήγορες Απαντήσεις
- **Βασική βιβλιοθήκη;** Aspose.Slides for Java  
- **Υποστηριζόμενος τύπος διαγράμματος;** Sunburst (radial hierarchical)  
- **Ελάχιστη έκδοση Java;** JDK 16  
- **Τυπικός χρόνος υλοποίησης;** 10‑15 λεπτά για ένα βασικό διάγραμμα  
- **Απαιτείται άδεια για παραγωγή;** Yes, a valid Aspose license  

## Τι είναι το Διάγραμμα Sunburst;
Ένα διάγραμμα sunburst είναι ένα ακτινικό διάγραμμα που οπτικοποιεί ιεραρχικά δεδομένα ενσωματώνοντας δακτυλίους από ένα κεντρικό σημείο προς τα έξω. Είναι ιδανικό για την απεικόνιση πολυεπίπεδων σχέσεων όπως δομές οργανισμών, κατηγορίες προϊόντων ή δέντρα συστήματος αρχείων. Κάθε συγκεντρικός δακτύλιος αντιπροσωπεύει ένα επίπεδο της ιεραρχίας, και το μέγεθος κάθε τμήματος αντανακλά την ποσοτική του αξία, επιτρέποντας στους θεατές να κατανοήσουν γρήγορα τόσο τη δομή όσο και το μέγεθος.

## Γιατί να Χρησιμοποιήσετε το Aspose.Slides για Java;
Το Aspose.Slides υποστηρίζει **50+ τύπους διαγραμμάτων** και μπορεί να χειριστεί παρουσιάσεις με **έως 10.000 διαφάνειες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας υψηλή απόδοση για επιχειρηματική αναφορά σε κλίμακα. Λειτουργεί δια-πλατφόρμα, προσφέρει εκτενή κάλυψη API και περιλαμβάνει ισχυρές επιλογές αδειοδότησης που αφαιρούν τους περιορισμούς αξιολόγησης, καθιστώντας το ιδανικό για περιβάλλοντα παραγωγής.

## Προαπαιτούμενα
- **Java Development Kit (JDK)** 16 ή νεότερο  
- **IDE** – IntelliJ IDEA, Eclipse ή οποιονδήποτε Java‑compatible editor  
- Βασική εξοικείωση με τη σύνταξη Java και τα εργαλεία κατασκευής Maven/Gradle  

## Ρύθμιση του Aspose.Slides για Java

### Εξάρτηση Maven
Προσθέστε το Maven artifact του Aspose.Slides στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Εξάρτηση Gradle
Αν προτιμάτε Gradle, συμπεριλάβετε την παρακάτω γραμμή στο `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση Λήψη
Μπορείτε επίσης να κατεβάσετε το τελευταίο JAR απευθείας από τη σελίδα των επίσημων εκδόσεων: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
Για να λειτουργήσετε χωρίς περιορισμούς αξιολόγησης, αποκτήστε άδεια:
- **Δωρεάν δοκιμή** – προσωρινή άδεια για γρήγορη αξιολόγηση.  
- **Προσωρινή άδεια** – ζητήστε μία από το [Aspose website](https://purchase.aspose.com/temporary-license).  
- **Πλήρης αγορά** – αγοράστε συνδρομή για απεριόριστη χρήση σε παραγωγή.

### Βασική Αρχικοποίηση
Η κλάση `Presentation` είναι το σημείο εισόδου για τη δημιουργία ή το άνοιγμα αρχείων PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Οδηγός Υλοποίησης

### Πώς να προσθέσετε ένα διάγραμμα sunburst σε παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java;
Φορτώστε μια νέα `Presentation`, προσθέστε μια διαφάνεια, εισάγετε ένα `IChart` τύπου `ChartType.Sunburst`, και καλέστε `save`. Αυτό το σύντομο μοτίβο τριών βημάτων δημιουργεί ένα πλήρως λειτουργικό διάγραμμα sunburst έτοιμο για περαιτέρω προσαρμογές.

#### Βήμα 1: Αρχικοποίηση της Παρουσίασης
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Βήμα 2: Προσθήκη Διαγράμματος Sunburst
Η διεπαφή `IChart` ορίζει ένα αντικείμενο διαγράμματος που μπορεί να τοποθετηθεί σε οποιαδήποτε διαφάνεια. Εδώ προσθέτουμε ένα διάγραμμα sunburst στις συντεταγμένες (100, 100) με μέγεθος 450 × 400 points.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Βήμα 3: Αποθήκευση της Παρουσίασης
Πάντα αποθηκεύετε τις αλλαγές καλώντας `save`. Μπορείτε να επιλέξετε PPTX, PDF ή οποιαδήποτε από τις 50+ υποστηριζόμενες μορφές εξόδου.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Τροποποίηση Σημείων Δεδομένων στο Διάγραμμα

#### Επισκόπηση
Μπορείτε να προσαρμόσετε κάθε τμήμα του sunburst—ετικέτες, χρώματα και ορατότητα—μέσω της συλλογής σημείων δεδομένων του διαγράμματος.

#### Βήμα 1: Πρόσβαση στη Συλλογή Σημείων Δεδομένων
Η πρώτη σειρά του διαγράμματος περιέχει μια συλλογή αντικειμένων `IChartDataPoint` που αντιπροσωπεύουν κάθε τμήμα.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Βήμα 2: Εμφάνιση Τιμής για Συγκεκριμένο Σημείο Δεδομένων
Ορίστε `IsValueShown` σε `true` στο επιθυμητό σημείο δεδομένων για να εμφανιστεί η αριθμητική του τιμή απευθείας στο τμήμα.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Βήμα 3: Τροποποίηση Μορφών Ετικετών
Ρυθμίστε την ορατότητα της ετικέτας, το χρώμα γραμματοσειράς και το φόντο για βελτίωση της αναγνωσιμότητας.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Βήμα 4: Ορισμός Χρώματος Γέμισης για Σημεία Δεδομένων
Προσαρμόστε το χρώμα γεμίσματος των μεμονωμένων τμημάτων ώστε να ταιριάζει με την παλέτα της εταιρείας σας ή για να τονίσετε σημαντικά τμήματα.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Βήμα 5: Αποθήκευση της Τροποποιημένης Παρουσίασης
Αποθηκεύστε το προσαρμοσμένο διάγραμμα αποθηκεύοντας ξανά την παρουσίαση.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Πρακτικές Εφαρμογές

1. **Business Analytics** – Οπτικοποίηση πωλήσεων ανά περιοχή → γραμμή προϊόντος → SKU σε μια ενιαία ακτινική προβολή.  
2. **Project Management** – Εμφάνιση δομών διάσπασης εργασίας, από φάσεις σε εργασίες σε υποεργασίες.  
3. **Education** – Χαρτογράφηση ιεραρχιών προγράμματος σπουδών, όπως τμήματα → μαθήματα → ενότητες.  

## Σκέψεις Απόδοσης

- **Memory Efficiency:** Το Aspose.Slides ρέει δεδομένα, έτσι ακόμη και ένα σετ 500‑page με πολλαπλά διαγράμματα παραμένει κάτω από 200 MB RAM.  
- **Garbage Collection:** Απελευθερώστε αντικείμενα διαφάνειας (`slide.dispose()`) όταν δεν χρειάζονται πια για αποφυγή διαρροών μνήμης.  

## Συχνές Ερωτήσεις

**Q: Τι είναι ένα διάγραμμα sunburst;**  
A: Ένα διάγραμμα sunburst οπτικοποιεί ιεραρχικά δεδομένα σε συγκεντρικούς δακτυλίους, με κάθε δακτύλιο να αντιπροσωπεύει ένα επίπεδο της ιεραρχίας.

**Q: Πώς εγκαθιστώ το Aspose.Slides για Java χρησιμοποιώντας Maven;**  
A: Προσθέστε την εξάρτηση Maven που φαίνεται στην ενότητα “Εξάρτηση Maven” στο `pom.xml` και εκτελέστε `mvn clean install`.

**Q: Μπορώ να προσαρμόσω άλλους τύπους διαγραμμάτων με το Aspose.Slides;**  
A: Ναι, η βιβλιοθήκη υποστηρίζει πάνω από 50 τύπους διαγραμμάτων, συμπεριλαμβανομένων των column, line, pie και radar διαγραμμάτων.

**Q: Η παρουσίασή μου δεν αποθηκεύεται—τι πρέπει να ελέγξω;**  
A: Επαληθεύστε ότι η διαδρομή αρχείου είναι σωστή, ότι ο φάκελος υπάρχει και ότι έχετε δικαιώματα εγγραφής. Επίσης, βεβαιωθείτε ότι καλείται η μέθοδος `Presentation.save()`.

**Q: Πού μπορώ να βρω περισσότερη βοήθεια ή παραδείγματα;**  
A: Επισκεφθείτε το [Aspose forum](https://forum.aspose.com/c/slides/11) ή συμβουλευτείτε την επίσημη [Aspose.Slides reference](https://reference.aspose.com/slides/java/).

## Πόροι
- **Τεκμηρίωση:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Αναφορά (lowercase):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Φόρουμ Κοινότητας:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Λήψεις:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Τελευταία Ενημέρωση:** 2026-07-17  
**Δοκιμάστηκε Με:** Aspose.Slides for Java 24.12  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Προσθέσετε Διαγράμματα σε PowerPoint Χρησιμοποιώντας το Aspose.Slides για Java: Οδηγός Βήμα‑Βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Κινούμενα Διαγράμματα PowerPoint Χρησιμοποιώντας το Aspose.Slides για Java – Οδηγός Βήμα‑Βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Δημιουργία διαγράμματος σε Java με Aspose.Slides – Προσθήκη & Επαλήθευση Διαγραμμάτων](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}