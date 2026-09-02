---
date: '2026-09-02'
description: Μάθετε πώς να προσθέσετε ένα συγκεντρωτικό διάγραμμα στήλης σε μια διαφάνεια
  PowerPoint χρησιμοποιώντας Aspose.Slides for Java, καλύπτοντας τη δημιουργία διαγράμματος,
  τη μορφοποίηση και την αποθήκευση ως PPTX.
keywords:
- add clustered column chart
- save powerpoint as pptx
- powerpoint chart formatting
- add chart to slide
- java create chart slide
lastmod: '2026-09-02'
og_description: Μάθετε πώς να προσθέσετε ένα συγκεντρωτικό διάγραμμα στήλης σε μια
  διαφάνεια PowerPoint χρησιμοποιώντας Aspose.Slides for Java, καλύπτοντας τη δημιουργία
  διαγράμματος, τη μορφοποίηση και την αποθήκευση ως PPTX.
og_image_alt: Guide showing how to add a clustered column chart to a PowerPoint slide
  with Aspose.Slides for Java
og_title: Προσθήκη συγκεντρωτικού διαγράμματος στήλης σε PPT χρησιμοποιώντας Aspose.Slides
  Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to add clustered column chart to a PowerPoint slide using
    Aspose.Slides for Java, covering chart creation, formatting, and saving as PPTX.
  headline: Add clustered column chart to PPT using Aspose.Slides Java
  type: TechArticle
- questions:
  - answer: Replace `ChartType.ClusteredColumn` with any other enum value such as
      `ChartType.Pie`, `ChartType.Line`, or `ChartType.Bar`.
    question: How do I add different types of charts using Aspose.Slides?
  - answer: Double‑check that you’re using JDK 16 or newer and that the Maven/Gradle
      dependency version matches the library you downloaded.
    question: What should I do if I encounter compilation errors?
  - answer: Yes. Access the chart’s `getChartData()` collection, create series and
      categories, and fill them with values retrieved at runtime.
    question: Can I populate the chart with data from a database?
  - answer: Split the work into multiple `Presentation` instances, reuse chart templates,
      and always dispose of objects promptly.
    question: How can I improve performance for very large presentations?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java PowerPoint automation
- chart formatting
- PPTX
title: Προσθήκη συγκεντρωτικού διαγράμματος στήλης σε PPT χρησιμοποιώντας Aspose.Slides
  Java
url: /el/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη διαγράμματος ομαδοποιημένων στηλών σε PPT χρησιμοποιώντας το Aspose.Slides Java

## Εισαγωγή
Σε αυτόν τον οδηγό θα **προσθέσετε διάγραμμα ομαδοποιημένων στηλών** σε μια παρουσίαση PowerPoint προγραμματιστικά με το Aspose.Slides for Java. Είτε δημιουργείτε επιχειρηματικές αναφορές, εκπαιδευτικά decks, είτε παρουσιάσεις μάρκετινγκ, η αυτοματοποίηση της δημιουργίας διαγραμμάτων εξοικονομεί χρόνο και εγγυάται συνέπεια. Θα περάσουμε από τη ρύθμιση της βιβλιοθήκης, τη δημιουργία μιας διαφάνειας, την προσθήκη του διαγράμματος, την εφαρμογή στυλ γραμμής και στρογγυλεμένων γωνιών, και τελικά την αποθήκευση του αρχείου ως PPTX. Στο τέλος θα είστε άνετοι με όλη τη ροή εργασίας για **προσθήκη διαγράμματος στη διαφάνεια** και ακόμη **δημιουργία λύσεων βασισμένων σε PowerPoint slide Java**.

### Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για εκκίνηση;** `Presentation`
- **Ποιος τύπος διαγράμματος χρησιμοποιείται;** `ChartType.ClusteredColumn`
- **Πώς ενεργοποιείτε στρογγυλεμένες γωνίες;** `chart.setRoundedCorners(true);`
- **Ποια μορφή συνιστάται για αποθήκευση;** `SaveFormat.Pptx`
- **Χρειάζεται άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· απαιτείται αγορασμένη άδεια για παραγωγή.

## Τι είναι ένα διάγραμμα ομαδοποιημένων στηλών;
Ένα διάγραμμα ομαδοποιημένων στηλών ομαδοποιεί πολλαπλές σειρές δεδομένων πλάι‑πλάι για κάθε κατηγορία, καθιστώντας το ιδανικό για σύγκριση τιμών μεταξύ διαφορετικών ομάδων. Το Aspose.Slides σας επιτρέπει να δημιουργήσετε αυτόν τον τύπο διαγράμματος εξ ολοκλήρου με κώδικα χωρίς να ανοίξετε το PowerPoint, και μπορείτε να προσαρμόσετε χρώματα, δείκτες και επιλογές άξονα ώστε να ταιριάζουν με το brand σας.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides for Java για την προσθήκη διαγράμματος ομαδοποιημένων στηλών;
Μπορείτε να αυτοματοποιήσετε ολόκληρη τη διαδικασία δημιουργίας διαγράμματος χωρίς αλληλεπίδραση UI, κάτι που είναι απαραίτητο για δημιουργία αναφορών από τον διακομιστή. Το Aspose.Slides λειτουργεί σε οποιοδήποτε λειτουργικό σύστημα συμβατό με Java, διαχειρίζεται παρουσιάσεις με έως και 500 διαφάνειες χωρίς πλήρη φόρτωση, και παρέχει πάνω από 50 ενσωματωμένα στυλ διαγραμμάτων. Αυτό αφαιρεί τις εξαρτήσεις COM και σας επιτρέπει να ενσωματώσετε οπτικά υψηλής ποιότητας απευθείας από τη Java.

## Προαπαιτούμενα
- **Aspose.Slides for Java** (v25.4 ή νεότερη) – υποστηρίζει 50+ τύπους διαγραμμάτων και 30+ μορφές εικόνας.  
- **JDK 16** (ή νεότερο) – απαιτείται για τις πιο πρόσφατες δυνατότητες της γλώσσας.  
- Ένα IDE όπως IntelliJ IDEA, Eclipse ή NetBeans.  

## Ρύθμιση του Aspose.Slides for Java
Μπορείτε να προσθέσετε τη βιβλιοθήκη μέσω Maven, Gradle ή άμεσης λήψης.

### Χρήση Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Χρήση Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση λήψη
Κατεβάστε την πιο πρόσφατη έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Βήματα απόκτησης άδειας
- **Δωρεάν δοκιμή** – δοκιμάστε όλες τις λειτουργίες χωρίς χρονικούς περιορισμούς.  
- **Προσωρινή άδεια** – ζητήστε μία από το portal του Aspose για πλήρη αξιολόγηση λειτουργιών.  
- **Αγορά** – αποκτήστε μόνιμη άδεια για χρήση σε παραγωγή.

## Οδηγός υλοποίησης

### Δημιουργία παρουσίασης και προσθήκη διαφάνειας
`Presentation` είναι το βασικό αντικείμενο Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη. Αφού το δημιουργήσετε, μπορείτε να έχετε πρόσβαση, να τροποποιήσετε ή να προσθέσετε διαφάνειες.

#### Επισκόπηση
Αρχικά, δημιουργούμε ένα νέο αντικείμενο `Presentation` και παίρνουμε την προεπιλεγμένη διαφάνεια που περιλαμβάνεται σε ένα νέο αρχείο.

#### Βήμα‑βήμα
**1. αρχικοποίηση του αντικειμένου Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. πρόσβαση στην πρώτη διαφάνεια**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. απελευθέρωση πόρων**  
```java
if (presentation != null) presentation.dispose();
```  

### Προσθήκη διαγράμματος σε διαφάνεια
`IChart` είναι η διεπαφή που αντιπροσωπεύει οποιοδήποτε διάγραμμα προστίθεται σε μια διαφάνεια. Καθορίζοντας `ChartType.ClusteredColumn` λέτε στο Aspose.Slides να αποδώσει ένα διάγραμμα ομαδοποιημένων στηλών.

#### Επισκόπηση
Τώρα ενσωματώνουμε ένα **διάγραμμα ομαδοποιημένων στηλών** στη διαφάνεια που μόλις προετοιμάσαμε.

#### Βήμα‑βήμα
**1. αρχικοποίηση του αντικειμένου Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. πρόσβαση στην πρώτη διαφάνεια**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. προσθήκη διαγράμματος ομαδοποιημένων στηλών**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. απελευθέρωση πόρων**  
```java
if (presentation != null) presentation.dispose();
```  

### Μορφοποίηση στυλ γραμμής διαγράμματος και ορισμός στρογγυλεμένων γωνιών
`Chart` παρέχει τη μέθοδο `getChartFormat()` που επιστρέφει ένα αντικείμενο `ChartFormat`, το οποίο μπορείτε να χρησιμοποιήσετε για να προσαρμόσετε γεμίσματα γραμμής, στυλ παύλας και στρογγυλεμένες γωνίες.

`Chart` είναι η συγκεκριμένη κλάση που υλοποιεί το `IChart` και αντιπροσωπεύει ένα αντικείμενο διαγράμματος σε μια διαφάνεια.

#### Επισκόπηση
Βελτιώστε την οπτική ελκυστικότητα εφαρμόζοντας γεμιστό στερεό γραμμής, ένα ενιαίο στυλ γραμμής και στρογγυλεμένες γωνίες.

#### Βήμα‑βήμα
**1. αρχικοποίηση του αντικειμένου Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. πρόσβαση στην πρώτη διαφάνεια**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. προσθήκη διαγράμματος ομαδοποιημένων στηλών**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. ορισμός μορφής γραμμής σε τύπο γεμίσματος στερεό**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```  

**5. εφαρμογή ενιαίου στυλ γραμμής**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```  

**6. ενεργοποίηση στρογγυλεμένων γωνιών για την περιοχή διαγράμματος**  
```java
chart.setRoundedCorners(true);
```  

**7. απελευθέρωση πόρων**  
```java
if (presentation != null) presentation.dispose();
```  

### Αποθήκευση παρουσίασης
`SaveFormat.Pptx` είναι η προτεινόμενη μορφή για σύγχρονα αρχεία PowerPoint, διατηρώντας όλη τη μορφοποίηση του διαγράμματος και επιτρέποντας επεξεργασία downstream.

#### Επισκόπηση
Τέλος, γράφουμε την παρουσίαση στο δίσκο σε μορφή PPTX, η οποία είναι το πρότυπο για λειτουργίες **αποθήκευσης PowerPoint ως PPTX**.

#### Βήμα‑βήμα
**1. αρχικοποίηση του αντικειμένου Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. ορισμός καταλόγου εξόδου και ονόματος αρχείου**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```  

**3. αποθήκευση της παρουσίασης σε μορφή PPTX**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```  

**4. απελευθέρωση πόρων**  
```java
if (presentation != null) presentation.dispose();
```  

## Πρακτικές εφαρμογές
- **Επιχειρηματικές αναφορές** – αυτοματοποιήστε τριμηνιαίες οικονομικές παρουσιάσεις με δυναμικά διαγράμματα.  
- **Εκπαιδευτικό περιεχόμενο** – δημιουργήστε διαφάνειες διαλέξεων που αντλούν δεδομένα από βάση δεδομένων.  
- **Παρουσιάσεις μάρκετινγκ** – οπτικοποιήστε τις τάσεις προϊόντων με επεξεργασμένα, brand‑συμβατά διαγράμματα.  

## Παράγοντες απόδοσης
- **Διαχείριση πόρων** – πάντα καλέστε `dispose()` ή χρησιμοποιήστε try‑with‑resources για απελευθέρωση της εγγενούς μνήμης.  
- **Βελτιστοποίηση μνήμης** – επεξεργαστείτε μεγάλα σύνολα δεδομένων σε μικρότερα batch· το Aspose.Slides μπορεί να διαχειριστεί παρουσιάσεις έως 500 MB χωρίς πλήρη φόρτωση.  
- **Καλές πρακτικές** – προτιμήστε αμετάβλητες δομές δεδομένων για σειρές διαγράμματος όταν είναι δυνατόν· αυτό μειώνει το φορτίο του GC και βελτιώνει την απόδοση.  

## Κοινά προβλήματα και λύσεις

| Πρόβλημα | Λύση |
|----------|------|
| **`NullPointerException` on `getSlides()`** | Βεβαιωθείτε ότι το αντικείμενο `Presentation` έχει δημιουργηθεί επιτυχώς πριν την πρόσβαση στις διαφάνειες. |
| **Chart not appearing** | Επαληθεύστε ότι οι διαστάσεις του διαγράμματος (x, y, width, height) βρίσκονται εντός των ορίων της διαφάνειας και ότι χρησιμοποιείται `ChartType.ClusteredColumn`. |
| **License not applied** | Φορτώστε το αρχείο άδειας πριν δημιουργήσετε το αντικείμενο `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Συχνές ερωτήσεις

**Ε: Πώς προσθέτω διαφορετικούς τύπους διαγραμμάτων χρησιμοποιώντας το Aspose.Slides;**  
Α: Αντικαταστήστε το `ChartType.ClusteredColumn` με οποιαδήποτε άλλη τιμή enum όπως `ChartType.Pie`, `ChartType.Line` ή `ChartType.Bar`.

**Ε: Τι πρέπει να κάνω αν αντιμετωπίσω σφάλματα μεταγλώττισης;**  
Α: Ελέγξτε ξανά ότι χρησιμοποιείτε JDK 16 ή νεότερο και ότι η έκδοση εξάρτησης Maven/Gradle ταιριάζει με τη βιβλιοθήκη που κατεβάσατε.

**Ε: Μπορώ να γεμίσω το διάγραμμα με δεδομένα από βάση δεδομένων;**  
Α: Ναι. Πρόσβαση στη συλλογή `getChartData()` του διαγράμματος, δημιουργία σειρών και κατηγοριών, και συμπλήρωση τους με τιμές που λαμβάνονται σε χρόνο εκτέλεσης.

**Ε: Πώς μπορώ να βελτιώσω την απόδοση για πολύ μεγάλες παρουσιάσεις;**  
Α: Διαχωρίστε τη δουλειά σε πολλαπλά αντικείμενα `Presentation`, επαναχρησιμοποιήστε πρότυπα διαγραμμάτων, και πάντα απελευθερώστε τα αντικείμενα άμεσα.

## Συμπέρασμα
Τώρα έχετε μια πλήρη, ολοκληρωμένη συνταγή για **προσθήκη διαγράμματος ομαδοποιημένων στηλών** σε μια διαφάνεια PowerPoint με το Aspose.Slides for Java. Πειραματιστείτε με άλλους τύπους διαγραμμάτων, συνδέστε ζωντανές πηγές δεδομένων, και ενσωματώστε αυτή τη λογική σε μεγαλύτερους αγωγούς αναφορών για να αυτοματοποιήσετε τη ροή εργασίας των παρουσιάσεών σας.

---

**Τελευταία ενημέρωση:** 2026-09-02  
**Δοκιμή με:** Aspose.Slides 25.4 for Java (JDK 16)  
**Συγγραφέας:** Aspose

## Σχετικά μαθήματα

- [Πώς να προσθέσετε διάγραμμα σε PowerPoint χρησιμοποιώντας το Aspose.Slides for Java: Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Δημιουργία διαγράμματος PowerPoint Java – Αποθήκευση παρουσιάσεων με διαγράμματα χρησιμοποιώντας το Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Προσθήκη κίνησης σε διάγραμμα PowerPoint χρησιμοποιώντας το Aspose.Slides for Java – Οδηγός βήμα‑βήμα](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}