---
date: '2026-06-23'
description: Μάθετε πώς να δημιουργήσετε table στο PowerPoint, να προσθέσετε text
  σε table cells, να σχεδιάσετε frames γύρω από το text, και να αποθηκεύσετε την presentation
  ως pptx χρησιμοποιώντας το Aspose.Slides for Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
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
title: Πώς να δημιουργήσετε table στο PowerPoint και να σχεδιάσετε frames με Aspose.Slides
  for Java
url: /el/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε πίνακα στο PowerPoint και να σχεδιάσετε πλαίσια με Aspose.Slides για Java

## Εισαγωγή

Creating a **create table in PowerPoint** programmatically can save you hours of manual formatting, especially when you need to highlight key numbers or add explanatory notes. In this tutorial you’ll discover how to add text to table cells, draw frames around specific paragraphs, set precise text alignment, and finally **save presentation as pptx** – all with the powerful Aspose.Slides for Java API. By the end you’ll have a slide that looks polished, is easy to read, and instantly draws the audience’s attention to the most important data.

## Γρήγορες Απαντήσεις
- **What does “add text to table” mean?** Σημαίνει την εισαγωγή ή την ενημέρωση του κειμενικού περιεχομένου των μεμονωμένων κελιών του πίνακα προγραμματιστικά.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – this **save presentation as pptx** step ολοκληρώνει τις αλλαγές σας.  
- **How can I align text inside a shape?** Χρησιμοποιήστε `TextAlignment.Left` (or Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Ναι – επαναλάβετε στα παραγράφους, λάβετε το οριοθέτημα τους και προσθέστε ένα `IAutoShape` χωρίς γέμισμα και με μαύρη γραμμή.  
- **Do I need a license?** Μια προσωρινή άδεια λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγική χρήση.  

## Γιατί να σχεδιάζετε πλαίσια γύρω από το κείμενο;

Drawing a frame (or rectangle) around a paragraph or a specific portion—such as any text containing the character **'0'**—instantly draws the audience’s attention to that content. It provides a clear visual cue without altering the underlying text, making it ideal for highlighting key figures, warnings, or separating sections within a slide.

## Προαπαιτούμενα

Before diving into the code, ensure you have the following:

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
- Εξοικείωση με λογισμικό παρουσίασης όπως το PowerPoint.  
- Εμπειρία στη χρήση ενός Integrated Development Environment (IDE) όπως IntelliJ IDEA ή Eclipse.

## Ρύθμιση Aspose.Slides για Java

`Presentation` είναι η βασική κλάση του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη και παρέχει πρόσβαση σε διαφάνειες, σχήματα και πίνακες. Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides, ακολουθήστε τα παρακάτω βήματα:

1. **Εγκατάσταση της Βιβλιοθήκης**: Χρησιμοποιήστε Maven ή Gradle για τη διαχείριση των εξαρτήσεων, ή κατεβάστε το απευθείας από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).
2. **Απόκτηση Άδειας**:
   - Ξεκινήστε με μια δωρεάν δοκιμή κατεβάζοντας μια προσωρινή άδεια από [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Για πλήρη πρόσβαση, εξετάστε την αγορά άδειας στο [Purchase Aspose.Slides](https://purchase.aspose.com/buy).
3. **Βασική Αρχικοποίηση**:  
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

## Πώς να Προσθέσετε Κείμενο σε Πίνακα στο Aspose.Slides για Java;

Load a new `Presentation`, create a table at the desired coordinates, populate cells with `TextFrame` objects, and finally call `pres.save("output.pptx", SaveFormat.Pptx)`. This sequence creates a **create table in PowerPoint**, injects custom text into each cell, and writes the result to a PPTX file in a single, efficient workflow.

### Χαρακτηριστικό 1: Δημιουργία Πίνακα και Προσθήκη Κειμένου σε Κελιά

#### Επισκόπηση
Αυτή η λειτουργία δείχνει πώς να **create table**, στη συνέχεια **add text to table** σε κελιά και αργότερα **save presentation as pptx**.

#### Βήματα

**1. Δημιουργία Πίνακα**  
Πρώτα, αρχικοποιήστε την παρουσίασή σας και προσθέστε έναν πίνακα στη θέση (50, 50) με καθορισμένα πλάτη στηλών και ύψη γραμμών.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Προσθήκη Κειμένου σε Κελιά**  
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

**3. Αποθήκευση της Παρουσίασης**  
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

Ένα AutoShape είναι ένα σχήμα που μπορεί να περιέχει κείμενο και γραφικά.

**1. Προσθήκη AutoShape**  
Προσθέστε ένα ορθογώνιο ως AutoShape στη θέση (400, 100) με καθορισμένες διαστάσεις.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum defines horizontal alignment options for text within a shape.

**2. Ορισμός Στοίχισης Κειμένου**  
Ορίστε το κείμενο σε “Text in shape” και στοίχιση αριστερά.  
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
Αυτή η λειτουργία εστιάζει στο **draw frames around text** και ακόμη στο **draw rectangle around paragraph** για τμήματα που περιέχουν τον χαρακτήρα ‘0’.

#### Βήματα

`IAutoShape` αντιπροσωπεύει ένα αντικείμενο σχήματος που μπορεί να σχεδιαστεί σε μια διαφάνεια, όπως τα ορθογώνια που χρησιμοποιούνται για πλαίσια.

**1. Δημιουργία Πίνακα**  
Επαναχρησιμοποιήστε τον κώδικα από “Create Table and Add Text to Cells” για την αρχική ρύθμιση.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Προσθήκη Παραγράφων**  
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

**3. Σχεδίαση Πλαισίων**  
Επαναλάβετε στις παραγράφους και τα τμήματα για να σχεδιάσετε πλαίσια γύρω τους.  
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

## Συνηθισμένα Σφάλματα & Συμβουλές

- **Έλεγχοι Null** – Πάντα τυλίξτε τη χρήση του `Presentation` σε ένα μπλοκ try‑finally για να διασφαλίσετε ότι το `pres.dispose()` εκτελείται και ελευθερώνει τους εγγενείς πόρους.  
- **Ακρίβεια Οριοθετημένου Ορθογωνίου** – Το ορθογώνιο που επιστρέφεται από το `para.getRect()` αντανακλά την τρέχουσα διάταξη· εάν αλλάξετε το μέγεθος γραμματοσειράς ή τα περιθώρια, επανυπολογίστε το ορθογώνιο πριν σχεδιάσετε το πλαίσιο.  
- **Απόδοση** – Όταν εργάζεστε με πολύ μεγάλους πίνακες, εξετάστε το batching προσθήκης σχημάτων ή την επαναχρήση ενός μόνο αντικειμένου `IAutoShape` με ενημερωμένη γεωμετρία για μείωση του φορτίου μνήμης.  

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω αυτά τα API με παλαιότερες εκδόσεις JDK;**  
A: Η βιβλιοθήκη υποστηρίζει JDK 8 και μετά, αλλά ο ταξινομητής `jdk16` προσφέρει την καλύτερη απόδοση σε νεότερα runtime.

**Q: Πώς μπορώ να αλλάξω το χρώμα του πλαισίου;**  
A: Τροποποιήστε το χρώμα γεμίσματος του format γραμμής, π.χ., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Είναι δυνατόν να εξάγετε την τελική διαφάνεια ως εικόνα;**  
A: Ναι—χρησιμοποιήστε `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` και στη συνέχεια αποθηκεύστε το byte array.

**Q: Τι γίνεται αν χρειαστεί να επισημάνω μόνο τη λέξη “Total” μέσα σε ένα κελί;**  
A: Επαναλάβετε μέσω `cell.getTextFrame().getParagraphs()`, εντοπίστε το τμήμα που περιέχει “Total”, και σχεδιάστε ένα ορθογώνιο γύρω από το οριοθέτημα αυτού του τμήματος.

**Q: Το Aspose.Slides διαχειρίζεται αποτελεσματικά μεγάλες παρουσιάσεις;**  
A: Το API μεταδίδει δεδομένα σε ροή και απελευθερώνει πόρους όταν καλείται το `pres.dispose()`, κάτι που βοηθά στη διαχείριση μνήμης για μεγάλα αρχεία.

---

**Τελευταία Ενημέρωση:** 2026-06-23  
**Δοκιμή Με:** Aspose.Slides for Java 25.4 (jdk16)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικές Οδηγίες

- [Aspose.Slides for Java&#58; Κατακτήστε τον Πίνακα PPTX & τη Διαχείριση Κειμένου σε Παρουσιάσεις PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Πώς να Δημιουργήσετε Δυναμικά Πλαίσια Κειμένου στο PowerPoint Χρησιμοποιώντας Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Προσθήκη Στηλών σε Πλαίσιο Κειμένου χρησιμοποιώντας Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}