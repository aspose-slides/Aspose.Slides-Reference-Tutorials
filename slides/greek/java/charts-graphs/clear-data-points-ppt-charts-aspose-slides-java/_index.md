---
date: '2026-08-27'
description: Μάθετε πώς να διαγράψετε chart data points σε PowerPoint χρησιμοποιώντας
  το Aspose.Slides for Java. Αυτό το step‑by‑step tutorial δείχνει πώς να διαγράψετε
  προγραμματιστικά chart values, best practices, και efficient series handling.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: Μάθετε πώς να διαγράψετε chart data points σε PowerPoint χρησιμοποιώντας
  το Aspose.Slides for Java. Ακολουθήστε step‑by‑step instructions για να επαναφέρετε
  προγραμματιστικά charts αποδοτικά.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: Πώς να διαγράψετε chart data points σε PowerPoint με Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'Πώς να διαγράψετε chart data points σε PowerPoint charts χρησιμοποιώντας το
  Aspose.Slides for Java: ένας ολοκληρωμένος οδηγός'
url: /el/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να διαγράψετε σημεία δεδομένων σε διαγράμματα PowerPoint χρησιμοποιώντας το Aspose.Slides for Java

## Εισαγωγή

Σε πολλές αλυσίδες αναφοράς χρειάζεται να **επαναφέρετε ένα διάγραμμα** χωρίς να δημιουργήσετε ξανά τη διάταξή του. Είτε ανανεώνετε έναν πίνακα ελέγχου, είτε διανέμετε ένα πρότυπο, είτε αυτοματοποιείτε νυχτερινές αναφορές, η γνώση του **πώς να διαγράψετε σημεία δεδομένων σε διάγραμμα** εξοικονομεί χρόνο και μειώνει τα σφάλματα. Αυτό το μάθημα σας δείχνει πώς να χρησιμοποιήσετε το **Aspose.Slides for Java** για να διαγράψετε προγραμματιστικά συγκεκριμένα σημεία ή ολόκληρη σειρά, διατηρώντας το οπτικό στυλ ανέπαφο.

**Τι θα μάθετε**
- Πώς το Aspose.Slides σας επιτρέπει να χειρίζεστε διαγράμματα PowerPoint από τη Java.  
- Οδηγίες βήμα‑βήμα για τη διαγραφή σημείων δεδομένων σε μια σειρά διαγράμματος.  
- Συμβουλές βέλτιστων πρακτικών για απόδοση και άδεια.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Slides for Java (v25.4+).  
- **Ποια μέθοδος διαγράφει πραγματικά ένα σημείο δεδομένων;** Ορίζοντας τις τιμές κελιών X και Y σε `null`.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι – μια εμπορική άδεια αφαιρεί τα όρια δοκιμής.  
- **Υποστηρίζεται η Java 16;** Απόλυτα· η βιβλιοθήκη λειτουργεί με JDK 16 και νεότερες.  
- **Μπορώ να στοχεύσω μόνο μία σειρά;** Ναι – επαναλάβετε τη συγκεκριμένη σειρά που θέλετε να διαγράψετε.

## Τι είναι το Aspose.Slides for Java;

Το Aspose.Slides for Java είναι ένα πλήρες API που επιτρέπει τη δημιουργία, επεξεργασία και μετατροπή αρχείων PowerPoint χωρίς το Microsoft Office. Υποστηρίζει πάνω από 70 τύπους διαγραμμάτων, 150+ μορφές αρχείων και μπορεί να επεξεργαστεί παρουσιάσεις έως 500 MB χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.

## Γιατί να διαγράψετε σημεία δεδομένων σε διάγραμμα;

Η διαγραφή σημείων δεδομένων σε διάγραμμα σας επιτρέπει να διατηρήσετε την υπάρχουσα διάταξη του διαγράμματος — όπως χρώματα, υπομνήματα, ρυθμίσεις αξόνων και δείκτες — ενώ αντικαθιστάτε τις υποκείμενες αριθμητικές τιμές. Αυτή η προσέγγιση είναι χρήσιμη όταν χρειάζεται να ανανεώσετε ένα διάγραμμα με νέα δεδομένα, να παρέχετε ένα πρότυπο με κενά σύμβολα, ή να δημιουργήσετε δυναμικούς πίνακες ελέγχου που αλλάζουν συχνά χωρίς να ξαναχτίζετε το οπτικό σχέδιο.

- Ανανέωση ενός διαγράμματος με νέο σύνολο δεδομένων διατηρώντας χρώματα, υπομνήματα και ρυθμίσεις αξόνων.  
- Διανομή ενός προτύπου που περιέχει κενά διαγράμματα έτοιμα για εισαγωγή από τον χρήστη.  
- Δημιουργία δυναμικών πινάκων ελέγχου όπου τα δεδομένα αλλάζουν συχνά.

## Πώς να διαγράψετε σημεία δεδομένων σε διάγραμμα PowerPoint χρησιμοποιώντας το Aspose.Slides for Java

Φορτώστε την παρουσίασή σας, εντοπίστε το διάγραμμα και ορίστε τα κελιά X και Y κάθε σημείου δεδομένων σε `null`. Αυτή η ενέργεια αφαιρεί τις αριθμητικές τιμές αλλά αφήνει τη σειρά, τους δείκτες και τη μορφοποίηση ανέπαφους. Η ολόκληρη διαδικασία ολοκληρώνεται συνήθως σε λιγότερο από ένα δευτερόλεπτο για ένα τυπικό PPTX με 10 διαφάνειες.

### Άμεση απάντηση
Για να διαγράψετε σημεία δεδομένων σε διάγραμμα, ανοίξτε το PPTX με `new Presentation("input.pptx")`, ανακτήστε το αντικείμενο `IChart`, επαναλάβετε τη ζητούμενη `IChartSeries` και καλέστε `dataPoint.getXValue().setValue(null)` και `dataPoint.getYValue().setValue(null)` για κάθε σημείο. Τέλος, αποθηκεύστε την παρουσίαση με `pres.save("output.pptx", SaveFormat.Pptx)`. Αυτή η προσέγγιση διαγράφει προγραμματιστικά τα δεδομένα διατηρώντας το οπτικό σχέδιο του διαγράμματος.

### Ορισμοί
- `Presentation` είναι το αντικείμενο υψηλότερου επιπέδου του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη.  
- `IChart` είναι η διεπαφή που παρέχει πρόσβαση στη σειρά, τους άξονες και τη μορφοποίηση ενός σχήματος διαγράμματος.  
- `IChartSeries` αντιπροσωπεύει μία μόνο σειρά μέσα σε ένα διάγραμμα και περιέχει μια συλλογή από αντικείμενα `IDataPoint`.  
- `IDataPoint` κρατά τις μεμονωμένες τιμές X και Y για ένα σημείο στο διάγραμμα.

### Υλοποίηση βήμα‑βήμα

1. **Φορτώστε την παρουσίαση** – δημιουργήστε ένα αντικείμενο `Presentation` που δείχνει στο αρχείο προέλευσης σας.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **Πρόσβαση στη διαφάνεια και στο διάγραμμα** – ανακτήστε τη διαφάνεια (συνήθως δείκτης 0) και μετατρέψτε το πρώτο σχήμα σε `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **Επανάληψη στη στοχευμένη σειρά** – επιλέξτε τη σειρά που θέλετε να διαγράψετε (π.χ., `chart.getChartData().getSeries().get_Item(0)`) και επαναλάβετε τα σημεία δεδομένων της, ορίζοντας και τις τιμές κελιών X και Y σε `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **Αποθήκευση της τροποποιημένης παρουσίασης** – γράψτε τις αλλαγές σε νέο αρχείο ή αντικαταστήστε το αρχικό.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## Ρύθμιση του Aspose.Slides for Java

### Εγκατάσταση μέσω Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Εγκατάσταση μέσω Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### Άμεση λήψη

Εναλλακτικά, κατεβάστε την πιο πρόσφατη έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση άδειας

Για να χρησιμοποιήσετε το Aspose.Slides πέρα από τους περιορισμούς της δοκιμής:
- Αποκτήστε μια **δωρεάν άδεια δοκιμής**.  
- Κάντε αίτηση για **προσωρινή άδεια** για αξιολόγηση.  
- Αγοράστε μια **εμπορική άδεια** για παραγωγική χρήση.

#### Βασική αρχικοποίηση και ρύθμιση

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## Πρακτικές εφαρμογές

Η διαγραφή σημείων δεδομένων σε διάγραμμα είναι χρήσιμη σε πολλές πραγματικές περιπτώσεις:

1. Αλυσίδες ανανέωσης δεδομένων – αντικατάσταση παλαιών αριθμών με φρέσκα αναλυτικά στοιχεία χωρίς να ξαναχτίζετε τη διάταξη του διαγράμματος.  
2. Διανομή προτύπων – παροχή προτύπων PowerPoint που περιέχουν κενά διαγράμματα έτοιμα για εισαγωγή από τον χρήστη.  
3. Δυναμικοί πίνακες ελέγχου – δημιουργία νυχτερινών παρουσιάσεων που αντλούν δεδομένα από API, διαγράφοντας πρώτα τις παλιές τιμές.  
4. Αυτοματοποιημένες εργασίες αναφοράς – ενσωμάτωση της λογικής διαγραφής σε CI/CD αλυσίδες για αυτόματη δημιουργία αναφορών.

## Σκέψεις για την απόδοση

- **Απελευθέρωση αντικειμένων**: Καλέστε `pres.dispose()` μετά την αποθήκευση για να απελευθερώσετε τους εγγενείς πόρους.  
- **Επεξεργασία παρτίδας**: Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `License` σε πολλά αρχεία για ελαχιστοποίηση του κόστους.  
- **Ρύθμιση JVM**: Αυξήστε το μέγεθος heap (`-Xmx2g` ή μεγαλύτερο) όταν επεξεργάζεστε παρουσιάσεις μεγαλύτερες από 200 MB.  
- **Λειτουργία αποδοτικής μνήμης**: Το Aspose.Slides μπορεί να ρέει μεγάλα αρχεία PPTX, επιτρέποντας την επεξεργασία έως 10 000 διαφανειών χωρίς πλήρη φόρτωση στη μνήμη.

## Συχνές ερωτήσεις

**Ε: Χρειάζομαι άδεια για εκδόσεις ανάπτυξης;**  
Α: Μια άδεια δοκιμής είναι επαρκής για ανάπτυξη και δοκιμές. Απαιτείται εμπορική άδεια για παραγωγικές εγκαταστάσεις.

**Ε: Υποστηρίζει το Aspose.Slides for Java τις δυνατότητες του PowerPoint 2016/2019;**  
Α: Ναι, η βιβλιοθήκη υποστηρίζει πλήρως τις σύγχρονες δυνατότητες PPTX, συμπεριλαμβανομένων των προχωρημένων τύπων διαγραμμάτων και SmartArt.

**Ε: Μπορώ να διαγράψω σημεία δεδομένων σε διάγραμμα που χρησιμοποιεί δευτερεύοντα άξονα;**  
Α: Απόλυτα – απλώς αναφερθείτε στη σειρά που ανήκει στο δευτερεύοντα άξονα και ορίστε τα σημεία δεδομένων της σε `null` όπως περιγράφηκε παραπάνω.

**Ε: Είναι δυνατόν να διαγράψετε μόνο τις τιμές Y διατηρώντας τις ετικέτες X;**  
Α: Ναι. Καλέστε `dataPoint.getYValue().setValue(null)` και αφήστε το κελί X αμετάβλητο.

**Ε: Πώς μπορώ να αυτοματοποιήσω αυτό για πολλαπλές παρουσιάσεις;**  
Α: Τυλίξτε τον κώδικα διαγραφής σε βρόχο που επαναλαμβάνει έναν φάκελο αρχείων PPTX, εφαρμόζοντας την ίδια λογική σε κάθε αρχείο.

## Πόροι

- [Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/java/)
- [Λήψη Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Αγορά Άδειας](https://purchase.aspose.com/buy)
- [Δωρεάν Έκδοση Δοκιμής](https://releases.aspose.com/slides/java/)
- [Αίτηση για Προσωρινή Άδεια](https://purchase.aspose.com/temporary-license/)
- [Φόρουμ Κοινότητας Aspose](https://forum.aspose.com/c/slides/11)

Με αυτούς τους πόρους είστε έτοιμοι να ξεκινήσετε τη διαγραφή σημείων δεδομένων σε διαγράμματα στις Java εφαρμογές σας. Καλή προγραμματιστική!

**Τελευταία ενημέρωση:** 2026-08-27  
**Δοκιμάστηκε με:** Aspose.Slides for Java 25.4 (JDK 16)  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Πώς να Επεξεργαστείτε Δεδομένα Διαγράμματος PowerPoint χρησιμοποιώντας Aspose.Slides for Java: Ένας Πλήρης Οδηγός](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Πώς να Προσθέσετε Διάγραμμα σε PowerPoint χρησιμοποιώντας Aspose.Slides for Java: Οδηγός Βήμα‑Βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Διαγραφή Συγκεκριμένων Σημείων Δεδομένων Σειράς Διαγράμματος σε Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}