---
date: '2026-06-08'
description: Μάθετε πώς να μορφοποιήσετε τις ετικέτες δεδομένων γραφήματος και να
  δημιουργήσετε ακριβή γραμμικά διαγράμματα σε Java χρησιμοποιώντας το Aspose.Slides.
  Ιδανικό για παρουσιάσεις, οικονομικές αναφορές και παραδείγματα έργων γραμμικών
  διαγραμμάτων Java.
keywords:
- format chart data labels
- java line chart example
- Aspose.Slides chart formatting
- precise line chart Java
- data label formatting Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to format chart data labels and create precise line charts
    in Java using Aspose.Slides. Ideal for presentations, financial reports, and Java
    line chart example projects.
  headline: How to Format Chart Data Labels for Precise Line Charts in Java
  type: TechArticle
- description: Learn how to format chart data labels and create precise line charts
    in Java using Aspose.Slides. Ideal for presentations, financial reports, and Java
    line chart example projects.
  name: How to Format Chart Data Labels for Precise Line Charts in Java
  steps:
  - name: Create a New Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that holds all slide
      content. Begin by instantiating it:'
  - name: Add a Line Chart
    text: 'Insert the chart onto the first slide at the desired location: **Parameters
      Explained** - `ChartType.Line` – creates a line chart. - `(50, 50)` – X/Y coordinates
      on the slide. - `(450, 300)` – width and height in points.'
  - name: Enable Data Table
    text: 'Activate the data table so labels appear directly beneath the chart: Enabling
      `setDataTable(true)` makes raw values visible, aiding quick data verification.'
  - name: Set Number Format for Precision
    text: 'Apply a two‑decimal‑place format to ensure every label reads `0.00`: This
      uniform formatting eliminates rounding inconsistencies and improves visual clarity.'
  - name: Save the Presentation
    text: 'Write the presentation to disk:'
  type: HowTo
- questions:
  - answer: Access each data point’s `getFormat().getFillFormat().setFillType(FillType.Solid)`
      and set the desired `SolidFillColor`.
    question: How can I change the color of data labels in Aspose.Slides?
  - answer: Yes – retrieve each series via `chart.getChartData().getSeries().get_Item(index)`
      and call `setNumberFormat` with the format you need.
    question: Is it possible to apply different number formats to separate series?
  - answer: Ensure `setDataTable(true)` is enabled and that the underlying data points
      contain non‑null values.
    question: My chart shows blank data labels; what should I check?
  - answer: Reuse a single `Presentation` template, clone slides, and call `dispose()`
      on each temporary object to keep memory usage low.
    question: How do I efficiently generate many presentations with charts?
  - answer: Absolutely – the library processes typical 100‑row data sets in under
      200 ms, making it suitable for on‑the‑fly chart generation.
    question: Can Aspose.Slides be used in real‑time reporting dashboards?
  type: FAQPage
title: Πώς να μορφοποιήσετε τις ετικέτες δεδομένων γραφήματος για ακριβή γραμμικά
  διαγράμματα σε Java
url: /el/java/charts-graphs/create-line-charts-precision-data-formatting-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να μορφοποιήσετε τις ετικέτες δεδομένων γραφήματος για ακριβή γραμμικά διαγράμματα σε Java

## Εισαγωγή

Η δημιουργία ελκυστικών και ακριβών διαγραμμάτων είναι απαραίτητη όταν προετοιμάζετε σημαντικές παρουσιάσεις. **Μορφοποιήστε τις ετικέτες δεδομένων γραφήματος** γρήγορα και αξιόπιστα με το **Aspose.Slides for Java**, ώστε να αποφύγετε την επίπονη, επιρρεπή σε σφάλματα χειροκίνητη εργασία. Σε αυτό το σεμινάριο θα μάθετε πώς να ρυθμίσετε το περιβάλλον σας, να εφαρμόσετε ακριβή μορφοποίηση αριθμών στις ετικέτες δεδομένων και να ενσωματώσετε το παραγόμενο γραμμικό διάγραμμα σε αρχείο PowerPoint.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται τη μορφοποίηση των ετικετών δεδομένων γραφήματος;** Aspose.Slides for Java.
- **Πόσες γραμμές κώδικα απαιτούνται για ένα βασικό γραμμικό διάγραμμα;** Περίπου 8 γραμμές (χωρίς τις εισαγωγές).
- **Μπορώ να ορίσω προσαρμοσμένες μορφές αριθμών;** Ναι – χρησιμοποιήστε `setNumberFormat` στη σειρά δεδομένων του διαγράμματος.
- **Απαιτείται άδεια για παραγωγική χρήση;** Ναι, μια αγορασμένη ή προσωρινή άδεια αφαιρεί τους περιορισμούς αξιολόγησης.
- **Λειτουργεί αυτό σε όλες τις κύριες εκδόσεις JDK;** Πλήρως υποστηρίζεται σε JDK 8‑21.

## Τι είναι η «μορφοποίηση ετικετών δεδομένων γραφήματος»;

`format chart data labels` αναφέρεται στην εφαρμογή ενός συγκεκριμένου αριθμητικού ή κειμενικού μοτίβου στις τιμές που εμφανίζονται σε ένα διάγραμμα, εξασφαλίζοντας συνέπεια και αναγνωσιμότητα σε όλη τη διαφάνεια. Ορίζοντας μια ενιαία μορφή—όπως δύο δεκαδικά ψηφία, σύμβολα νομίσματος ή ποσοστών—εγγυάστε ότι κάθε σημείο δεδομένων παρουσιάζεται με τον ίδιο τρόπο, βοηθώντας το κοινό να ερμηνεύσει τις πληροφορίες γρήγορα και μειώνοντας τον κίνδυνο λανθασμένης ανάγνωσης τιμών.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides for Java για αυτήν την εργασία;

Το Aspose.Slides υποστηρίζει **30+ τύπους διαγραμμάτων** και μπορεί να επεξεργαστεί παρουσιάσεις με **200+ διαφάνειες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, παρέχοντας απόδοση υποδευτερολέπτου για τυπικά σύνολα δεδομένων. Το ευέλικτο API του επιτρέπει τον πλήρη προγραμματιστικό έλεγχο κάθε οπτικού στοιχείου, εξαλείφοντας την ανάγκη για χειροκίνητη επεξεργασία PowerPoint.

## Προαπαιτούμενα
- **Aspose.Slides for Java** – προσθέστε τη βιβλιοθήκη ως εξάρτηση Maven ή Gradle (δείτε τον οδηγό εγκατάστασης παρακάτω).  
- **Java Development Kit (JDK)** – έκδοση 8 ή νεότερη.  
- **Βασικές γνώσεις Java** – πρέπει να είστε εξοικειωμένοι με κλάσεις, μεθόδους και κατασκευές Maven/Gradle.

## Ρύθμιση του Aspose.Slides for Java

### Οδηγός Εγκατάστασης

Προσθέστε το Aspose.Slides ως εξάρτηση στο έργο σας:

**Maven**

Συμπεριλάβετε αυτό το απόσπασμα στο αρχείο `pom.xml` σας:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Μπορείτε επίσης να βρείτε την πιο πρόσφατη έκδοση στη σελίδα [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Gradle**

Προσθέστε αυτό στο αρχείο `build.gradle` σας:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Εναλλακτικά, κατεβάστε την πιο πρόσφατη έκδοση από το [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας

- **Free Trial** – κατεβάστε μια δοκιμαστική έκδοση από [Get a Free Trial or Temporary License](https://releases.aspose.com/slides/java/).  
- **Temporary License** – ζητήστε άδεια περιορισμένου χρόνου για εκτεταμένες δοκιμές μέσω της [Aspose's Temporary License page](https://purchase.aspose.com/temporary-license/).  
- **Purchase** – αποκτήστε πλήρη συνδρομή για παραγωγικές εγκαταστάσεις.  
- **Buy** – αγοράστε άδεια στο [Buy Aspose.Slides](https://purchase.aspose.com/buy).

### Βασική Αρχικοποίηση

`Presentation` είναι η κύρια κλάση του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη. Δημιουργήστε ένα νέο αντικείμενο `Presentation` για να ξεκινήσετε την προγραμματιστική δημιουργία διαφανειών.

## Οδηγός Υλοποίησης

Σε αυτήν την ενότητα θα περάσουμε από ένα **java line chart example** που δείχνει ακριβή μορφοποίηση ετικετών δεδομένων.

### Πώς να μορφοποιήσετε τις ετικέτες δεδομένων γραφήματος στο Aspose.Slides for Java;

Φορτώστε μια νέα παρουσίαση, προσθέστε ένα γραμμικό διάγραμμα και εφαρμόστε μορφή αριθμού με δύο δεκαδικά ψηφία σε κάθε ετικέτα – όλα σε λιγότερο από ένα λεπτό κώδικα. Η κλήση API `chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(i).setNumberFormat("0.00")` εγγυάται ομοιόμορφη ακρίβεια σε όλη τη σειρά.

### Δημιουργία Γραμμικού Διαγράμματος

**Επισκόπηση**

Θα δημιουργήσουμε ένα απλό γραμμικό διάγραμμα στην πρώτη διαφάνεια μιας νέας παρουσίασης. Αυτό περιλαμβάνει τον ορισμό των διαστάσεων του διαγράμματος, την προσθήκη σειράς δεδομένων και την ενεργοποίηση πίνακα δεδομένων για ορατότητα ετικετών.

#### Βήμα 1: Δημιουργία Νέας Παρουσίασης
`Presentation` είναι το αντικείμενο υψηλού επιπέδου του Aspose.Slides που περιέχει όλο το περιεχόμενο των διαφανειών. Ξεκινήστε με την δημιουργία του:
```java
Presentation pres = new Presentation();
```

#### Βήμα 2: Προσθήκη Γραμμικού Διαγράμματος
Εισάγετε το διάγραμμα στην πρώτη διαφάνεια στην επιθυμητή θέση:
```java
IChart chart = pres.getSlides().get_Item(0).getShapes()
                   .addChart(ChartType.Line, 50, 50, 450, 300);
```
**Επεξήγηση Παραμέτρων**
- `ChartType.Line` – δημιουργεί ένα γραμμικό διάγραμμα.  
- `(50, 50)` – συντεταγμένες X/Y στη διαφάνεια.  
- `(450, 300)` – πλάτος και ύψος σε points.

#### Βήμα 3: Ενεργοποίηση Πίνακα Δεδομένων
Ενεργοποιήστε τον πίνακα δεδομένων ώστε οι ετικέτες να εμφανίζονται απευθείας κάτω από το διάγραμμα:
```java
chart.setDataTable(true);
```
Η ενεργοποίηση του `setDataTable(true)` καθιστά ορατές τις ακατέργαστες τιμές, διευκολύνοντας την ταχεία επαλήθευση των δεδομένων.

#### Βήμα 4: Ορισμός Μορφής Αριθμού για Ακρίβεια
Εφαρμόστε μορφή με δύο δεκαδικά ψηφία ώστε κάθε ετικέτα να εμφανίζει `0.00`:
```java
chart.getChartData().getSeries().get_Item(0).setNumberFormatOfValues("#,##0.00");
```
Αυτή η ενιαία μορφοποίηση εξαλείφει τις ασυνέπειες στρογγυλοποίησης και βελτιώνει την οπτική σαφήνεια.

#### Βήμα 5: Αποθήκευση Παρουσίασης
Γράψτε την παρουσίαση στο δίσκο:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/PrecisionOfDatalabels_out.pptx", SaveFormat.Pptx);
```

### Συχνά Προβλήματα και Λύσεις
- **Write permissions** – βεβαιωθείτε ότι ο φάκελος εξόδου είναι εγγράψιμος.  
- **Missing data labels** – επιβεβαιώστε ότι κλήθηκε `setDataTable(true)` πριν από την αποθήκευση.  
- **Performance with large datasets** – καλέστε `presentation.dispose()` μετά την αποθήκευση για απελευθέρωση μνήμης.

## Πρακτικές Εφαρμογές
Οι δυνατότητες δημιουργίας διαγραμμάτων του Aspose.Slides for Java υπερβαίνουν τα βασικά παραδείγματα:

1. **Financial Reports** – εμφάνιση τριμηνιαίων κερδών με ακριβή δεκαδική ακρίβεια.  
2. **Academic Presentations** – παρουσίαση πειραματικών αποτελεσμάτων όπου κάθε εκατοστούς μετράει.  
3. **Sales Dashboards** – απεικόνιση μηνιαίων τάσεων με σαφώς μορφοποιημένους αριθμούς.  
4. **BI Integration** – ενσωμάτωση παραγόμενων διαγραμμάτων σε πύλες επιχειρηματικής νοημοσύνης για αυτοματοποιημένες αναφορές.

## Σκέψεις Απόδοσης
Κατά την επεξεργασία μεγάλων συνόλων δεδομένων ή παρουσιάσεων με πολλές διαφάνειες:

- Αποδεσμεύστε τα αντικείμενα `Presentation` μέσω `presentation.dispose()` για απελευθέρωση εγγενών πόρων.  
- Χρησιμοποιήστε σύντομες μορφές αριθμών (π.χ., “0.00”) για μικρότερο μέγεθος αρχείου ενώ διατηρείται η αναγνωσιμότητα.  
- Περιορίστε τον αριθμό σειρών ανά διάγραμμα σε κάτω από 20 για βέλτιστη ταχύτητα απόδοσης σε τυπικούς διακομιστές.

## Συχνές Ερωτήσεις

**Q: Πώς μπορώ να αλλάξω το χρώμα των ετικετών δεδομένων στο Aspose.Slides;**  
A: Πρόσβαση σε κάθε σημείο δεδομένων μέσω `getFormat().getFillFormat().setFillType(FillType.Solid)` και ορίστε το επιθυμητό `SolidFillColor`.

**Q: Είναι δυνατόν να εφαρμόσω διαφορετικές μορφές αριθμών σε ξεχωριστές σειρές;**  
A: Ναι – ανακτήστε κάθε σειρά μέσω `chart.getChartData().getSeries().get_Item(index)` και καλέστε `setNumberFormat` με τη μορφή που χρειάζεστε.

**Q: Το διάγραμμα μου εμφανίζει κενές ετικέτες δεδομένων· τι πρέπει να ελέγξω;**  
A: Βεβαιωθείτε ότι το `setDataTable(true)` είναι ενεργοποιημένο και ότι τα υποκείμενα σημεία δεδομένων περιέχουν μη‑null τιμές.

**Q: Πώς μπορώ να δημιουργήσω αποδοτικά πολλές παρουσιάσεις με διαγράμματα;**  
A: Επαναχρησιμοποιήστε ένα πρότυπο `Presentation`, κλωνοποιήστε διαφάνειες και καλέστε `dispose()` σε κάθε προσωρινό αντικείμενο για χαμηλή χρήση μνήμης.

**Q: Μπορεί το Aspose.Slides να χρησιμοποιηθεί σε πίνακες ελέγχου αναφοράς σε πραγματικό χρόνο;**  
A: Απόλυτα – η βιβλιοθήκη επεξεργάζεται τυπικά σύνολα δεδομένων 100 γραμμών σε κάτω από 200 ms, καθιστώντας την κατάλληλη για δημιουργία διαγραμμάτων «on‑the‑fly».

Για πρόσθετη βοήθεια, επισκεφθείτε το [Aspose Community Forum](https://forum.aspose.com/c/slides/11).

## Συμπέρασμα
Τώρα έχετε ένα πλήρες **java line chart example** που μορφοποιεί τις ετικέτες δεδομένων του διαγράμματος με ακρίβεια, αποθηκεύει το αποτέλεσμα και ενσωματώνεται άψογα σε οποιαδήποτε ροή εργασίας PowerPoint. Εξερευνήστε την πλήρη [documentation](https://reference.aspose.com/slides/java/) και το [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/) για να πειραματιστείτε με άλλους τύπους διαγραμμάτων, animations και προχωρημένες επιλογές στυλ.

### Επόμενα Βήματα
- Αυτοματοποιήστε τη δημιουργία διαγραμμάτων από πολλαπλές πηγές δεδομένων.  
- Συνδυάστε πολλαπλούς τύπους διαγραμμάτων σε μία διαφάνεια για πιο πλούσια αφήγηση.  
- Εξερευνήστε την εξαγωγή PDF του Aspose.Slides για κοινή χρήση διαγραμμάτων με χρήστες που δεν χρησιμοποιούν PowerPoint.

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Σχετικά Μαθήματα

- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Create & Format Charts in Java Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)
- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}