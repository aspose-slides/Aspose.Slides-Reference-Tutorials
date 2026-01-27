---
date: '2026-01-11'
description: Μάθετε πώς να χρησιμοποιείτε το Aspose Slides για Java, προσθέστε δείκτες
  εικόνας σε γραφήματα και διαμορφώστε την εξάρτηση Maven του Aspose Slides για προσαρμοσμένα
  οπτικά στοιχεία γραφημάτων.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Πώς να χρησιμοποιήσετε το Aspose Slides Java - Προσθήκη δεικτών εικόνας σε
  διαγράμματα'
url: /el/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να χρησιμοποιήσετε το Aspose Slides Java: Προσθήκη Δεικτών Εικόνας σε Διαγράμματα

## Bevezetés
Δημιουργία οπτικά ελκυστικών παρουσιάσεων είναι δκλι αποτελεσματική επικοινωνία, και τα διαγράμματα είν ισχυρό εργαλείο για τη μετάδοση σύνθετων δεδομένων συνοπτικά. Όταν αναρωτιέστε **πώς να χρησιμοποιήσετε το Aspose** γιακετν διαγράμματα σας να ξεχωρίζουν, οι προσαρμοσμένοί δεει εικόνας είναι η απάντηση. Οι τυπικοί δείκτες μπορεί να φαίνονται γενικοί, αεμικοί, αελάκοί, αλλάκοί μπορείτε να τους αντικαταστήσετε με οποιαδήποτε εικόνα—κάνοντας κάθε σημείο δεδομένων άμεσα αναγνωρίσιμο.

Σε αυτό το bemutató, θα περάσουμε από όλη τη διαδικασία πρήοσθρήοσ δεικτών εικόνας σε ένα γράφημα γραμμής, από**Aτη ρύθμη τη ρύθμμ függőség** μέχρι τη φόρτωση εικόνων και την εφαρμογή τους σε σημεία δεδομένων. További információ να **προσθέσετε εικόνες σε σειρά διαγράμματος**, και θαι θα έτοιμο προς εκτέλεση δείγμα κώδικα.

**Τι Θα Μάθετε**
- Πώς να ρυθμίσετε το Aspose.Slides for Java (συμπεριλαμβανομένων Maven/Gradle)
- Δημιουργία μιας βασικής παρουσίασης και διαγράμμας
- Προσθήκη δεικτών εικόνας σε σημεία δεδομένων του διαγράμματος
- Διαμόρφωση μεγέθους και στυλ δείκτη για βέλτιστη αππστη

Έτοιμοι να βελτιώσετε τα διαγράμματά σας; Ας εμβαθύνουμε στις προαπαιτήσεις πριν ξεκινήσουμε!

### Gyors válaszok
- **Ποιος είναι ο κύριος σκοπός;** Προσθήκη προσνωμοσμΎαρμοσμέα εικόνας σε σημεία δεδομένων διαγράμματος.
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Slides for Java (Maven/Gradle).
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί α αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.
- **Ποια έκδοση Java υποστηρίζεται;** JDK16 ή νεότερη.
- **Μπορώ να χρησιμοποιήσω οποιαδήποτε μορφή εικόναας,**P,PEGΝα΂;** κ.λπ., εφόσον το αρχείο είναι προσβάσιμο.

### Előfeltételek
Az oktatóanyag követéséhez a következőkre lesz szüksége:
1. **Aspose.Slides for Java Library** – αποκτήστε μέσω Maven, Gradle ή άμεσης λήψης.
2. **Java fejlesztői környezet** – εγκατεστημένο JDK16 ή νεότερο.
3. **Βασικές Γνώσεις Προγραμματισμού Java** – η εξοικείωση ξείωση και τις έννοιες της Java θα είναι χρήσιμη.

## Τι είναι η εξάρτηση Aspose Slides Maven;
Η εξάρτηση Maven αντλεί τα σωστά binárisok για την έκδοση Java σας. Η προσθήκη της στο `pom.xml` εξασφαλίζει ότι η βιβλιοθαήκη διαθέσιμη κατά τη διάρκεια της μεταγλώττισης και σης και της και της μεταγλώττισης και της

### Maven telepítés
Προσθέστε την ακόλουθη εξάρτηση στο αρχείο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle telepítés
Συμπεριλάβετε αυτή τη γραμμή στο αρχείο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Εναλλακτικά, κατεβάστε την τελευταία έκδοση από τκο [Asdes for Java. kiadások](https://releases.aspose.com/slides/java/).

#### Licencbeszerzés lépései
- **Δωρεάν Δοκιμή** – ξεκινήστε με μια προσωρινή άδεια γμή** εξερευνήσετε τις δυνατότητες.
- **Προσωρινή Άδεια** – ξεκλειδώστε προηγμένες δυνατετηττΌτη δοκιμή.
- **Αγορά** – αποκτήστε πλήρη άδεια για εμπορικά έργα.

## Alapvető inicializálás és beállítás
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

## Megvalósítási útmutató
Παρακάτω είναι ένας βήμα‑βήμα οδηγός για την προσΎδήιτοσθήή εικόνας σε ένα διάγραμμα. Κάθε μπλοκ κώδικα συνοδεύεται από εξήγηση ώστε να κκιε να κοδεύεται από εξήγηση **γιατί** κάθε γραμμή είναι σημαντική.

### 1. lépés: Hozzon létre egy új prezentációt diagrammal
Προσθέτουμε ένα διάγραμμα γραμμής με προεπιλεγμεπιλεγμένος στην πρώτη διαφάνεια.

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

### 2. lépés: A diagramadatok elérése és konfigurálása
Καθαρίζουμε τυχόν προεπιλεγμένες σειρές και προσθι προσθι δικές μας, προετοιμάζοντας το φύλλο εργασμοοσ γι΁παρς σημεία δεδομένων.

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

### 3. lépés: Képjelzők hozzáadása a diagram adatpontjaihoz
Εδώ δείχνουμε **πώς να προσθέσετε δείκτες** χρησιμοΎμοε εικόνες. Αντικαταστήστε τις διαδρομές helyőrző με την πραγματική θέσ εικόνων σας.

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

### 4. lépés: Jelölő méretének konfigurálása és a prezentáció mentése 
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

## Gyakori problémák és hibaelhárítás
- **FileNotFoundException** – Επαληθεύστε ότι οι διαδρομές εικόνας (`YOUR_DOCUMENT_DIRECTORY/...ίνα)ε σωστές και τα αρχεία υπάρχουν.
- **LicenseException** – Βεβαιωθείτε ότι έχετε ορίσει μια έγκυρη άδεposeινρη άδεposeια A καλέσετε οποιοδήποτε API στην παραγωγή.
- **A jelölő nem látható** – Αυξήστε το `setMarkerSize` ή χρησιμοποιήστε εικόνες υψηεόες υψηλό ανάλυσης για πιο καθαρή εμφάνιση.

## Gyakran Ismételt Kérdések

**Ε: Μπορώ να χρησιμοποιήσω εικόνες PNG αντί για**α JPEG γιε δε;
Α: Ναι, οποιαδήποτε μορφή εικόνας υποστηρίζεται αβ. BMP, GIF) λειτουργεί ως δείκτης.

**Ε: Χρειάζομαι άδεια για τα πακέτα Maven/Gradle;**
Α: Μια προσωρινή άδεια είναι επαρκής για αμάπτυξι δ΂τυξη κα απαιτείται πλήρης άδεια για εμπορική διανομή.

**Ε: Είναι δυνατόν να προσθέσω διαφορετικές εικόνεάκ΃ες σημείο δεδομένων στην ίδια σειρά;**
Α: Απόλυτα. Στο παράδειγμα "AddImageMarkers" να φορτώσετε μια μοναδική εικόνα για κάθε σημείο.

**Ε: Πώς η "aspose slides maven dependency" επηρεάζει το μέγεθος του έργου;**
Α: Το πακέτο Maven περιλαμβάνει μόνο τα απαραίτητα binárisok γιν για επιλεγμένη έκδοση JDK, διατηρώντας το αποτύπωμα λογικό. Μπορείτε επίσης να χρησιμοποιήσετε την έκδοση **no-dependencies** ναν μέγεθος είναι πρόβλημα.

**Ε: Ποιες εκδόσεις Java υποστηρίζονται;**
Α: Το Aspose.Slides for Java υποστηρίζει JDK8 έως JDK21. αλλά μπορείτε να προσαρμόσετε τον ταξινομητή αναλόγως.

## Következtetés
Ακολουθώντας αυτόν τον οδηγό, τώρα γνωρίζετε **πώς να χρησιμοποιήσετε το Aspose** για να εμπλουτίσετε τα μιαγγρά προσαρμοσμένους δείκτες εικόνας, πώς να διαμορφώσετε την **Aspose Slides Maven függőség**, και πώς να **προσθέσετε ενικσετε ενικσετε σειρά διαγράμματος** για μια επαγγελματική εμφάνιση. Πειραματιστείτε με διαφορετικά εικονίδια, μεγέθη κ΅τε διαγραμμάτων για να δημιουργήσετε παρουσιμμεις πγμάσεις πον ξεχωρίζουν.

---

**Utolsó frissítés:** 2026-01-11
**Tesztelve:** Aspose.Slides for Java 25.4 (jdk16)
**Szerző:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}