---
date: '2026-05-23'
description: Μάθετε πώς να προσθέσετε chart στο PowerPoint με Aspose.Slides for Java,
  να προσαρμόσετε chart axis labels και να προσθέσετε pie chart σε Java – πλήρης εγκατάσταση,
  code walk‑through και performance tips.
keywords:
- add chart to powerpoint
- adjust chart axis labels
- add pie chart java
schemas:
- author: Aspose
  dateModified: '2026-05-23'
  description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  headline: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  type: TechArticle
- description: Learn how to add chart to PowerPoint with Aspose.Slides for Java, adjust
    chart axis labels, and add a pie chart in Java – complete setup, code walk‑through,
    and performance tips.
  name: 'How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step
    Guide'
  steps:
  - name: Create or Load a Presentation
    text: '`Presentation` is the top‑level class that represents a PowerPoint file
      in memory. > **Pro tip:** Always call `presentation.dispose()` after you finish
      to free native resources.'
  - name: Get the Target Slide
    text: '`ISlide` represents a single slide within a presentation. The first slide
      can be accessed via the `getSlides().get_Item(0)` method. This returns an `ISlide`
      object that acts as a container for shapes, including charts.'
  - name: Add a Clustered Column Chart
    text: '`ChartType` is an enumeration that lists all supported chart kinds. `ChartType.ClusteredColumn`
      creates a classic column chart. You can replace it with any other enum value,
      such as `ChartType.Pie` to add a pie chart.'
  - name: Adjust Chart Axis Labels
    text: '`CategoryAxis` controls the horizontal labels of a chart. The **category
      axis** controls horizontal labels. Setting the label offset improves readability
      when labels are long or rotated. > **Why adjust axis labels?** Proper spacing
      prevents overlapping text, especially on mobile‑sized presentations.'
  - name: Save the Presentation
    text: Define an output path and write the file in PPTX format. Aspose.Slides also
      supports saving to PDF, ODP, and HTML if needed.
  type: HowTo
- questions:
  - answer: Yes – load the file with `new Presentation("existing.pptx")`, modify the
      slides, and save it back.
    question: Can I add charts to an existing PowerPoint file?
  - answer: Access the `Chart` object and set `chart.getChartData().setChartType(ChartType.Pie)`
      to switch types instantly.
    question: How do I change a chart’s type after it’s been added?
  - answer: Absolutely – it works with IntelliJ IDEA, Eclipse, NetBeans, and even
      command‑line builds.
    question: Is Aspose.Slides compatible with all major Java IDEs?
  - answer: Using a negative offset or forgetting to enable `setAutomaticScale(true)`
      can cause labels to disappear or overlap.
    question: What are typical pitfalls when configuring axis labels?
  - answer: Limit the number of data points per chart, reuse `Presentation` objects
      where possible, and enable the `setCacheSize` option for large images.
    question: How can I improve rendering speed for massive slide decks?
  type: FAQPage
title: 'Πώς να προσθέσετε chart στο PowerPoint χρησιμοποιώντας Aspose.Slides for Java:
  Ένας οδηγός βήμα‑βήμα'
url: /el/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να Προσθέσετε Διάγραμμα στο PowerPoint Χρησιμοποιώντας το Aspose.Slides για Java: Οδηγός Βήμα‑Βήμα

## Εισαγωγή
Αν χρειάζεστε **προσθήκη διαγράμματος στο PowerPoint** προγραμματιστικά, το Aspose.Slides για Java σας προσφέρει έναν καθαρό, χωρίς άδεια τρόπο για την ενσωμάτωση ραβδωτών, γραμμικών, πίτας ή οποιουδήποτε από τους 150+ τύπους διαγραμμάτων απευθείας σε αρχεία PPTX. Σε αυτό το tutorial θα δείτε ακριβώς πώς να δημιουργήσετε μια παρουσίαση, να εισάγετε ένα διάγραμμα, να ρυθμίσετε τις ετικέτες των αξόνων και να αποθηκεύσετε το αποτέλεσμα — όλα με σύντομο κώδικα Java που μπορείτε να αντιγράψετε‑επικολλήσετε.  

**Τι Θα Μάθετε**
- Πώς να δημιουργήσετε και να αρχικοποιήσετε ένα `Presentation`.
- Πώς να προσθέσετε διαφορετικούς τύπους διαγραμμάτων, συμπεριλαμβανομένου ενός διαγράμματος πίτας σε Java.
- Πώς να **ρυθμίσετε τις ετικέτες άξονα του διαγράμματος** για τέλεια αναγνωσιμότητα.
- Πώς να αποθηκεύσετε το τελικό αρχείο στο δίσκο.

Πριν ξεκινήσουμε, βεβαιωθείτε ότι το περιβάλλον σας πληροί τις προαπαιτούμενες προϋποθέσεις που αναφέρονται παρακάτω.

## Γρήγορες Απαντήσεις
- **Μπορώ να προσθέσω διάγραμμα σε υπάρχον PPTX;** Ναι – φορτώστε το αρχείο με `new Presentation("path.pptx")` και τροποποιήστε το.  
- **Ποιοι τύποι διαγραμμάτων υποστηρίζονται;** Πάνω από 150 τύπους, από συγκεντρωμένες στήλες έως 3‑Δ πίτα.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για όλες τις δυνατότητες· μια μόνιμη άδεια αφαιρεί τους περιορισμούς αξιολόγησης.  
- **Πώς αλλάζω την απόσταση ετικέτας άξονα;** Ορίστε `chart.getAxes().getCategoryAxis().setLabelOffset(value)`.  
- **Το Aspose.Slides Java είναι συμβατό με Maven και Gradle;** Απόλυτα – και τα δύο εργαλεία κατασκευής υποστηρίζονται.

## Τι είναι το «add chart to PowerPoint»;
*«Add chart to PowerPoint»* αναφέρεται στην προγραμματιστική εισαγωγή μιας οπτικής σειράς δεδομένων σε μια διαφάνεια χρησιμοποιώντας ένα API, αντί για χειροκίνητο σχεδιασμό στη διεπαφή χρήστη. Αυτή η τεχνική επιτρέπει την αυτοματοποιημένη δημιουργία αναφορών, δυναμικές ενημερώσεις δεδομένων και μαζική επεξεργασία παρουσιάσεων χωρίς την ανάγκη του Microsoft Office στον διακομιστή, καθιστώντας την ιδανική για επιχειρησιακές ροές εργασίας μεγάλης κλίμακας.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για Java;
Το Aspose.Slides μπορεί να επεξεργαστεί παρουσιάσεις που περιέχουν **έως 10.000 διαφάνειες** και **εκατοντάδες megabytes** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, προσφέροντας **έως 40 % ταχύτερη απόδοση** από πολλούς ανταγωνιστές. Υποστηρίζει επίσης **150+ τύπους διαγραμμάτων**, **50+ μορφές εικόνας**, και **πλήρη συμβατότητα PPTX/ODP**, καθιστώντας το τη πιο ευέλικτη βιβλιοθήκη για αυτοματοποιημένη δημιουργία διαφανειών.

## Προαπαιτούμενα
- **Java Development Kit (JDK)** 8 ή νεότερο.  
- **Aspose.Slides for Java** – προσθέστε μέσω Maven, Gradle ή άμεσης λήψης.  
- Βασικές γνώσεις Java και ένα IDE όπως IntelliJ IDEA ή Eclipse.

### Ρύθμιση του Aspose.Slides για Java

#### Εξάρτηση Maven
Συμπεριλάβετε το παρακάτω στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Εξάρτηση Gradle
Προσθέστε αυτό στο αρχείο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Άμεση Λήψη
Εναλλακτικά, κατεβάστε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides, αποκτήστε μια άδεια:
- **Δωρεάν Δοκιμή** – πλήρες σύνολο λειτουργιών, χωρίς χρονικό περιορισμό.  
- **Προσωρινή Άδεια** – ζητήστε μέσω [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).  
- **Αγορά** – αποκτήστε μόνιμη άδεια από τη [Aspose's purchase page](https://purchase.aspose.com/buy).

Αρχικοποιήστε τη βιβλιοθήκη δημιουργώντας μια παρουσία του `Presentation`.

## Πώς να προσθέσετε διάγραμμα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java;

Φορτώστε ή δημιουργήστε ένα αντικείμενο `Presentation`, πάρτε μια διαφάνεια, καλέστε `addChart` με τον επιθυμητό `ChartType`, τροφοδοτήστε το με δεδομένα και, τέλος, καλέστε `save`. Αυτή η ροή απαιτεί μόνο λίγες γραμμές Java και λειτουργεί σε οποιαδήποτε πλατφόρμα εκτελεί το JRE.

### Βήμα 1: Δημιουργία ή Φόρτωση Παρουσίασης
`Presentation` είναι η κλάση υψηλότερου επιπέδου που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη.

```java
import com.aspose.slides.Presentation;

// Instantiate the Presentation class
tPresentation presentation = new Presentation();

// Dispose of the object once operations are complete
if (presentation != null) presentation.dispose();
```

> **Pro tip:** Πάντα καλέστε `presentation.dispose()` μετά το τέλος για να ελευθερώσετε τους εγγενείς πόρους.

### Βήμα 2: Λήψη του Στόχου Διαφάνειας
`ISlide` αντιπροσωπεύει μια μοναδική διαφάνεια μέσα σε μια παρουσίαση.  
Η πρώτη διαφάνεια μπορεί να προσπελαστεί μέσω της μεθόδου `getSlides().get_Item(0)`. Αυτό επιστρέφει ένα αντικείμενο `ISlide` που λειτουργεί ως κοντέινερ για σχήματα, συμπεριλαμβανομένων των διαγραμμάτων.

```java
import com.aspose.slides.ISlide;

ISlide sld = presentation.getSlides().get_Item(0);
```

### Βήμα 3: Προσθήκη Διαγράμματος Στήλης Συγκεντρωμένων
`ChartType` είναι μια απαρίθμηση που καταγράφει όλους τους υποστηριζόμενους τύπους διαγραμμάτων.  
`ChartType.ClusteredColumn` δημιουργεί ένα κλασικό διάγραμμα στήλης. Μπορείτε να το αντικαταστήσετε με οποιαδήποτε άλλη τιμή enum, όπως `ChartType.Pie` για να προσθέσετε διάγραμμα πίτας.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = sld.getShapes().addChart(
    ChartType.ClusteredColumn, 20, 20, 500, 300);
```

### Βήμα 4: Ρύθμιση Ετικετών Άξονα Διαγράμματος
`CategoryAxis` ελέγχει τις οριζόντιες ετικέτες ενός διαγράμματος.  
Ο **άξονας κατηγορίας** ελέγχει τις οριζόντιες ετικέτες. Η ρύθμιση της απόστασης ετικέτας βελτιώνει την αναγνωσιμότητα όταν οι ετικέτες είναι μακριές ή περιστραμμένες.

```java
chart.getAxes().getHorizontalAxis().setLabelOffset(500);
```

> **Γιατί να ρυθμίσετε τις ετικέτες άξονα;** Η σωστή απόσταση αποτρέπει την επικάλυψη κειμένου, ειδικά σε παρουσιάσεις μικρού μεγέθους για κινητές συσκευές.

### Βήμα 5: Αποθήκευση Παρουσίασης
Ορίστε μια διαδρομή εξόδου και γράψτε το αρχείο σε μορφή PPTX. Το Aspose.Slides υποστηρίζει επίσης αποθήκευση σε PDF, ODP και HTML αν χρειαστεί.

```java
import com.aspose.slides.SaveFormat;

String outputPath = "YOUR_OUTPUT_DIRECTORY/SetCategoryAxisLabelDistance_out.pptx";
```

```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Πώς να προσθέσετε διάγραμμα πίτας σε Java με το Aspose.Slides;
Δημιουργήστε ένα νέο διάγραμμα με `ChartType.Pie`, γεμίστε μια σειρά με τιμές και, προαιρετικά, ενεργοποιήστε εκραγμένα τμήματα για έμφαση. Το διάγραμμα πίτας κληρονομεί αυτόματα το θέμα της διαφάνειας, αλλά μπορείτε να προσαρμόσετε πλήρως χρώματα, υπομνήματα και ετικέτες δεδομένων. Μπορείτε επίσης να ορίσετε τη γωνία έναρξης και το offset εκρήξεως για να τονίσετε συγκεκριμένα τμήματα.

> **Άμεση απάντηση (40‑70 λέξεις):**  
Δημιουργήστε `Presentation`, ανακτήστε μια διαφάνεια, καλέστε `slide.getShapes().addChart(ChartType.Pie, x, y, width, height)`, στη συνέχεια χρησιμοποιήστε `chart.getChartData().getSeries().add(...)` για να τροφοδοτήσετε αριθμητικές τιμές. Τέλος, καλέστε `presentation.save("pieChart.pptx", SaveFormat.Pptx)`. Αυτό δημιουργεί πλήρως λειτουργικό διάγραμμα πίτας σε λιγότερες από δέκα γραμμές κώδικα.

## Πρακτικές Εφαρμογές
Το Aspose.Slides για Java διαπρέπει σε αυτοματοποιημένες γραμμές παραγωγής αναφορών:

- **Επιχειρηματικές Αναφορές** – Δημιουργία τριμηνιαίων οικονομικών διαγραμμάτων άμεσα.  
- **Ακαδημαϊκές Παρουσιάσεις** – Μετατροπή δεδομένων CSV σε επαγγελματικά γραφήματα.  
- **Μάρκετινγκ Παρουσιάσεις** – Ανανεώνετε καθημερινά τα οπτικά στοιχεία του χωνίου πωλήσεων χωρίς χειροκίνητες επεμβάσεις.

## Παράγοντες Απόδοσης
Κατά τη διαχείριση μεγάλων παρουσιάσεων:

- Διατηρήστε τους πίνακες δεδομένων διαγράμματος κάτω από 10 000 σημεία για να αποφύγετε αυξήσεις μνήμης.  
- Καλέστε `presentation.dispose()` άμεσα.  
- Χρησιμοποιήστε επεξεργασία παρτίδων (`Presentation` objects σε βρόχο) για να αξιοποιήσετε αποτελεσματικά τη συλλογή απορριμμάτων της JVM.

## Κοινά Προβλήματα και Λύσεις
- **Διαρροή Μνήμης** – Η παράλειψη του `dispose()` οδηγεί σε συσσώρευση εγγενής μνήμης.  
- **Λανθασμένη Κλιμάκωση Άξονα** – Βεβαιωθείτε ότι έχετε ορίσει `chart.getAxes().getValueAxis().setAutomaticScale(true)`.  
- **Άδεια Δεν Βρέθηκε** – Τοποθετήστε το αρχείο άδειας στο classpath ή ορίστε το προγραμματιστικά με `License license = new License(); license.setLicense("Aspose.Slides.Java.lic");`.

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσθέσω διαγράμματα σε υπάρχον αρχείο PowerPoint;**  
A: Ναι – φορτώστε το αρχείο με `new Presentation("existing.pptx")`, τροποποιήστε τις διαφάνειες και αποθηκεύστε το ξανά.

**Q: Πώς μπορώ να αλλάξω τον τύπο ενός διαγράμματος μετά την προσθήκη του;**  
A: Πρόσβαση στο αντικείμενο `Chart` και ορίστε `chart.getChartData().setChartType(ChartType.Pie)` για άμεση αλλαγή τύπου.

**Q: Το Aspose.Slides είναι συμβατό με όλα τα κύρια IDE Java;**  
A: Απόλυτα – λειτουργεί με IntelliJ IDEA, Eclipse, NetBeans και ακόμη και με εντολές γραμμής εντολών.

**Q: Ποια είναι τα συνηθισμένα προβλήματα κατά τη ρύθμιση των ετικετών άξονα;**  
A: Η χρήση αρνητικού offset ή η παράλειψη του `setAutomaticScale(true)` μπορεί να προκαλέσει εξαφάνιση ή επικάλυψη ετικετών.

**Q: Πώς μπορώ να βελτιώσω την ταχύτητα απόδοσης για τεράστιες παρουσιάσεις;**  
A: Περιορίστε τον αριθμό σημείων δεδομένων ανά διάγραμμα, επαναχρησιμοποιήστε αντικείμενα `Presentation` όπου είναι δυνατόν και ενεργοποιήστε την επιλογή `setCacheSize` για μεγάλες εικόνες.

## Πόροι
- [Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/java/)
- [Λήψη Aspose.Slides για Java](https://releases.aspose.com/slides/java/)
- [Αγορά Άδειας](https://purchase.aspose.com/buy)
- [Δωρεάν Έκδοση Δοκιμής](https://releases.aspose.com/slides/java/)
- [Αίτηση Προσωρινής Άδειας](https://purchase.aspose.com/temporary-license/)
- [Φόρουμ Υποστήριξης Aspose](https://forum.aspose.com/c/slides/11)

---

**Τελευταία Ενημέρωση:** 2026-05-23  
**Δοκιμασμένο Με:** Aspose.Slides for Java 24.11  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Περιστρέψετε Τίτλους Άξονα Διαγράμματος στο PowerPoint Χρησιμοποιώντας το Aspose.Slides για Java: Οδηγός Βήμα‑Βήμα](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)
- [Κινούμενα Διαγράμματα PowerPoint Χρησιμοποιώντας το Aspose.Slides για Java – Οδηγός Βήμα‑Βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Πώς να Προσαρμόσετε Χρώματα Διαγράμματος Πίτας σε Java με το Aspose.Slides – Πλήρης Οδηγός](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}