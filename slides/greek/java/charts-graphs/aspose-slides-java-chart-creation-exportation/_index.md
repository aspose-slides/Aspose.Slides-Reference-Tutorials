---
date: '2026-06-03'
description: Μάθετε πώς να εξάγετε διάγραμμα σε Excel και να δημιουργήσετε διάγραμμα
  Java χρησιμοποιώντας το Aspose.Slides for Java. Κατακτήστε την οπτικοποίηση δεδομένων,
  τις διαφάνειες επιχειρηματικών αναφορών και τη δημιουργία βιβλίου εργασίας.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Εξαγωγή διαγράμματος σε Excel και δημιουργία διαγραμμάτων με Aspose.Slides
url: /el/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Εξαγωγή Διαγράμματος σε Excel και Δημιουργία Διαγραμμάτων με Aspose.Slides

**Αποκτήστε Τεχνικές Οπτικοποίησης Δεδομένων με Aspose.Slides for Java**

Στο σημερινό περιβάλλον που καθοδηγείται από δεδομένα, η *εξαγωγή διαγράμματος σε Excel* προγραμματιστικά είναι μια δεξιότητα που μπορεί να μετατρέψει ακατέργαστους αριθμούς σε συναρπαστικές οπτικές ιστορίες. Είτε δημιουργείτε μια παρουσίαση επιχειρηματικής αναφοράς είτε έναν διαδραστικό πίνακα αναλύσεων, το Aspose.Slides for Java σας δίνει τη δυνατότητα να δημιουργείτε, να προσαρμόζετε και να εξάγετε διαγράμματα απευθείας από τον κώδικά σας. Σε αυτό το μάθημα θα μάθετε πώς να δημιουργείτε αντικείμενα διαγράμματος, να εξάγετε δεδομένα διαγράμματος σε Excel και να συνδέετε διαγράμματα με εξωτερικά βιβλία εργασίας για απρόσκοπτη διαχείριση δεδομένων.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη απαιτείται;** Aspose.Slides for Java (v25.4+).  
- **Μπορώ να εξάγω δεδομένα διαγράμματος σε Excel;** Ναι – χρησιμοποιήστε `readWorkbookStream()` και γράψτε τα bytes σε αρχείο *.xlsx*.  
- **Ποια έκδοση Java απαιτείται;** JDK 16 ή νεότερη.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμαστική άδεια λειτουργεί για αξιολόγηση· απαιτείται μόνιμη άδεια για παραγωγή.  
- **Τι τύπο διαγράμματος παρουσιάζεται;** Διάγραμμα Πίτας, αλλά η ίδια προσέγγιση λειτουργεί για Γραμμικά, Στήλες και άλλους τύπους διαγραμμάτων.

## Τι είναι το Aspose.Slides for Java;
Το Aspose.Slides for Java είναι ένα καθαρά Java API που επιτρέπει στους προγραμματιστές να δημιουργούν, να επεξεργάζονται και να μετατρέπουν παρουσιάσεις PowerPoint χωρίς το Microsoft Office. Παρέχει ένα ολοκληρωμένο σύνολο κλάσεων για διαχείριση διαφανειών, δημιουργία διαγραμμάτων και μετατροπή μορφών, επιτρέποντας αυτοματοποιημένες λύσεις αναφοράς. Υποστηρίζει **πάνω από 50 τύπους διαγραμμάτων**, πλήρη σύνδεση δεδομένων και άμεση εξαγωγή σε Excel, καθιστώντας το ιδανικό για έργα **data visualization java**.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για δημιουργία διαγράμματος και εξαγωγή διαγράμματος σε Excel;
Εξαγωγή διαγράμματος σε Excel γρήγορα και αξιόπιστα. Το Aspose.Slides αφαιρεί την ανάγκη εγκατάστασης Office, προσφέρει **πάνω από 50 ενσωματωμένα στυλ διαγραμμάτων**, και επεξεργάζεται παρουσιάσεις **έως 300 MB σε λιγότερο από 30 δευτερόλεπτα** σε τυπικό εξοπλισμό διακομιστή. Επιπλέον, παρέχει εγγενή δημιουργία βιβλίου εργασίας Excel, επιτρέποντας στους αναλυτές να εργάζονται με ακατέργαστους αριθμούς χωρίς χειροκίνητη αντιγραφή‑επικόλληση.

## Προαπαιτούμενα
Πριν προχωρήσουμε, βεβαιωθείτε ότι έχετε τα εξής:

### Απαιτούμενες Βιβλιοθήκες και Εκδόσεις
- **Aspose.Slides for Java** έκδοση 25.4 ή νεότερη (υποστηρίζει JDK 16+)

### Απαιτήσεις Περιβάλλοντος
- Java Development Kit (JDK) 16 ή νεότερο  
- Ένα IDE όπως IntelliJ IDEA ή Eclipse (ή οποιονδήποτε επεξεργαστή κειμένου προτιμάτε)

### Προαπαιτούμενες Γνώσεις
- Βασικές δεξιότητες προγραμματισμού Java  
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

Εναλλακτικά, μπορείτε να [κατεβάσετε την τελευταία έκδοση απευθείας](https://releases.aspose.com/slides/java/).

### Βήματα Απόκτησης Άδειας
Το Aspose.Slides προσφέρει δωρεάν δοκιμαστική άδεια για να εξερευνήσετε όλες τις δυνατότητές του. Μπορείτε επίσης να υποβάλετε αίτηση για προσωρινή άδεια ή να αγοράσετε μια για παρατεταμένη χρήση. Ακολουθήστε τα παρακάτω βήματα:

1. Επισκεφθείτε τη [σελίδα Αγοράς Aspose](https://purchase.aspose.com/buy) για να αποκτήσετε την άδειά σας.  
2. Για δωρεάν δοκιμή, κατεβάστε από το [Releases](https://releases.aspose.com/slides/java/).  
3. Υποβάλετε αίτηση για προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

Μόλις έχετε το αρχείο άδειας, αρχικοποιήστε το στην εφαρμογή Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Οδηγός Βήμα‑βήμα

### Πώς να δημιουργήσετε διάγραμμα – Φόρτωση Παρουσίασης
Φορτώστε ένα υπάρχον αρχείο PowerPoint πριν προσθέσετε ή τροποποιήσετε διαγράμματα.  
Η κλάση `Presentation` αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη, εκθέτοντας διαφάνειες, σχήματα και αντικείμενα διαγράμματος.  
Φορτώστε το αρχείο σας με `new Presentation("input.pptx")`, στη συνέχεια εργαστείτε με την πρώτη διαφάνεια χρησιμοποιώντας `presentation.getSlides().get_Item(0)`. Πάντα καλέστε `presentation.dispose()` σε ένα μπλοκ `finally` για να απελευθερώσετε τους εγγενείς πόρους.

### Πώς να δημιουργήσετε διάγραμμα – Προσθήκη Διαγράμματος Πίτας σε Διαφάνεια
Εισάγετε ένα Διάγραμμα Πίτας, ιδανικό για εμφάνιση αναλογικών δεδομένων.  
Η διεπαφή `IChart` είναι το κύριο σημείο εισόδου για τη διαχείριση διαγραμμάτων· η μέθοδος `addChart` δημιουργεί νέο διάγραμμα στη στοχευμένη διαφάνεια. Καθορίστε τον τύπο διαγράμματος (`ChartType.Pie`), τις συντεταγμένες X/Y και το πλάτος/ύψος. Μετά τη δημιουργία, μπορείτε να προσαρμόσετε τίτλους, υπόμνημα και σειρές δεδομένων μέσω του αντικειμένου `ChartData`.

### Πώς να εξάγετε διάγραμμα σε Excel – Εξαγωγή Δεδομένων Διαγράμματος
Η εξαγωγή δεδομένων διαγράμματος επιτρέπει στους αναλυτές να εργάζονται με τους αριθμούς στο Excel, προσφέροντας βαθύτερη κατανόηση.  
Η μέθοδος `readWorkbookStream()` επιστρέφει το υποκείμενο βιβλίο εργασίας Excel του διαγράμματος ως πίνακα byte. Καλέστε `chart.getChartData().readWorkbookStream()` για να λάβετε το βιβλίο εργασίας και γράψτε αυτόν τον πίνακα σε αρχείο με όνομα `externalWorkbook1.xlsx` χρησιμοποιώντας τυπική Java I/O. Το παραγόμενο αρχείο Excel περιέχει τα ακριβή δεδομένα που χρησιμοποιήθηκαν από το διάγραμμα, έτοιμο για περαιτέρω ανάλυση.

### Πώς να δημιουργήσετε διάγραμμα – Ορισμός Εξωτερικού Βιβλίου Εργασίας για Δυναμικά Δεδομένα
Συνδέστε ένα διάγραμμα με εξωτερικό βιβλίο εργασίας για να επιτρέψετε ζωντανές ενημερώσεις δεδομένων χωρίς επαναδημιουργία της διαφάνειας.  
Η μέθοδος `setExternalWorkbook()` συνδέει το διάγραμμα με ένα εξωτερικό αρχείο Excel για δυναμικές ενημερώσεις. Χρησιμοποιήστε `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` για να συνδέσετε το διάγραμμα με το εξωτερικό αρχείο. Όταν το βιβλίο εργασίας Excel τροποποιηθεί, το διάγραμμα θα αντανακλά αυτόματα τις αλλαγές την επόμενη φορά που θα ανοίξει η παρουσίαση, υποστηρίζοντας σενάρια δυναμικής αναφοράς.

## Πρακτικές Εφαρμογές
Το Aspose.Slides προσφέρει ευέλικτες λύσεις για διάφορα πραγματικά σενάρια:

1. **Διαφάνειες Επιχειρηματικών Αναφορών:** Αυτόματη δημιουργία διαγραμμάτων απόδοσης τριμηνιαίων αποτελεσμάτων από τις ροές δεδομένων σας.  
2. **Ακαδημαϊκές Παρουσιάσεις:** Μετατροπή ερευνητικών δεδομένων σε σαφείς οπτικοποιήσεις χωρίς χειροκίνητη δημιουργία διαγραμμάτων.  
3. **Οικονομική Ανάλυση:** Εξαγωγή δεδομένων διαγράμματος σε Excel για ελεγκτές ώστε να επαληθεύσουν τους αριθμούς, μειώνοντας τα χειροκίνητα σφάλματα.  
4. **Ανάλυση Μάρκετινγκ:** Οπτικοποίηση μετρικών εκστρατειών και κοινή χρήση επεξεργάσιμων βιβλίων εργασίας με ενδιαφερόμενους για συνεργατική λήψη αποφάσεων.  
5. **Αυτοματοποιημένη Δημιουργία Πίνακα Ελέγχου:** Συνδυάστε το API δημιουργίας διαγραμμάτων με προγραμματισμένες εργασίες για παραγωγή ενημερωμένων διαφανειών κάθε πρωί.

## Συνηθισμένα Προβλήματα & Επίλυση
- **`FileNotFoundException`** – Επαληθεύστε ότι το `dataDir` δείχνει σε έγκυρο φάκελο και ότι η διαδρομή εξόδου είναι εγγράψιμη.  
- **Διαρροές μνήμης** – Πάντα καλέστε `presentation.dispose()` σε μπλοκ `finally` για να ελευθερώσετε τους εγγενείς πόρους.  
- **Το διάγραμμα δεν εμφανίζεται** – Βεβαιωθείτε ότι ο δείκτης διαφάνειας (`get_Item(0)`) αντιστοιχεί σε υπάρχουσα διαφάνεια και ότι οι διαστάσεις του διαγράμματος βρίσκονται εντός των ορίων της διαφάνειας.  
- **Η εξαγωγή Excel παράγει κενό αρχείο** – Επιβεβαιώστε ότι το διάγραμμα περιέχει πραγματικά σειρές δεδομένων πριν καλέσετε `readWorkbookStream()`.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω διαφορετικό τύπο διαγράμματος (π.χ., Στήλη, Γραμμή) με τον ίδιο κώδικα;**  
Α: Ναι. Αντικαταστήστε το `ChartType.Pie` με οποιαδήποτε άλλη τιμή του enum `ChartType`, όπως `ChartType.Bar` ή `ChartType.Line`.

**Ε: Είναι δυνατόν να ενημερώσω το εξωτερικό βιβλίο εργασίας μετά τη δημιουργία του διαγράμματος;**  
Α: Απόλυτα. Τροποποιήστε το αρχείο Excel απευθείας· το συνδεδεμένο διάγραμμα θα αντανακλά τις αλλαγές την επόμενη φορά που θα ανοίξει η παρουσίαση.

**Ε: Χρειάζομαι ξεχωριστή άδεια για τη λειτουργία εξαγωγής σε Excel;**  
Α: Όχι. Η δυνατότητα εξαγωγής σε Excel περιλαμβάνεται στην τυπική άδεια Aspose.Slides for Java.

**Ε: Ποιες εκδόσεις Java υποστηρίζονται;**  
Α: Το Aspose.Slides for Java υποστηρίζει JDK 16 και νεότερες· παλαιότερες εκδόσεις μπορεί να λειτουργούν αλλά δεν έχουν δοκιμαστεί επίσημα.

**Ε: Πώς μπορώ να ενσωματώσω το παραγόμενο βιβλίο εργασίας Excel μέσα στο αρχείο PPTX;**  
Α: Χρησιμοποιήστε `chart.getChartData().setExternalWorkbook(null)` για να ενσωματώσετε το βιβλίο εργασίας, ή διατηρήστε τον εξωτερικό σύνδεσμο για δυναμικές ενημερώσεις.

---

**Τελευταία Ενημέρωση:** 2026-06-03  
**Δοκιμασμένο Με:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Συγγραφέας:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Δημιουργία διαγράμματος σε Java με Aspose.Slides – Προσθήκη & Επικύρωση Διαγραμμάτων](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Ανάκτηση Δεδομένων Workbook από Διαγράμματα PowerPoint χρησιμοποιώντας Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Πώς να Ενημερώσετε το Πεδίο Δεδομένων Διαγράμματος PowerPoint χρησιμοποιώντας Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}