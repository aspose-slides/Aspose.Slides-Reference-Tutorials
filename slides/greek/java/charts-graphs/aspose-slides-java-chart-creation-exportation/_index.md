---
date: '2026-02-09'
description: Μάθετε πώς να δημιουργείτε γράφημα και να εξάγετε το γράφημα στο Excel
  χρησιμοποιώντας το Aspose.Slides for Java. Κατακτήστε την οπτικοποίηση δεδομένων,
  τις διαφάνειες επιχειρηματικών αναφορών και τη δημιουργία βιβλίου εργασίας.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Πώς να δημιουργήσετε γράφημα με το Aspose.Slides Java
url: /el/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε γράφημα χρησιμοποιώντας το Aspose.Slides for Java

**Κατακτήστε τις τεχνικές οπτικοποίησης δεδομένων με το Aspose.Slides for Java**

Στο σημερινό περιβάλλον που βασίζεται στα δεδομένα, η *δημιουργία γραφήματος* προγραμματιστικά είναι μια δεξιότητα που μπορεί να μετατρέψει ακατέργαστους αριθμούς σε συναρπαστικές οπτικές ιστορίες. Είτε δημιουργείτε μια παρουσίαση επιχειρηματικής αναφοράς είτε έναν διαδραστικό πίνακα ελέγχου αναλυτικών δεδομένων, το Aspose.Slides for Java σας δίνει τη δυνατότητα να παράγετε, να προσαρμόζετε και να εξάγετε γραφήματα απευθείας από τον κώδικά σας. Σε αυτό το tutorial θα μάθετε πώς να δημιουργείτε αντικείμενα γραφήματος, να εξάγετε τα δεδομένα του γραφήματος σε Excel και να συνδέετε τα γραφήματα με εξωτερικά βιβλία εργασίας για απρόσκοπτη διαχείριση δεδομένων.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρειάζεται;** Aspose.Slides for Java (v25.4+).  
- **Μπορώ να εξάγω τα δεδομένα του γραφήματος σε Excel;** Ναι – χρησιμοποιήστε `readWorkbookStream()` και γράψτε τα byte σε αρχείο *.xlsx*.  
- **Ποια έκδοση Java απαιτείται;** JDK 16 ή νεότερη.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται μόνιμη άδεια για παραγωγή.  
- **Τι τύπο γραφήματος παρουσιάζεται;** Γράφημα Πίτας, αλλά η ίδια προσέγγιση λειτουργεί για Bar, Line και άλλους τύπους γραφημάτων.

## Τι είναι το Aspose.Slides for Java;
Το Aspose.Slides for Java είναι ένα καθαρό Java API που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται και να μετατρέπουν παρουσιάσεις PowerPoint χωρίς το Microsoft Office. Υποστηρίζει πλήρη γκάμα τύπων γραφημάτων, σύνδεση δεδομένων και δυνατότητες εξαγωγής, καθιστώντας το ιδανικό για **data visualization java** έργα.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για δημιουργία γραφήματος και εξαγωγή σε Excel;
- **Χωρίς εγκατάσταση Office** – λειτουργεί σε οποιονδήποτε διακομιστή ή περιβάλλον cloud.  
- **Πλούσια βιβλιοθήκη γραφημάτων** – δεκάδες τύπους γραφημάτων και πλήρη έλεγχο στυλ.  
- **Άμεση εξαγωγή σε Excel** – δημιουργήστε εξωτερικό βιβλίο εργασίας για περαιτέρω ανάλυση.  
- **Βελτιστοποιημένη απόδοση** – χαμηλό αποτύπωμα μνήμης και γρήγορη επεξεργασία μεγάλων παρουσιάσεων.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

### Απαιτούμενες Βιβλιοθήκες και Εκδόσεις
- **Aspose.Slides for Java** έκδοση 25.4 ή νεότερη

### Απαιτήσεις Περιβάλλοντος
- Java Development Kit (JDK) 16 ή νεότερο  
- Ένα IDE όπως IntelliJ IDEA ή Eclipse (ή οποιοδήποτε κειμενογράφο προτιμάτε)

### Προαπαιτούμενες Γνώσεις
- Βασικές γνώσεις προγραμματισμού Java  
- Εξοικείωση με εργαλεία κατασκευής Maven ή Gradle

## Ρύθμιση Aspose.Slides for Java
Προσθέστε τη βιβλιοθήκη στο έργο σας χρησιμοποιώντας το αγαπημένο σας σύστημα κατασκευής.

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

Εναλλακτικά, μπορείτε να [κατεβάσετε την πιο πρόσφατη έκδοση απευθείας](https://releases.aspose.com/slides/java/).

### Βήματα Απόκτησης Άδειας
Το Aspose.Slides προσφέρει δωρεάν δοκιμαστική άδεια για να εξερευνήσετε όλες τις δυνατότητές του. Μπορείτε επίσης να ζητήσετε προσωρινή άδεια ή να αγοράσετε μια για παρατεταμένη χρήση. Ακολουθήστε τα παρακάτω βήματα:

1. Επισκεφθείτε τη [σελίδα Αγοράς Aspose](https://purchase.aspose.com/buy) για να αποκτήσετε την άδειά σας.  
2. Για δωρεάν δοκιμή, κατεβάστε από το [Releases](https://releases.aspose.com/slides/java/).  
3. Αιτηθείτε προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

Μόλις έχετε το αρχείο άδειας, αρχικοποιήστε το στην εφαρμογή Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Οδηγός Βήμα‑Βήμα

### Πώς να δημιουργήσετε γράφημα – Φόρτωση Παρουσίασης
Η φόρτωση ενός υπάρχοντος αρχείου PowerPoint είναι το πρώτο βήμα πριν προσθέσετε ή τροποποιήσετε γραφήματα.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**Επεξήγηση:**  
- `Presentation` αντιπροσωπεύει το αρχείο PowerPoint.  
- Πάντα καλέστε `dispose()` για να απελευθερώσετε τους εγγενείς πόρους.

### Πώς να δημιουργήσετε γράφημα – Προσθήκη Γραφήματος Πίτας σε Διαφάνεια
Τώρα θα εισάγουμε ένα γράφημα Πίτας, ιδανικό για την εμφάνιση ποσοστιαίων δεδομένων.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Επεξήγηση:**  
- `addChart` εισάγει το γράφημα στην πρώτη διαφάνεια.  
- Οι παράμετροι ορίζουν τον τύπο γραφήματος, τη θέση X/Y και το μέγεθος.

### Πώς να εξάγετε γράφημα σε Excel – Εξαγωγή Δεδομένων Γραφήματος
Η εξαγωγή των δεδομένων του γραφήματος επιτρέπει στους αναλυτές να δουλέψουν με τους αριθμούς στο Excel, προσφέροντας βαθύτερη κατανόηση.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Επεξήγηση:**  
- `readWorkbookStream()` εξάγει το υποκείμενο βιβλίο εργασίας Excel του γραφήματος ως πίνακα byte.  
- Ο πίνακας byte γράφεται στο `externalWorkbook1.xlsx`, παρέχοντάς σας ένα έτοιμο αρχείο Excel.

### Πώς να δημιουργήσετε γράφημα – Ορισμός Εξωτερικού Βιβλίου Εργασίας για Δυναμικά Δεδομένα
Η σύνδεση ενός γραφήματος με εξωτερικό βιβλίο εργασίας σας επιτρέπει να ενημερώνετε το γράφημα απλώς επεξεργάζοντας το αρχείο Excel.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Επεξήγηση:**  
- `setExternalWorkbook` συνδέει το γράφημα με το καθορισμένο αρχείο Excel, ενεργοποιώντας ζωντανές ενημερώσεις δεδομένων χωρίς επαναδημιουργία της διαφάνειας.

## Πρακτικές Εφαρμογές
Το Aspose.Slides προσφέρει ευέλικτες λύσεις για διάφορα πραγματικά σενάρια:

1. **Διαφάνειες Επιχειρηματικών Αναφορών:** Αυτόματη δημιουργία γραφημάτων απόδοσης τριμήνου από τις ροές δεδομένων σας.  
2. **Ακαδημαϊκές Παρουσιάσεις:** Μετατροπή ερευνητικών δεδομένων σε καθαρές οπτικοποιήσεις χωρίς χειροκίνητη δημιουργία γραφημάτων.  
3. **Οικονομική Ανάλυση:** Εξαγωγή δεδομένων γραφήματος σε Excel για ελεγκτές ώστε να επαληθεύσουν τους αριθμούς.  
4. **Μάρκετινγκ Αναλύσεις:** Οπτικοποίηση μετρικών καμπάνιας και κοινή χρήση επεξεργάσιμων βιβλίων εργασίας με ενδιαφερόμενους.

## Συχνά Προβλήματα & Επίλυση
- **`FileNotFoundException`** – Επαληθεύστε ότι το `dataDir` δείχνει σε έγκυρο φάκελο και ότι η διαδρομή εξόδου είναι εγγράψιμη.  
- **Διαρροές μνήμης** – Πάντα καλέστε `pres.dispose()` σε μπλοκ `finally` για να ελευθερώσετε τους εγγενείς πόρους.  
- **Το γράφημα δεν εμφανίζεται** – Βεβαιωθείτε ότι ο δείκτης διαφάνειας (`get_Item(0)`) αντιστοιχεί σε διαφάνεια που πράγματι υπάρχει.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω διαφορετικό τύπο γραφήματος (π.χ., Bar, Line) με τον ίδιο κώδικα;**  
Α: Ναι. Αντικαταστήστε το `ChartType.Pie` με οποιαδήποτε άλλη τιμή του enum `ChartType`, όπως `ChartType.Bar` ή `ChartType.Line`.

**Ε: Είναι δυνατόν να ενημερώσω το εξωτερικό βιβλίο εργασίας μετά τη δημιουργία του γραφήματος;**  
Α: Απόλυτα. Τροποποιήστε το αρχείο Excel απευθείας· το συνδεδεμένο γράφημα θα αντανακλά τις αλλαγές την επόμενη φορά που θα ανοίξει η παρουσίαση.

**Ε: Χρειάζομαι ξεχωριστή άδεια για τη λειτουργία εξαγωγής σε Excel;**  
Α: Όχι. Η δυνατότητα εξαγωγής σε Excel περιλαμβάνεται στην τυπική άδεια του Aspose.Slides for Java.

**Ε: Ποιες εκδόσεις Java υποστηρίζονται;**  
Α: Το Aspose.Slides for Java υποστηρίζει JDK 16 και νεότερες· παλαιότερες εκδόσεις μπορεί να λειτουργούν αλλά δεν είναι επίσημα δοκιμασμένες.

**Ε: Πώς μπορώ να ενσωματώσω το παραγόμενο βιβλίο εργασίας Excel μέσα στο αρχείο PPTX;**  
Α: Χρησιμοποιήστε `chart.getChartData().setExternalWorkbook(null)` για να ενσωματώσετε το βιβλίο εργασίας, ή διατηρήστε τον εξωτερικό σύνδεσμο για δυναμικές ενημερώσεις.

---

**Τελευταία ενημέρωση:** 2026-02-09  
**Δοκιμασμένο με:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}