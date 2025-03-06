---
title: Ορίστε τη λειτουργία διάταξης στις διαφάνειες Java
linktitle: Ορίστε τη λειτουργία διάταξης στις διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε λειτουργίες διάταξης για διαφάνειες Java χρησιμοποιώντας το Aspose.Slides. Προσαρμόστε τη θέση και το μέγεθος του γραφήματος σε αυτόν τον οδηγό βήμα προς βήμα με τον πηγαίο κώδικα.
weight: 23
url: /el/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορίστε τη λειτουργία διάταξης στις διαφάνειες Java


## Εισαγωγή στο Set Layout Mode σε Java Slides

Σε αυτό το σεμινάριο, θα μάθουμε πώς να ρυθμίζουμε τη λειτουργία διάταξης για ένα γράφημα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Η λειτουργία διάταξης καθορίζει τη θέση και το μέγεθος του γραφήματος εντός της διαφάνειας.

## Προαπαιτούμενα

 Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας Java. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από[εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Πρώτα, πρέπει να δημιουργήσουμε μια νέα παρουσίαση.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθέστε μια διαφάνεια και ένα γράφημα

Στη συνέχεια, θα προσθέσουμε μια διαφάνεια και ένα γράφημα σε αυτό. Σε αυτό το παράδειγμα, θα δημιουργήσουμε ένα γράφημα στηλών ομαδοποίησης.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Βήμα 3: Ορισμός διάταξης γραφήματος

 Τώρα, ας ορίσουμε τη διάταξη για το γράφημα. Θα προσαρμόσουμε τη θέση και το μέγεθος του γραφήματος μέσα στη διαφάνεια χρησιμοποιώντας το`setX`, `setY`, `setWidth`, `setHeight` μεθόδους. Επιπλέον, θα ορίσουμε το`LayoutTargetType` για να προσδιορίσετε τη λειτουργία διάταξης.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Σε αυτό το παράδειγμα, έχουμε ορίσει το γράφημα να έχει τον τύπο στόχο της διάταξης ως "Εσωτερικό", που σημαίνει ότι θα τοποθετηθεί και θα έχει μέγεθος σε σχέση με την εσωτερική περιοχή της διαφάνειας.

## Βήμα 4: Αποθηκεύστε την Παρουσίαση

Τέλος, ας αποθηκεύσουμε την παρουσίαση με τις ρυθμίσεις διάταξης γραφήματος.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Ολοκληρώστε τον πηγαίο κώδικα για τη ρύθμιση της λειτουργίας διάταξης σε διαφάνειες Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα

 Σε αυτό το σεμινάριο, μάθαμε πώς να ορίζουμε τη λειτουργία διάταξης για ένα γράφημα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε τη θέση και το μέγεθος του γραφήματος σύμφωνα με τις συγκεκριμένες απαιτήσεις σας προσαρμόζοντας τις τιμές στο`setX`, `setY`, `setWidth`, `setHeight` , και`setLayoutTargetType`μεθόδους. Αυτό σας δίνει τον έλεγχο της τοποθέτησης των γραφημάτων στις διαφάνειές σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τη λειτουργία διάταξης για ένα γράφημα στο Aspose.Slides για Java;

 Για να αλλάξετε τη λειτουργία διάταξης για ένα γράφημα στο Aspose.Slides για Java, μπορείτε να χρησιμοποιήσετε το`setLayoutTargetType` μέθοδος στην περιοχή του γραφήματος. Μπορείτε να το ρυθμίσετε σε οποιοδήποτε από τα δύο`LayoutTargetType.Inner` ή`LayoutTargetType.Outer` ανάλογα με την επιθυμητή διάταξη.

### Μπορώ να προσαρμόσω τη θέση και το μέγεθος του γραφήματος εντός της διαφάνειας;

 Ναι, μπορείτε να προσαρμόσετε τη θέση και το μέγεθος του γραφήματος μέσα στη διαφάνεια χρησιμοποιώντας το`setX`, `setY`, `setWidth` , και`setHeight` μεθόδους στην περιοχή του γραφήματος. Προσαρμόστε αυτές τις τιμές για τη θέση και το μέγεθος του γραφήματος σύμφωνα με τις απαιτήσεις σας.

### Πού μπορώ να βρω περισσότερες πληροφορίες σχετικά με το Aspose.Slides for Java;

 Μπορείτε να βρείτε περισσότερες πληροφορίες σχετικά με το Aspose.Slides for Java στο[τεκμηρίωση](https://reference.aspose.com/slides/java/). Περιλαμβάνει λεπτομερείς αναφορές και παραδείγματα API για να σας βοηθήσει να εργάζεστε αποτελεσματικά με διαφάνειες και γραφήματα σε Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
