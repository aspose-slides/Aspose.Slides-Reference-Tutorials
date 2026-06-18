---
date: '2026-06-08'
description: Μάθετε πώς να προσθέσετε series σε chart και να προσαρμόσετε stacked
  column charts σε .NET presentations χρησιμοποιώντας Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Προσθήκη Series σε Chart με Aspose.Slides for Java στο .NET
url: /el/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Κατακτώντας την Προσαρμογή Διαγραμμάτων σε Παρουσιάσεις .NET με Aspose.Slides για Java

## Εισαγωγή
Στον κόσμο των παρουσιάσεων που βασίζονται σε δεδομένα, τα διαγράμματα είναι απαραίτητα εργαλεία που μετατρέπουν ακατέργαστους αριθμούς σε συναρπαστικές οπτικές ιστορίες. Όταν χρειάζεται να **προσθέσετε σειρά σε διάγραμμα** προγραμματιστικά, ειδικά μέσα σε αρχεία παρουσίασης .NET, η εργασία μπορεί να φαίνεται δύσκολη. Ευτυχώς, το **Aspose.Slides for Java** παρέχει ένα ισχυρό, γλώσσα‑ανεξάρτητο API που κάνει τη δημιουργία και προσαρμογή διαγραμμάτων απλή — ακόμη και όταν ο προορισμός σας είναι ένα .NET PPTX. Αυτός ο οδηγός σας καθοδηγεί στη προσθήκη σειρών, στην κατασκευή ενός στοίβακτου διαγράμματος στήλης και στη λεπτομερή ρύθμιση οπτικών στοιχείων όπως το πλάτος κενών, ώστε να μπορείτε να δημιουργήσετε δυναμικές, πλούσιες σε δεδομένα διαφάνειες που φαίνονται επαγγελματικές και καλοσχεδιασμένες.

## Γρήγορες Απαντήσεις
Η κλάση `Presentation` αντιπροσωπεύει ένα αρχείο PPTX, και η `slide.getShapes().addChart(...)` εισάγει ένα σχήμα διαγράμματος. Χρησιμοποιήστε `chart.getChartData().getSeries().add(...)` για να προσθέσετε μια σειρά, και το `setGapWidth()` ρυθμίζει το κενό.

- **Ποια είναι η κύρια κλάση για την έναρξη μιας παρουσίασης;** `Presentation` – αντιπροσωπεύει ένα αρχείο PPTX στη μνήμη.  
- **Ποια μέθοδος προσθέτει διάγραμμα σε μια διαφάνεια;** `slide.getShapes().addChart(...)` δημιουργεί το αντικείμενο διαγράμματος στη διαφάνεια.  
- **Πώς προσθέτετε μια νέα σειρά;** `chart.getChartData().getSeries().add(...)` εισάγει μια νέα σειρά δεδομένων.  
- **Μπορείτε να αλλάξετε το πλάτος του κενών μεταξύ των ράβδων;** Ναι — καλέστε `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (η τιμή είναι ποσοστό).  
- **Χρειάζομαι άδεια για παραγωγή;** Απόλυτα — μια έγκυρη άδεια Aspose.Slides for Java ξεκλειδώνει όλες τις λειτουργίες και αφαιρεί τα υδατογραφήματα αξιολόγησης.

## Τι είναι η «προσθήκη σειράς σε διάγραμμα»;
Η προσθήκη μιας σειράς σε ένα διάγραμμα σημαίνει την εισαγωγή μιας νέας συλλογής σημείων δεδομένων που το διάγραμμα αποδίδει ως ξεχωριστό οπτικό στοιχείο (π.χ., μια ξεχωριστή ομάδα στηλών). Κάθε σειρά μπορεί να έχει τις δικές της τιμές, χρώματα και μορφοποίηση, επιτρέποντας σύγκριση πολλαπλών συνόλων δεδομένων πλάι‑πλάι.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides for Java για την τροποποίηση παρουσιάσεων .NET;
Το Aspose.Slides for Java σας επιτρέπει να δημιουργήσετε ή να επεξεργαστείτε αρχεία PPTX που είναι πλήρως συμβατά με τους προβολείς PowerPoint .NET, χωρίς να απαιτείται εγκατάσταση του Microsoft Office. Χρησιμοποιήστε το Aspose.Slides for Java όταν χρειάζεστε μια λύση διακομιστή, πολλαπλών πλατφορμών, που δημιουργεί ή ενημερώνει αρχεία .NET PPTX, υποστηρίζει πάνω από 50 τύπους διαγραμμάτων και επεξεργάζεται αρχεία έως 500 MB χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη. Το API του λειτουργεί σε Java, Kotlin, Scala ή οποιαδήποτε γλώσσα JVM, παρέχοντας το ίδιο αποτέλεσμα που αναμένουν οι προγραμματιστές .NET.

## Προαπαιτούμενα
- **Aspose.Slides for Java** βιβλιοθήκη (έκδοση 25.4 ή νεότερη).  
- Maven, Gradle ή χειροκίνητη λήψη JAR.  
- Βασικές γνώσεις Java και εξοικείωση με τη δομή αρχείου PPTX.  

## Ρύθμιση του Aspose.Slides for Java
### Εγκατάσταση Maven
Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Εγκατάσταση Gradle
Συμπεριλάβετε αυτή τη γραμμή στο αρχείο `build.gradle` σας:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση Λήψη
Εναλλακτικά, κατεβάστε το πιο πρόσφατο JAR από την επίσημη σελίδα κυκλοφορίας: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Απόκτηση Άδειας**  
Ξεκινήστε με μια δωρεάν δοκιμή κατεβάζοντας μια προσωρινή άδεια από [εδώ](https://purchase.aspose.com/temporary-license/). Για παραγωγική χρήση, αγοράστε πλήρη άδεια για να ξεκλειδώσετε όλες τις λειτουργίες και να αφαιρέσετε τα υδατογραφήματα αξιολόγησης.

## Οδηγός Υλοποίησης Βήμα‑Βήμα
Κάτω από κάθε βήμα θα βρείτε ένα σύντομο απόσπασμα κώδικα (απ unchanged) ακολουθούμενο από εξήγηση του τι κάνει.

### Βήμα 1: Δημιουργία Κενής Παρουσίασης
`Presentation` είναι η κλάση εισόδου που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Ξεκινάμε με ένα καθαρό αρχείο PPTX, το οποίο μας παρέχει έναν καμβά για την προσθήκη διαγραμμάτων.*

### Βήμα 2: Προσθήκη Στοίβακτου Διαγράμματος Στήλης στη Διαφάνεια
`Chart` αντιπροσωπεύει ένα σχήμα διαγράμματος μέσα σε μια διαφάνεια. `ChartType.StackedColumn` καθορίζει ένα στοίβακτο διάγραμμα στήλης.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Η μέθοδος `addChart` δημιουργεί ένα **στοίβακτο διάγραμμα στήλης** και το τοποθετεί στην πάνω‑αριστερή γωνία της διαφάνειας.*

### Βήμα 3: Προσθήκη Σειρών στο Διάγραμμα (Κύριος Στόχος)
`Series` περιλαμβάνει μια μόνο σειρά δεδομένων σε ένα διάγραμμα.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Εδώ **προσθέτουμε σειρά σε διάγραμμα** — κάθε κλήση δημιουργεί μια νέα σειρά δεδομένων που θα εμφανιστεί ως ξεχωριστή ομάδα στηλών.*

### Βήμα 4: Προσθήκη Κατηγοριών στο Διάγραμμα
`Category` ορίζει μια ετικέτα άξονα X για τα δεδομένα του διαγράμματος.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Οι κατηγορίες λειτουργούν ως ετικέτες του άξονα X, δίνοντας νόημα σε κάθε στήλη.*

### Βήμα 5: Συμπλήρωση Δεδομένων Σειράς
`DataPoint` κρατά μια αριθμητική τιμή για μια σειρά σε μια συγκεκριμένη κατηγορία.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Τα σημεία δεδομένων δίνουν σε κάθε σειρά τις αριθμητικές της τιμές, τις οποίες το διάγραμμα θα αποδώσει ως ύψος ράβδων.*

### Βήμα 6: Ορισμός Πλάτους Κενού για την Ομάδα Σειρών του Διαγράμματος
`SeriesGroup` ελέγχει τις ιδιότητες διάταξης για μια ομάδα σειρών, όπως το πλάτος του κενού.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Η ρύθμιση του πλάτους του κενού βελτιώνει την αναγνωσιμότητα, ειδικά όταν υπάρχουν πολλές κατηγορίες.*

## Συνηθισμένες Περιπτώσεις Χρήσης
- **Οικονομική αναφορά** — σύγκριση τριμηνιαίων εσόδων μεταξύ επιχειρησιακών μονάδων.  
- **Πίνακες ελέγχου έργων** — εμφάνιση ποσοστών ολοκλήρωσης εργασιών ανά ομάδα.  
- **Αναλύσεις μάρκετινγκ** — οπτικοποίηση της απόδοσης εκστρατειών πλάι‑πλάι.  
Αυτά τα σενάρια ωφελούνται από το **παράδειγμα στοίβακτου διαγράμματος στήλης** επειδή αναδεικνύουν τις συνεισφορές των μεμονωμένων κατηγοριών σε ένα σύνολο.

## Συμβουλές Απόδοσης
- **Επαναχρησιμοποίηση του αντικειμένου `Presentation`** κατά τη δημιουργία πολλαπλών διαγραμμάτων για μείωση του φορτίου μνήμης.  
- **Περιορίστε τον αριθμό των σημείων δεδομένων** μόνο στα απαραίτητα για την οπτική ιστορία· το Aspose.Slides μπορεί να διαχειριστεί 10.000 σημεία, αλλά η ταχύτητα απόδοσης μειώνεται μετά από ~5.000.  
- **Καταστρέψτε τα αντικείμενα** (`presentation.dispose()`) μετά την αποθήκευση για να ελευθερώσετε πόρους και να αποφύγετε διαρροές μνήμης.  

## Συχνές Ερωτήσεις
**Q: Μπορώ να προσθέσω άλλους τύπους διαγραμμάτων εκτός από το στοίβακτο στήλης;**  
A: Ναι, το Aspose.Slides υποστηρίζει γραμμικά, πίτες, περιοχές, ραντάρ, φυσαλίδες και πάνω από 50 άλλους τύπους διαγραμμάτων, όλα προσβάσιμα μέσω της ίδιας μεθόδου `addChart`.

**Q: Χρειάζομαι ξεχωριστή άδεια για έξοδο .NET;**  
A: Όχι, η ίδια άδεια Java λειτουργεί για όλες τις μορφές εξόδου, συμπεριλαμβανομένων των αρχείων .NET PPTX.

**Q: Πώς αλλάζω την παλέτα χρωμάτων του διαγράμματος;**  
A: Χρησιμοποιήστε `series.getFormat().getFill().setFillType(FillType.Solid)` και στη συνέχεια ορίστε το επιθυμητό αντικείμενο `Color` για κάθε σειρά.

**Q: Είναι δυνατόν να προσθέσω ετικέτες δεδομένων προγραμματιστικά;**  
A: Απόλυτα. Καλέστε `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` για να εμφανίσετε την αριθμητική τιμή σε κάθε στήλη.

**Q: Τι γίνεται αν χρειαστεί να ενημερώσω μια υπάρχουσα παρουσίαση;**  
A: Φορτώστε το αρχείο με `new Presentation("existing.pptx")`, τροποποιήστε το διάγραμμα χρησιμοποιώντας τις ίδιες κλήσεις API και αποθηκεύστε το ξανά στο δίσκο.

## Συμπέρασμα
Τώρα έχετε έναν πλήρη, ολοκληρωμένο οδηγό για το πώς να **προσθέσετε σειρά σε διάγραμμα**, να δημιουργήσετε ένα **στοίβακτο διάγραμμα στήλης** και να ρυθμίσετε λεπτομερώς την εμφάνισή του σε παρουσιάσεις .NET χρησιμοποιώντας το Aspose.Slides for Java. Πειραματιστείτε με διαφορετικούς τύπους διαγραμμάτων, χρώματα και πηγές δεδομένων για να δημιουργήσετε εντυπωσιακές οπτικές αναφορές που θα εντυπωσιάσουν τα ενδιαφερόμενα μέρη και θα προωθήσουν αποφάσεις βασισμένες σε δεδομένα.

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Διαγράμματα Στοίβακτης Στήλης με Ποσοστό σε .NET χρησιμοποιώντας το Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Δημιουργία και Διαχείριση Σειρών Διαγράμματος με το Aspose.Slides .NET για Αποτελεσματική Οπτικοποίηση Δεδομένων](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Καθαρισμός Συγκεκριμένων Σημείων Δεδομένων Σειράς Διαγράμματος με το Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}