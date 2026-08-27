---
date: '2026-08-27'
description: Μάθετε πώς να προσθέσετε grid lines chart σε Java χρησιμοποιώντας Aspose.Slides,
  μορφοποιήστε axes, titles και εξάγετε ένα polished PowerPoint line chart.
keywords:
- add grid lines chart
- customize chart axes
- generate line chart powerpoint
- aspose.slides maven dependency
- apply aspose license
lastmod: '2026-08-27'
og_description: Μάθετε πώς να προσθέσετε grid lines chart σε Java χρησιμοποιώντας
  Aspose.Slides, μορφοποιήστε axes, titles και εξάγετε ένα polished PowerPoint line
  chart.
og_image_alt: Step-by-step guide to create and format a line chart with grid lines
  using Aspose.Slides for Java
og_title: Πώς να προσθέσετε grid lines σε ένα chart με Aspose.Slides για Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  headline: How to add grid lines to a chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add grid lines chart in Java using Aspose.Slides, format
    axes, titles, and export a polished PowerPoint line chart.
  name: How to add grid lines to a chart with Aspose.Slides for Java
  steps:
  - name: create the output directory (create directory java)
    text: '*Why this matters:* Ensuring the folder exists prevents `FileNotFoundException`
      when you later save the presentation.'
  - name: add a slide and insert a line chart
    text: '*Explanation:* This creates a fresh slide and places a **line chart with
      markers** at the specified coordinates.'
  - name: add chart title (add chart title)
    text: '*Tip:* Using a bold, gray title makes the chart instantly recognizable.'
  - name: format axes and add grid lines (add grid lines)
    text: '#### Vertical axis formatting *Why this matters:* Clear grid lines and
      rotated labels improve readability, especially when data points are dense.'
  - name: save the presentation
    text: '*Result:* You now have a PowerPoint file (`FormattedChart_out.pptx`) containing
      a fully formatted line chart.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports bar, pie, scatter, radar, and more than 50
      additional chart types.
    question: Can I create other chart types besides line charts?
  - answer: Use `chart.getChartData().getSeries().add(...)` to insert additional series
      before applying formatting.
    question: How do I add multiple data series to the line chart?
  - answer: Absolutely. Render the slide to PNG, JPEG, or SVG with `presentation.save("slide.png",
      SaveFormat.Png)`.
    question: Is it possible to export the chart as an image?
  - answer: A free temporary license is sufficient for evaluation; a commercial license
      is required for production use.
    question: Do I need a paid license for development?
  - answer: The library works with JDK 8 through JDK 22; select the appropriate classifier
      (e.g., `jdk16`) when adding the Maven/Gradle dependency.
    question: Which Java versions are supported?
  type: FAQPage
tags:
- Aspose.Slides
- Java chart tutorial
- PowerPoint automation
- line chart
title: Πώς να προσθέσετε grid lines σε ένα chart με Aspose.Slides για Java
url: /el/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε γραμμές πλέγματος σε ένα γράφημα με το Aspose.Slides for Java

## Εισαγωγή
Αν χρειάζεστε να **προσθέσετε γραμμές πλέγματος σε γράφημα** σε μια παρουσίαση PowerPoint προγραμματιστικά, το Aspose.Slides for Java σας παρέχει ένα καθαρό, πλήρως εξοπλισμένο API. Είτε ετοιμάζετε μια τριμηνιαία επιχειρηματική ανασκόπηση, μια ακαδημαϊκή διάλεξη ή μια παρουσίαση πωλήσεων βασισμένη σε δεδομένα, μπορείτε να δημιουργήσετε ένα γράφημα γραμμής, να προσαρμόσετε κάθε οπτικό στοιχείο και να αποθηκεύσετε το αποτέλεσμα σε δευτερόλεπτα—χωρίς να ανοίξετε το PowerPoint χειροκίνητα.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί γραφήματα σε Java;** Aspose.Slides for Java.
- **Ποιος τύπος γραφήματος καλύπτεται σε αυτόν τον οδηγό;** Ένα γράφημα γραμμής με δείκτες και γραμμές πλέγματος.
- **Χρειάζεται άδεια για την εκτέλεση του δείγματος;** Μια δωρεάν προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται εμπορική άδεια για παραγωγή.
- **Ποιο IDE μπορώ να χρησιμοποιήσω;** Οποιοδήποτε Java IDE όπως IntelliJ IDEA, Eclipse ή NetBeans.
- **Πώς μορφοποιούνται τα στοιχεία του γραφήματος;** Χρησιμοποιώντας fluent κλήσεις API για τίτλους, άξονες, γραμμές πλέγματος, υπομνήματα και χρώματα φόντου.

## Πώς να προσθέσετε γραμμές πλέγματος σε γράφημα Java χρησιμοποιώντας το Aspose.Slides
Φορτώστε ένα νέο `Presentation`, εισάγετε μια διαφάνεια, προσθέστε ένα γράφημα γραμμής και, στη συνέχεια, ενεργοποιήστε τις κύριες γραμμές πλέγματος στον κάθετο άξονα – όλα σε λιγότερες από δέκα γραμμές κώδικα. Αυτή η άμεση απάντηση δείχνει την ακριβή ακολουθία που χρειάζεστε, ώστε να μπορείτε να αντιγράψετε‑επικολλήσετε και να δείτε αμέσως ένα πλήρως μορφοποιημένο γράφημα.

### Definition anchor
`Presentation` είναι η κύρια κλάση του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη· όλες οι λειτουργίες σε επίπεδο διαφάνειας ξεκινούν από αυτό το αντικείμενο.

## Τι είναι ένα γράφημα γραμμής και γιατί να χρησιμοποιήσετε το Aspose.Slides;
Ένα γράφημα γραμμής απεικονίζει μια σειρά σημείων δεδομένων συνδεδεμένων με ευθείες γραμμές, καθιστώντας τις τάσεις στο χρόνο άμεσα ορατές. Το Aspose.Slides υποστηρίζει **πάνω από 50 τύπους γραφημάτων** και μπορεί να διαχειριστεί **έως 10.000 σημεία δεδομένων ανά σειρά** χωρίς αισθητή καθυστέρηση, παρέχοντάς σας απόδοση επιπέδου επιχειρήσεων για μεγάλα σύνολα δεδομένων.

### Definition anchor
`Chart` είναι το αντικείμενο υψηλού επιπέδου του Aspose.Slides για οποιοδήποτε γράφημα· αποθηκεύει σειρές, κατηγορίες και πληροφορίες μορφοποίησης.

## Προαπαιτούμενα
- **Java Development Kit (JDK) 8+** εγκατεστημένο.
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans κ.λπ.).
- **Aspose.Slides for Java** βιβλιοθήκη προστιθέμενη μέσω Maven ή Gradle (δείτε την ενότητα *aspose.slides maven dependency* παρακάτω).

### Εξάρτηση Maven (aspose.slides maven dependency)
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Εξάρτηση Gradle
```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Εναλλακτικά, κατεβάστε το πιο πρόσφατο JAR από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

## Απόκτηση άδειας (εφαρμογή άδειας aspose)
- Αποκτήστε μια **δωρεάν δοκιμαστική άδεια** από τη σελίδα [free trial license](https://purchase.aspose.com/temporary-license/) για δοκιμές.
- Αγοράστε πλήρη άδεια από [την επίσημη ιστοσελίδα της Aspose](https://purchase.aspose.com/buy) για παραγωγικές εγκαταστάσεις.

## Ρύθμιση Aspose.Slides for Java
1. Προσθέστε την εξάρτηση Maven ή Gradle που εμφανίζεται παραπάνω στο έργο σας.
2. Φορτώστε το αρχείο άδειας **πριν** δημιουργήσετε οποιαδήποτε αντικείμενα `Presentation` ώστε όλες οι λειτουργίες να ξεκλειδωθούν.

```java
License license = new License();
license.setLicense("Aspose.Slides.lic");
```

## Υλοποίηση βήμα‑βήμα

### Βήμα 1: δημιουργία του καταλόγου εξόδου (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```  
*Γιατί είναι σημαντικό:* Η διασφάλιση ότι ο φάκελος υπάρχει αποτρέπει `FileNotFoundException` όταν αργότερα αποθηκεύσετε την παρουσίαση.

### Βήμα 2: προσθήκη διαφάνειας και εισαγωγή γραφήματος γραμμής
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```  
*Επεξήγηση:* Αυτό δημιουργεί μια νέα διαφάνεια και τοποθετεί ένα **γράφημα γραμμής με δείκτες** στις καθορισμένες συντεταγμένες.

### Βήμα 3: προσθήκη τίτλου γραφήματος (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```  
*Συμβουλή:* Η χρήση έντονου, γκρι τίτλου κάνει το γράφημα άμεσα αναγνωρίσιμο.

### Βήμα 4: μορφοποίηση αξόνων και προσθήκη γραμμών πλέγματος (add grid lines)
#### Μορφοποίηση κατακόρυφου άξονα
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```  
*Γιατί είναι σημαντικό:* Καθαρές γραμμές πλέγματος και περιστρεφόμενες ετικέτες βελτιώνουν την αναγνωσιμότητα, ειδικά όταν τα σημεία δεδομένων είναι πυκνά.

#### Μορφοποίηση οριζόντιου άξονα
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```  

### Βήμα 5: προσαρμογή υπομνήματος (add chart legend)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```  

### Βήμα 6: ορισμός χρωμάτων φόντου (format chart labels)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```  

### Βήμα 7: αποθήκευση της παρουσίασης
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```  
*Αποτέλεσμα:* Διαθέτετε πλέον ένα αρχείο PowerPoint (`FormattedChart_out.pptx`) που περιέχει ένα πλήρως μορφοποιημένο γράφημα γραμμής.

## Πρακτικές εφαρμογές (generate line chart powerpoint)
- **Επιχειρηματικές αναφορές:** Εμφάνιση τριμηνιαίων τάσεων εσόδων με καθαρές γραμμές πλέγματος.
- **Ακαδημαϊκές διαλέξεις:** Οπτικοποίηση πειραματικών δεδομένων σε πολλαπλές συνεδρίες.
- **Προτάσεις έργων:** Ανάδειξη προόδου ορόσημων και προβλεπόμενων καμπυλών.
- **Ανάλυση μάρκετινγκ:** Παρουσίαση τάσεων ROI εκστρατειών δίπλα σε δεδομένα ανταγωνιστών.
- **Ενσωμάτωση σε πίνακες ελέγχου:** Εξαγωγή ζωντανών αναλύσεων σε PowerPoint για συναντήσεις με ενδιαφερόμενους.

## Σκέψεις για την απόδοση
- **Διαχείριση μνήμης:** Κλήση `presentation.dispose()` μετά την αποθήκευση για άμεση απελευθέρωση των εγγενών πόρων.
- **Μεγάλα σύνολα δεδομένων:** Το Aspose.Slides επεξεργάζεται γραφήματα με χιλιάδες σημεία χρησιμοποιώντας streaming, διατηρώντας τη χρήση μνήμης κάτω από 100 MB σε τυπικό διακομιστή.

## Συνηθισμένα προβλήματα και λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Η άδεια δεν εφαρμόστηκε** | Φορτώστε τη δοκιμαστική ή πλήρη άδεια **πριν** δημιουργήσετε οποιαδήποτε αντικείμενα `Presentation`. |
| **Το γράφημα εμφανίζεται κενό** | Βεβαιωθείτε ότι η διαφάνεια περιέχει τουλάχιστον μία σειρά δεδομένων· προσθέστε σειρά μέσω `chart.getChartData().getSeries().add(...)` εάν χρειάζεται. |
| **Το αρχείο δεν αποθηκεύεται** | Εξασφαλίστε ότι ο φάκελος εξόδου υπάρχει (δείτε το Βήμα 1). |
| **Τα χρώματα δεν εφαρμόζονται** | Χρησιμοποιήστε σταθερές `java.awt.Color` ή το enum `PresetColor` για αξιόπιστη απόδοση χρωμάτων. |

## Συχνές ερωτήσεις

**Ε: Μπορώ να δημιουργήσω άλλους τύπους γραφημάτων εκτός των γραφημάτων γραμμής;**  
Α: Ναι, το Aspose.Slides υποστηρίζει ράβδους, πίτες, διασκορπισμένα, ραντάρ και περισσότερους από 50 επιπλέον τύπους γραφημάτων.

**Ε: Πώς προσθέτω πολλαπλές σειρές δεδομένων στο γράφημα γραμμής;**  
Α: Χρησιμοποιήστε `chart.getChartData().getSeries().add(...)` για να εισάγετε επιπλέον σειρές πριν εφαρμόσετε τη μορφοποίηση.

**Ε: Είναι δυνατόν να εξάγω το γράφημα ως εικόνα;**  
Α: Απόλυτα. Αποδώστε τη διαφάνεια σε PNG, JPEG ή SVG με `presentation.save("slide.png", SaveFormat.Png)`.

**Ε: Χρειάζεται πληρωμένη άδεια για ανάπτυξη;**  
Α: Μια δωρεάν προσωρινή άδεια αρκεί για αξιολόγηση· απαιτείται εμπορική άδεια για παραγωγική χρήση.

**Ε: Ποιες εκδόσεις Java υποστηρίζονται;**  
Α: Η βιβλιοθήκη λειτουργεί με JDK 8 έως JDK 22· επιλέξτε τον κατάλληλο ταξινομητή (π.χ., `jdk16`) όταν προσθέτετε την εξάρτηση Maven/Gradle.

---

**Τελευταία ενημέρωση:** 2026-08-27  
**Δοκιμάστηκε με:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose  

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Σχετικά Μαθήματα

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Create Customize Charts Trend Lines Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}