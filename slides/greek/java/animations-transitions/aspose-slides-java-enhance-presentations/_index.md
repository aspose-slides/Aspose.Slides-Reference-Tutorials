---
date: '2025-12-10'
description: Μάθετε πώς να προσθέτετε κείμενο σε πίνακα και να σχεδιάζετε πλαίσια
  γύρω από το κείμενο στο PowerPoint χρησιμοποιώντας το Aspose.Slides for Java. Αυτός
  ο οδηγός καλύπτει τη δημιουργία πινάκων, τη ρύθμιση της στοίχισης του κειμένου και
  την πλαισίωση του περιεχομένου.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides για Java – προσθήκη κειμένου σε πίνακα και χειρισμός πλαισίου
url: /el/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Κατάκτηση της Διαχείρισης Πινάκων και Πλαισίων σε Παρουσιάσεις με το Aspose.Slides for Java

## Εισαγωγή

Η αποτελεσματική παρουσίαση δεδομένων μπορεί να είναι πρόκληση στο PowerPoint. Είτε είστε προγραμματιστής λογισμικού είτε σχεδιαστής παρουσιάσεων, **add text table** κελιά και σχεδιάστε πλαίσια γύρω από σημαντικές παραγράφους ώστε οι διαφάνειές σας να ξεχωρίζουν. Σε αυτό το tutorial θα δείτε ακριβώς πώς να προσθέσετε κείμενο σε πίνακα, να το ευθυγραμμίσετε και να σχεδιάσετε πλαίσια γύρω από το κείμενο — όλα με το Aspose.Slides for Java. Στο τέλος, θα μπορείτε να δημιουργήσετε επαγγελματικές παρουσιάσεις που τονίζουν τις σωστές πληροφορίες τη σωστή στιγμή.

Έτοιμοι να μεταμορφώσετε τις παρουσιάσεις σας; Ας ξεκινήσουμε!

## Γρήγορες Απαντήσεις
- **What does “add text to table” mean?** Σημαίνει την εισαγωγή ή την ενημέρωση του κειμενικού περιεχομένου των μεμονωμένων κελιών πίνακα προγραμματιστικά.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – αυτό το βήμα **save presentation as pptx** ολοκληρώνει τις αλλαγές σας.  
- **How can I align text inside a shape?** Χρησιμοποιήστε `TextAlignment.Left` (ή Center/Right) μέσω `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Ναι – επαναλάβετε τις παραγράφους, λάβετε το οριακό τους ορθογώνιο και προσθέστε ένα `IAutoShape` χωρίς γέμισμα και με μαύρη γραμμή.  
- **Do I need a license?** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγική χρήση.

## Προαπαιτούμενα

Πριν βουτήξετε στον κώδικα, βεβαιωθείτε ότι έχετε τα παρακάτω:

### Απαιτούμενες Βιβλιοθήκες
Θα χρειαστείτε το Aspose.Slides for Java. Δείτε πώς να το συμπεριλάβετε χρησιμοποιώντας Maven ή Gradle:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Ρύθμιση Περιβάλλοντος
Βεβαιωθείτε ότι έχετε εγκατεστημένο το Java Development Kit (JDK), προτιμότερα JDK 16 ή νεότερο, καθώς αυτό το παράδειγμα χρησιμοποιεί τον ταξινομητή `jdk16`.

### Προαπαιτούμενες Γνώσεις
- Βασική κατανόηση του προγραμματισμού Java.  
- Εξοικείωση με λογισμικό παρουσιάσεων όπως το PowerPoint.  
- Εμπειρία στη χρήση ενός ολοκληρωμένου περιβάλλοντος ανάπτυξης (IDE) όπως το IntelliJ IDEA ή το Eclipse.

## Ρύθμιση του Aspose.Slides for Java

Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides, ακολουθήστε τα παρακάτω βήματα:

1. **Install the Library**: Χρησιμοποιήστε Maven ή Gradle για τη διαχείριση των εξαρτήσεων, ή κατεβάστε το απευθείας από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Ξεκινήστε με δωρεάν δοκιμή κατεβάζοντας μια προσωρινή άδεια από [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Για πλήρη πρόσβαση, εξετάστε την αγορά άδειας στο [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**: Αρχικοποιήστε το περιβάλλον παρουσίασής σας με το παρακάτω απόσπασμα κώδικα:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Γιατί να προσθέσετε κείμενο σε πίνακα και να σχεδιάσετε πλαίσια;

Η προσθήκη κειμένου σε πίνακα σας επιτρέπει να παρουσιάσετε δομημένα δεδομένα με σαφήνεια, ενώ η σχεδίαση πλαισίων γύρω από παραγράφους ή συγκεκριμένα τμήματα (π.χ. εκείνα που περιέχουν τον χαρακτήρα **'0'**) τραβά το βλέμμα του κοινού σε σημαντικές τιμές. Αυτός ο συνδυασμός είναι ιδανικός για οικονομικές αναφορές, πίνακες ελέγχου ή οποιαδήποτε διαφάνεια όπου χρειάζεται να τονίσετε βασικούς αριθμούς χωρίς ακαταστασία.

## Πώς να προσθέσετε κείμενο σε πίνακα στο Aspose.Slides for Java

### Χαρακτηριστικό 1: Δημιουργία Πίνακα και Προσθήκη Κειμένου σε Κελιά

#### Επισκόπηση
Αυτή η λειτουργία δείχνει πώς να **how to create table**, στη συνέχεια **add text to table** κελιά και τελικά **save presentation as pptx**.

#### Βήματα

**1. Δημιουργία Πίνακα**  
Αρχικά, αρχικοποιήστε την παρουσίασή σας και προσθέστε έναν πίνακα στη θέση (50, 50) με καθορισμένα πλάτη στηλών και ύψη γραμμών.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Προσθήκη Κειμένου σε Κελιά**  
Δημιουργήστε παραγράφους με τμήματα κειμένου και προσθέστε τα σε ένα συγκεκριμένο κελί.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Αποθήκευση της Παρουσίασης**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Χαρακτηριστικό 2: Προσθήκη TextFrame σε AutoShape και Ορισμός Ευθυγράμμισης

#### Επισκόπηση
Μάθετε πώς να προσθέσετε ένα πλαίσιο κειμένου με συγκεκριμένη ευθυγράμμιση σε ένα auto shape—ένα παράδειγμα του **set text alignment java**.

#### Βήματα

**1. Προσθήκη AutoShape**  
Προσθέστε ένα ορθογώνιο ως AutoShape στη θέση (400, 100) με καθορισμένες διαστάσεις.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Ορισμός Ευθυγράμμισης Κειμένου**  
Ορίστε το κείμενο σε “Text in shape” και ευθυγραμμίστε το αριστερά.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Αποθήκευση της Παρουσίασης**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Χαρακτηριστικό 3: Σχεδίαση Πλαισίων γύρω από Παραγράφους και Τμήματα σε Κελιά Πίνακα

#### Επισκόπηση
Αυτή η λειτουργία εστιάζει στο **draw frames around text** και ακόμη και στο **draw rectangle around paragraph** για τμήματα που περιέχουν τον χαρακτήρα ‘0’.

#### Βήματα

**1. Δημιουργία Πίνακα**  
Επαναχρησιμοποιήστε τον κώδικα από το “Create Table and Add Text to Cells” για την αρχική ρύθμιση.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Προσθήκη Παραγράφων**  
Επαναχρησιμοποιήστε τον κώδικα δημιουργίας παραγράφων από την προηγούμενη λειτουργία.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Σχεδίαση Πλαισίων**  
Επαναλάβετε τις παραγράφους και τα τμήματα για να σχεδιάσετε πλαίσια γύρω τους.
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```

**4. Αποθήκευση της Παρουσίασης**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Συμπέρασμα
Ακολουθώντας αυτόν τον οδηγό, μπορείτε να **add text to table**, να ευθυγραμμίσετε κείμενο μέσα σε σχήματα και να **draw frames around text** για να τονίσετε σημαντικές πληροφορίες. Η κατάκτηση αυτών των τεχνικών σας επιτρέπει να δημιουργήσετε εξαιρετικά επαγγελματικές, δεδομενο‑κατευθυνόμενες παρουσιάσεις με το Aspose.Slides for Java. Για περαιτέρω εξερεύνηση, δοκιμάστε να συνδυάσετε αυτές τις λειτουργίες με γραφήματα, animations ή εξαγωγή σε PDF.

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω αυτά τα APIs με παλαιότερες εκδόσεις JDK;**  
A: Η βιβλιοθήκη υποστηρίζει JDK 8 και μετά, αλλά ο ταξινομητής `jdk16` παρέχει την καλύτερη απόδοση σε νεότερα runtime.

**Q: Πώς αλλάζω το χρώμα του πλαισίου;**  
A: Τροποποιήστε το χρώμα γεμίσματος της μορφής γραμμής, π.χ., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Είναι δυνατόν να εξάγω τη τελική διαφάνεια ως εικόνα;**  
A: Ναι—χρησιμοποιήστε `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` και στη συνέχεια αποθηκεύστε το byte array.

**Q: Τι κάνω αν χρειάζεται να επισημάνω μόνο τη λέξη “Total” μέσα σε ένα κελί;**  
A: Επαναλάβετε μέσω `cell.getTextFrame().getParagraphs()`, εντοπίστε το τμήμα που περιέχει “Total”, και σχεδιάστε ένα ορθογώνιο γύρω από το οριακό πλαίσιο του τμήματος.

**Q: Διαχειρίζεται το Aspose.Slides μεγάλες παρουσιάσεις αποδοτικά;**  
A: Το API μεταδίδει δεδομένα σε ροή και απελευθερώνει πόρους όταν κληθεί το `pres.dispose()`, κάτι που βοηθά στη διαχείριση μνήμης για μεγάλα αρχεία.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}