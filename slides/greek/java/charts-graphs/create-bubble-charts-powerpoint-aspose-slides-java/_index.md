---
date: '2026-09-17'
description: Μάθετε πώς να δημιουργήσετε bubble chart powerpoint χρησιμοποιώντας Aspose.Slides
  for Java. Αυτός ο οδηγός σας δείχνει πώς να προσθέσετε chart σε slide, να ρυθμίσετε
  το μέγεθος του bubble και να αποθηκεύσετε το PPTX αποδοτικά.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Μάθετε πώς να δημιουργήσετε bubble chart powerpoint χρησιμοποιώντας
  Aspose.Slides for Java. Αυτό το tutorial εξηγεί πώς να προσθέσετε chart σε slide,
  να προσαρμόσετε τα μεγέθη των bubble και να αποθηκεύσετε το presentation αποδοτικά.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Δημιουργία bubble chart powerpoint με Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Δημιουργία bubble chart powerpoint με Aspose.Slides for Java
url: /el/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Δημιουργία διαγράμματος φυσαλίδων PowerPoint με Aspose.Slides για Java

## Εισαγωγή
Αν χρειάζεστε **δημιουργία διαγράμματος φυσαλίδων PowerPoint** παρουσιάσεων προγραμματιστικά, το Aspose.Slides για Java σας προσφέρει ένα καθαρό, server‑side API που λειτουργεί χωρίς το Microsoft Office. Σε αυτό το tutorial θα μάθετε πώς να προσθέσετε ένα διάγραμμα σε μια διαφάνεια, να ελέγξετε τα μεγέθη των φυσαλίδων και να αποθηκεύσετε το τελικό PPTX ενώ διαχειρίζεστε αποδοτικά τους πόρους. Τα βήματα είναι διαχωρισμένα ώστε να μπορείτε να αντιγράψετε‑και‑επικολλήσετε τον κώδικα σε οποιοδήποτε έργο Java και να δείτε τα αποτελέσματα αμέσως.

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη χρειάζομαι;** Aspose.Slides για Java
- **Ποια έκδοση Java απαιτείται;** JDK 16 ή νεότερη
- **Πώς προσθέτω ένα διάγραμμα φυσαλίδων;** Καλέστε `addChart(ChartType.Bubble, …)` σε μια διαφάνεια
- **Μπορώ να αλλάξω το μέγεθος της φυσαλίδας;** Ναι, μέσω `setBubbleSizeScale()`
- **Πώς αποθηκεύω το αρχείο;** Χρησιμοποιήστε `pres.save("Result.pptx", SaveFormat.Pptx)`

## Τι είναι η δημιουργία διαγράμματος φυσαλίδων PowerPoint;
Η δημιουργία ενός διαγράμματος φυσαλίδων στο PowerPoint σημαίνει την προγραμματιστική παραγωγή ενός διαγράμματος όπου κάθε σημείο δεδομένων αντιπροσωπεύεται από μια φυσαλίδα της οποίας η θέση X, η θέση Y και το μέγεθος κωδικοποιούν τρεις διαστάσεις δεδομένων. Το Aspose.Slides για Java διαχειρίζεται την απόδοση, έτσι δεν χρειάζεται να έχετε εγκατεστημένο το PowerPoint.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για Java;
Το Aspose.Slides υποστηρίζει **πάνω από 50 τύπους διαγραμμάτων**, μπορεί να επεξεργαστεί παρουσιάσεις έως **2 GB** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, και λειτουργεί σε οποιαδήποτε πλατφόρμα που υποστηρίζει Java 16+. Αυτές οι ποσοτικοποιημένες δυνατότητες το καθιστούν αξιόπιστη επιλογή για επιχειρηματική αναφορά.

## Προαπαιτούμενα
- **Java Development Kit** 16 ή νεότερο εγκατεστημένο.
- **Aspose.Slides για Java** βιβλιοθήκη (προσθέστε μέσω Maven, Gradle ή άμεσης λήψης JAR).
- Βασική εξοικείωση με τη σύνταξη της Java και τον αντικειμενοστραφή προγραμματισμό.

## Ρύθμιση του Aspose.Slides για Java
Για να αρχίσετε να χρησιμοποιείτε το Aspose.Slides, συμπεριλάβετε τη βιβλιοθήκη στο σύστημα κατασκευής σας.

### Maven
Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Συμπεριλάβετε αυτό στο `build.gradle` σας:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση λήψη
Μπορείτε επίσης να αποκτήσετε το τελευταίο JAR από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Απόκτηση άδειας
- **Δωρεάν δοκιμή** – εξερευνήστε όλες τις δυνατότητες χωρίς κόστος.  
- **Προσωρινή άδεια** – εκτεταμένη αξιολόγηση για μεγαλύτερα έργα.  
- **Πλήρης άδεια** – απαιτείται για παραγωγικές εγκαταστάσεις.

### Βασική αρχικοποίηση και ρύθμιση
Η κλάση `Presentation` είναι το σημείο εισόδου για τη δημιουργία ή τη φόρτωση αρχείων PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Οδηγός υλοποίησης
Παρακάτω υπάρχει ένας βήμα‑βήμα οδηγός για τη δημιουργία διαγράμματος φυσαλίδων και τη διαχείριση των πόρων.

## Πώς να δημιουργήσετε διάγραμμα φυσαλίδων PowerPoint
Σε αυτήν την ενότητα θα μάθετε τη συγκεκριμένη σειρά κλήσεων API που απαιτούνται για τη δημιουργία ενός διαγράμματος φυσαλίδων, τη διαμόρφωση των οπτικών του ιδιοτήτων και την αποθήκευση του αποτελέσματος ως αρχείο PPTX. Η προσέγγιση λειτουργεί για οποιοδήποτε έργο Java που περιλαμβάνει το Aspose.Slides και ακολουθεί τις βέλτιστες πρακτικές διαχείρισης πόρων.

### Άμεση απάντηση
Δημιουργήστε ένα νέο `Presentation`, καλέστε `addChart(ChartType.Bubble, …)` στη ζητούμενη διαφάνεια, προσαρμόστε την κλίμακα μεγέθους των φυσαλίδων με `setBubbleSizeScale(150)`, στη συνέχεια αποθηκεύστε χρησιμοποιώντας `pres.save("Result.pptx", SaveFormat.Pptx)`. Αυτή η ακολουθία προσθέτει ένα πλήρως λειτουργικό διάγραμμα φυσαλίδων σε λίγες μόνο γραμμές Java.

- **`ChartType.Bubble`** αντιπροσωπεύει τον τύπο διαγράμματος φυσαλίδων.  
- **`addChart`** εισάγει ένα νέο διάγραμμα του καθορισμένου τύπου σε μια διαφάνεια.  
- **`setBubbleSizeScale`** ρυθμίζει το συνολικό μέγεθος των φυσαλίδων στο διάγραμμα.  
- **`SaveFormat.Pptx`** καθορίζει τη μορφή αρχείου PPTX για αποθήκευση.  

#### Βήμα‑βήμα υλοποίηση
**1. Initialize presentation** – instantiate the `Presentation` object.  
```java
Presentation pres = new Presentation();
```

**2. Add bubble chart** – insert the chart at the chosen coordinates.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` λέει στο Aspose.Slides να δημιουργήσει ένα διάγραμμα φυσαλίδων.  
- Οι αριθμητικές παράμετροι ορίζουν τη θέση X/Y και το πλάτος/ύψος σε μονάδες σημείου.

**3. Configure bubble size scale** – enlarge bubbles for better visual impact.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Η ρύθμιση της κλίμακας σε **150 %** κάνει κάθε φυσαλίδα 1,5 × μεγαλύτερη από την προεπιλογή.

**4. Save presentation** – write the PPTX to disk.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Συμβουλές αντιμετώπισης προβλημάτων
- Επαληθεύστε τα δικαιώματα εγγραφής για το φάκελο εξόδου.  
- Επιβεβαιώστε ότι το JAR του Aspose.Slides ταιριάζει με την έκδοση JDK που χρησιμοποιείτε.

## Πώς να διαχειριστείτε αποτελεσματικά τους πόρους του PowerPoint
Η αποτελεσματική διαχείριση πόρων αποτρέπει διαρροές μνήμης και διατηρεί το αποτύπωμα του JVM χαμηλό, ειδικά όταν επεξεργάζεστε μεγάλες παρουσιάσεις ή λειτουργείτε σε περιβάλλον διακομιστή. Ακολουθήστε το παρακάτω πρότυπο για να διασφαλίσετε ότι οι εγγενείς πόροι απελευθερώνονται ακόμη και σε περίπτωση εξαίρεσης.

Η αποδοτική διαχείριση πόρων αποτρέπει διαρροές μνήμης, ειδικά κατά την επεξεργασία μεγάλων δεξαμενών.

### Άμεση απάντηση
Αφού ολοκληρώσετε την εργασία με ένα `Presentation`, καλέστε πάντα `pres.dispose()` μέσα σε ένα μπλοκ `try‑finally`; αυτό απελευθερώνει τους εγγενείς πόρους και επιτρέπει στη JVM να ανακτήσει τη μνήμη άμεσα.

- **`pres.dispose()`** απελευθερώνει τους εγγενείς πόρους που χρησιμοποιεί η παρουσίαση.

**1. Create and modify** – work with the presentation as needed.  
```java
Presentation pres = new Presentation();
```

**2. Dispose resources** – free memory once processing is complete.  
```java
if (pres != null) pres.dispose();
```

## Πρακτικές εφαρμογές
Τα διαγράμματα φυσαλίδων διαπρέπουν σε σενάρια όπου χρειάζεται ταυτόχρονη οπτικοποίηση τριών διαστάσεων δεδομένων:

1. **Ανάλυση αγοράς** – το μέγεθος της φυσαλίδας αντιπροσωπεύει τα έσοδα ενώ οι άξονες X/Y δείχνουν την ανάπτυξη και το μερίδιο αγοράς.  
2. **Δείκτες απόδοσης** – σύγκριση παραγωγικότητας υπαλλήλων (X), ικανοποίησης (Y) και επιρροής (μέγεθος).  
3. **Γεωγραφικά δεδομένα** – απεικόνιση πόλεων με πληθυσμό κωδικοποιημένο στο μέγεθος της φυσαλίδας.  
4. **Διαχείριση έργων** – οπτικοποίηση χρονοδιαγράμματος (X), κόστους (Y) και κινδύνου (μέγεθος) σε μία διαφάνεια.

## Παράγοντες απόδοσης
- **Χρήση πόρων** – απελευθερώστε τις παρουσιάσεις άμεσα για να διατηρήσετε τη χρήση του heap χαμηλή.  
- **Διαχείριση μνήμης Java** – τυλίξτε την εργασία παρουσίασης σε `try‑finally` για να εγγυηθείτε την απελευθέρωση ακόμη και σε περίπτωση εξαίρεσης.  
- **Παραμείνετε ενημερωμένοι** – αναβαθμίστε στην πιο πρόσφατη έκδοση του Aspose.Slides για να επωφεληθείτε από βελτιώσεις απόδοσης και διορθώσεις σφαλμάτων.

## Συχνές ερωτήσεις

**Τ: Τι είναι το Aspose.Slides για Java;**  
Α: Το Aspose.Slides για Java είναι μια ανεξάρτητη βιβλιοθήκη που σας επιτρέπει να δημιουργείτε, να επεξεργάζεστε και να μετατρέπετε αρχεία PowerPoint χωρίς την ανάγκη του Microsoft Office.

**Τ: Πώς ενσωματώνω το Aspose.Slides στο υπάρχον έργο Java;**  
Α: Προσθέστε την εξάρτηση Maven ή Gradle που εμφανίζεται παραπάνω, ή τοποθετήστε το JAR στην classpath, στη συνέχεια εισάγετε `com.aspose.slides.*`.

**Τ: Μπορώ να χρησιμοποιήσω το Aspose.Slides για μεγάλες παρουσιάσεις;**  
Α: Ναι, η βιβλιοθήκη διαχειρίζεται αποδοτικά παρουσιάσεις έως **2 GB** και υποστηρίζει streaming για να αποφύγετε τη φόρτωση ολόκληρου του αρχείου στη μνήμη.

**Τ: Ποιοι τύποι διαγραμμάτων είναι διαθέσιμοι εκτός από τα διαγράμματα φυσαλίδων;**  
Α: Υπάρχουν πάνω από **50 τύποι διαγραμμάτων**, συμπεριλαμβανομένων των ραβδογράμματα, γραμμικά, πίτες, ραδιογράμματα και καταρράκτες.

**Τ: Υπάρχει ενσωματωμένη υποστήριξη για το στυλ των στοιχείων του διαγράμματος;**  
Α: Απόλυτα. Μπορείτε να προσαρμόσετε χρώματα, γραμματοσειρές, περιγράμματα και ετικέτες δεδομένων μέσω των αντικειμένων `ChartSeries` και `ChartTitle` του διαγράμματος.

## Πόροι
- **Τεκμηρίωση**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Λήψη**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Αγορά**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Δωρεάν δοκιμή**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Προσωρινή άδεια**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Υποστήριξη**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Τελευταία ενημέρωση:** 2026-09-17  
**Δοκιμή με:** Aspose.Slides για Java 25.4 (jdk16)  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να προσθέσετε διάγραμμα σε PowerPoint χρησιμοποιώντας Aspose.Slides για Java: Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java δημιουργία διαγράμματος PowerPoint χρησιμοποιώντας Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Δημιουργία διαγράμματος PowerPoint Java – Αποθήκευση παρουσιάσεων με διαγράμματα χρησιμοποιώντας Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}