---
date: '2026-07-08'
description: Μάθετε πώς να προσθέσετε διαγράμματα πίτας σε παρουσιάσεις PowerPoint
  χρησιμοποιώντας Aspose.Slides for Java. Ακολουθήστε αυτόν τον step‑by‑step οδηγό
  για να δημιουργήσετε και να προσαρμόσετε επαγγελματικά διαγράμματα πίτας.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Προσθέστε διάγραμμα πίτας PowerPoint χρησιμοποιώντας Aspose.Slides
  for Java. Αυτό το tutorial δείχνει πώς να δημιουργήσετε και να προσαρμόσετε διαγράμματα
  πίτας προγραμματιστικά, ιδανικό για automated reports.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Προσθήκη διαγράμματος πίτας PowerPoint με Aspose.Slides for Java – Quick
  Guide
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Πώς να προσθέσετε διάγραμμα πίτας PowerPoint με Aspose.Slides for Java
url: /el/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Προσθήκη διαγράμματος πίτας PowerPoint με Aspose.Slides για Java

## Εισαγωγή

Αν χρειάζεστε να **προσθέσετε διαφάνειες PowerPoint με διάγραμμα πίτας** χωρίς να ανοίγετε χειροκίνητα το PowerPoint, βρίσκεστε στο σωστό μέρος. Σε αυτόν τον οδηγό θα σας καθοδηγήσουμε στη ρύθμιση του Aspose.Slides for Java, τη δημιουργία ενός διαγράμματος πίτας και την προσαρμογή κάθε φέτας — ιδανικό για αυτοματοποιημένες αναφορές, πίνακες ελέγχου ή εξατομικευμένες παρουσιάσεις. Στο τέλος θα έχετε ένα επαναχρησιμοποιήσιμο απόσπασμα Java που δημιουργεί ένα επαγγελματικό αρχείο PowerPoint με διάγραμμα πίτας σε δευτερόλεπτα.

### Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί το διάγραμμα;** Aspose.Slides for Java (latest release).  
- **Μπορώ να το τρέξω χωρίς γραφικό περιβάλλον;** Yes—no Office installation required.  
- **Ποια έκδοση Java είναι βέλτιστη;** JDK 16+ for best performance and GC improvements.  
- **Πώς μπορώ να εκτοπίσω (explode) μια φέτα;** Call `setExplosion` on the `IDataPoint` and set a pixel offset.  
- **Χρειάζομαι άδεια για παραγωγή;** A trial works for development; a permanent license removes all evaluation limits.

## Γιατί να προσθέσετε διάγραμμα πίτας PowerPoint χρησιμοποιώντας Aspose.Slides για Java;

Μπορείτε να δημιουργήσετε ενημερωμένες οπτικές αναφορές απευθείας από τις υπηρεσίες back‑end σας, εξαλείφοντας τα σφάλματα αντιγραφής‑επικόλλησης και εξασφαλίζοντας στυλ σύμφωνο με το brand. Το Aspose.Slides υποστηρίζει **70+ τύπους διαγραμμάτων** και μπορεί να επεξεργαστεί παρουσιάσεις με **10.000+ διαφάνειες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, καθιστώντας το ιδανικό για αυτοματοποίηση μεγάλης κλίμακας.

## Προαπαιτούμενα

- **Aspose.Slides for Java** – the tutorial references version 25.4 (the latest at the time of writing).  
- **Java Development Kit** – JDK 16 or newer is recommended.  
- **Maven** ή **Gradle** για διαχείριση εξαρτήσεων.  

## Ρύθμιση Aspose.Slides για Java

### Maven
Προσθέστε αυτή την εξάρτηση στο αρχείο `pom.xml` σας:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Συμπεριλάβετε τα παρακάτω στο αρχείο `build.gradle` σας:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Εναλλακτικά, κατεβάστε την πιο πρόσφατη έκδοση απευθείας από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Άδεια
Για να χρησιμοποιήσετε το Aspose.Slides χωρίς περιορισμούς:

- Ξεκινήστε με μια **free trial** για αξιολόγηση του API.  
- Ζητήστε μια **temporary license** για εκτεταμένη δοκιμή στη σελίδα [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Αγοράστε πλήρη συνδρομή μέσω της [Purchase page](https://purchase.aspose.com/buy).

## Πώς να προσθέσετε διάγραμμα πίτας PowerPoint χρησιμοποιώντας Aspose.Slides για Java

Φορτώστε μια νέα παρουσίαση, εισάγετε ένα διάγραμμα πίτας και αποθηκεύστε το αρχείο — όλα σε τρία σύντομα βήματα. Αυτό το μοτίβο λειτουργεί για οποιοδήποτε μέγεθος συνόλου δεδομένων και μπορεί να τυλιχθεί σε βρόχο για αυτόματη δημιουργία δεκάδων διαφανειών. Η προσέγγιση είναι ελαφριά, απαιτώντας μόνο λίγες γραμμές κώδικα και χωρίς εξωτερικούς πόρους, καθιστώντας την κατάλληλη τόσο για μικρά βοηθητικά προγράμματα όσο και για μεγάλες εργασίες παρτίδας.

### Βήμα 1: Αρχικοποίηση της Παρουσίασης
Η κλάση `Presentation` αντιπροσωπεύει ένα μόνο αρχείο PowerPoint στη μνήμη. Η δημιουργία μιας παρουσίας σας δίνει ένα νέο, κενό σύνολο διαφανειών για εργασία.
```java
Presentation pres = new Presentation();
```

### Βήμα 2: Προσθήκη του Διαγράμματος Πίτας
Εισάγετε ένα διάγραμμα πίτας στην πρώτη διαφάνεια. Οι συντεταγμένες (50, 50) και το μέγεθος (600 × 400) ταιριάζουν με μια τυπική διάταξη 16:9 και αφήνουν χώρο για τίτλους.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Βήμα 3: Αποθήκευση της Παρουσίασης
Γράψτε την παρουσίαση στο δίσκο. Αντικαταστήστε το `YOUR_OUTPUT_DIRECTORY` με το φάκελο όπου θέλετε να αποθηκευτεί το αρχείο.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Βήμα 4: Καθαρισμός Πόρων
Αποδεσμεύστε το αντικείμενο `Presentation` για να ελευθερώσετε τους εγγενείς πόρους και να αποφύγετε διαρροές μνήμης.
```java
if (pres != null) pres.dispose();
```

## Πώς να προσαρμόσετε την εκτόξευση (explosion) και το χρώμα του σημείου δεδομένων;

Φορτώστε το διάγραμμα, εντοπίστε το στοχευόμενο σημείο δεδομένων και στη συνέχεια εφαρμόστε μια απόσταση εκτόξευσης και ένα γεμάτο χρώμα γεμίσματος. Αυτό κάνει τη φέτα να ξεχωρίζει για έμφαση. Αυτές οι προσαρμογές βοηθούν στην προσέλκυση της προσοχής του κοινού σε κρίσιμες τιμές και βελτιώνουν τη συνολική αναγνωσιμότητα του διαγράμματος.

### Βήμα 1: Φόρτωση υπάρχουσας παρουσίασης (ή επαναχρησιμοποίηση της πρόσφατα δημιουργημένης)
Το αντικείμενο `Presentation` φορτώνει ένα υπάρχον αρχείο PowerPoint στη μνήμη, επιτρέποντάς σας να τροποποιήσετε το περιεχόμενό του.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Βήμα 2: Πρόσβαση στο Διάγραμμα και στο Στόχο Σημείου Δεδομένων
Η διεπαφή `IDataPoint` αντιπροσωπεύει ένα μεμονωμένο σημείο δεδομένων (φέτα) μέσα σε μια σειρά διαγράμματος.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Βήμα 3: Εφαρμογή Εκτόξευσης και Χρώματος
`setExplosion(int)` ορίζει την απόσταση, σε pixel, με την οποία μια φέτα μετατοπίζεται από το κέντρο του διαγράμματος. Διαχωρίστε τη φέτα οπτικά με `setExplosion(20)` και αλλάξτε το γέμισμά της σε μπλε χρησιμοποιώντας `setFillType(FillType.Solid)` και `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Βήμα 4: Αποθήκευση και Αποδέσμευση
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Πρακτικές Εφαρμογές

- **Αναφορές Πωλήσεων:** Τονίστε τα κορυφαία προϊόντα με εκτοξευμένες φέτες.  
- **Ανάλυση Προϋπολογισμού:** Αναθέστε διαφορετικά χρώματα στα τμήματα για γρήγορη οπτική σύγκριση.  
- **Εκπαιδευτικές Διαφάνειες:** Διαιρέστε σύνθετες έννοιες σε εύπεπτα τμήματα διαγράμματος.  

## Σκέψεις Απόδοσης

- Αποδεσμεύστε τα αντικείμενα άμεσα για να αποφύγετε διαρροές μνήμης, ειδικά όταν δημιουργείτε πολλές διαφάνειες σε βρόχο.  
- Παρακολουθήστε τη χρήση του heap για μεγάλες παρουσιάσεις· χρησιμοποιήστε την υπερφόρτωση `Save` που δέχεται `OutputStream` για ροή δεδομένων και διατήρηση χαμηλού αποτυπώματος μνήμης.  
- Μείνετε στην **JDK 16+** για να επωφεληθείτε από τις τελευταίες βελτιώσεις της συλλογής απορριμμάτων, που μπορούν να μειώσουν το χρόνο επεξεργασίας έως και 30 % για πακέτα 1.000 διαφανειών.

## Συμπέρασμα

Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή ροή εργασίας για **προσθήκη διαγραμμάτων πίτας PowerPoint** χρησιμοποιώντας το Aspose.Slides for Java. Πειραματιστείτε με διαφορετικές αποστάσεις εκτόξευσης, χρώματα και σύνολα δεδομένων για να ταιριάζουν με το branding σας. Όταν είστε έτοιμοι, εξερευνήστε άλλους τύπους διαγραμμάτων — ράβδων, γραμμής ή διασποράς — για να δημιουργήσετε έναν πλήρη πίνακα αναλυτικών δεδομένων μέσα στο PowerPoint.

## Συχνές Ερωτήσεις

**Q: Ποιο είναι το μεγαλύτερο πλεονέκτημα της χρήσης του Aspose.Slides για Java;**  
A: Σας επιτρέπει να δημιουργείτε, επεξεργάζεστε και αποδίδετε αρχεία PowerPoint προγραμματιστικά χωρίς την ανάγκη εγκατάστασης του Microsoft Office, υποστηρίζοντας πάνω από 70 τύπους διαγραμμάτων και 100 + μορφές αρχείων.

**Q: Μπορώ να δημιουργήσω αρχείο PowerPoint από το μηδέν;**  
A: Ναι, δημιουργήστε ένα αντικείμενο `Presentation`, προσθέστε διαφάνειες, διαγράμματα ή σχήματα, και στη συνέχεια καλέστε `save` — όλα σε καθαρό κώδικα Java.

**Q: Πώς μπορώ να εκτοπίσω (explode) μια συγκεκριμένη φέτα πίτας;**  
A: Ανακτήστε το `IDataPoint` για τη φέτα και καλέστε `setExplosion(pixelOffset)`. Η απόσταση ορίζει πόσο μακριά μετακινείται η φέτα προς τα έξω.

**Q: Υπάρχει όριο στον αριθμό των διαφανειών που μπορώ να δημιουργήσω;**  
A: Το Aspose.Slides μπορεί να διαχειριστεί παρουσιάσεις με έως και **10.000 διαφάνειες** σε ένα μόνο αρχείο, εφόσον ροή (stream) το αποτέλεσμα για να αποφύγετε τη φόρτωση όλου στη μνήμη.

**Q: Πού μπορώ να βρω πιο προχωρημένα παραδείγματα προσαρμογής διαγραμμάτων;**  
A: Δείτε την επίσημη [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) για λεπτομερείς αναφορές API και παραδείγματα έργων.

## Πόροι

- **Τεκμηρίωση:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Λήψη Βιβλιοθήκης:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Αγορά Άδειας:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Δωρεάν Δοκιμή:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Προσωρινή Άδεια:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Φόρουμ Υποστήριξης:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Προσθέσετε Διαγράμματα στο PowerPoint Χρησιμοποιώντας Aspose.Slides για Java: Οδηγός Βήμα-Βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create and Validate Chart Layouts in PowerPoint Using Aspose.Slides for Java | SEO-Optimized Guide](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}