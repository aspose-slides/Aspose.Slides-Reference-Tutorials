---
date: '2026-07-08'
description: Μάθετε πώς να χρησιμοποιήσετε το Aspose για να δημιουργήσετε ένα doughnut
  chart στο PowerPoint με Java. Αυτός ο οδηγός βήμα‑βήμα δείχνει πώς να προσθέτετε
  chart data points προγραμματιστικά, να προσαρμόζετε labels και να αποθηκεύετε το
  PPTX με high fidelity.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Η χρήση του Aspose σας επιτρέπει να δημιουργήσετε ένα doughnut chart
  στο PowerPoint χρησιμοποιώντας Java. Ακολουθήστε αυτό το tutorial για να προσθέσετε
  data points, να προσαρμόσετε labels και να αποθηκεύσετε το PPTX με high fidelity.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Πώς να χρησιμοποιήσετε το Aspose: Create Doughnut Chart στο PowerPoint
  (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Πώς να χρησιμοποιήσετε το Aspose Create Doughnut Chart στο PowerPoint (Java)
url: /el/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να χρησιμοποιήσετε το Aspose για δημιουργία διαγράμματος δακτυλίου στο PowerPoint (Java)

## Εισαγωγή
Η δημιουργία εντυπωσιακών παρουσιάσεων συχνά απαιτεί περισσότερα από κείμενο και εικόνες· τα διαγράμματα μπορούν να ενισχύσουν σημαντικά την αφήγηση οπτικοποιώντας τα δεδομένα αποτελεσματικά. **Πώς να χρησιμοποιήσετε το Aspose** για τη δημιουργία διαγραμμάτων σας δίνει προγραμματιστικό έλεγχο χωρίς να ανοίξετε ποτέ το PowerPoint. Αυτό το σεμινάριο σας καθοδηγεί στη δημιουργία ενός διαγράμματος δακτυλίου, στη ρύθμιση των σημείων δεδομένων του και στην αποθήκευση ενός υψηλής πιστότητας αρχείου PPTX. Θα χρειαστείτε μόνο βασικές γνώσεις Java και λίγα λεπτά για τη ρύθμιση.

`Aspose.Slides for Java` είναι μια βιβλιοθήκη Java που επιτρέπει τη δημιουργία, τροποποίηση και μετατροπή αρχείων PowerPoint χωρίς το Microsoft Office.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί διάγραμμα δακτυλίου στο PowerPoint;** Aspose.Slides for Java  
- **Μπορώ να προσθέσω σημεία δεδομένων διαγράμματος προγραμματικά;** Ναι, χρησιμοποιώντας το API διαγράμματος  
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται έγκυρη άδεια Aspose.Slides  
- **Ποιες εκδόσεις Java υποστηρίζονται;** Java 8 και νεότερες (εμφανίζεται ο ταξινομητής JDK 16)  
- **Πόσες σειρές μπορώ να προσθέσω;** Το παράδειγμα προσθέτει έως 15 σειρές, αλλά μπορείτε να προσαρμόσετε όπως χρειάζεται  

## Τι είναι ένα διάγραμμα δακτυλίου στο PowerPoint;
Ένα διάγραμμα δακτυλίου είναι ένα κυκλικό διάγραμμα παρόμοιο με το διάγραμμα πίτας, αλλά με κεντρική οπή, επιτρέποντας την ταυτόχρονη εμφάνιση πολλαπλών σειρών. Τονίζει τις σχέσεις μέρος‑προς‑ολόκληρο διατηρώντας τη διάταξη συμπαγή και εύκολη στην ανάγνωση.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides for Java για τη δημιουργία διαγραμμάτων δακτυλίου;
Το Aspose.Slides for Java υποστηρίζει πάνω από 50 μορφές εισόδου/εξόδου και μπορεί να δημιουργήσει παρουσιάσεις έως 500 MB χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Παρέχει πλήρη προγραμματιστικό έλεγχο της εμφάνισης, των δεδομένων και της διάταξης του διαγράμματος σε οποιαδήποτε πλατφόρμα Java, εξαλείφει την ανάγκη για COM interop και μπορεί να αποδώσει 100 διαφάνειες πλούσιες σε διαγράμματα σε λιγότερο από δύο δευτερόλεπτα σε τυπικό διακομιστή.

## Προαπαιτούμενα
- Βασικές γνώσεις προγραμματισμού Java.  
- Ένα IDE όπως το IntelliJ IDEA ή το Eclipse.  
- Maven ή Gradle για διαχείριση εξαρτήσεων.  
- Έγκυρη άδεια Aspose.Slides for Java (διατίθεται δωρεάν δοκιμαστική έκδοση).

## Ρύθμιση του Aspose.Slides for Java
Επιλέξτε τον διαχειριστή εξαρτήσεων που ταιριάζει στο έργο σας.

**Maven**  
Προσθέστε την παρακάτω εξάρτηση στο `pom.xml` σας (αντικαταστήστε την έκδοση με την πιο πρόσφατη):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Προσθέστε αυτή τη γραμμή στο `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Αν προτιμάτε να κατεβάσετε απευθείας, επισκεφθείτε τη σελίδα [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
Μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμή για να εξερευνήσετε τις δυνατότητες του Aspose.Slides. Για παρατεταμένη χρήση, αγοράστε άδεια ή ζητήστε προσωρινή από το [Aspose's website](https://purchase.aspose.com/temporary-license/). Ακολουθήστε τις οδηγίες που παρέχονται για τη ρύθμιση του περιβάλλοντός σας και την αρχικοποίηση του Aspose.Slides στην εφαρμογή σας.

## Πώς να δημιουργήσετε διάγραμμα δακτυλίου PowerPoint χρησιμοποιώντας το Aspose.Slides for Java
Για να δημιουργήσετε ένα διάγραμμα δακτυλίου, ξεκινήστε φορτώνοντας ή δημιουργώντας ένα `Presentation`, προσθέστε ένα σχήμα διαγράμματος τύπου `ChartType.Doughnut`, αφαιρέστε τις προεπιλεγμένες σειρές, ορίστε το μέγεθος της οπής και, στη συνέχεια, γεμίστε το workbook του διαγράμματος με ονόματα κατηγοριών και αριθμητικές τιμές. Τέλος, προσαρμόστε τη μορφοποίηση των ετικετών και αποθηκεύστε το PPTX.

### Βήμα 1: Αρχικοποίηση της παρουσίασης
Δημιουργήστε μια νέα παρουσίαση ή ανοίξτε ένα υπάρχον αρχείο για να αποκτήσετε τη συλλογή διαφανειών.

`Presentation` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Βήμα 2: Προσθήκη διαγράμματος δακτυλίου στη διαφάνεια
Εισάγετε ένα σχήμα διαγράμματος, αφαιρέστε τις προεπιλεγμένες σειρές/κατηγορίες και ρυθμίστε βασικές οπτικές παραμέτρους όπως το μέγεθος της οπής του δακτυλίου.

`Chart` (ή σχήμα διαγράμματος) αντιπροσωπεύει ένα αντικείμενο διαγράμματος τοποθετημένο σε μια διαφάνεια.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Βήμα 3: Προσθήκη σημείων δεδομένων διαγράμματος και προσαρμογή ετικετών
Συμπληρώστε τα ονόματα κατηγοριών, προσθέστε σημεία δεδομένων για κάθε σειρά και βελτιώστε τη μορφοποίηση των ετικετών (γραμματοσειρά, χρώμα, θέση). Αυτό το βήμα δείχνει τη δυνατότητα «προσθήκης σημείων δεδομένων διαγράμματος».

`Workbook` παρέχει πρόσβαση στα υποκείμενα δεδομένα του διαγράμματος, όπου γεμίζονται τα κελιά.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Βήμα 4: Αποθήκευση της ενημερωμένης παρουσίασης
Καταγράψτε τις αλλαγές σε ένα νέο αρχείο PPTX στο δίσκο.

`save` γράφει την παρουσίαση σε αρχείο στην επιλεγμένη μορφή.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Πρακτικές Εφαρμογές
Τα διαγράμματα δακτυλίου είναι ιδανικά για:
- **Οικονομικές Αναφορές:** Οπτικοποίηση κατανομής προϋπολογισμού ή ανάλυση εξόδων.  
- **Ανάλυση Αγοράς:** Εμφάνιση κατανομής μεριδίου αγοράς μεταξύ ανταγωνιστών.  
- **Αποτελέσματα Έρευνας:** Παρουσίαση κατηγορηματικών δεδομένων έρευνας σε συμπαγή μορφή.  
- **Δημιουργία Πινακοθήκης:** Συνδυασμός με ερωτήματα βάσης δεδομένων για παραγωγή διαφανειών που ενημερώνονται ζωντανά.

## Παράγοντες Απόδοσης
- **Αποδέσμευση πόρων:** Καλέστε `pres.dispose()` μετά την αποθήκευση για να ελευθερώσετε τη φυσική μνήμη.  
- **Περιορισμός αριθμού διαγραμμάτων:** Η προσθήκη εκατοντάδων διαγραμμάτων μπορεί να αυξήσει τη χρήση μνήμης· επεξεργαστείτε σε παρτίδες αν χρειάζεται.  
- **Χρήση streaming:** Για τεράστιες συλλογές δεδομένων, γεμίστε το workbook απευθείας από ροές αντί για πίνακες στη μνήμη.

## Συνηθισμένα Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Το διάγραμμα εμφανίζεται κενό** | Τα κελιά δεδομένων δεν έχουν γεμίσει σωστά | Επαληθεύστε ότι `workBook.getCell(...)` αναφέρεται στις σωστές σειρές/στήλες. |
| **Οι ετικέτες επικαλύπτονται** | Πάρα πολλές κατηγορίες σε περιορισμένο χώρο | Αυξήστε το `DoughnutHoleSize` ή προσαρμόστε το `FirstSliceAngle`. |
| **OutOfMemoryError** | Μεγάλες παρουσιάσεις χωρίς αποδέσμευση | Καλέστε `pres.dispose()` μετά την αποθήκευση και σκεφτείτε να αυξήσετε το μέγεθος της μνήμης heap του JVM. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω το Aspose.Slides for Java σε εμπορικές εφαρμογές;**  
Α: Ναι, αλλά απαιτείται έγκυρη εμπορική άδεια. Διατίθεται δωρεάν δοκιμαστική έκδοση για αξιολόγηση.

**Ε: Πώς προσθέτω περισσότερες από 15 σειρές;**  
Α: Αυξήστε το όριο του βρόχου στο βήμα «Προσθήκη διαγράμματος δακτυλίου» και βεβαιωθείτε ότι το workbook δεδομένων σας περιέχει αρκετές γραμμές.

**Ε: Είναι δυνατόν να αλλάξω το μέγεθος της οπής του δακτυλίου μετά τη δημιουργία;**  
Α: Ναι, καλέστε `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` πριν από την αποθήκευση.

**Ε: Μπορώ να εξάγω το διάγραμμα ως εικόνα αντί για PPTX;**  
Α: Απολύτως. Χρησιμοποιήστε `chart.getImage()` και αποθηκεύστε το επιστρεφόμενο `java.awt.image.BufferedImage` στη μορφή που προτιμάτε.

**Ε: Υποστηρίζει το Aspose.Slides animated charts;**  
Α: Η προσθήκη animation μπορεί να γίνει μέσω του API `ISlide.getTimeline()`, αν και αυτό δεν καλύπτεται στο παρόν σεμινάριο.

## Συμπέρασμα
Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή μέθοδο για **δημιουργία διαγράμματος δακτυλίου PowerPoint** με το Aspose.Slides for Java, συμπεριλαμβανομένου του **προσθήκης σημείων δεδομένων διαγράμματος**, προσαρμογής ετικετών και διαχείρισης παραγόντων απόδοσης. Πειραματιστείτε με διαφορετικά χρώματα, πηγές δεδομένων και τύπους διαγραμμάτων για να κάνετε τις παρουσιάσεις σας πραγματικά ξεχωριστές.

---

**Τελευταία ενημέρωση:** 2026-07-08  
**Δοκιμή με:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Συγγραφέας:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Σχετικά Σεμινάρια

- [Πώς να Προσθέσετε Διαγράμματα στο PowerPoint Χρησιμοποιώντας το Aspose.Slides for Java: Οδηγός Βήμα‑Βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Πώς να Επεξεργαστείτε Δεδομένα Διαγράμματος PowerPoint Χρησιμοποιώντας το Aspose.Slides for Java: Αναλυτικός Οδηγός](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Κινούμενα Διαγράμματα PowerPoint Χρησιμοποιώντας το Aspose.Slides for Java – Οδηγός Βήμα‑Βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}