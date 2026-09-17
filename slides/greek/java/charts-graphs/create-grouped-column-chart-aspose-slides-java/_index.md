---
date: '2026-09-17'
description: Μάθετε πώς να προσθέσετε clustered column chart σε μια παρουσίαση PowerPoint,
  να προσαρμόσετε το PowerPoint chart και να εισάγετε data series chart χρησιμοποιώντας
  Aspose.Slides for Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Μάθετε πώς να προσθέσετε clustered column chart σε μια παρουσίαση
  PowerPoint χρησιμοποιώντας Aspose.Slides for Java, συμπεριλαμβανομένων των βημάτων
  για την εισαγωγή data series, την customize grouping, και την αποθήκευση του αρχείου
  ως PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Προσθέστε clustered column chart στο PowerPoint χρησιμοποιώντας Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: Πώς να προσθέσετε clustered column chart στο PowerPoint χρησιμοποιώντας Aspose.Slides
  for Java
url: /el/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να προσθέσετε συγκεντρωτικό γράφημα στηλών σε PowerPoint χρησιμοποιώντας Aspose.Slides for Java

## Εισαγωγή

Όταν χρειάζεται να **προσθέσετε συγκεντρωτικό γράφημα στηλών** σε μια παρουσίαση PowerPoint, μια σαφής οπτική μπορεί να μετατρέψει ακατέργαστους αριθμούς σε μια άμεσα κατανοητή ιστορία. Η χειροκίνητη δημιουργία αυτού στο PowerPoint μπορεί να είναι χρονοβόρα, ειδικά όταν πρέπει να δημιουργήσετε πολλές διαφάνειες προγραμματιστικά. **Aspose.Slides for Java** αφαιρεί το εμπόδιο – σας επιτρέπει να δημιουργήσετε, να προσαρμόσετε γραφήματα PowerPoint και να εισάγετε δεδομένα σειράς γραφήματος με μόνο λίγες γραμμές κώδικα.

Σε αυτό το tutorial θα μάθετε πώς να:
- Αρχικοποιήσετε μια νέα παρουσίαση PowerPoint με Aspose.Slides for Java.  
- **Προσθέσετε γράφημα στη διαφάνεια** και το ρυθμίσετε ως συγκεντρωτικό γράφημα στηλών.  
- **Δημιουργήσετε ομαδοποιημένο γράφημα στηλών** ορίζοντας επίπεδα ομαδοποίησης για τις κατηγορίες.  
- **Εισάγετε γράφημα σειράς δεδομένων** ώστε τα δεδομένα σας να εμφανίζονται σωστά.  
- Αποθηκεύσετε την ολοκληρωμένη παρουσίαση ως αρχείο PPTX.

## Γρήγορες απαντήσεις
- **Ποια είναι η κύρια κλάση;** `Presentation` από `com.aspose.slides`.  
- **Ποιος τύπος γραφήματος χρησιμοποιείται;** `ChartType.ClusteredColumn`.  
- **Χρειάζομαι άδεια για δοκιμή;** Μια δωρεάν δοκιμή λειτουργεί, αλλά μια άδεια αφαιρεί τους περιορισμούς αξιολόγησης.  
- **Ποια έκδοση Java υποστηρίζεται;** JDK 16 ή νεότερη (το παράδειγμα χρησιμοποιεί JDK 16).  
- **Πώς να εκτελέσετε το παράδειγμα;** Προσθέστε την εξάρτηση Maven/Gradle, μεταγλωττίστε και εκτελέστε τη μέθοδο `main`.

## Τι είναι η προσθήκη συγκεντρωτικού γραφήματος στηλών;

Ένα συγκεντρωτικό γράφημα στηλών εμφανίζει πολλαπλές σειρές δεδομένων πλάι‑πλάι για κάθε κατηγορία, επιτρέποντάς σας να συγκρίνετε τιμές μεταξύ ομάδων σε ένα ενιαίο οπτικό στοιχείο. Είναι ιδανικό για τριμηνιαίες πωλήσεις, αποτελέσματα ερευνών ή οποιοδήποτε σενάριο όπου χρειάζεται να αντιπαραβάλετε αρκετά σύνολα δεδομένων μέσα στην ίδια κατηγορία.

## Γιατί να χρησιμοποιήσετε Aspose.Slides για την προσθήκη συγκεντρωτικού γραφήματος στηλών;

Μπορείτε να δημιουργήσετε δεκάδες διαφάνειες αυτόματα, να προσαρμόσετε κάθε οπτικό στοιχείο και να εκτελέσετε τον κώδικα σε οποιοδήποτε λειτουργικό σύστημα υποστηρίζει Java — χωρίς να απαιτείται εγκατάσταση Microsoft Office. Το Aspose.Slides υποστηρίζει **πάνω από 50 τύπους γραφημάτων** και μπορεί να επεξεργαστεί παρουσιάσεις με **έως 500 διαφάνειες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, καθιστώντας το κατάλληλο για μεγάλης κλίμακας pipelines αναφορών.

## Προαπαιτούμενα

- Βιβλιοθήκη **Aspose.Slides for Java** (συνιστάται η τελευταία έκδοση).  
- JDK 16 ή νεότερο.  
- Εργαλείο κατασκευής Maven ή Gradle (ή μπορείτε να προσθέσετε το JAR χειροκίνητα).  
- Ένα IDE ή κειμενογράφο για την εκτέλεση κώδικα Java.

## Ρύθμιση Aspose.Slides για Java

Προσθέστε τη βιβλιοθήκη στο έργο σας χρησιμοποιώντας ένα από τα παρακάτω σενάρια κατασκευής.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Εναλλακτικά, μπορείτε να κατεβάσετε απευθείας την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση άδειας

Πριν την παραγωγική χρήση, αποκτήστε άδεια:
- **Δωρεάν δοκιμή** – εξερευνήστε όλες τις δυνατότητες χωρίς αγορά.  
- **Προσωρινή άδεια** – αξιολογήστε επεκταμένες δυνατότητες για σύντομο χρονικό διάστημα.  
- **Πλήρης άδεια** – ξεκλειδώστε απεριόριστη χρήση. Λάβετε την από [σελίδα αγοράς του Aspose](https://purchase.aspose.com/buy).

## Πώς να προσθέσετε συγκεντρωτικό γράφημα στηλών σε PowerPoint χρησιμοποιώντας Aspose.Slides for Java;

Φορτώστε μια νέα `Presentation`, προσθέστε μια διαφάνεια, εισάγετε ένα `Chart` τύπου `ChartType.ClusteredColumn`, γεμίστε το εσωτερικό workbook με κατηγορίες και σειρές, και στη συνέχεια αποθηκεύστε το αρχείο ως PPTX. Αυτή η ακολουθία δημιουργεί ένα πλήρως λειτουργικό ομαδοποιημένο γράφημα στηλών με λίγες κλήσεις API.

### Αρχικοποίηση παρουσίασης

`Presentation` είναι η κλάση που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη, επιτρέποντάς σας να προσθέτετε διαφάνειες, σχήματα και γραφήματα προγραμματιστικά.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Προσθήκη γραφήματος στη διαφάνεια

`ChartType.ClusteredColumn` λέει στο Aspose.Slides να αποδώσει ένα ομαδοποιημένο γράφημα στηλών.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Προετοιμασία βιβλίου δεδομένων γραφήματος

Το γράφημα αποθηκεύει τα δεδομένα του σε ένα εσωτερικό workbook. Η εκκαθάρισή του σας δίνει ένα καθαρό ξεκίνημα για προσαρμοσμένα δεδομένα.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Προσθήκη κατηγοριών με επίπεδα ομαδοποίησης

Η ομαδοποίηση των κατηγοριών δημιουργεί το εφέ του ομαδοποιημένου γραφήματος στηλών. Κάθε κατηγορία μπορεί να ανήκει σε λογική ομάδα που εμφανίζεται στις ετικέτες του άξονα.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Προσθήκη σειράς δεδομένων στο γράφημα

Τα αντικείμενα `Series` αντιπροσωπεύουν μεμονωμένες στήλες στο γράφημα. Η προσθήκη πολλαπλών σειρών οδηγεί σε στήλες πλάι‑πλάι για κάθε κατηγορία.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Αποθήκευση παρουσίασης με γράφημα

Η αποθήκευση του `Presentation` γράφει ένα τυπικό αρχείο PPTX που μπορεί να ανοιχθεί σε οποιονδήποτε προβολέα PowerPoint.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Πρακτικές εφαρμογές

- **Επιχειρηματικές αναφορές** – σύγκριση τριμηνιαίων εσόδων ανά περιοχή.  
- **Ακαδημαϊκή έρευνα** – παρουσίαση πειραματικών αποτελεσμάτων ομαδοποιημένων ανά συνθήκες δοκιμής.  
- **Διαχείριση έργων** – οπτικοποίηση ποσοστών ολοκλήρωσης εργασιών για πολλαπλές ομάδες σε μία διαφάνεια.

## Σκέψεις απόδοσης

- **Διαχείριση μνήμης** – απελευθερώστε μεγάλα workbooks μετά τη χρήση.  
- **Λειτουργίες σε παρτίδες** – αποφύγετε την ενημέρωση του γραφήματος μέσα σε σφιχτούς βρόχους· συλλέξτε πρώτα τα δεδομένα, έπειτα εφαρμόστε τα.  
- **Ενσωματωμένες βελτιστοποιήσεις** – το Aspose.Slides παρέχει μεθόδους όπως `Presentation.optimize()` για μεγάλα αρχεία, μειώνοντας το αποτύπωμα μνήμης έως και **30 %**.

## Συνηθισμένα προβλήματα & συμβουλές

- **Πρόβλημα:** Ξεχάσατε να εκκαθαρίσετε τις υπάρχουσες σειρές/κατηγορίες, κάτι που μπορεί να οδηγήσει σε διπλότυπα δεδομένα.  
  **Συμβουλή:** Πάντα καλέστε `clear()` πριν γεμίσετε νέα δεδομένα.  
- **Πρόβλημα:** Χρήση λανθασμένης διεύθυνσης κελιού (π.χ., `"c2"` αντί για `"C2"`).  
  **Συμβουλή:** Οι αναφορές κελιών δεν είναι ευαίσθητες σε πεζά‑κεφαλαία, αλλά διατηρήστε τη συνέπεια για ευανάγνωστο κώδικα.  
- **Συμβουλή:** Χρησιμοποιήστε `setGroupingItem` για δημιουργία ουσιωδών ετικετών ομάδας· εμφανίζονται αυτόματα στη λεζάντα του γραφήματος.

## Συχνές ερωτήσεις

**Q1: Πώς μπορώ να προσθέσω πολλαπλές σειρές στο γράφημά μου;**  
A1: Καλέστε επανειλημμένα `ch.getChartData().getSeries().add()`, παρέχοντας μοναδικό όνομα και σημεία δεδομένων για κάθε σειρά.

**Q2: Ποια είναι μερικά κοινά προβλήματα με τα γραφήματα Aspose.Slides;**  
A2: Τα προβλήματα συχνά προέρχονται από ασυμφωνίες περιοχών δεδομένων ή ελλιπή κελιά workbook. Επαληθεύστε ότι κάθε κατηγορία και σημείο δεδομένων έχει αντίστοιχο κελί.

**Q3: Μπορώ να χρησιμοποιήσω Aspose.Slides με άλλες γλώσσες προγραμματισμού;**  
A3: Ναι, η Aspose παρέχει ισοδύναμες βιβλιοθήκες για .NET, C++, Python και άλλα.

**Q4: Πώς ενημερώνω ένα υπάρχον γράφημα σε μια παρουσίαση;**  
A4: Φορτώστε την παρουσίαση, εντοπίστε το γράφημα μέσω `slide.getShapes().get_Item(index)`, έπειτα τροποποιήστε τις σειρές ή τη μορφοποίηση όπως απαιτείται.

**Q5: Υπάρχουν περιορισμοί στους τύπους γραφημάτων με Aspose.Slides;**  
A5: Η βιβλιοθήκη υποστηρίζει πάνω από **50 τύπους γραφημάτων** και προσθέτει συνεχώς νέους· ελέγξτε πάντα την πιο πρόσφατη τεκμηρίωση για τη λίστα.

## Πόροι

- **Τεκμηρίωση:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Λήψη:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Αγορά:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Δωρεάν δοκιμή:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Προσωρινή άδεια:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Φόρουμ υποστήριξης:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Τελευταία ενημέρωση:** 2026-09-17  
**Δοκιμάστηκε με:** Aspose.Slides for Java 25.4 (JDK 16)  
**Συγγραφέας:** Aspose

## Σχετικά tutorials

- [Δημιουργία οδηγού δημιουργίας γραφημάτων σε Java με Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Πώς να προσθέσετε γράφημα σε PowerPoint χρησιμοποιώντας Aspose.Slides for Java: Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Προσθήκη animation σε γράφημα PowerPoint χρησιμοποιώντας Aspose.Slides for Java – Οδηγός βήμα‑βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}