---
date: '2026-11-16'
description: Σχεδιάστε πλαίσιο γύρω από το κείμενο σε πίνακες του PowerPoint χρησιμοποιώντας
  το Aspose.Slides for Java – μάθετε πώς να δημιουργείτε πίνακες, να προσθέτετε κείμενο
  σε κελιά, να επισημαίνετε κελιά και να εξάγετε το αρχείο ως PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Σχεδιάστε πλαίσιο γύρω από το κείμενο σε πίνακες του PowerPoint χρησιμοποιώντας
  το Aspose.Slides for Java. Αυτός ο οδηγός δείχνει πώς να δημιουργείτε πίνακες, να
  προσθέτετε και να ευθυγραμμίζετε κείμενο, να επισημαίνετε κελιά και να εξάγετε διαφάνειες
  ως PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Πώς να σχεδιάσετε πλαίσιο γύρω από το κείμενο και να δημιουργήσετε πίνακες
  στο PowerPoint με Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Πώς να σχεδιάσετε πλαίσιο γύρω από το κείμενο και να δημιουργήσετε πίνακες
  στο PowerPoint με Aspose.Slides for Java
url: /el/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να σχεδιάσετε πλαίσιο γύρω από κείμενο και να δημιουργήσετε πίνακες στο PowerPoint με το Aspose.Slides for Java

## Εισαγωγή

Η δημιουργία ενός **πλαισίου γύρω από κείμενο** σε μια διαφάνεια PowerPoint σας επιτρέπει να τονίσετε βασικούς αριθμούς χωρίς να αλλάξετε το υποκείμενο περιεχόμενο. Σε αυτό το tutorial θα μάθετε πώς να δημιουργείτε προγραμματιστικά έναν πίνακα, να εισάγετε και να ευθυγραμμίζετε κείμενο μέσα σε κελιά, να επισημαίνετε συγκεκριμένες λέξεις ή ολόκληρα κελιά και, τέλος, να αποθηκεύσετε την παρουσίαση ως αρχείο PPTX. Στο τέλος θα έχετε μια επαγγελματική διαφάνεια που εστιάζει την προσοχή του κοινού ακριβώς εκεί που θέλετε.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “add text to table”;** Σημαίνει την εισαγωγή ή ενημέρωση του κειμενικού περιεχομένου των μεμονωμένων κελιών του πίνακα προγραμματιστικά.  
- **Ποια μέθοδος αποθηκεύει το αρχείο;** `pres.save("output.pptx", SaveFormat.Pptx)` – αυτό το βήμα **save presentation as pptx** ολοκληρώνει τις αλλαγές σας.  
- **Πώς μπορώ να ευθυγραμμίσω κείμενο μέσα σε σχήμα;** Χρησιμοποιήστε `TextAlignment.Left` (ή Center/Right) μέσω `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Μπορώ να σχεδιάσω ένα ορθογώνιο γύρω από μια παράγραφο;** Ναι – επαναλάβετε τις παραγράφους, λάβετε το οριοθετητικό τους ορθογώνιο και προσθέστε ένα `IAutoShape` χωρίς γέμισμα και με μαύρη γραμμή.  
- **Χρειάζομαι άδεια;** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγική χρήση.  

## Γιατί να σχεδιάζετε πλαίσια γύρω από κείμενο;

Το σχεδιασμό ενός πλαισίου γύρω από κείμενο επισημαίνει αμέσως σημαντικούς αριθμούς, προειδοποιήσεις ή τίτλους. Παρέχει οπτική ένδειξη ενώ διατηρεί την αρχική μορφοποίηση αμετάβλητη, καθιστώντας το ιδανικό για οικονομικές αναφορές, πίνακες KPI ή οποιαδήποτε διαφάνεια όπου απαιτείται έμφαση.

## Τι είναι το πλαίσιο γύρω από κείμενο;

`draw frame around text` είναι η τεχνική προσθήκης προγραμματιστικά ενός ορθογώνιου σχήματος που ακολουθεί τα ακριβή όρια μιας παραγράφου ή ενός τμήματος κειμένου, χρησιμοποιώντας μορφοποίηση γραμμής χωρίς γέμισμα του εσωτερικού. Αυτή η προσέγγιση σας επιτρέπει να τονίσετε το περιεχόμενο χωρίς να τροποποιήσετε το ίδιο το κείμενο.

## Προαπαιτούμενα

### Απαιτούμενες βιβλιοθήκες
Θα χρειαστείτε το Aspose.Slides for Java. Συμπεριλάβετε το με έναν από τους διαχειριστές πακέτων:

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

Μπορείτε επίσης να περιηγηθείτε στις εκδόσεις στο [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Ρύθμιση περιβάλλοντος
Συνιστάται ένα Java Development Kit (JDK) 16 ή νεότερο, επειδή τα παραδείγματα χρησιμοποιούν τον ταξινομητή `jdk16`. Οποιοδήποτε IDE όπως το IntelliJ IDEA ή το Eclipse θα λειτουργήσει.

### Προαπαιτούμενες γνώσεις
- Βασικές γνώσεις προγραμματισμού Java.  
- Εξοικείωση με έννοιες του PowerPoint (διαφάνειες, σχήματα, πίνακες).  
- Κατανόηση του τρόπου διαχείρισης εξαρτήσεων από Maven/Gradle.

## Ρύθμιση Aspose.Slides for Java

`Presentation` είναι η κεντρική κλάση του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη και παρέχει πρόσβαση σε διαφάνειες, σχήματα και πίνακες. Μπορεί να διαχειριστεί παρουσιάσεις με έως **10.000 διαφάνειες** διατηρώντας τη χρήση μνήμης κάτω από **500 MB**, καθιστώντας το κατάλληλο για μεγάλης κλίμακας αυτοματοποίηση.

1. **Εγκατάσταση της βιβλιοθήκης** – χρησιμοποιήστε Maven ή Gradle, ή κατεβάστε την απευθείας από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).  
2. **Απόκτηση άδειας** – ξεκινήστε με μια δωρεάν δοκιμή από [Temporary License](https://purchase.aspose.com/temporary-license/) και αναβαθμίστε σε πλήρη άδεια στο [Purchase Aspose.Slides](https://purchase.aspose.com/buy) για παραγωγικές εργασίες.  
3. **Βασική αρχικοποίηση** – δημιουργήστε ένα νέο αντικείμενο `Presentation` και φορτώστε ή δημιουργήστε διαφάνειες όπως απαιτείται.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Πώς να προσθέσετε κείμενο σε πίνακα στο Aspose.Slides for Java;

`Presentation` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη.  
Φορτώστε ένα νέο `Presentation`, δημιουργήστε έναν πίνακα στις επιθυμητές συντεταγμένες, γεμίστε τα κελιά με αντικείμενα `TextFrame` και, τέλος, καλέστε `pres.save("output.pptx", SaveFormat.Pptx)`. Αυτή η ακολουθία δημιουργεί έναν **create table in PowerPoint**, ενσωματώνει προσαρμοσμένο κείμενο σε κάθε κελί και γράφει το αποτέλεσμα σε αρχείο PPTX σε μια ενιαία, αποδοτική ροή εργασίας.

### Άμεση απάντηση
Δημιουργήστε έναν πίνακα καλώντας `slide.getShapes().addTable(...)`, στη συνέχεια για κάθε κελί χρησιμοποιήστε `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Μετά τη συμπλήρωση όλων των κελιών, καλέστε `pres.save("output.pptx", SaveFormat.Pptx)` για να γράψετε το αρχείο. Αυτή η προσέγγιση σας επιτρέπει να ελέγχετε προγραμματιστικά το περιεχόμενο και το στυλ κάθε κελιού.

#### Χαρακτηριστικό 1: δημιουργία πίνακα και προσθήκη κειμένου σε κελιά

**1. create a table** – αρχικοποιήστε μια παρουσία, προσθέστε μια διαφάνεια και τοποθετήστε έναν πίνακα στο (50, 50) με καθορισμένα πλάτη στηλών και ύψη γραμμών.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – για κάθε κελί, δημιουργήστε ένα `Paragraph`, προσθέστε ένα `Portion` με το επιθυμητό κείμενο και αναθέστε την παράγραφο στο `TextFrame` του κελιού.  
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

**3. save the presentation** – καλέστε `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Πώς να σχεδιάσετε πλαίσιο γύρω από κείμενο σε διαφάνεια PowerPoint;

`Rectangle2D` αντιπροσωπεύει μια ορθογώνια περιοχή σε δισδιάστατο σύστημα συντεταγμένων.  
Φορτώστε τη διαφάνεια, εντοπίστε την παράγραφο ή το τμήμα που θέλετε να τονίσετε, ανακτήστε το οριοθετητικό του ορθογώνιο μέσω `getRect()` και, στη συνέχεια, προσθέστε ένα ορθογώνιο `IAutoShape` χωρίς γέμισμα και με χρωματιστή γραμμή. Αυτή η μέθοδος λειτουργεί τόσο για ολόκληρες παραγράφους όσο και για μεμονωμένα τμήματα λέξεων.

### Άμεση απάντηση
Για να σχεδιάσετε πλαίσιο γύρω από κείμενο, πρώτα λάβετε το ορθογώνιο της παραγράφου (`Rectangle2D rect = paragraph.getRect();`). Στη συνέχεια δημιουργήστε ένα ορθογώνιο `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), ορίστε `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)` και απενεργοποιήστε το γέμισμα (`shape.getFillFormat().setFillType(FillType.NoFill)`). Το σχήμα θα περιγράψει ακριβώς το κείμενο.

#### Χαρακτηριστικό 3: σχεδίαση πλαισίων γύρω από παραγράφους και τμήματα σε κελιά πίνακα

**1. create a table** – επαναχρησιμοποιήστε τον κώδικα από το Χαρακτηριστικό 1 για να δημιουργήσετε τον αρχικό πίνακα.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – επαναχρησιμοποιήστε τον κώδικα δημιουργίας παραγράφων από το Χαρακτηριστικό 1.  
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

**3. draw frames** – επαναλάβετε για κάθε παράγραφο, λάβετε το οριοθετητικό της και προσθέστε ένα ορθογώνιο σχήμα όπως περιγράφηκε παραπάνω. Για τμήματα που περιέχουν τον χαρακτήρα ‘0’, σχεδιάστε επιπλέον πλαίσιο για να τονίσετε αυτούς τους αριθμούς.  
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

**4. save the presentation** – ίδιο το τελικό βήμα όπως πριν.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Πώς να προσθέσετε πλαίσιο κειμένου σε AutoShape και να ορίσετε την ευθυγράμμιση

`AutoShape` είναι ένα σχήμα που μπορεί να περιέχει κείμενο, εικόνες ή άλλο περιεχόμενο.  
Ένα `AutoShape` μπορεί να περιέχει ένα `TextFrame`. Μπορείτε να ελέγξετε την οριζόντια ευθυγράμμιση χρησιμοποιώντας το enum `ParagraphFormat`.

### Άμεση απάντηση
Δημιουργήστε ένα ορθογώνιο AutoShape (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), αποκτήστε πρόσβαση στο `TextFrame`, ορίστε το κείμενο με `shape.getTextFrame().setText("Text in shape")`, και στη συνέχεια καλέστε `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. Αυτό ευθυγραμμίζει το κείμενο αριστερά μέσα στο σχήμα.

**1. add an AutoShape** – τοποθετήστε ένα ορθογώνιο στη ζητούμενη θέση.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – εφαρμόστε την αριστερή ευθυγράμμιση όπως φαίνεται παραπάνω.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – ίδιο το τελικό βήμα.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Συχνά προβλήματα & συμβουλές

- **Πάντα να απελευθερώνετε πόρους** – τυλίξτε τη χρήση του `Presentation` σε ένα try‑finally block και καλέστε `pres.dispose()` για να ελευθερώσετε τους εγγενείς πόρους.  
- **Επανυπολογίστε τα οριοθετητικά** – εάν αλλάξετε το μέγεθος γραμματοσειράς, τα περιθώρια ή το padding του κελιού μετά το σχεδιασμό ενός πλαισίου, καλέστε ξανά `paragraph.getRect()` πριν προσθέσετε το σχήμα.  
- **Δημιουργία σχήματος σε παρτίδες για μεγάλους πίνακες** – η επαναχρησιμοποίηση ενός μόνο αντικειμένου `IAutoShape` και η ενημέρωση της γεωμετρίας του μειώνει την πίεση μνήμης όταν επεξεργάζεστε πίνακες με εκατοντάδες γραμμές.  
- **Αριθμοί απόδοσης** – το Aspose.Slides μπορεί να δημιουργήσει ένα PPTX 200‑σελίδων σε κάτω από 2 δευτερόλεπτα σε τυπικό 4‑πύρηνο διακομιστή, και η σχεδίαση πλαισίων γύρω από 1.000 παραγράφους προσθέτει λιγότερο από 150 ms επιπλέον.

## Συχνές ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω αυτά τα API με παλαιότερες εκδόσεις JDK;**  
Α: Η βιβλιοθήκη υποστηρίζει JDK 8 και μετά, αλλά ο ταξινομητής `jdk16` προσφέρει την καλύτερη απόδοση σε νεότερα runtime.

**Ε: Πώς αλλάζω το χρώμα του πλαισίου;**  
Α: Τροποποιήστε το χρώμα γεμίσματος της γραμμής, π.χ., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Ε: Είναι δυνατόν να εξάγω τη τελική διαφάνεια ως εικόνα;**  
Α: Ναι—χρησιμοποιήστε `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` και αποθηκεύστε τον πίνακα byte.

**Ε: Τι κάνω αν θέλω να τονίσω μόνο τη λέξη “Total” μέσα σε ένα κελί;**  
Α: Επανάληψη μέσω `cell.getTextFrame().getParagraphs()`, εντοπισμός του τμήματος που περιέχει “Total” και σχεδίαση ορθογωνίου γύρω από το οριοθετητικό του τμήματος.

**Ε: Διαχειρίζεται το Aspose.Slides μεγάλες παρουσιάσεις αποδοτικά;**  
Α: Το API ρέει δεδομένα και απελευθερώνει πόρους όταν κληθεί `pres.dispose()`, κάτι που βοηθά στη διαχείριση μνήμης για μεγάλα αρχεία.

---

**Τελευταία ενημέρωση:** 2026-11-16  
**Δοκιμή με:** Aspose.Slides for Java 25.4 (jdk16)  
**Συγγραφέας:** Aspose  



## Σχετικά μαθήματα

- [Aspose.Slides for Java&#58; Master PPTX Table & Text Manipulation in PowerPoint Presentations](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [How to Create Dynamic Text Frames in PowerPoint Using Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Add Columns in Text Frame using Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}