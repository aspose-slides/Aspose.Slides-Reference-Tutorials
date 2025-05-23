---
"date": "2025-04-17"
"description": "Μάθετε να δημιουργείτε επαγγελματικές παρουσιάσεις χρησιμοποιώντας το Aspose.Slides για Java. Αυτός ο οδηγός καλύπτει τη ρύθμιση του περιβάλλοντός σας, την προσθήκη γραφημάτων στοιβαγμένων στηλών και την προσαρμογή τους για λόγους σαφήνειας."
"title": "Master Stacked Column Charts σε Java με το Aspose.Slides™ Ένας Πλήρης Οδηγός"
"url": "/el/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Κύριοι γραφήματα στοιβαγμένων στηλών σε Java με το Aspose.Slides: Ένας ολοκληρωμένος οδηγός

## Εισαγωγή

Αναβαθμίστε τις παρουσιάσεις σας ενσωματώνοντας διορατικές οπτικοποιήσεις δεδομένων με τη δύναμη του Aspose.Slides για Java. Η δημιουργία διαφανειών επαγγελματικής εμφάνισης με γραφήματα στοιβαγμένων στηλών είναι απλή, είτε προετοιμάζετε επιχειρηματικές αναφορές είτε παρουσιάζετε στατιστικά στοιχεία έργων.

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να χρησιμοποιήσετε το Aspose.Slides για Java για να δημιουργήσετε δυναμικές παρουσιάσεις και να προσθέσετε οπτικά ελκυστικά γραφήματα στοιβαγμένων στηλών. Μέχρι το τέλος αυτού του οδηγού, θα είστε εξοπλισμένοι με τις απαραίτητες δεξιότητες για να:
- Ρυθμίστε το περιβάλλον σας για να χρησιμοποιήσετε το Aspose.Slides
- Δημιουργήστε μια παρουσίαση από την αρχή
- Προσθήκη και προσαρμογή γραφημάτων στηλών με ποσοστιαία στοίβαξη
- Μορφοποιήστε τους άξονες του γραφήματος και τις ετικέτες δεδομένων για λόγους σαφήνειας

Ας εμβαθύνουμε στη δημιουργία παρουσιάσεων που θα αιχμαλωτίσουν το κοινό σας.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
- **Κιτ ανάπτυξης Java (JDK):** Έκδοση 8 ή νεότερη.
- **IDE:** Οποιοδήποτε Ολοκληρωμένο Περιβάλλον Ανάπτυξης όπως το IntelliJ IDEA ή το Eclipse.
- **Maven/Gradle:** Για τη διαχείριση εξαρτήσεων (προαιρετικό αλλά συνιστάται).
- **Βασικές γνώσεις Java:** Εξοικείωση με τις έννοιες προγραμματισμού Java.

## Ρύθμιση του Aspose.Slides για Java
Για να ξεκινήσετε, πρέπει να συμπεριλάβετε τη βιβλιοθήκη Aspose.Slides στο έργο σας. Δείτε πώς:

**Maven:**
Προσθέστε αυτήν την εξάρτηση στο δικό σας `pom.xml` αρχείο:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Βαθμός:**
Συμπεριλάβετε αυτό στο δικό σας `build.gradle` αρχείο:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Άμεση λήψη:**
Εναλλακτικά, κατεβάστε την τελευταία έκδοση του JAR από [Aspose.Slides για εκδόσεις Java](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
Μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμαστική περίοδο για να εξερευνήσετε τις λειτουργίες του Aspose.Slides. Για να καταργήσετε τους περιορισμούς αξιολόγησης, εξετάστε το ενδεχόμενο να αποκτήσετε μια προσωρινή ή αγορασμένη άδεια χρήσης.
- **Δωρεάν δοκιμή:** Αποκτήστε πρόσβαση σε περιορισμένες λειτουργίες χωρίς άμεσο κόστος.
- **Προσωρινή Άδεια:** Αίτημα μέσω [Ιστότοπος του Aspose](https://purchase.aspose.com/temporary-license/).
- **Αγορά:** Επισκεφθείτε τη σελίδα αγοράς για πλήρη πρόσβαση.

### Βασική Αρχικοποίηση
Δείτε πώς μπορείτε να αρχικοποιήσετε το Aspose.Slides στην εφαρμογή Java σας:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Δημιουργήστε μια παρουσία της κλάσης Presentation
        Presentation presentation = new Presentation();
        
        // Εκτέλεση λειτουργιών στο αντικείμενο παρουσίασης
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Οδηγός Εφαρμογής

### Δημιουργία παρουσίασης και προσθήκη διαφάνειας
**Επισκόπηση:**
Ξεκινήστε δημιουργώντας μια απλή παρουσίαση με μια αρχική διαφάνεια. Αυτή είναι η βάση για περαιτέρω βελτιώσεις.

#### Βήμα 1: Αρχικοποίηση αντικειμένου παρουσίασης
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Δημιουργήστε μια νέα παρουσία παρουσίασης
        Presentation presentation = new Presentation();
        
        // Αναφορά στην πρώτη διαφάνεια (δημιουργήθηκε αυτόματα)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Βήμα 2: Αποθήκευση της παρουσίασης
```java
// Αποθήκευση της παρουσίασης σε αρχείο
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Προσθήκη γραφήματος ποσοστιαίας στοίβας σε μια διαφάνεια
**Επισκόπηση:**
Βελτιώστε τη διαφάνειά σας προσθέτοντας ένα γράφημα στηλών με ποσοστιαία στοίβα, επιτρέποντας την εύκολη σύγκριση δεδομένων.

#### Βήμα 1: Αρχικοποίηση και πρόσβαση στη διαφάνεια
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Προχωρήστε στην προσθήκη γραφήματος στο επόμενο βήμα
    }
}
```

#### Βήμα 2: Προσθήκη γραφήματος σε διαφάνεια
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Προσαρμογή της μορφής αρίθμησης άξονα γραφήματος
**Επισκόπηση:**
Προσαρμόστε τη μορφή αριθμών του κάθετου άξονα του γραφήματός σας για βελτιωμένη αναγνωσιμότητα.

#### Βήμα 1: Προσθήκη και πρόσβαση σε γράφημα
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Βήμα 2: Ορισμός προσαρμοσμένης μορφής αριθμού
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Προσθήκη σειρών και σημείων δεδομένων σε γράφημα
**Επισκόπηση:**
Συμπληρώστε το γράφημά σας με σειρές δεδομένων, κάνοντάς το ενημερωτικό και οπτικά ελκυστικό.

#### Βήμα 1: Αρχικοποίηση παρουσίασης και γραφήματος
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Βήμα 2: Προσθήκη Σειράς Δεδομένων
```java
// Διαγραφή υπαρχουσών σειρών και προσθήκη νέων
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Προσθέστε περισσότερα σημεία δεδομένων όπως απαιτείται
```

### Μορφοποίηση χρώματος γεμίσματος σειράς
**Επισκόπηση:**
Βελτιώστε την αισθητική του γραφήματός σας μορφοποιώντας το χρώμα γεμίσματος κάθε σειράς.

#### Βήμα 1: Αρχικοποίηση και πρόσβαση στο γράφημα
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Βήμα 2: Ορισμός χρωμάτων γεμίσματος
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Επαναλάβετε για άλλες σειρές με διαφορετικά χρώματα
```

### Μορφοποίηση ετικετών δεδομένων
**Επισκόπηση:**
Κάντε τις ετικέτες δεδομένων σας πιο ευανάγνωστες προσαρμόζοντας τη μορφή τους.

#### Βήμα 1: Πρόσβαση σε σειρές γραφημάτων και σημεία δεδομένων
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Βήμα 2: Προσαρμογή ετικετών δεδομένων
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Σύναψη
Ακολουθώντας αυτόν τον οδηγό, μάθατε πώς να ρυθμίσετε το Aspose.Slides για Java και να δημιουργήσετε δυναμικές παρουσιάσεις με γραφήματα στηλών με ποσοστιαία στοίβαξη. Προσαρμόστε τα γραφήματά σας περαιτέρω προσαρμόζοντας τα χρώματα και τις ετικέτες ώστε να ταιριάζουν στις ανάγκες σας.

Καλή κωδικοποίηση!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}