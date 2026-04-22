---
date: '2026-02-09'
description: Μάθετε πώς να σχεδιάζετε πλαίσια γύρω από το κείμενο και να προσθέτετε
  κείμενο σε κελιά πινάκων στο PowerPoint χρησιμοποιώντας το Aspose.Slides for Java.
  Αυτό το σεμινάριο καλύπτει τη δημιουργία πινάκων, τον καθορισμό της στοίχισης του
  κειμένου και την αποθήκευση της παρουσίασης ως pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Πώς να σχεδιάσετε πλαίσια και να προσθέσετε κείμενο σε πίνακα με το Aspose.Slides
  για Java
url: /el/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να Σχεδιάσετε Πλαίσια και να Προσθέσετε Κείμενο σε Πίνακα σε Παρουσιάσεις με το Aspose.Slides for Java

## Εισαγωγή

Η παρουσίαση δεδομένων με σαφήνεια στο PowerPoint μπορεί να είναι πραγματικό εμπόδιο, ειδικά όταν χρειάζεται να **add text to table** κελιά και να επισημάνετε σημαντικές τιμές με οπτικές ενδείξεις. Σε αυτόν τον οδηγό θα μάθετε **how to draw frames** γύρω από συγκεκριμένες παραγράφους, να ορίσετε την στοίχιση κειμένου μέσα σε σχήματα, και τελικά **save presentation as pptx**—όλα χρησιμοποιώντας το Aspose.Slides for Java. Στο τέλος θα έχετε μια επαγγελματική σειρά διαφανειών που κατευθύνει το βλέμμα του κοινού ακριβώς εκεί που θέλετε.

Έτοιμοι να κάνετε τις διαφάνειές σας να ξεχωρίζουν; Ας περάσουμε τη διαδικασία βήμα προς βήμα.

## Γρήγορες Απαντήσεις
- **What does “add text to table” mean?** Σημαίνει την εισαγωγή ή την ενημέρωση του κειμενικού περιεχομένου των μεμονωμένων κελιών πίνακα προγραμματιστικά.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – αυτό το βήμα **save presentation as pptx** ολοκληρώνει τις αλλαγές σας.  
- **How can I align text inside a shape?** Χρησιμοποιήστε `TextAlignment.Left` (ή Center/Right) μέσω του `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Ναι – επαναλάβετε τις παραγράφους, λάβετε το οριοθέτημα τους και προσθέστε ένα `IAutoShape` χωρίς γέμισμα και με μαύρη γραμμή.  
- **Do I need a license?** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγική χρήση.  

## Γιατί να Σχεδιάζετε Πλαίσια γύρω από το Κείμενο;

Η σχεδίαση ενός πλαισίου (ή ορθογωνίου) γύρω από μια παράγραφο ή ένα συγκεκριμένο τμήμα (για παράδειγμα, οποιοδήποτε κείμενο που περιέχει τον χαρακτήρα **'0'**) τραβά αμέσως την προσοχή. Αυτή η τεχνική είναι ιδανική για:

- Τονίζοντας τα κύρια οικονομικά στοιχεία σε έναν πίνακα.  
- Τονίζοντας προειδοποιήσεις ή σημαντικές σημειώσεις σε μια διαφάνεια.  
- Δημιουργώντας οπτικούς διαχωριστές χωρίς να προσθέτετε επιπλέον σχήματα χειροκίνητα.

## Προαπαιτούμενα

Πριν βυθιστείτε στον κώδικα, βεβαιωθείτε ότι έχετε τα εξής:

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

## Ρύθμιση του Aspose.Slides για Java

Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides, ακολουθήστε τα παρακάτω βήματα:

1. **Install the Library**: Χρησιμοποιήστε Maven ή Gradle για τη διαχείριση των εξαρτήσεων, ή κατεβάστε το απευθείας από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Ξεκινήστε με μια δωρεάν δοκιμή κατεβάζοντας μια προσωρινή άδεια από [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Για πλήρη πρόσβαση, σκεφτείτε την αγορά άδειας στο [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Αρχικοποιήστε το περιβάλλον παρουσίασής σας με το παρακάτω απόσπασμα κώδικα:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Πώς να Προσθέσετε Κείμενο σε Πίνακα στο Aspose.Slides για Java

### Χαρακτηριστικό 1: Δημιουργία Πίνακα και Προσθήκη Κειμένου σε Κελιά

#### Επισκόπηση
Αυτή η λειτουργία δείχνει πώς να **create table**, στη συνέχεια **add text to table** κελιά και αργότερα **save presentation as pptx**.

#### Βήματα

**1. Create a Table**  
Πρώτα, αρχικοποιήστε την παρουσίασή σας και προσθέστε έναν πίνακα στη θέση (50, 50) με καθορισμένα πλάτη στηλών και ύψη γραμμών.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Δημιουργήστε παραγράφους με τμήματα κειμένου και προσθέστε τις σε ένα συγκεκριμένο κελί.
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

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Χαρακτηριστικό 2: Προσθήκη TextFrame σε AutoShape και Ορισμός Στοίχισης

#### Επισκόπηση
Μάθετε πώς να προσθέσετε ένα πλαίσιο κειμένου με συγκεκριμένη στοίχιση σε ένα auto shape—ένα παράδειγμα του **set text alignment java**.

#### Βήματα

**1. Add an AutoShape**  
Προσθέστε ένα ορθογώνιο ως AutoShape στη θέση (400, 100) με καθορισμένες διαστάσεις.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Ορίστε το κείμενο σε “Text in shape” και ευθυγραμμίστε το αριστερά.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Χαρακτηριστικό 3: Σχεδίαση Πλαισίων γύρω από Παραγράφους και Τμήματα σε Κελιά Πίνακα

#### Επισκόπηση
Αυτή η λειτουργία εστιάζει στο **draw frames around text** και ακόμη στο **draw rectangle around paragraph** για τμήματα που περιέχουν τον χαρακτήρα ‘0’.

#### Βήματα

**1. Create a Table**  
Επαναχρησιμοποιήστε τον κώδικα από το “Create Table and Add Text to Cells” για την αρχική ρύθμιση.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Επαναχρησιμοποιήστε τον κώδικα δημιουργίας παραγράφων από το προηγούμενο χαρακτηριστικό.
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

**3. Draw Frames**  
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

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Συνηθισμένα Πιθανά Σφάλματα & Συμβουλές

- **Null checks** – Πάντα τυλίξτε τη χρήση του `Presentation` σε ένα μπλοκ try‑finally ώστε να εξασφαλίζεται ότι το `pres.dispose()` εκτελείται και ελευθερώνει τους εγγενείς πόρους.  
- **Bounding rectangle accuracy** – Το ορθογώνιο που επιστρέφεται από το `para.getRect()` αντικατοπτρίζει την τρέχουσα διάταξη· εάν αλλάξετε το μέγεθος γραμματοσειράς ή τα περιθώρια, υπολογίστε ξανά το ορθογώνιο πριν σχεδιάσετε το πλαίσιο.  
- **Performance** – Όταν εργάζεστε με πολύ μεγάλους πίνακες, σκεφτείτε την ομαδοποίηση προσθήκης σχημάτων ή την επαναχρησιμοποίηση ενός μόνο αντικειμένου `IAutoShape` με ενημερωμένη γεωμετρία για να μειώσετε το φορτίο μνήμης.  

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω αυτά τα API με παλαιότερες εκδόσεις JDK;**  
A: Η βιβλιοθήκη υποστηρίζει JDK 8 και μετά, αλλά ο ταξινομητής `jdk16` προσφέρει την καλύτερη απόδοση σε νεότερα περιβάλλοντα εκτέλεσης.

**Q: Πώς αλλάζω το χρώμα του πλαισίου;**  
A: Τροποποιήστε το χρώμα γεμίσματος του format γραμμής, π.χ., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Είναι δυνατόν να εξάγω την τελική διαφάνεια ως εικόνα;**  
A: Ναι—χρησιμοποιήστε `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` και στη συνέχεια αποθηκεύστε το byte array.

**Q: Τι κάνω αν χρειάζεται να επισημάνω μόνο τη λέξη “Total” μέσα σε ένα κελί;**  
A: Επαναλάβετε μέσω του `cell.getTextFrame().getParagraphs()`, εντοπίστε το τμήμα που περιέχει “Total”, και σχεδιάστε ένα ορθογώνιο γύρω από το οριοθέτημα του τμήματος.

**Q: Διαχειρίζεται το Aspose.Slides μεγάλες παρουσιάσεις αποδοτικά;**  
A: Το API μεταδίδει δεδομένα σε ροή και απελευθερώνει πόρους όταν κληθεί το `pres.dispose()`, κάτι που βοηθά στη διαχείριση μνήμης για μεγάλα αρχεία.

---

**Τελευταία Ενημέρωση:** 2026-02-09  
**Δοκιμή Με:** Aspose.Slides for Java 25.4 (jdk16)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
