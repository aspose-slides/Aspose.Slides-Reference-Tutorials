---
date: '2026-07-03'
description: Μάθετε πώς να δημιουργήσετε διαγράμματα ηλιακού βήμα προς βήμα σε Java
  χρησιμοποιώντας το Aspose.Slides, με πλήρεις επιλογές προσαρμογής για παρουσιάσεις
  PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Πώς να δημιουργήσετε διαγράμματα ηλιακού τύπου σε Java χρησιμοποιώντας το Aspose.Slides
url: /el/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε διαγράμματα Sunburst σε Java χρησιμοποιώντας το Aspose.Slides

## Εισαγωγή
Στις σημερινές παρουσιάσεις που βασίζονται στα δεδομένα, η γρήγορη δημιουργία οπτικοποιήσεων **πώς να δημιουργήσετε sunburst** μπορεί να ξεχωρίσει τις διαφάνειές σας. Αυτό το σεμινάριο σας καθοδηγεί στη δημιουργία ενός διαγράμματος Sunburst με το Aspose.Slides για Java, από τη ρύθμιση του έργου μέχρι την τελική εξαγωγή, ώστε να μπορείτε να παραδίδετε εντυπωσιακά ιεραρχικά γραφικά δεδομένων χωρίς να αφήσετε το οικοσύστημα της Java.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για ένα αρχείο PowerPoint;** `Presentation` – αντιπροσωπεύει ολόκληρο το PPTX στη μνήμη.  
- **Πόσες γραμμές κώδικα απαιτούνται για ένα βασικό sunburst;** Συνήθως 5–7 γραμμές μόλις η βιβλιοθήκη αναφερθεί.  
- **Ποια μορφές εξόδου υποστηρίζονται;** PPTX, PDF, PNG, SVG και HTML.  
- **Μπορώ να μορφοποιήσω μεμονωμένα τμήματα;** Ναι – τα χρώματα γεμίσματος, τα περιγράμματα και οι ετικέτες δεδομένων είναι πλήρως προσαρμόσιμα.  
- **Χρειάζομαι άδεια για παραγωγή;** Μια δωρεάν αξιολόγηση λειτουργεί για δοκιμές· απαιτείται εμπορική άδεια για την ανάπτυξη.

## Τι είναι το Διάγραμμα Sunburst;
Ένα διάγραμμα Sunburst οπτικοποιεί ιεραρχικά δεδομένα ως συγκεντρικούς δακτυλίους, όπου κάθε δακτύλιος αντιπροσωπεύει ένα επίπεδο της ιεραρχίας. Επιτρέπει στους θεατές να κατανοήσουν τις σχέσεις γονέα‑παιδί με μια ματιά, καθιστώντας το ιδανικό για οργανωτικά διαγράμματα, ταξινομικές απεικονίσεις και μετρικές πολλαπλών επιπέδων. Είναι ιδιαίτερα χρήσιμο για την εμφάνιση κατηγοριών πολλαπλών επιπέδων όπως γραμμές προϊόντων, γεωγραφικές περιοχές ή οργανωτικές δομές, επιτρέποντας στους θεατές να δουν τόσο τη συνολική κατανομή όσο και την λεπτομερή ανάλυση εντός κάθε τμήματος.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για διαγράμματα Sunburst;
Το Aspose.Slides υποστηρίζει **30+ τύπους διαγραμμάτων**, επεξεργάζεται αρχεία έως **500 MB** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη, και αποδίδει γραφικά σε **300 DPI** για κρυστάλλινη έξοδο. Αυτές οι μετρήσιμες δυνατότητες εξασφαλίζουν γρήγορη δημιουργία και υψηλής ποιότητας οπτικά στοιχεία ακόμη και για μεγάλες παρουσιάσεις. Επιπλέον, η βιβλιοθήκη προσφέρει λειτουργίες ασφαλείς για νήματα και ενσωματώνεται άψογα με δημοφιλή εργαλεία κατασκευής Java, καθιστώντας την κατάλληλη τόσο για δημιουργία παρουσιάσεων σε επιφάνεια εργασίας όσο και σε διακομιστή σε μεγάλη κλίμακα.

## Προαπαιτούμενα
- Java Development Kit (JDK) 8 ή νεότερο.  
- Maven ή Gradle για διαχείριση εξαρτήσεων.  
- Aspose.Slides for Java (τελευταία έκδοση).  
- Βασική κατανόηση των ιεραρχικών δομών δεδομένων.

## Πώς να δημιουργήσετε διαγράμματα Sunburst βήμα προς βήμα;
Φορτώστε το περιβάλλον σας, προσθέστε ένα διάγραμμα, τροφοδοτήστε το με ιεραρχικά δεδομένα, μορφοποιήστε το και αποθηκεύστε το αρχείο – όλα σε λίγα απλά βήματα. Παρακάτω είναι η ακριβής ροή εργασίας που μπορείτε να ακολουθήσετε χωρίς να γράψετε επιπλέον κώδικα boilerplate. Η διαδικασία είναι πλήρως αυτοματοποιημένη, δεν απαιτεί χειροκίνητη αλληλεπίδραση UI, και μπορεί να ενσωματωθεί σε εργασίες batch ή web services για παραγωγή διαγραμμάτων κατ' απαίτηση.

### Βήμα 1: Ρύθμιση του Έργου
Προσθέστε την εξάρτηση Aspose.Slides Maven (ή το ισοδύναμο απόσπασμα Gradle) στο `pom.xml` σας. Αυτό φέρνει όλα τα απαιτούμενα δυαδικά αρχεία και τις μεταβατικές βιβλιοθήκες.

### Βήμα 2: Φόρτωση ή δημιουργία παρουσίασης
`Presentation` είναι το αντικείμενο υψηλότερου επιπέδου του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη. Δημιουργήστε το με `new Presentation()` για μια νέα παρουσία ή περάστε μια διαδρομή αρχείου για να ανοίξετε ένα υπάρχον PPTX.

### Βήμα 3: Προσθήκη διαγράμματος Sunburst
Εισάγετε ένα νέο σχήμα διαγράμματος σε μια διαφάνεια χρησιμοποιώντας `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Αυτό δημιουργεί το placeholder Sunburst έτοιμο για δεδομένα. `ChartType.Sunburst` καθορίζει τον τύπο διαγράμματος Sunburst όταν προστίθεται σε μια διαφάνεια.

### Βήμα 4: Συμπλήρωση ιεραρχικών δεδομένων
`ChartData` περιέχει τις σειρές δεδομένων και τις κατηγορίες για ένα διάγραμμα. Πρόσβαση στη συλλογή `ChartData` του διαγράμματος και προσθέστε σειρές και κατηγορίες που αντανακλούν την ιεραρχία σας. Για κάθε επίπεδο, καθορίστε τη σχέση γονέα‑παιδιού μέσω της ιδιότητας `ParentSeries`, επιτρέποντας στο διάγραμμα να αποδίδει αυτόματα συγκεντρικούς δακτυλίους.

### Βήμα 5: Προσαρμογή εμφάνισης
Ρυθμίστε λεπτομερώς τα χρώματα των τμημάτων, τα στυλ περιγραμμάτων και τις ετικέτες δεδομένων μέσω των αντικειμένων `ChartSeries` και `ChartDataPoint`. `ChartSeries` αντιπροσωπεύει μια σειρά σημείων δεδομένων σε ένα διάγραμμα. `ChartDataPoint` αντιπροσωπεύει ένα μεμονωμένο σημείο δεδομένων μέσα σε μια σειρά. Μπορείτε επίσης να ενεργοποιήσετε την περιστροφή 3‑Δ ή να ορίσετε την ιδιότητα `Explode` για να τονίσετε συγκεκριμένα τμήματα.

### Βήμα 6: Αποθήκευση της παρουσίασης
Το enum `SaveFormat` ορίζει τις μορφές αρχείων στις οποίες μπορείτε να αποθηκεύσετε μια παρουσίαση. Καλέστε `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` για να γράψετε το αρχείο στο δίσκο. Μπορείτε επίσης να εξάγετε σε PDF ή PNG αλλάζοντας την τιμή του enum `SaveFormat`.

## Πώς να προσαρμόσετε τα χρώματα του διαγράμματος Sunburst;
Καθορίστε ένα χρώμα γεμίσματος για κάθε `ChartDataPoint` χρησιμοποιώντας `point.getFillFormat().setFillType(FillType.Solid)` και στη συνέχεια `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Αυτή η άμεση προσέγγιση σας επιτρέπει να ταιριάξετε την εταιρική ταυτότητα ή να τονίσετε βασικά σημεία δεδομένων. Μπορείτε επίσης να εφαρμόσετε διαβαθμίσεις, να ρυθμίσετε τη διαφάνεια ή να χρησιμοποιήσετε χρώματα θέματος για να διασφαλίσετε τη συνέπεια με το υπόλοιπο σχεδιασμό της διαφάνειας.

## Συχνά Προβλήματα και Λύσεις
- **Πρόβλημα:** Η ιεραρχία εμφανίζεται επίπεδη.  
  **Λύση:** Βεβαιωθείτε ότι κάθε σειρά παιδιού αναφέρει σωστά το `ParentSeries`. Η έλλειψη συνδέσμων κάνει το διάγραμμα να αντιμετωπίζει όλα τα δεδομένα ως ένα μόνο επίπεδο.
- **Πρόβλημα:** Το εξαγόμενο PNG φαίνεται θολό.  
  **Λύση:** Αυξήστε το DPI εξαγωγής ορίζοντας `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Πρόβλημα:** Μεγάλα αρχεία PPTX προκαλούν OutOfMemoryError.  
  **Λύση:** Χρησιμοποιήστε `Presentation.setMemoryOptimization(true)` για ροή δεδομένων και διατήρηση χαμηλής χρήσης μνήμης.

## Συχνές Ερωτήσεις

**Ε:** Μπορώ να δημιουργήσω διάγραμμα Sunburst από αρχείο CSV;  
**Α:** Ναι. Διαβάστε το CSV, δημιουργήστε την ιεραρχία στη μνήμη και τροφοδοτήστε την στη συλλογή `ChartData` του διαγράμματος πριν την αποθηκεύσετε.

**Ε:** Υποστηρίζει το Aspose.Slides κινούμενες μεταβάσεις για διαγράμματα Sunburst;  
**Α:** Ναι. Εφαρμόστε ένα `SlideShowTransition` στη διαφάνεια ή χρησιμοποιήστε `ChartFormat.setAnimationEnabled(true)` για κινούμενη αναπαράσταση επιπέδου διαγράμματος.

**Ε:** Είναι δυνατόν να εξάγετε το διάγραμμα ως γραφικό SVG vector;  
**Α:** Απόλυτα. Αποθηκεύστε την παρουσίαση με `SaveFormat.Svg` για να λάβετε μια κλιμακώσιμη διανυσματική έκδοση του διαγράμματος Sunburst.

**Ε:** Ποιος είναι ο μέγιστος αριθμός σημείων δεδομένων που μπορεί να διαχειριστεί ένα διάγραμμα Sunburst;  
**Α:** Το Aspose.Slides επεξεργάζεται αξιόπιστα έως **10.000** σημεία δεδομένων σε ένα ενιαίο διάγραμμα Sunburst χωρίς μείωση απόδοσης.

**Ε:** Χρειάζομαι ξεχωριστή άδεια για κάθε περιβάλλον ανάπτυξης;  
**Α:** Μία εμπορική άδεια καλύπτει όλα τα περιβάλλοντα (development, staging, production) εφόσον τηρούνται οι όροι άδειας.

## Συμπέρασμα
Τώρα έχετε έναν πλήρη, βήμα‑προς‑βήμα οδηγό για **πώς να δημιουργήσετε sunburst** διαγράμματα σε Java χρησιμοποιώντας το Aspose.Slides. Ακολουθώντας τη ροή εργασίας παραπάνω, μπορείτε να δημιουργήσετε υψηλής ποιότητας, πλήρως προσαρμόσιμες ιεραρχικές οπτικοποιήσεις για οποιαδήποτε παρουσίαση PowerPoint.

**Τελευταία ενημέρωση:** 2026-07-03  
**Δοκιμάστηκε με:** Aspose.Slides for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [Πώς να προσθέσετε διαγράμματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java: Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Κατακτήστε την προσαρμογή διαγραμμάτων PowerPoint χρησιμοποιώντας το Aspose.Slides Java για δυναμικές παρουσιάσεις](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Κινούμενες κατηγορίες διαγραμμάτων PowerPoint με το Aspose.Slides για Java | Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}