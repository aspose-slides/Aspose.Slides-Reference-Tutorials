---
title: Ορισμός εξωτερικού βιβλίου εργασίας με ενημέρωση δεδομένων γραφήματος σε διαφάνειες Java
linktitle: Ορισμός εξωτερικού βιβλίου εργασίας με ενημέρωση δεδομένων γραφήματος σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε εξωτερικά βιβλία εργασίας και να ενημερώνετε δεδομένα γραφήματος σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Βελτιώστε τις δεξιότητές σας στον αυτοματισμό του PowerPoint.
type: docs
weight: 20
url: /el/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

## Εισαγωγή στον ορισμό εξωτερικού βιβλίου εργασίας με ενημέρωση δεδομένων γραφήματος σε διαφάνειες Java

Σε αυτόν τον αναλυτικό οδηγό, θα σας καθοδηγήσουμε στη διαδικασία ρύθμισης ενός εξωτερικού βιβλίου εργασίας με ενημερωμένα δεδομένα γραφήματος σε Java Slides χρησιμοποιώντας το Aspose.Slides for Java API. Αυτή η ισχυρή βιβλιοθήκη σάς επιτρέπει να χειρίζεστε τις παρουσιάσεις του PowerPoint μέσω προγραμματισμού, καθιστώντας εύκολη την αυτοματοποίηση εργασιών όπως η ενημέρωση δεδομένων γραφήματος από μια εξωτερική πηγή. Μέχρι το τέλος αυτού του σεμιναρίου, θα έχετε μια ξεκάθαρη κατανόηση του τρόπου επίτευξης αυτής της εργασίας με οδηγίες βήμα προς βήμα και τον συνοδευτικό κώδικα Java.

## Προαπαιτούμενα

Πριν προχωρήσουμε στην υλοποίηση, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Slides για Java: Θα πρέπει να έχετε εγκατεστημένη τη βιβλιοθήκη Aspose.Slides for Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).

2. Περιβάλλον ανάπτυξης Java: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης Java στο σύστημά σας.

## Βήμα 1: Δημιουργία νέας παρουσίασης

Για να ξεκινήσετε, ας δημιουργήσουμε μια νέα παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Εδώ είναι ο κώδικας Java για να το κάνετε αυτό:

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα

Τώρα, ας προσθέσουμε ένα γράφημα στην παρουσίασή μας. Θα δημιουργήσουμε ένα γράφημα πίτας σε αυτό το παράδειγμα:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Βήμα 3: Ορισμός εξωτερικού βιβλίου εργασίας

Εδώ ορίζουμε το εξωτερικό βιβλίο εργασίας ως πηγή δεδομένων για το γράφημά μας. Πρέπει να δώσετε τη διεύθυνση URL στο εξωτερικό βιβλίο εργασίας, ακόμα κι αν δεν υπάρχει προς το παρόν:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://διαδρομή/δεν/υπάρχει", false);
```

## Βήμα 4: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση με τα ενημερωμένα δεδομένα γραφήματος:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Ολοκληρώστε τον πηγαίο κώδικα για το σύνολο του εξωτερικού βιβλίου εργασίας με ενημερωμένα δεδομένα γραφήματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://διαδρομή/δεν/υπάρχει", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## συμπέρασμα

Συγχαρητήρια! Μάθατε πώς να ορίζετε ένα εξωτερικό βιβλίο εργασίας με ενημερωμένα δεδομένα γραφήματος σε Java Slides χρησιμοποιώντας το Aspose.Slides for Java. Αυτό μπορεί να είναι απίστευτα χρήσιμο για τη δυναμική ενημέρωση γραφημάτων στις παρουσιάσεις σας στο PowerPoint από εξωτερικές πηγές δεδομένων.

## Συχνές ερωτήσεις

### Πώς μπορώ να ενημερώσω τα δεδομένα εξωτερικού βιβλίου εργασίας για το γράφημα;

Για να ενημερώσετε τα δεδομένα εξωτερικού βιβλίου εργασίας για το γράφημα, πρέπει απλώς να τροποποιήσετε τα δεδομένα στο εξωτερικό βιβλίο εργασίας στην καθορισμένη διεύθυνση URL. Την επόμενη φορά που θα ανοίξετε την παρουσίαση, το Aspose.Slides για Java θα ανακτήσει τα ενημερωμένα δεδομένα από το εξωτερικό βιβλίο εργασίας και θα ενημερώσει το γράφημα ανάλογα.

### Μπορώ να χρησιμοποιήσω ένα τοπικό αρχείο ως εξωτερικό βιβλίο εργασίας;

Ναι, μπορείτε να χρησιμοποιήσετε ένα τοπικό αρχείο ως εξωτερικό βιβλίο εργασίας παρέχοντας τη διαδρομή αρχείου αντί για μια διεύθυνση URL. Απλώς βεβαιωθείτε ότι η διαδρομή του αρχείου είναι σωστή και προσβάσιμη από την εφαρμογή Java.

### Υπάρχουν περιορισμοί στη χρήση εξωτερικών βιβλίων εργασίας με το Aspose.Slides για Java;

Ενώ η χρήση εξωτερικών βιβλίων εργασίας είναι μια ισχυρή δυνατότητα, λάβετε υπόψη ότι η διαθεσιμότητα των δεδομένων του εξωτερικού βιβλίου εργασίας εξαρτάται από την προσβασιμότητά του στη διεύθυνση URL ή τη διαδρομή αρχείου που παρέχεται. Βεβαιωθείτε ότι η εξωτερική πηγή δεδομένων είναι διαθέσιμη όταν ανοίγετε την παρουσίαση για να αποφύγετε προβλήματα ανάκτησης δεδομένων.

### Μπορώ να προσαρμόσω την εμφάνιση του γραφήματος μετά τη ρύθμιση του εξωτερικού βιβλίου εργασίας;

Ναι, μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος, συμπεριλαμβανομένου του τίτλου, των ετικετών, των χρωμάτων και άλλων, ακόμη και μετά τη ρύθμιση του εξωτερικού βιβλίου εργασίας. Το Aspose.Slides για Java παρέχει εκτενείς επιλογές μορφοποίησης γραφήματος για να καλύψει τις ανάγκες σας.

### Πού μπορώ να βρω περισσότερη τεκμηρίωση και πόρους για το Aspose.Slides για Java;

 Για λεπτομερή τεκμηρίωση και πρόσθετους πόρους, επισκεφθείτε την τεκμηρίωση Aspose.Slides for Java στη διεύθυνση[εδώ](https://reference.aspose.com/slides/java/).