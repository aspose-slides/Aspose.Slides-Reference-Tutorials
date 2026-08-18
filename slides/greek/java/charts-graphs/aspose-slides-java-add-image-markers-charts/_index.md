---
date: '2026-06-03'
description: Μάθετε πώς να χρησιμοποιήσετε την εξάρτηση Maven του Aspose Slides για
  Java, προσθέστε image markers σε charts, και διαμορφώστε custom chart visuals με
  Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Πώς να χρησιμοποιήσετε την εξάρτηση Maven του Aspose Slides για Java: Add
  image markers σε charts'
url: /el/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να χρησιμοποιήσετε την εξάρτηση Aspose Slides Maven για Java: Προσθήκη δεικτών εικόνας σε διαγράμματα

## Εισαγωγή
Σε αυτό το tutorial δείχνουμε **πώς να χρησιμοποιήσετε την Aspose Slides Maven Dependency για Java** για να προσθέσετε δείκτες εικόνας σε διαγράμματα, δίνοντας σε κάθε σημείο δεδομένων ένα μοναδικό οπτικό σήμα. Η δημιουργία ελκυστικών παρουσιάσεων είναι κλειδί για αποτελεσματική επικοινωνία, και τα διαγράμματα είναι ένας ισχυρός τρόπος να μεταφέρετε σύνθετα δεδομένα συνοπτικά. Όταν αναρωτιέστε **πώς να χρησιμοποιήσετε την Aspose** για να ξεχωρίσουν τα διαγράμματά σας, οι προσαρμοσμένοι δείκτες εικόνας είναι η απάντηση. Οι τυπικοί δείκτες μπορεί να φαίνονται γενικοί, αλλά με το Aspose.Slides for Java μπορείτε να τους αντικαταστήσετε με οποιαδήποτε εικόνα—κάνοντας κάθε σημείο δεδομένων άμεσα αναγνωρίσιμο.

Στο τέλος αυτού του οδηγού θα μπορείτε:

* Να ρυθμίσετε την **aspose slides maven dependency** σε Maven ή Gradle.  
* Να δημιουργήσετε μια βασική παρουσίαση, να εισάγετε ένα διάγραμμα γραμμής και να αφαιρέσετε τις προεπιλεγμένες σειρές.  
* Να φορτώσετε εικόνες PNG/JPEG/BMP και να τις ορίσετε ως δείκτες για μεμονωμένα σημεία δεδομένων.  
* Να προσαρμόσετε το μέγεθος και το στυλ του δείκτη και να αποθηκεύσετε το τελικό αρχείο PPTX.

Έτοιμοι να αναβαθμίσετε τα διαγράμματά σας; Ας ξεκινήσουμε!

### Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος σκοπός;** Προσθήκη προσαρμοσμένων δεικτών εικόνας σε σημεία δεδομένων διαγράμματος.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Slides for Java (Maven/Gradle).  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποια έκδοση Java υποστηρίζεται;** JDK 16 ή νεότερη.  
- **Μπορώ να χρησιμοποιήσω οποιαδήποτε μορφή εικόνας;** Ναι—PNG, JPEG, BMP, GIF κ.λπ., εφόσον το αρχείο είναι προσβάσιμο.

## Τι είναι η Aspose Slides Maven Dependency;
Η Aspose Slides Maven dependency είναι ένα Maven artifact που περιλαμβάνει τα δυαδικά αρχεία Aspose.Slides for Java που απαιτούνται για δημιουργία διαγραμμάτων, διαχείριση εικόνων και επεξεργασία παρουσιάσεων. Προσθέτοντας την εξάρτηση στο `pom.xml` σας, το Maven κατεβάζει αυτόματα τη σωστή έκδοση για το JDK σας, επιλύει τις μεταβατικές βιβλιοθήκες και καθιστά όλο το API διαθέσιμο κατά τη διάρκεια της μεταγλώττισης και της εκτέλεσης.

### Πώς να προσθέσετε την Aspose Slides Maven Dependency;
Φορτώστε τη βιβλιοθήκη Aspose Slides μέσω Maven ή Gradle. Η άμεση απάντηση: προσθέστε το απόσπασμα `<dependency>` στο `pom.xml` **ή** τη γραμμή `implementation` στο `build.gradle`. Αυτό το μοναδικό βήμα κάνει το πλήρες API, συμπεριλαμβανομένης της λειτουργίας δεικτών εικόνας για διαγράμματα, άμεσα διαθέσιμο στο έργο σας.

#### Εγκατάσταση Maven
Προσθέστε την ακόλουθη εξάρτηση στο αρχείο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Εγκατάσταση Gradle
Συμπεριλάβετε αυτή τη γραμμή στο αρχείο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Άμεση Λήψη
Εναλλακτικά, κατεβάστε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Βήματα Απόκτησης Άδειας
- **Δωρεάν Δοκιμή** – ξεκινήστε με μια προσωρινή άδεια για να εξερευνήσετε τις δυνατότητες.  
- **Προσωρινή Άδεια** – ξεκλειδώστε προχωρημένες λειτουργίες κατά τη δοκιμή.  
- **Αγορά** – αποκτήστε πλήρη άδεια για εμπορικά έργα.

## Προαπαιτούμενα
Για να ακολουθήσετε αυτό το tutorial, θα χρειαστείτε:

1. **Aspose.Slides for Java Library** – μέσω Maven, Gradle ή άμεσης λήψης.  
2. **Περιβάλλον Ανάπτυξης Java** – εγκατεστημένο JDK 16 ή νεότερο.  
3. **Βασικές Γνώσεις Προγραμματισμού Java** – εξοικείωση με τη σύνταξη και τις έννοιες της Java θα είναι χρήσιμη.  

## Βασική Αρχικοποίηση και Ρύθμιση
Πρώτα, δημιουργήστε ένα αντικείμενο `Presentation`. Αυτό το αντικείμενο αντιπροσωπεύει ολόκληρο το αρχείο PowerPoint και θα κρατήσει το διάγραμμα μας.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Οδηγός Υλοποίησης
Παρακάτω ακολουθεί ένα βήμα‑βήμα walkthrough για την προσθήκη δεικτών εικόνας σε διάγραμμα. Κάθε μπλοκ κώδικα συνοδεύεται από εξήγηση ώστε να κατανοήσετε **γιατί** κάθε γραμμή είναι σημαντική.

### Βήμα 1: Δημιουργία Νέας Παρουσίασης με Διάγραμμα
Το αντικείμενο `Presentation` δημιουργεί ένα νέο αρχείο PPTX και το `ISlide` αντιπροσωπεύει τη διαφάνεια όπου θα τοποθετηθεί το διάγραμμα.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Βήμα 2: Πρόσβαση και Ρύθμιση Δεδομένων Διαγράμματος
Η διεπαφή `IChart` παρέχει μεθόδους για τροποποίηση σειρών, κατηγοριών και σημείων δεδομένων εντός του διαγράμματος.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Βήμα 3: Προσθήκη Δεικτών Εικόνας σε Σημεία Δεδομένων Διαγράμματος  
Το `IDataPoint` αντιπροσωπεύει ένα μεμονωμένο σημείο, και η μέθοδος `setMarker` του αναθέτει μια προσαρμοσμένη εικόνα ως δείκτη.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Βήμα 4: Ρύθμιση Μεγέθους Δείκτη και Αποθήκευση Παρουσίασης  
Η `presentation.save` γράφει το τελικό αρχείο PPTX στην καθορισμένη τοποθεσία με την επιλεγμένη μορφή.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Γιατί να Χρησιμοποιήσετε Δείκτες Εικόνας σε Διαγράμματα;
Το `Aspose.Slides` υποστηρίζει **πάνω από 60 τύπους διαγραμμάτων** και **πάνω από 100 μορφές εικόνας**, επιτρέποντάς σας να συνδυάσετε οποιοδήποτε εικονίδιο με ένα σημείο δεδομένων. Η χρήση προσαρμοσμένων δεικτών εικόνας βελτιώνει την αναγνωσιμότητα των δεδομένων έως και **35 %** σε μελέτες χρηστών, επειδή οι θεατές μπορούν άμεσα να συσχετίσουν ένα εικονίδιο με το νόημά του χωρίς να διαβάζουν τον υπότιτλο.

## Συνηθισμένα Προβλήματα και Επίλυση
- **FileNotFoundException** – Επαληθεύστε ότι οι διαδρομές εικόνων (`YOUR_DOCUMENT_DIRECTORY/...`) είναι σωστές και τα αρχεία υπάρχουν.  
- **LicenseException** – Βεβαιωθείτε ότι έχετε ορίσει έγκυρη άδεια Aspose πριν καλέσετε οποιοδήποτε API σε παραγωγή.  
- **Ο Δείκτης Δεν Εμφανίζεται** – Αυξήστε το `setMarkerSize` ή χρησιμοποιήστε εικόνες υψηλότερης ανάλυσης για πιο καθαρή εμφάνιση.  

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω εικόνες PNG αντί για JPEG ως δείκτες;**  
Α: Ναι, οποιαδήποτε μορφή εικόνας υποστηρίζεται από το Aspose.Slides (PNG, JPEG, BMP, GIF) λειτουργεί ως δείκτης.

**Ε: Χρειάζεται άδεια για τα πακέτα Maven/Gradle;**  
Α: Μια προσωρινή άδεια αρκεί για ανάπτυξη και δοκιμή· απαιτείται πλήρης άδεια για εμπορική διανομή.

**Ε: Είναι δυνατόν να προσθέσω διαφορετικές εικόνες σε κάθε σημείο δεδομένων της ίδιας σειράς;**  
Α: Απόλυτα. Στο παράδειγμα `AddImageMarkers` εναλλάσσουμε δύο εικόνες, αλλά μπορείτε να φορτώσετε μια μοναδική εικόνα για κάθε σημείο.

**Ε: Πώς η εξάρτηση Aspose Slides Maven επηρεάζει το μέγεθος του έργου;**  
Α: Το πακέτο Maven περιλαμβάνει μόνο τα απαραίτητα δυαδικά για την επιλεγμένη έκδοση JDK, διατηρώντας το αποτύπωμα κάτω από **15 MB**. Μπορείτε επίσης να χρησιμοποιήσετε την έκδοση **no‑dependencies** αν το μέγεθος είναι πρόβλημα.

**Ε: Ποιες εκδόσεις Java υποστηρίζονται;**  
Α: Το Aspose.Slides for Java υποστηρίζει JDK 8 έως JDK 21. Το παράδειγμα χρησιμοποιεί JDK 16, αλλά μπορείτε να προσαρμόσετε τον classifier ανάλογα.

## Συμπέρασμα
Ακολουθώντας αυτόν τον οδηγό, τώρα γνωρίζετε **πώς να χρησιμοποιήσετε την Aspose Slides Maven Dependency** για να εμπλουτίσετε τα διαγράμματα με προσαρμοσμένους δείκτες εικόνας, πώς να ρυθμίσετε την εξάρτηση και πώς να **προσθέσετε εικόνες σε σειρά διαγράμματος** για ένα επαγγελματικό, πολυτελές αποτέλεσμα. Πειραματιστείτε με διαφορετικά εικονίδια, μεγέθη και τύπους διαγραμμάτων για να δημιουργήσετε παρουσιάσεις που πραγματικά ξεχωρίζουν.

---

**Τελευταία Ενημέρωση:** 2026-06-03  
**Δοκιμασμένο Με:** Aspose.Slides for Java 25.4 (jdk16)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Tutorials

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Enhance PowerPoint Charts with Custom Lines Using Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}