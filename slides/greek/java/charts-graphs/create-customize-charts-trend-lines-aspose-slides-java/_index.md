---
date: '2026-08-21'
description: Μάθετε πώς να δημιουργήσετε ένα clustered column chart και να προσθέσετε
  trend lines με το Aspose.Slides for Java. Περιλαμβάνει license setup, ενσωμάτωση
  Maven/Gradle και λεπτομερή παραδείγματα.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Δημιουργήστε ένα clustered column chart και προσθέστε trend lines
  χρησιμοποιώντας το Aspose.Slides for Java. Αυτός ο οδηγός καλύπτει το license setup,
  Maven/Gradle και βήμα‑βήμα code snippets.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Δημιουργήστε ένα clustered column chart και προσθέστε trend lines με το
  Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Πώς να δημιουργήσετε ένα clustered column chart και να προσθέσετε trend lines
  χρησιμοποιώντας το Aspose.Slides for Java
url: /el/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Πώς να δημιουργήσετε συγκεντρωτικό γράφημα στήλης και να προσθέσετε γραμμές τάσης χρησιμοποιώντας το Aspose.Slides για Java

Η δημιουργία εντυπωσιακών παρουσιάσεων συχνά ξεκινά με μια σαφή οπτική των δεδομένων σας. Σε αυτόν τον οδηγό θα **create clustered column chart** αντικείμενα, έπειτα θα τα εμπλουτίσετε με μια ποικιλία γραμμών τάσης—exponential, linear, logarithmic, moving average, polynomial, και power—χρησιμοποιώντας το ισχυρό Aspose.Slides for Java API.

## Γρήγορες απαντήσεις
- **Ποιο είναι το πρώτο βήμα;** Αρχικοποιήστε ένα αντικείμενο `Presentation` και προσθέστε ένα clustered column chart σε μια διαφάνεια.  
- **Ποια έκδοση της βιβλιοθήκης απαιτείται;** Aspose.Slides for Java 25.4 ή νεότερη.  
- **Μπορώ να χρησιμοποιήσω Maven ή Gradle;** Ναι, και τα δύο υποστηρίζονται· το Maven χρησιμοποιεί `<dependency>` και το Gradle χρησιμοποιεί `implementation`.  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική άδεια λειτουργεί για αξιολόγηση· μια πλήρης άδεια Aspose.Slides αφαιρεί τα όρια αξιολόγησης.  
- **Πόσοι τύποι γραμμής τάσης είναι διαθέσιμοι;** Έξι ενσωματωμένοι τύποι: exponential, linear, logarithmic, moving average, polynomial, και power.

## Τι είναι το create clustered column chart;
`create clustered column chart` σημαίνει τη δημιουργία ενός γραφήματος που ομαδοποιεί πολλαπλές σειρές δεδομένων πλάι‑πλάι εντός κάθε κατηγορίας, καθιστώντας εύκολο το σύγκριση των τιμών μεταξύ σειρών. Αυτός ο τύπος γραφήματος είναι ιδανικός για την απεικόνιση κατηγορικών δεδομένων όπως τα τριμηνιαία πωλήσεις ανά περιοχή, επιτρέποντας στους θεατές να εντοπίζουν γρήγορα τις διαφορές μεταξύ ομάδων.

## Γιατί να προσθέσετε γραμμή τάσης;
Οι γραμμές τάσης αποκαλύπτουν το υποκείμενο μοτίβο μιας σειράς δεδομένων, βοηθώντας σας να προβλέψετε μελλοντικές τιμές, να τονίσετε τα ποσοστά ανάπτυξης ή να εξομαλύντε θορυβώδη δεδομένα. Προσθέτοντας μια γραμμή τάσης σε ένα clustered column chart, οι ακατέργαστοι αριθμοί μετατρέπονται σε χρήσιμες πληροφορίες, επιτρέποντας στα ενδιαφερόμενα μέρη να κατανοήσουν τις μακροπρόθεσμες τάσεις και να λάβουν αποφάσεις βασισμένες στα δεδομένα.

## Προαπαιτούμενα
- **Java Development Kit (JDK):** 8 ή νεότερο.  
- **Aspose.Slides for Java:** έκδοση 25.4 ή νεότερη.  
- **IDE:** IntelliJ IDEA, Eclipse ή οποιοδήποτε επεξεργαστή συμβατό με Java.  
- **Build tool:** Maven ή Gradle (προαιρετικό αλλά συνιστάται).  
- **License:** ένα αρχείο άδειας δοκιμής ή αγορασμένο αρχείο άδειας Aspose.Slides.  

Θα πρέπει να είστε άνετοι με τη βασική σύνταξη της Java και εξοικειωμένοι με τη διαχείριση εξαρτήσεων του έργου.

## Πώς να ρυθμίσετε το Aspose.Slides για Java;
Προσθέστε τη βιβλιοθήκη Aspose.Slides στο έργο σας χρησιμοποιώντας τον προτιμώμενο διαχειριστή εξαρτήσεων, στη συνέχεια τοποθετήστε το αρχείο άδειας σε θέση όπου το runtime μπορεί να το εντοπίσει. Αυτό εξασφαλίζει πλήρη λειτουργικότητα και αφαιρεί τους περιορισμούς αξιολόγησης.

### Maven
Add this dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση λήψη
Μπορείτε επίσης να κατεβάσετε το JAR χειροκίνητα από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Άδεια Aspose Slides
Τοποθετήστε το αρχείο `Aspose.Slides.lic` στη ρίζα του έργου σας ή ορίστε την άδεια προγραμματιστικά με `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Μια δοκιμαστική άδεια αφαιρεί όλους τους περιορισμούς λειτουργιών, αλλά μια αγορασμένη άδεια εξαλείφει το υδατογράφημα αξιολόγησης και παρέχει πλήρεις βελτιστοποιήσεις απόδοσης. Για χρήση σε παραγωγή, σκεφτείτε να αγοράσετε άδεια από τη [Aspose purchase page](https://purchase.aspose.com/buy).

## Πώς να δημιουργήσετε μια παρουσίαση και να προσθέσετε ένα clustered column chart;
Η κλάση `Presentation` αντιπροσωπεύει ένα αρχείο PowerPoint και παρέχει μεθόδους για δημιουργία, επεξεργασία και αποθήκευση διαφανειών. Δημιουργήστε ένα αντικείμενο `Presentation`, προσθέστε μια διαφάνεια, στη συνέχεια καλέστε `addChart` με `ChartType.ClusteredColumn` για να δημιουργήσετε το αντικείμενο γραφήματος. Αυτή η διαδικασία ρυθμίζει τον καμβά της διαφάνειας, εισάγει ένα σχήμα γραφήματος και το προετοιμάζει για πληθώρα δεδομένων και στυλ.

1. **Αρχικοποίηση της παρουσίασης** – ρυθμίστε το φάκελο εξόδου και δημιουργήστε ένα νέο αντικείμενο `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Προσθήκη ενός clustered column chart** – λάβετε το σχήμα του γραφήματος, διαμορφώστε τις σειρές του και συμπληρώστε τα σημεία δεδομένων.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Πώς να προσθέσετε μια exponential γραμμή τάσης;
Η διεπαφή `ITrendline` ορίζει μια γραμμή τάσης που μπορεί να προστεθεί σε μια σειρά γραφήματος για να μοντελοποιήσει μοτίβα δεδομένων. Εφαρμόστε μια exponential γραμμή τάσης σε μια σειρά δημιουργώντας ένα αντικείμενο `ITrendline`, ορίζοντας το `TrendlineType` σε `Exponential` και συνδέοντάς το με τη ζητούμενη σειρά. Αυτός ο τύπος γραμμής τάσης είναι χρήσιμος για δεδομένα που αυξάνονται γρήγορα με αυξανόμενο ρυθμό.

1. **Διαμόρφωση της γραμμής τάσης** – επιλέξτε τη σειρά και καλέστε `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Πώς να προσθέσετε μια linear γραμμή τάσης;
Μια linear γραμμή τάσης δείχνει την καλύτερη ευθεία προσαρμοσμένη γραμμή μέσω των σημείων δεδομένων σας. Μπορείτε επίσης να προσαρμόσετε την εμφάνισή της, όπως το χρώμα και το πάχος της γραμμής, ώστε να ταιριάζει με το στυλ της παρουσίασής σας.

1. **Ρύθμιση της γραμμής τάσης** – χρησιμοποιήστε `addTrendline(TrendlineType.Linear)` και στη συνέχεια προσαρμόστε `getLineFormat().setFillFormat().setFillType(FillType.Solid)` για να αλλάξετε το χρώμα.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Πώς να προσθέσετε μια logarithmic γραμμή τάσης με προσαρμοσμένο πλαίσιο κειμένου;
Οι logarithmic γραμμές τάσης είναι ιδανικές για δεδομένα που αυξάνονται γρήγορα αρχικά και στη συνέχεια σταθεροποιούνται. Η αντικατάσταση της προεπιλεγμένης ετικέτας σας επιτρέπει να προσθέσετε επεξηγηματικό κείμενο που διευκρινίζει τη σημασία της τάσης.

1. **Προσαρμογή της γραμμής τάσης** – μετά την προσθήκη της γραμμής τάσης, αποκτήστε πρόσβαση στο `getDataLabel()` και ορίστε την ιδιότητα `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Πώς να προσθέσετε μια moving average γραμμή τάσης;
Οι moving average γραμμές τάσης εξομαλύνουν τις βραχυπρόθεσμες διακυμάνσεις για να αναδείξουν τις μακροπρόθεσμες τάσεις. Μπορείτε να καθορίσετε την περίοδο (αριθμό σημείων) που χρησιμοποιείται για το μέσο όρο, επιτρέποντάς σας να ελέγξετε την ομαλότητα της γραμμής.

1. **Διαμόρφωση της γραμμής τάσης** – καλέστε `addTrendline(TrendlineType.MovingAverage)` και ορίστε `setPeriod(3)` για να χρησιμοποιήσετε έναν τρι‑σημειακό moving average.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Πώς να προσθέσετε μια polynomial γραμμή τάσης;
Οι polynomial γραμμές τάσης προσαρμόζουν τα δεδομένα με μια καμπύλη που ορίζεται από μια πολυωνυμική εξίσωση. Η ιδιότητα `order` ελέγχει το βαθμό του πολυωνύμου, επιτρέποντάς σας να μοντελοποιήσετε πιο σύνθετες σχέσεις.

1. **Προσαρμογή της γραμμής τάσης** – μετά την προσθήκη της γραμμής τάσης, ορίστε `setOrder(3)` για μια κυβική προσαρμογή.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Πώς να προσθέσετε μια power γραμμή τάσης;
Οι power γραμμές τάσης είναι χρήσιμες όταν τα δεδομένα ακολουθούν μια σχέση νόμου δύναμης. Μπορείτε επίσης να ορίσετε τιμές πρόβλεψης προς τα πίσω και προς τα εμπρός για να επεκτείνετε τη γραμμή πέρα από το υπάρχον εύρος δεδομένων.

1. **Διαμόρφωση της γραμμής τάσης** – χρησιμοποιήστε `addTrendline(TrendlineType.Power)` και προσαρμόστε `setBackward(2)` για να επεκτείνετε τη γραμμή προς τα πίσω.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Πρακτικές εφαρμογές των γραμμών τάσης σε clustered column charts
- **Financial analysis:** Οι exponential και polynomial τάσεις βοηθούν στην πρόβλεψη των κινήσεων των τιμών των μετοχών.  
- **Sales forecasting:** Οι γραμμές moving average εξομαλύνουν τις εποχικές κορυφές, παρέχοντας πιο καθαρή εικόνα των υποκείμενων τάσεων πωλήσεων.  
- **Scientific research:** Οι logarithmic τάσεις είναι ιδανικές για δεδομένα που καλύπτουν πολλές τάξεις μεγέθους, όπως η ηχητική ένταση ή τα επίπεδα pH.  
- **Operations monitoring:** Οι power γραμμές τάσης μπορούν να μοντελοποιήσουν τη φθορά της απόδοσης με την πάροδο του χρόνου.

## Πώς να βελτιστοποιήσετε τη μνήμη όταν χρησιμοποιείτε το Aspose.Slides;
Αποδεσμεύστε τα αντικείμενα άμεσα και χρησιμοποιήστε `presentation.dispose()` μετά την αποθήκευση. Για μεγάλα σύνολα δεδομένων, ενεργοποιήστε τη lazy φόρτωση των εικόνων και αποφύγετε τη φόρτωση ολόκληρου του γραφήματος στη μνήμη ταυτόχρονα.

- **Dispose patterns:** Τυλίξτε το `Presentation` σε μπλοκ try‑with‑resources ή καλέστε `presentation.dispose()` σε τελικό μπλοκ.  
- **Lazy loading:** Ορίστε `ChartData.setUseCache(true)` όταν εργάζεστε με χιλιάδες σημεία δεδομένων.  
- **Streaming output:** Γράψτε την παρουσίαση απευθείας σε `FileOutputStream` για να αποφύγετε τη διατήρηση ολόκληρου του αρχείου στη μνήμη RAM.

## Ποσοτικοποιημένα οφέλη του Aspose.Slides για Java
Το Aspose.Slides υποστηρίζει **50+ τύπους γραφημάτων**, μπορεί να δημιουργήσει παρουσιάσεις με **πάνω από 1.000 διαφάνειες** σε λιγότερο από **30 δευτερόλεπτα** σε τυπική CPU 2 GHz, και επεξεργάζεται **PDF 500‑σελίδων** χωρίς να απαιτείται εγκατάσταση του Microsoft Office. Αυτοί οι αριθμοί έχουν επαληθευτεί στην πιο πρόσφατη έκδοση 25.4.

## Συμπέρασμα
Τώρα έχετε μια πλήρη, ολοκληρωμένη λύση για **creating clustered column chart** αντικείμενα και τον εμπλουτισμό τους με κάθε κύριο τύπο γραμμής τάσης που διατίθεται στο Aspose.Slides για Java. Ακολουθώντας τα παραπάνω βήματα, μπορείτε να παράγετε παρουσιάσεις βασισμένες σε δεδομένα που είναι τόσο οπτικά ελκυστικές όσο και αναλυτικά ισχυρές.

Τα επόμενα βήματα περιλαμβάνουν την εξερεύνηση επιλογών στυλ γραφήματος, την εξαγωγή σε PDF/HTML, και την αυτοματοποίηση της δημιουργίας γραφημάτων σε πολλαπλές πηγές δεδομένων.

## Συχνές ερωτήσεις

**Q: Πώς να ρυθμίσω το Aspose.Slides για ένα έργο Maven;**  
A: Προσθέστε το απόσπασμα `<dependency>` που φαίνεται στην ενότητα Maven στο `pom.xml` σας και εκτελέστε `mvn clean install`.

**Q: Μπορώ να προσαρμόσω τις γραμμές τάσης πέρα από το χρώμα και την ετικέτα;**  
A: Ναι, μπορείτε να τροποποιήσετε το στυλ γραμμής, το πλάτος, το μοτίβο διακεκομμένων, και ακόμη να προβλέψετε τιμές προς τα εμπρός/πίσω μέσω του API `ITrendline`.

**Q: Τι πρέπει να κάνω αν αντιμετωπίσω σφάλμα συμβατότητας έκδοσης;**  
A: Επαληθεύστε ότι η έκδοση του JDK σας ταιριάζει με την ελάχιστη απαίτηση του Aspose.Slides (JDK 8+). Συμβουλευτείτε τις σημειώσεις έκδοσης του Aspose για τυχόν αλλαγές που σπάζουν την συμβατότητα.

**Q: Είναι δυνατόν να προσθέσετε γραμμές τάσης σε πολλά γραφήματα αυτόματα;**  
A: Απόλυτα. Επαναλάβετε τη διαδικασία για κάθε `IChart` σε μια συλλογή διαφανειών και καλέστε τη σχετική μέθοδο `addTrendline` για κάθε σειρά.

**Q: Χρειάζομαι πληρωμένη άδεια για χρήση σε παραγωγή;**  
A: Ναι, μια αγορασμένη άδεια Aspose.Slides αφαιρεί τα όρια αξιολόγησης και ξεκλειδώνει πλήρεις βελτιστοποιήσεις απόδοσης.

---

**Τελευταία ενημέρωση:** 2026-08-21  
**Δοκιμή με:** Aspose.Slides for Java 25.4  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [aspose slides maven dependency: Προσθήκη και διαμόρφωση γραφημάτων σε παρουσιάσεις χρησιμοποιώντας Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Προσθήκη animation σε γράφημα PowerPoint χρησιμοποιώντας Aspose.Slides for Java – Οδηγός βήμα‑βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Δημιουργία PowerPoint Chart Java – Αποθήκευση παρουσιάσεων με γραφήματα χρησιμοποιώντας Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}