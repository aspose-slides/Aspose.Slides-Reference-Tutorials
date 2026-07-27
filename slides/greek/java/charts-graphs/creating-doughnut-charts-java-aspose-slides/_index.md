---
date: '2026-07-27'
description: Μάθετε πώς να δημιουργήσετε doughnut chart java χρησιμοποιώντας Aspose.Slides
  – ένας γρήγορος οδηγός για τη ρύθμιση της library, την προσθήκη ενός προσαρμόσιμου
  doughnut chart, την προσαρμογή του hole size και την αποθήκευση του presentation.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Μάθετε πώς να δημιουργήσετε doughnut chart java χρησιμοποιώντας Aspose.Slides
  – ένας γρήγορος οδηγός για τη ρύθμιση της library, την προσθήκη ενός προσαρμόσιμου
  doughnut chart, την προσαρμογή του hole size και την αποθήκευση του presentation.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Δημιουργία doughnut chart Java – Βήμα‑βήμα με Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Δημιουργία doughnut chart Java – Βήμα‑βήμα με Aspose.Slides
url: /el/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε διαγράμματα ντόνατ σε Java χρησιμοποιώντας το Aspose.Slides για παρουσιάσεις

## Εισαγωγή
Η δημιουργία οπτικά ελκυστικών παρουσιάσεων είναι απαραίτητη για την αποτελεσματική μετάδοση πληροφοριών. **Create doughnut chart java** είναι μια συχνή απαίτηση όταν χρειάζεται να απεικονίσετε ποσοστιαία δεδομένα με μοντέρνο στυλ. Σε αυτό το tutorial θα μάθετε πώς να ρυθμίσετε το Aspose.Slides for Java, να δημιουργήσετε ένα διάγραμμα ντόνατ, να προσαρμόσετε το μέγεθος της τρύπας και τα χρώματα, και τέλος να αποθηκεύσετε το αρχείο παρουσίασης. Στο τέλος θα έχετε ένα επαναχρησιμοποιήσιμο πρότυπο που μπορείτε να ενσωματώσετε σε οποιοδήποτε έργο Java που δημιουργεί αυτόματα PowerPoint decks.

**Τι θα μάθετε:**
- Ρύθμιση του Aspose.Slides for Java
- Δημιουργία και διαμόρφωση διαγραμμάτων ντόνατ σε παρουσιάσεις
- Προσαρμογή της αισθητικής του διαγράμματος, όπως το μέγεθος της τρύπας
- Αποθήκευση της παρουσίασης με το νέο διάγραμμα

Ας ξεκινήσουμε με τη ρύθμιση του περιβάλλοντος!

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη δημιουργεί doughnut chart java;** Aspose.Slides for Java.
- **Πόσες γραμμές κώδικα απαιτούνται για ένα βασικό doughnut chart;** Περίπου 8–10 γραμμές μετά την δημιουργία της παρουσίασης.
- **Μπορώ να αλλάξω το μέγεθος της τρύπας;** Ναι, η μέθοδος `setHoleSize(double)` δέχεται τιμές από 0 % έως 100 %.
- **Ποιοι μορφότυποι εξόδου υποστηρίζονται;** PPTX, PDF, XPS, PNG, JPEG και αρκετοί άλλοι (πάνω από 50 συνολικά).
- **Χρειάζομαι άδεια για παραγωγική χρήση;** Απαιτείται εμπορική άδεια για απεριόριστη χρήση· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.

## Τι είναι το Aspose.Slides for Java;
**Aspose.Slides for Java** είναι ένα πλήρως διαχειριζόμενο API που επιτρέπει στους προγραμματιστές να δημιουργούν, τροποποιούν, μετατρέπουν και αποδίδουν αρχεία PowerPoint χωρίς το Microsoft Office. Υποστηρίζει περισσότερα από 50 μορφότυπους αρχείων και μπορεί να διαχειριστεί παρουσιάσεις με χιλιάδες διαφάνειες διατηρώντας χαμηλή χρήση μνήμης.

## Γιατί να χρησιμοποιείτε διαγράμματα ντόνατ σε παρουσιάσεις;
Τα διαγράμματα ντόνατ εμφανίζουν σχέσεις μέρος‑προς‑ολό, αφήνοντας χώρο στο κέντρο για ετικέτες ή εικόνες. Το Aspose.Slides μπορεί να αποδώσει διαγράμματα ντόνατ έως **500 διαφάνειες ανά λεπτό** σε έναν τυπικό διακομιστή 2.5 GHz, και επεξεργάζεται **παρουσιάσεις εκατοντάδων σελίδων** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, καθιστώντας το ιδανικό για λύσεις αναφοράς μεγάλης κλίμακας.

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε καλύψει τα παρακάτω προαπαιτούμενα:

### Απαιτούμενες Βιβλιοθήκες και Εκδόσεις
Για να εργαστείτε με το Aspose.Slides for Java, συμπεριλάβετε το στη έργο σας μέσω Maven ή Gradle, ή κατεβάστε το απευθείας.

#### Απαιτήσεις Ρύθμισης Περιβάλλοντος
- Ένα λειτουργικό Java Development Kit (JDK), προτιμότερα έκδοση 8 ή νεότερη.
- Ένα Integrated Development Environment (IDE) όπως IntelliJ IDEA ή Eclipse.

### Προαπαιτούμενες Γνώσεις
Η εξοικείωση με τη Java και τις βασικές έννοιες προγραμματισμού είναι ωφέλιμη. Βασικές γνώσεις Maven ή Gradle θα βοηθήσουν στην απλοποίηση της διαδικασίας ρύθμισης.

## Ρύθμιση του Aspose.Slides for Java
Η ενσωμάτωση του Aspose.Slides στο έργο σας μπορεί να γίνει με διάφορους τρόπους:

**Maven:**  
Προσθέστε αυτή την εξάρτηση στο αρχείο `pom.xml` σας:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Συμπεριλάβετε αυτό στο αρχείο `build.gradle` σας:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Άμεση Λήψη:**  
Εναλλακτικά, κατεβάστε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
- **Δωρεάν Δοκιμή:** Ξεκινήστε κατεβάζοντας μια δοκιμαστική έκδοση για να εξερευνήσετε τις δυνατότητες του Aspose.Slides.  
- **Προσωρινή Άδεια:** Αποκτήστε μια προσωρινή άδεια για εκτεταμένη λειτουργικότητα χωρίς περιορισμούς.  
- **Αγορά:** Για συνεχή χρήση, απαιτείται αγορά άδειας.

Μόλις έχετε ρυθμίσει τη βιβλιοθήκη και το περιβάλλον σας, ας προχωρήσουμε στην υλοποίηση του διαγράμματος ντόνατ.

## Πώς να δημιουργήσετε ένα διάγραμμα ντόνατ σε Java;
Φορτώστε ένα νέο αντικείμενο `Presentation`, προσθέστε ένα διάγραμμα ντόνατ σε μια διαφάνεια, ορίστε το μέγεθος της τρύπας και αποθηκεύστε το αρχείο – όλα σε λίγες απλές κλήσεις API. Αυτή η προσέγγιση σας δίνει πλήρη έλεγχο στα δεδομένα του διαγράμματος, την εμφάνιση και τη μορφή εξόδου, και λειτουργεί χωρίς την ανάγκη εγκατάστασης του Microsoft PowerPoint στον διακομιστή.

### Αρχικοποίηση Αντικειμένου Presentation
Η κλάση `Presentation` είναι το κορυφαίο αντικείμενο του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Αυτό το βήμα δημιουργεί μια κενή παρουσίαση όπου μπορείτε να προσθέσετε διαφάνειες, σχήματα και διαγράμματα.

### Προσθήκη Διαγράμματος Ντόνατ στη Διαφάνεια
`ISlide` είναι η διεπαφή για μια μοναδική διαφάνεια· μπορείτε να ανακτήσετε την πρώτη διαφάνεια ή να προσθέσετε μια νέα.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Η μέθοδος `addChart` δημιουργεί ένα διάγραμμα ντόνατ· οι παράμετροι ορίζουν τη θέση (X, Y) και το μέγεθος (πλάτος, ύψος) στη διαφάνεια.

### Διαμόρφωση Μεγέθους Τρύπας Ντόνατ
`Chart` εκθέτει τη μέθοδο `setHoleSize(double)` για να ελέγξει την εσωτερική ακτίνα ως ποσοστό της ακτίνας του διαγράμματος.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Ορίζοντας το μέγεθος της τρύπας στο 90 % κάνει το διάγραμμα να φαίνεται σχεδόν ως πλήρης κύκλος, χρήσιμο όταν θέλετε να τονίσετε τα εξωτερικά τμήματα.

### Αποθήκευση Παρουσίασης
`presentation.save(String, SaveFormat)` γράφει το αρχείο στο δίσκο στη μορφή που επιλέξατε.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Το παράδειγμα αποθηκεύει το αποτέλεσμα ως `DoughnutHoleSize_out.pptx`, αλλά μπορείτε επίσης να επιλέξετε PDF, PNG ή οποιονδήποτε από τους 50+ υποστηριζόμενους μορφότυπους.

### Καθαρισμός Πόρων
Καλώντας `presentation.dispose()` απελευθερώνετε τους εγγενείς πόρους και αποτρέπετε διαρροές μνήμης, κάτι ιδιαίτερα σημαντικό σε διακομιστές με μακρά διάρκεια λειτουργίας.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Πρακτικές Εφαρμογές
Τα διαγράμματα ντόνατ είναι ευέλικτα. Εδώ είναι μερικά σενάρια όπου ξεχωρίζουν:
1. **Κατανομή Προϋπολογισμού:** Εμφανίζει πώς ένας προϋπολογισμός κατανέμεται μεταξύ τμημάτων.  
2. **Αποτελέσματα Έρευνας:** Οπτικοποιεί τις απαντήσεις σε ερωτήσεις με πολλαπλές επιλογές.  
3. **Πηγές Κυκλοφορίας Ιστοσελίδας:** Δείχνει το ποσοστό της κυκλοφορίας που προέρχεται από διαφορετικά κανάλια (οργανικό, πληρωμένο, παραπομπή κ.λπ.).

## Σκέψεις για την Απόδοση
Κατά τη χρήση του Aspose.Slides, λάβετε υπόψη τις παρακάτω συμβουλές για βέλτιστη απόδοση:
- Αποδεσμεύετε τα αντικείμενα `Presentation` μόλις τελειώσετε για να ελευθερώσετε τη φυσική μνήμη.  
- Χρησιμοποιήστε ροές (`FileInputStream`, `ByteArrayOutputStream`) για μεγάλα σύνολα δεδομένων ώστε να αποφύγετε τη φόρτωση ολόκληρων αρχείων στη RAM.  
- Επαναχρησιμοποιήστε αντικείμενα διαγράμματος όταν δημιουργείτε πολλές διαφάνειες σε βρόχο για να μειώσετε το κόστος δημιουργίας αντικειμένων.

## Συχνά Προβλήματα και Λύσεις
- **Σφάλμα κατά την αποθήκευση:** Επαληθεύστε ότι ο φάκελος εξόδου υπάρχει και ότι η εφαρμογή έχει δικαιώματα εγγραφής.  
- **Απουσία δεδομένων διαγράμματος:** Βεβαιωθείτε ότι έχετε γεμίσει τη συλλογή `ChartData` του διαγράμματος πριν καλέσετε `setHoleSize`.  
- **Αιχμές μνήμης:** Για παρουσιάσεις με χιλιάδες διαφάνειες, μειώστε το μέγεθος με `Presentation.setSlideSize` και αποδεσμεύστε ενδιάμεσες διαφάνειες άμεσα.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να προσαρμόσω τα χρώματα των τμημάτων του διαγράμματος ντόνατ;**  
Α: Ναι. Χρησιμοποιήστε `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` και στη συνέχεια ορίστε το επιθυμητό χρώμα RGB.

**Ε: Πώς προσθέτω ετικέτες δεδομένων στο διάγραμμά μου;**  
Α: Καλέστε `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` για να εμφανίσετε την τιμή μέσα σε κάθε τμήμα.

**Ε: Μπορώ να αποθηκεύσω τα διαγράμματα σε μορφές εκτός του PPTX;**  
Α: Απόλυτα. Το Aspose.Slides υποστηρίζει PDF, XPS, PNG, JPEG, TIFF και πολλές άλλες μορφές—πάνω από 50 συνολικά.

**Ε: Τι πρέπει να κάνω αν αντιμετωπίσω εξαίρεση κατά τη φόρτωση μεγάλης παρουσίασης;**  
Α: Χρησιμοποιήστε τον κατασκευαστή `Presentation` που δέχεται ροή και ενεργοποιήστε `loadOptions.setLoadFormat(LoadFormat.Pptx)` για να ροήσετε το αρχείο και να μειώσετε την κατανάλωση μνήμης.

**Ε: Μπορώ να αυτοματοποιήσω τις ενημερώσεις του διαγράμματος με ζωντανές πηγές δεδομένων;**  
Α: Ναι. Ανακτήστε δεδομένα από βάση ή REST API, ενημερώστε τη συλλογή `ChartData` και καλέστε `chart.refresh()` πριν αποθηκεύσετε την παρουσίαση.

## Πόροι
- **Τεκμηρίωση:** Εξερευνήστε λεπτομερείς αναφορές API στο [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Λήψη:** Λάβετε την τελευταία έκδοση της βιβλιοθήκης από [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Αγορά:** Για πλήρη πρόσβαση, αγοράστε άδεια στο [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Δωρεάν Δοκιμή:** Δοκιμάστε το Aspose.Slides με μια δωρεάν δοκιμή διαθέσιμη στη σελίδα λήψης.  
- **Προσωρινή Άδεια:** Αποκτήστε προσωρινή άδεια για εκτεταμένη δοκιμή χωρίς περιορισμούς.  
- **Υποστήριξη:** Έχετε ερωτήσεις; Επισκεφθείτε το [Aspose Forum](https://forum.aspose.com/c/slides/11) για βοήθεια.

---

**Τελευταία Ενημέρωση:** 2026-07-27  
**Δοκιμασμένο Με:** Aspose.Slides for Java 24.12  
**Συγγραφέας:** Aspose

## Σχετικά Tutorials

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}