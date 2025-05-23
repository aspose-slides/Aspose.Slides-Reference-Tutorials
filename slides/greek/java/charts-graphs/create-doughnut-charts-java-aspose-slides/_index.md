---
"date": "2025-04-17"
"description": "Μάθετε πώς να δημιουργείτε εκπληκτικά γραφήματα ντόνατ σε Java με το Aspose.Slides. Αυτός ο ολοκληρωμένος οδηγός καλύπτει την αρχικοποίηση, τη διαμόρφωση δεδομένων και την αποθήκευση παρουσιάσεων."
"title": "Δημιουργήστε γραφήματα ντόνατ σε Java χρησιμοποιώντας το Aspose.Slides - Ένας ολοκληρωμένος οδηγός"
"url": "/el/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργήστε γραφήματα ντόνατ σε Java χρησιμοποιώντας το Aspose.Slides: Ένας οδηγός βήμα προς βήμα

## Εισαγωγή

Στο σημερινό περιβάλλον που βασίζεται σε δεδομένα, η αποτελεσματική οπτικοποίηση πληροφοριών είναι το κλειδί για την ενίσχυση της κατανόησης και της αλληλεπίδρασης. Ενώ η δημιουργία επαγγελματικών γραφημάτων μέσω προγραμματισμού μπορεί να φαίνεται δύσκολη, ειδικά με Java, αυτός ο οδηγός θα σας καθοδηγήσει στη χρήση του Aspose.Slides για Java για να δημιουργήσετε γραφήματα Doughnut χωρίς κόπο.

Ακολουθώντας αυτά τα βήματα, οι προγραμματιστές θα αποκτήσουν πρακτική εμπειρία στον χειρισμό διαφανειών παρουσίασης και στην απρόσκοπτη ενσωμάτωση οπτικοποίησης δεδομένων.

**Βασικά σημεία:**
- Αρχικοποιήστε ένα αντικείμενο παρουσίασης χρησιμοποιώντας το Aspose.Slides Java.
- Διαμορφώστε δεδομένα γραφήματος και διαχειριστείτε υπάρχουσες σειρές ή κατηγορίες.
- Προσθέστε και προσαρμόστε σειρές και κατηγορίες για τα γραφήματά σας.
- Μορφοποιήστε και εμφανίστε σημεία δεδομένων αποτελεσματικά.
- Αποθηκεύστε την παρουσίασή σας σε διάφορες μορφές με ευκολία.

Πριν ξεκινήσετε την υλοποίηση, βεβαιωθείτε ότι έχετε όλα όσα χρειάζεστε για να ξεκινήσετε.

## Προαπαιτούμενα

Για να ακολουθήσετε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε:

- **Απαιτούμενες βιβλιοθήκες:**
  - Aspose.Slides για Java έκδοση 25.4 ή νεότερη.
  
- **Ρύθμιση περιβάλλοντος:**
  - JDK 16 ή νεότερη έκδοση εγκατεστημένη στο σύστημά σας.
  - Ένα IDE όπως το IntelliJ IDEA, το Eclipse ή το NetBeans.

- **Προαπαιτούμενα Γνώσεων:**
  - Βασική κατανόηση των εννοιών προγραμματισμού Java.
  - Εξοικείωση με τη διαχείριση εξαρτήσεων σε έργα Maven ή Gradle.

## Ρύθμιση του Aspose.Slides για Java

Για να ενσωματώσετε το Aspose.Slides στο έργο σας, ακολουθήστε τα παρακάτω βήματα με βάση το εργαλείο δημιουργίας σας:

**Ρύθμιση Maven:**
Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` αρχείο:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Ρύθμιση Gradle:**
Συμπεριλάβετε τα ακόλουθα στο `build.gradle` αρχείο:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Άμεση λήψη:**
Εναλλακτικά, κατεβάστε την τελευταία έκδοση απευθείας από [Aspose.Slides για εκδόσεις Java](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας

Για να χρησιμοποιήσετε το Aspose.Slides χωρίς περιορισμούς αξιολόγησης:
- **Δωρεάν δοκιμή:** Ξεκινήστε με μια προσωρινή άδεια χρήσης για να εξερευνήσετε όλες τις λειτουργίες.
- **Προσωρινή Άδεια:** Αποκτήστε ένα μέσω του [Ιστότοπος Aspose](https://purchase.aspose.com/temporary-license/).
- **Αγορά:** Σκεφτείτε το ενδεχόμενο αγοράς για συνεχή χρήση.

Εφαρμόστε την άδεια χρήσης σας στην εφαρμογή Java χρησιμοποιώντας:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Οδηγός Εφαρμογής

### Αρχικοποίηση παρουσίασης και γραφήματος

#### Επισκόπηση
Ξεκινήστε αρχικοποιώντας ένα αντικείμενο παρουσίασης και προσθέτοντας ένα γράφημα Doughnut στην πρώτη διαφάνεια.

**Βήμα 1: Αρχικοποίηση παρουσίασης**
Φορτώστε ένα υπάρχον αρχείο PPTX ή δημιουργήστε ένα νέο:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Βήμα 2: Προσθήκη γραφήματος ντόνατ**
Δημιουργήστε ένα γράφημα στην πρώτη διαφάνεια σε καθορισμένες συντεταγμένες:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Ρύθμιση παραμέτρων βιβλίου εργασίας δεδομένων γραφήματος και εκκαθάριση υπαρχουσών σειρών/κατηγοριών

#### Επισκόπηση
Ρυθμίστε τις παραμέτρους του βιβλίου εργασίας δεδομένων γραφήματος και καταργήστε τυχόν προϋπάρχουσες σειρές ή κατηγορίες.

**Βήμα 1: Βιβλίο εργασίας δεδομένων γραφήματος πρόσβασης**
Ανακτήστε το βιβλίο εργασίας που είναι συνδεδεμένο με το γράφημά σας:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Βήμα 2: Διαγραφή υπαρχουσών σειρών και κατηγοριών**
Βεβαιωθείτε ότι δεν υπάρχουν υπολειπόμενα σημεία δεδομένων:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Προσθήκη Σειράς σε Γράφημα

#### Επισκόπηση
Συμπληρώστε το γράφημά σας με πολλαπλές σειρές, καθεμία από τις οποίες έχει προσαρμοστεί ως προς την εμφάνιση και τη συμπεριφορά της.

**Βήμα 1: Προσθήκη Σειρών Επαναληπτικά**
Επαναλάβετε τους δείκτες για να προσθέσετε σειρές:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Προσαρμόστε τη σειρά
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Προσθήκη κατηγοριών και σημείων δεδομένων σε γράφημα

#### Επισκόπηση
Διαμορφώστε κατηγορίες και προσθέστε σημεία δεδομένων με συγκεκριμένη μορφοποίηση για ετικέτες.

**Βήμα 1: Προσθήκη κατηγοριών**
Δείκτες επανάληψης για κάθε κατηγορία:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Βήμα 2: Προσθήκη σημείων δεδομένων σε κάθε σειρά**
Επαναλάβετε κάθε σειρά για την τρέχουσα κατηγορία:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Ρυθμίσεις μορφής σημείου δεδομένων
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Μορφοποίηση ετικέτας για την τελευταία σειρά
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Προσαρμογή επιλογών εμφάνισης
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Προσαρμογή θέσης ετικέτας
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Αποθήκευση της παρουσίασης

#### Επισκόπηση
Μόλις διαμορφώσετε το γράφημά σας, αποθηκεύστε την παρουσίαση σε έναν καθορισμένο κατάλογο.

**Βήμα 1: Αποθήκευση της παρουσίασης**
Χρησιμοποιήστε το `save` μέθοδος εγγραφής αλλαγών:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Σύναψη

Τώρα μάθατε πώς να δημιουργείτε και να προσαρμόζετε γραφήματα Doughnut σε Java χρησιμοποιώντας το Aspose.Slides. Αυτά τα βήματα παρέχουν μια βάση για την ενσωμάτωση εξελιγμένων οπτικοποιήσεων δεδομένων στις παρουσιάσεις σας.

**Επόμενα βήματα:**
- Πειραματιστείτε με διαφορετικούς τύπους γραφημάτων που είναι διαθέσιμοι στο Aspose.Slides.
- Εξερευνήστε πρόσθετες επιλογές προσαρμογής, όπως χρώματα, γραμματοσειρές και στυλ, ώστε να ταιριάζουν με τις ανάγκες της επωνυμίας σας.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}