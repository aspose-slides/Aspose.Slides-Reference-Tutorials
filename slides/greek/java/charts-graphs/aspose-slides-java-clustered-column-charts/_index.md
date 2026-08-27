---
date: '2026-08-27'
description: Μάθετε πώς να δημιουργήσετε συγκεντρωτικό γράφημα στήλης σε Java χρησιμοποιώντας
  το Aspose.Slides, προσθέστε το γράφημα, ορίστε αυτόματα τα χρώματα των σειρών και
  αποθηκεύστε την παρουσίαση ως PPTX.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: Μάθετε πώς να δημιουργήσετε συγκεντρωτικό γράφημα στήλης σε Java χρησιμοποιώντας
  το Aspose.Slides, προσθέστε το γράφημα, ορίστε αυτόματα τα χρώματα των σειρών και
  αποθηκεύστε την παρουσίαση ως PPTX—όλα με σαφείς οδηγίες βήμα‑βήμα.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: Δημιουργήστε συγκεντρωτικό γράφημα στήλης σε Java με το Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: Πώς να δημιουργήσετε συγκεντρωτικό γράφημα στήλης σε Java με το Aspose.Slides
url: /el/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε συγκεντρωτικό γράφημα στήλης σε Java με Aspose.Slides

## Εισαγωγή

Δημιουργώντας ένα συγκεντρωτικό γράφημα στήλης προγραμματιστικά σας εξοικονομεί ώρες χειροκίνητης μορφοποίησης και εγγυάται τη συνέπεια σε πολλές παρουσιάσεις. Σε αυτό το σεμινάριο θα μάθετε **πώς να δημιουργήσετε συγκεντρωτικό γράφημα στήλης** σε Java με Aspose.Slides, **πώς να προσθέσετε γράφημα**, **πώς να ορίσετε χρώματα**, και **πώς να αποθηκεύσετε την παρουσίαση ως PPTX**. Θα καλύψουμε τα πάντα από την εγκατάσταση της βιβλιοθήκης μέχρι την προσαρμογή των χρωμάτων γεμίσματος των σειρών και την αποθήκευση του αρχείου, ώστε να μπορείτε να ενσωματώσετε πλούσιες οπτικοποιήσεις δεδομένων σε οποιοδήποτε PowerPoint deck.

## Γρήγορες απαντήσεις
- **Ποια είναι η κύρια κλάση για εργασία με παρουσιάσεις;** `Presentation` from the `com.aspose.slides` package.  
- **Πώς προσθέτω ένα συγκεντρωτικό γράφημα στήλης;** Call `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **Μπορούν τα χρώματα των σειρών να οριστούν αυτόματα;** Yes—enable `setAutomaticSeriesColor(true)` on each series.  
- **Ποια μορφή πρέπει να χρησιμοποιήσω για την αποθήκευση του αρχείου;** `SaveFormat.Pptx` produces a standard PowerPoint file.  
- **Απαιτείται άδεια για παραγωγή;** A trial works for development; a full license is needed for commercial use.

## Τι είναι ένα συγκεντρωτικό γράφημα στήλης;

Ένα συγκεντρωτικό γράφημα στήλης εμφανίζει πολλαπλές σειρές δεδομένων πλάι‑πλάι για κάθε κατηγορία, καθιστώντας εύκολο το σύγκριση τιμών μεταξύ ομάδων. Το Aspose.Slides υποστηρίζει αυτόν τον τύπο γραφήματος έτοιμο προς χρήση και σας επιτρέπει να ελέγχετε κάθε οπτικό στοιχείο προγραμματιστικά.

## Γιατί να δημιουργήσετε ένα συγκεντρωτικό γράφημα στήλης με Aspose.Slides;

Το Aspose.Slides μπορεί να διαχειριστεί **πάνω από 50 μορφές εισόδου και εξόδου** και να επεξεργαστεί παρουσιάσεις με **εκατοντάδες διαφάνειες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Αυτή η αποδοτικότητα σημαίνει ότι μπορείτε να δημιουργήσετε μεγάλες decks σε περιβάλλον διακομιστή με ελάχιστη κατανάλωση πόρων.

## Προαπαιτούμενα

- **Java Development Kit** 16 ή νεότερο.  
- **Maven** ή **Gradle** για διαχείριση εξαρτήσεων.  
- Βασική εξοικείωση με τη σύνταξη της Java και τις αντικειμενοστραφείς έννοιες.  

### Απαιτούμενες βιβλιοθήκες και εξαρτήσεις

Χρειάζεστε τη βιβλιοθήκη Aspose.Slides for Java (έκδοση 25.4 ή νεότερη). Η βιβλιοθήκη είναι πλήρως συμβατή με JDK 16 και προσφέρει πλούσιο API για τη διαχείριση γραφημάτων.

### Απαιτήσεις ρύθμισης περιβάλλοντος

Το IDE σας (IntelliJ IDEA, Eclipse, VS Code) πρέπει να είναι ρυθμισμένο ώστε να μεταγλωττίζει κώδικα Java 16 και να επιλύει εξαρτήσεις Maven/Gradle.

### Προαπαιτούμενη γνώση

Η κατανόηση της δομής των διαφανειών PowerPoint και της βασικής ορολογίας γραφημάτων (σειρές, κατηγορίες, σημεία δεδομένων) θα σας βοηθήσει να ακολουθήσετε τα παραδείγματα πιο γρήγορα.

## Ρύθμιση του Aspose.Slides για Java

Ενσωματώστε τη βιβλιοθήκη στο έργο σας χρησιμοποιώντας μία από τις παρακάτω μεθόδους.

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

**Άμεση λήψη** – obtain the JAR from the official releases page: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Βήματα απόκτησης άδειας

- **Δωρεάν δοκιμή** – εγγραφείτε στον ιστότοπο Aspose για να λάβετε ένα προσωρινό αρχείο άδειας.  
- **Προσωρινή άδεια** – ζητήστε άδεια 30 ημερών για μεγαλύτερα σύνολα δοκιμών.  
- **Πλήρης άδεια** – αγοράστε για απεριόριστη χρήση σε παραγωγή.

**Βασική αρχικοποίηση και ρύθμιση**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## Πώς να προσθέσετε ένα συγκεντρωτικό γράφημα στήλης;

`Presentation` αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη.  

**Άμεση απάντηση:**  
Δημιουργήστε ένα αντικείμενο `Presentation`, το οποίο αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη, ανακτήστε την πρώτη διαφάνεια και καλέστε `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`. Αυτή η εντολή εισάγει ένα πλήρως λειτουργικό συγκεντρωτικό γράφημα στήλης, έτοιμο για πληθώρα δεδομένων, και το τοποθετεί στις καθορισμένες συντεταγμένες στη διαφάνεια.

### Δυνατότητα 1: δημιουργία συγκεντρωτικού γραφήματος στήλης

Η κλάση `Presentation` αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη και παρέχει πρόσβαση σε διαφάνειες, σχήματα και αντικείμενα γραφημάτων.

**Βήμα 1: αρχικοποίηση παρουσίασης**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**Βήμα 2: προσθήκη συγκεντρωτικού γραφήματος στήλης**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**Βήμα 3: εκκαθάριση πόρων**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Πώς να ορίσετε χρώματα για το γράφημα;

`Series` αντιπροσωπεύει μια συλλογή σημείων δεδομένων μέσα σε ένα γράφημα.  

**Άμεση απάντηση:**  
Αφού δημιουργηθεί το γράφημα, αποκτήστε τα δεδομένα του μέσω `chart.getChartData()` και επαναλάβετε για κάθε αντικείμενο `Series`. Για κάθε σειρά, καλέστε `setAutomaticSeriesColor(true)` στη γονική σειρά. Το Aspose.Slides τότε αυτόματα αναθέτει ένα ξεχωριστό, αντιθετικό χρώμα από την παλέτα του σε κάθε σειρά, εξασφαλίζοντας οπτική σαφήνεια χωρίς χειροκίνητη επιλογή χρώματος.

### Δυνατότητα 2: αυτόματη ρύθμιση χρώματος γεμίσματος σειράς

`IChart` είναι η διεπαφή που αντιπροσωπεύει ένα σχήμα γραφήματος· εκθέτει τη μέθοδο `getChartData()` για τη διαχείριση σειρών.

**Βήμα 1: πρόσβαση στο γράφημα και επανάληψη στις σειρές**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**Βήμα 2: διαχείριση πόρων**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Πώς να αποθηκεύσετε την παρουσίαση ως PPTX;

`save` γράφει την παρουσίαση σε ένα αρχείο στην επιλεγμένη μορφή.  

**Άμεση απάντηση:**  
Καθορίστε μια διαδρομή εξόδου όπως `"output/ClusteredColumnChart.pptx"` και καλέστε `presentation.save(outputPath, SaveFormat.Pptx)`. Η μέθοδος `save` σειριοποιεί ολόκληρο το σύνολο διαφανειών, συμπεριλαμβανομένων όλων των σχημάτων, γραφημάτων και πόρων, σε ένα τυπικό αρχείο PPTX που μπορεί να ανοιχθεί από το PowerPoint 2010 ή νεότερο, καθώς και από πολλούς online προβολείς.

### Δυνατότητα 3: αποθήκευση παρουσίασης στο δίσκο

Η αποθήκευση με `SaveFormat.Pptx` παράγει ένα αρχείο συμβατό με PowerPoint 2010 και νεότερο, καθώς και με τους περισσότερους online προβολείς.

**Βήμα 1: ορισμός διαδρομής εξόδου**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**Βήμα 2: αποθήκευση παρουσίασης**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## Πρακτικές εφαρμογές

- **Οικονομική αναφορά** – σύγκριση τριμηνιαίου εσόδους ανά γραμμή προϊόντος.  
- **Ανάλυση μάρκετινγκ** – οπτικοποίηση απόδοσης καμπάνιας ανά περιοχή.  
- **Διαχείριση έργων** – εμφάνιση ταχύτητας sprint ή κατανομής πόρων ανά ομάδες.  

## Παρατηρήσεις απόδοσης

- Αποδεσμεύστε άμεσα τα αντικείμενα `Presentation` για να ελευθερώσετε τους εγγενείς πόρους.  
- Χρησιμοποιήστε `presentation.getSlides().removeUnusedResources()` πριν από την αποθήκευση για να μειώσετε το μέγεθος του αρχείου.  
- Συμπληρώστε τις σειρές του γραφήματος με ελαφριές συλλογές (π.χ., `ArrayList<Double>`) για να διατηρήσετε τη χρήση μνήμης χαμηλή.

## Συμπέρασμα

Τώρα ξέρετε πώς να **δημιουργήσετε συγκεντρωτικό γράφημα στήλης**, αυτόματα **ορίσετε χρώματα**, και **αποθηκεύσετε την παρουσίαση ως PPTX** χρησιμοποιώντας το Aspose.Slides για Java. Αυτά τα βήματα σας επιτρέπουν να δημιουργείτε διαφάνειες βασισμένες σε δεδομένα προγραμματιστικά, εξαλείφοντας την επαναλαμβανόμενη χειροκίνητη εργασία και εξασφαλίζοντας οπτική συνέπεια σε όλη την οργάνωσή σας.

**Επόμενα βήματα:**  
Εξερευνήστε προχωρημένες προσαρμογές όπως ετικέτες δεδομένων, μορφοποίηση αξόνων και δυναμική σύνδεση δεδομένων από βάσεις δεδομένων ή αρχεία CSV για περαιτέρω εμπλουτισμό των παρουσιάσεών σας.

## Συχνές ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω αυτόν τον κώδικα σε web εφαρμογή;**  
A: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server environment, including Spring Boot and Jakarta EE.

**Q: Υποστηρίζει η βιβλιοθήκη άλλους τύπους γραφημάτων;**  
A: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and many more.

**Q: Τι γίνεται αν ο φάκελος εξόδου δεν υπάρχει;**  
A: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))` to avoid `FileNotFoundException`.

**Q: Πώς να διαχειριστώ μεγάλα σύνολα δεδομένων (χιλιάδες σημεία);**  
A: Populate series using streaming APIs or batch inserts, and consider disabling chart animation to improve rendering speed.

**Q: Πού μπορώ να βρω περισσότερα παραδείγματα κώδικα;**  
A: Visit the official documentation and sample repository: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## Πόροι

- **Τεκμηρίωση:** [Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Αναφορά:** [Αναφορά Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Λήψη:** [Λήψη Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Αγορά:** [Αγορά άδειας](https://purchase.aspose.com/buy)  
- **Δωρεάν δοκιμή:** [Ξεκινήστε δωρεάν δοκιμή](https://releases.aspose.com/slides/java/)  
- **Προσωρινή άδεια:** [Αίτηση εδώ](https://purchase.aspose.com/temporary-license/)  
- **Υποστήριξη:** [Φόρουμ Aspose](https://forum.aspose.com/c/slides/11)

---

**Τελευταία ενημέρωση:** 2026-08-27  
**Δοκιμάστηκε με:** Aspose.Slides 25.4 (JDK 16)  
**Συγγραφέας:** Aspose

## Σχετικά σεμινάρια

- [Δημιουργία γραφήματος PowerPoint Java – Αποθήκευση παρουσιάσεων με γραφήματα χρησιμοποιώντας Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Εξάρτηση maven Aspose Slides: Προσθήκη και διαμόρφωση γραφημάτων σε παρουσιάσεις χρησιμοποιώντας Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Προσθήκη animation σε γράφημα PowerPoint χρησιμοποιώντας Aspose.Slides for Java – Οδηγός βήμα‑βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}