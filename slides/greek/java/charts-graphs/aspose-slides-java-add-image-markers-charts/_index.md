---
date: '2026-01-11'
description: Μάθετε πώς να χρησιμοποιείτε το Aspose Slides για Java, προσθέστε δείκτες
  εικόνας σε γραφήματα και διαμορφώστε την εξάρτηση Maven του Aspose Slides για προσαρμοσμένα
  οπτικά στοιχεία γραφημάτων.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Πώς να χρησιμοποιήσετε το Aspose Slides Java: Προσθήκη δεικτών εικόνας σε
  διαγράμματα'
url: /el/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να χρησιμοποιήσετε το Aspose Slides Java: Προσθήκη Δεικτών Εικόνας σε Διαγράμματα

## Introduction
Δημιουργία οπτικά ελκυστικών παρουσιάσεων είναι κλειδί για αποτελεσματική επικοινωνία, και τα διαγράμματα είναι ένα ισχυρό εργαλείο για τη μετάδοση σύνθετων δεδομένων συνοπτικά. Όταν αναρωτιέστε **πώς να χρησιμοποιήσετε το Aspose** για να κάνετε τα διαγράμματα σας να ξεχωρίζουν, οι προσαρμοσμένοι δείκτες εικόνας είναι η απάντηση. Οι τυπικοί δείκτες μπορεί να φαίνονται γενικοί, αλλά με το Aspose.Slides for Java μπορείτε να τους αντικαταστήσετε με οποιαδήποτε εικόνα—κάνοντας κάθε σημείο δεδομένων άμεσα αναγνωρίσιμο.

Σε αυτό το tutorial, θα περάσουμε από όλη τη διαδικασία προσθήκης δεικτών εικόνας σε ένα γράφημα γραμμής, από τη ρύθμιση της **Aspose Slides Maven dependency** μέχρι τη φόρτωση εικόνων και την εφαρμογή τους σε σημεία δεδομένων. Στο τέλος θα είστε άνετοι με το **πώς να προσθέσετε δείκτες**, πώς να **προσθέσετε εικόνες σε σειρά διαγράμματος**, και θα έχετε ένα έτοιμο προς εκτέλεση δείγμα κώδικα.

**Τι Θα Μάθετε**
- Πώς να ρυθμίσετε το Aspose.Slides for Java (συμπεριλαμβανομένων Maven/Gradle)
- Δημιουργία μιας βασικής παρουσίασης και διαγράμματος
- Προσθήκη δεικτών εικόνας σε σημεία δεδομένων του διαγράμματος
- Διαμόρφωση μεγέθους και στυλ δείκτη για βέλτιστη απεικόνιση

Έτοιμοι να βελτιώσετε τα διαγράμματά σας; Ας εμβαθύνουμε στις προαπαιτήσεις πριν ξεκινήσουμε!

### Quick Answers
- **Ποιος είναι ο κύριος σκοπός;** Προσθήκη προσαρμοσμένων δεικτών εικόνας σε σημεία δεδομένων διαγράμματος.  
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Slides for Java (Maven/Gradle).  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποια έκδοση Java υποστηρίζεται;** JDK 16 ή νεότερη.  
- **Μπορώ να χρησιμοποιήσω οποιαδήποτε μορφή εικόνας;** Ναι—PNG, JPEG, BMP κ.λπ., εφόσον το αρχείο είναι προσβάσιμο.

### Prerequisites
To follow this tutorial, you'll need:
1. **Aspose.Slides for Java Library** – αποκτήστε μέσω Maven, Gradle ή άμεσης λήψης.  
2. **Java Development Environment** – εγκατεστημένο JDK 16 ή νεότερο.  
3. **Βασικές Γνώσεις Προγραμματισμού Java** – η εξοικείωση με τη σύνταξη και τις έννοιες της Java θα είναι χρήσιμη.

## Τι είναι η εξάρτηση Aspose Slides Maven;
Η εξάρτηση Maven αντλεί τα σωστά binaries για την έκδοση Java σας. Η προσθήκη της στο `pom.xml` εξασφαλίζει ότι η βιβλιοθήκη είναι διαθέσιμη κατά τη διάρκεια της μεταγλώττισης και της εκτέλεσης.

### Maven Installation
Προσθέστε την ακόλουθη εξάρτηση στο αρχείο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Installation
Συμπεριλάβετε αυτή τη γραμμή στο αρχείο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Εναλλακτικά, κατεβάστε την τελευταία έκδοση από το [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Δωρεάν Δοκιμή** – ξεκινήστε με μια προσωρινή άδεια για να εξερευνήσετε τις δυνατότητες.  
- **Προσωρινή Άδεια** – ξεκλειδώστε προηγμένες δυνατότητες κατά τη δοκιμή.  
- **Αγορά** – αποκτήστε πλήρη άδεια για εμπορικά έργα.

## Basic Initialization and Setup
Πρώτα, δημιουργήστε ένα αντικείμενο `Presentation`. Αυτό το αντικείμενο αντιπροσωπεύει ολόκληρο το αρχείο PowerPoint και θα κρατήσει το διάγραμμά μας.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Implementation Guide
Παρακάτω είναι ένας βήμα‑βήμα οδηγός για την προσθήκη δεικτών εικόνας σε ένα διάγραμμα. Κάθε μπλοκ κώδικα συνοδεύεται από εξήγηση ώστε να κατανοήσετε **γιατί** κάθε γραμμή είναι σημαντική.

### Step 1: Create a New Presentation with a Chart
Προσθέτουμε ένα διάγραμμα γραμμής με προεπιλεγμένους δείκτες στην πρώτη διαφάνεια.

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

### Step 2: Access and Configure Chart Data
Καθαρίζουμε τυχόν προεπιλεγμένες σειρές και προσθέτουμε τις δικές μας, προετοιμάζοντας το φύλλο εργασίας για προσαρμοσμένα σημεία δεδομένων.

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

### Step 3: Add Image Markers to Chart Data Points  
Εδώ δείχνουμε **πώς να προσθέσετε δείκτες** χρησιμοποιώντας εικόνες. Αντικαταστήστε τις διαδρομές placeholder με την πραγματική θέση των εικόνων σας.

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

### Step 4: Configure Marker Size and Save the Presentation  
Ρυθμίζουμε το στυλ του δείκτη για καλύτερη ορατότητα και γράφουμε το τελικό αρχείο PPTX.

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

## Common Issues and Troubleshooting
- **FileNotFoundException** – Επαληθεύστε ότι οι διαδρομές εικόνας (`YOUR_DOCUMENT_DIRECTORY/...`) είναι σωστές και τα αρχεία υπάρχουν.  
- **LicenseException** – Βεβαιωθείτε ότι έχετε ορίσει μια έγκυρη άδεια Aspose πριν καλέσετε οποιοδήποτε API στην παραγωγή.  
- **Marker Not Visible** – Αυξήστε το `setMarkerSize` ή χρησιμοποιήστε εικόνες υψηλότερης ανάλυσης για πιο καθαρή εμφάνιση.

## Frequently Asked Questions

**Ε: Μπορώ να χρησιμοποιήσω εικόνες PNG αντί για JPEG για δείκτες;**  
Α: Ναι, οποιαδήποτε μορφή εικόνας υποστηρίζεται από το Aspose.Slides (PNG, JPEG, BMP, GIF) λειτουργεί ως δείκτης.

**Ε: Χρειάζομαι άδεια για τα πακέτα Maven/Gradle;**  
Α: Μια προσωρινή άδεια είναι επαρκής για ανάπτυξη και δοκιμές· απαιτείται πλήρης άδεια για εμπορική διανομή.

**Ε: Είναι δυνατόν να προσθέσω διαφορετικές εικόνες σε κάθε σημείο δεδομένων στην ίδια σειρά;**  
Α: Απόλυτα. Στο παράδειγμα `AddImageMarkers` εναλλάσσουμε δύο εικόνες, αλλά μπορείτε να φορτώσετε μια μοναδική εικόνα για κάθε σημείο.

**Ε: Πώς η `aspose slides maven dependency` επηρεάζει το μέγεθος του έργου;**  
Α: Το πακέτο Maven περιλαμβάνει μόνο τα απαραίτητα binaries για την επιλεγμένη έκδοση JDK, διατηρώντας το αποτύπωμα λογικό. Μπορείτε επίσης να χρησιμοποιήσετε την έκδοση **no‑dependencies** αν το μέγεθος είναι πρόβλημα.

**Ε: Ποιες εκδόσεις Java υποστηρίζονται;**  
Α: Το Aspose.Slides for Java υποστηρίζει JDK 8 έως JDK 21. Το παράδειγμα χρησιμοποιεί JDK 16, αλλά μπορείτε να προσαρμόσετε τον ταξινομητή αναλόγως.

## Conclusion
Ακολουθώντας αυτόν τον οδηγό, τώρα γνωρίζετε **πώς να χρησιμοποιήσετε το Aspose** για να εμπλουτίσετε τα διαγράμματα με προσαρμοσμένους δείκτες εικόνας, πώς να διαμορφώσετε την **Aspose Slides Maven dependency**, και πώς να **προσθέσετε εικόνες σε σειρά διαγράμματος** για μια επαγγελματική εμφάνιση. Πειραματιστείτε με διαφορετικά εικονίδια, μεγέθη και τύπους διαγραμμάτων για να δημιουργήσετε παρουσιάσεις που πραγματικά ξεχωρίζουν.

---

**Last Updated:** 2026-01-11  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}