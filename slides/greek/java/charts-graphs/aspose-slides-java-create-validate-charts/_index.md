---
date: '2026-07-22'
description: Μάθετε πώς να προσθέσετε clustered column chart σε Java με Aspose.Slides,
  καλύπτοντας τη δημιουργία του chart βήμα‑βήμα, την επαλήθευση της διάταξης και πώς
  να προσθέσετε το chart στη διαφάνεια.
keywords:
- add clustered column chart
- how to add chart
- create chart in java
- add chart to slide
lastmod: '2026-07-22'
og_description: Προσθήκη clustered column chart σε Java χρησιμοποιώντας Aspose.Slides.
  Αυτός ο οδηγός δείχνει τη δημιουργία βήμα‑βήμα, την επαλήθευση και πώς να προσθέσετε
  το chart στη διαφάνεια σε αρχείο PowerPoint.
og_image_alt: 'Developer guide: add clustered column chart in Java using Aspose.Slides'
og_title: Προσθήκη clustered column chart σε Java με Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn how to add clustered column chart in Java with Aspose.Slides,
    covering step‑by‑step chart creation, layout validation, and how to add chart
    to slide.
  headline: How to add clustered column chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add clustered column chart in Java with Aspose.Slides,
    covering step‑by‑step chart creation, layout validation, and how to add chart
    to slide.
  name: How to add clustered column chart in Java with Aspose.Slides
  steps:
  - name: Set Up Your Presentation
    text: 'Load an existing file or start a new one:'
  - name: Add a clustered column chart
    text: '`ChartType.ClusteredColumn` specifies a clustered column chart type. Here
      we **add clustered column chart** to the first slide at a specific location:'
  - name: Validate the chart layout
    text: '`validateChartLayout()` checks the chart''s geometry and ensures elements
      are correctly positioned. After placing the chart, make sure everything lines
      up correctly:'
  type: HowTo
- questions:
  - answer: It’s a powerful Java library for creating, editing, and converting PowerPoint
      files without Microsoft Office.
    question: What is Aspose.Slides?
  - answer: Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/)
      and follow the request steps.
    question: How do I obtain a temporary license?
  - answer: Yes, Aspose.Slides supports bar, line, pie, area, and many more chart
      types.
    question: Can I create other chart types besides clustered column?
  - answer: Absolutely. Use `chart.getChartData().getSeries().add(...)` and `chart.getChartData().getCategories().add(...)`.
    question: Is there a way to add data to the chart programmatically?
  - answer: The Java version is cross‑platform and runs on Windows, Linux, and macOS.
    question: Does the library work on all operating systems?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java charting
- create chart in java
- add chart to slide
title: Πώς να προσθέσετε clustered column chart σε Java με Aspose.Slides
url: /el/java/charts-graphs/aspose-slides-java-create-validate-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να προσθέσετε ένα συγκεντρωμένο γράφημα στήλης σε Java με το Aspose.Slides

Στον σημερινό κόσμο που βασίζεται στα δεδομένα, η οπτικοποίηση πληροφοριών μέσω γραφημάτων είναι απαραίτητη για τη μετατροπή ακατέργαστων αριθμών σε σαφείς πληροφορίες. Εάν χρειάζεται να **add clustered column chart** σε μια παρουσίαση PowerPoint προγραμματιστικά, το Aspose.Slides for Java παρέχει ένα καθαρό, πλήρως διαχειριζόμενο API που σας επιτρέπει να δημιουργείτε, να διαμορφώνετε και να επικυρώνετε γραφήματα χωρίς να ανοίγετε ποτέ το PowerPoint. Είτε χτίζετε μια μηχανή αναφορών, μια εκπαιδευτική εφαρμογή ή έναν πίνακα ελέγχου σε πραγματικό χρόνο, αυτό το tutorial σας καθοδηγεί βήμα‑βήμα—from library setup to saving the final presentation.

## Γρήγορες Απαντήσεις
- **What library lets you add clustered column chart in Java?** Aspose.Slides for Java.
- **Which chart type is demonstrated?** A clustered column chart.
- **How do you verify the chart layout?** Call `validateChartLayout()` on the chart object.
- **Can you retrieve the plot area size?** Yes, via `chart.getPlotArea().getActualX()` and related methods.
- **What is the final step?** Save the presentation with `pres.save(...)`.

## Τι Θα Μάθετε
- How to set up Aspose.Slides for Java in your project  
- **How to add chart** – specifically a clustered column chart – and add it to a slide  
- **How to validate chart** layout programmatically  
- Ανάκτηση και ερμηνεία διαστάσεων περιοχής σχεδίασης  
- Αποθήκευση της παρουσίασης με το ενημερωμένο γράφημα  

## Προαπαιτούμενα
- **Java Development Kit (JDK)** – JDK 16 ή νεότερο.  
- **Aspose.Slides for Java** – η βιβλιοθήκη (θα χρησιμοποιήσουμε την έκδοση 25.4 στα παραδείγματα).  
- **IDE** – IntelliJ IDEA, Eclipse ή οποιονδήποτε επεξεργαστή συμβατό με Java.  

## Ρύθμιση του Aspose.Slides για Java
Μπορείτε να ενσωματώσετε το Aspose.Slides στο έργο σας με Maven, Gradle ή άμεση λήψη.

### Maven
Το απόσπασμα Maven προσθέτει τη βιβλιοθήκη Aspose.Slides στο classpath του έργου σας.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Συμπεριλάβετε αυτή τη γραμμή στο αρχείο `build.gradle` για να κατεβάσετε τη βιβλιοθήκη από το Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση Λήψη
Εναλλακτικά, κατεβάστε τη βιβλιοθήκη απευθείας από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Απόκτηση Άδειας
- **Free Trial** – περιορισμένες λειτουργίες για γρήγορη αξιολόγηση.  
- **[Aspose Temporary License](https://purchase.aspose.com/temporary-license/)** – ζητήστε ένα βραχυπρόθεσμο κλειδί για πλήρη δοκιμή.  
- **Purchase** – αγοράστε συνδρομή για χρήση σε παραγωγή.

#### Βασική Αρχικοποίηση και Ρύθμιση
`Presentation` είναι η βασική κλάση του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη. Μετά τη δημιουργία ενός αντικειμένου μπορείτε να αρχίσετε να προσθέτετε διαφάνειες, σχήματα ή γραφήματα.

```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your chart creation logic will go here
        presentation.dispose();  // Clean up resources
    }
}
```

## Πώς να προσθέσετε γράφημα σε διαφάνεια και να δημιουργήσετε ένα συγκεντρωμένο γράφημα στήλης
`Presentation` αντιπροσωπεύει το έγγραφο PowerPoint που επεξεργάζεστε. Φορτώστε ή δημιουργήστε ένα `Presentation`, αποκτήστε πρόσβαση στην πρώτη διαφάνεια και καλέστε `addChart` με `ChartType.ClusteredColumn`. Αυτό εισάγει ένα πλήρως λειτουργικό συγκεντρωμένο γράφημα στήλης στις καθορισμένες συντεταγμένες, μετά από το οποίο μπορείτε να γεμίσετε σειρές και κατηγορίες πριν αποθηκεύσετε. Το γράφημα θα υιοθετήσει αυτόματα το θέμα της διαφάνειας και μπορείτε να προσαρμόσετε περαιτέρω χρώματα, τίτλους και υπομνήματα όπως χρειάζεται.

Η δημιουργία γραφημάτων σε παρουσιάσεις είναι απλή με το Aspose.Slides. Οι παρακάτω ενότητες αναλύουν κάθε βήμα.

### Βήμα 1: Ρυθμίστε την Παρουσίασή Σας
Φορτώστε ένα υπάρχον αρχείο ή ξεκινήστε ένα νέο:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.Pptx");
```

### Βήμα 2: Προσθέστε ένα συγκεντρωμένο γράφημα στήλης
`ChartType.ClusteredColumn` ορίζει τον τύπο συγκεντρωμένου γραφήματος στήλης. Εδώ **add clustered column chart** στην πρώτη διαφάνεια σε συγκεκριμένη θέση:

```java
import com.aspose.slides.ShapeType;

Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 350
);
```

### Βήμα 3: Επικυρώστε τη διάταξη του γραφήματος
`validateChartLayout()` ελέγχει τη γεωμετρία του γραφήματος και διασφαλίζει ότι τα στοιχεία είναι σωστά τοποθετημένα. Μετά την τοποθέτηση του γραφήματος, βεβαιωθείτε ότι όλα ευθυγραμμίζονται σωστά:

```java
chart.validateChartLayout();
```

#### Γιατί η επικύρωση είναι σημαντική
`validateChartLayout()` ελέγχει για αλληλοεπικάλυψη στοιχείων, ελλιπείς άξονες και άλλες οπτικές ασυνέπειες, διασφαλίζοντας ότι το κοινό σας βλέπει ένα επαγγελματικό γράφημα.

## Πώς να λάβετε διαστάσεις περιοχής σχεδίασης από ένα γράφημα
`Chart` είναι το αντικείμενο που περιλαμβάνει όλες τις οπτικές και δεδομενικές πτυχές ενός γραφήματος. `getPlotArea()` επιστρέφει το ορθογώνιο της περιοχής σχεδίασης του γραφήματος, επιτρέποντας ακριβή ευθυγράμμιση πρόσθετων σχημάτων. Πρόσβαση στο αντικείμενο γραφήματος για ανάγνωση των μετρικών της περιοχής σχεδίασης:

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

Ανάκτηση διαστάσεων περιοχής σχεδίασης:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();

System.out.println("Plot Area: X=" + x + ", Y=" + y + ", Width=" + w + ", Height=" + h);
```

Αυτές οι τιμές είναι χρήσιμες όταν χρειάζεται να ευθυγραμμίσετε άλλα σχήματα ή να υπολογίσετε προσαρμοσμένα περιθώρια.

## Πώς να αποθηκεύσετε την παρουσίαση με το νέο γράφημα
`Presentation` είναι το κοντέινερ που περιέχει όλες τις διαφάνειες, σχήματα και γραφήματα. Καλέστε `save` στο αντικείμενο `Presentation`, καθορίζοντας τη μορφή εξόδου (π.χ., PPTX). Αυτό γράφει το τροποποιημένο deck στο δίσκο, διατηρώντας το νεοπροστέθηκε γράφημα και τυχόν επικυρώσεις διάταξης που εκτελέσατε, ενώ επίσης απελευθερώνει τους εγγενείς πόρους όταν αποδεσμευτεί.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
```

## Πρακτικές Εφαρμογές
- **Business Reporting** – Αυτοματοποιήστε τα τριμηνιαία decks με ενημερωμένα γραφήματα.  
- **Educational Tools** – Δημιουργήστε διαφάνειες διαλέξεων που απεικονίζουν τάσεις δεδομένων σε πραγματικό χρόνο.  
- **Dashboard Integration** – Εξάγετε αναλύσεις σε πραγματικό χρόνο σε PowerPoint για εκτελεστικές ενημερώσεις.

## Σκέψεις Απόδοσης
- Αποδεσμεύστε το αντικείμενο `Presentation` (`pres.dispose()`) για να ελευθερώσετε τους εγγενείς πόρους.  
- Κατά την επεξεργασία μεγάλων decks, επαναχρησιμοποιήστε αντικείμενα γραφήματος όπου είναι δυνατόν για να μειώσετε την κατανάλωση μνήμης.  
- Προτιμήστε streaming APIs για τεράστιες συλλογές δεδομένων ώστε να αποφύγετε τη φόρτωση όλων στη μνήμη ταυτόχρονα.  
- Το Aspose.Slides υποστηρίζει **πάνω από 40 τύπους γραφημάτων** και μπορεί να αποδίδει γραφήματα με **έως 10.000 σημεία δεδομένων ανά σειρά** χωρίς αισθητή καθυστέρηση.

## Κοινά Προβλήματα & Επίλυση
| Σύμπτωμα | Πιθανή Αιτία | Διόρθωση |
|---------|--------------|----------|
| Το γράφημα εμφανίζεται κενό | Δεν προστέθηκαν σειρές δεδομένων | Χρησιμοποιήστε `chart.getChartData().getSeries().add(...)` πριν από την επικύρωση. |
| Η επικύρωση διάταξης προκαλεί σφάλματα | Αλληλοεπικάλυψη σχημάτων στη διαφάνεια | Ρυθμίστε τις συντεταγμένες X/Y ή αυξήστε τις διαστάσεις του γραφήματος. |
| `OutOfMemoryError` σε μεγάλα αρχεία | Μη αποδέσμευση αντικειμένων | Καλέστε `presentation.dispose()` σε ένα `finally` block. |

## Συχνές Ερωτήσεις

**Q: What is Aspose.Slides?**  
A: It’s a powerful Java library for creating, editing, and converting PowerPoint files without Microsoft Office.

**Q: How do I obtain a temporary license?**  
A: Visit [Aspose Temporary License](https://purchase.aspose.com/temporary-license/) and follow the request steps.

**Q: Can I create other chart types besides clustered column?**  
A: Yes, Aspose.Slides supports bar, line, pie, area, and many more chart types.

**Q: Is there a way to add data to the chart programmatically?**  
A: Absolutely. Use `chart.getChartData().getSeries().add(...)` and `chart.getChartData().getCategories().add(...)`.

**Q: Does the library work on all operating systems?**  
A: The Java version is cross‑platform and runs on Windows, Linux, and macOS.

## Πόροι
- [Τεκμηρίωση](https://reference.aspose.com/slides/java/)
- [Λήψη Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Αγορά Συνδρομής](https://purchase.aspose.com/buy)
- [Δωρεάν Δοκιμή](https://releases.aspose.com/slides/java/)
- [Αίτηση για Προσωρινή Άδεια](https://purchase.aspose.com/temporary-license/)
- [Φόρουμ Υποστήριξης](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Γράφημα σε Java με το Aspose.Slides: Ολοκληρωμένος Οδηγός](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Δημιουργία και Επικύρωση Διατάξεων Γραφημάτων σε PowerPoint Χρησιμοποιώντας Aspose.Slides for Java | SEO-Βελτιστοποιημένος Οδηγός](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)
- [Πώς να Προσθέσετε και να Διαμορφώσετε Γραφήματα σε Παρουσιάσεις Χρησιμοποιώντας Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}