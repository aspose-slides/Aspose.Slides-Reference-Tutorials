---
title: Προσθήκη χρώματος σε σημεία δεδομένων σε διαφάνειες Java
linktitle: Προσθήκη χρώματος σε σημεία δεδομένων σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε χρώμα σε σημεία δεδομένων σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java.
weight: 10
url: /el/java/chart-data-manipulation/add-color-data-points-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Εισαγωγή στην προσθήκη χρώματος σε σημεία δεδομένων σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να προσθέτετε χρώμα σε σημεία δεδομένων σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Αυτός ο οδηγός βήμα προς βήμα περιλαμβάνει παραδείγματα πηγαίου κώδικα για να σας βοηθήσει να επιτύχετε αυτήν την εργασία.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Περιβάλλον Ανάπτυξης Java
- Aspose.Slides για βιβλιοθήκη Java

## Βήμα 1: Δημιουργία νέας παρουσίασης

Αρχικά, θα δημιουργήσουμε μια νέα παρουσίαση χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η παρουσίαση θα χρησιμεύσει ως το δοχείο για το διάγραμμά μας.

```java
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα Sunburst

Τώρα, ας προσθέσουμε ένα γράφημα Sunburst στην παρουσίαση. Καθορίζουμε τον τύπο, τη θέση και το μέγεθος του γραφήματος.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Βήμα 3: Πρόσβαση σε σημεία δεδομένων

 Για να τροποποιήσουμε τα σημεία δεδομένων στο γράφημα, πρέπει να έχουμε πρόσβαση στο`IChartDataPointCollection` αντικείμενο.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Βήμα 4: Προσαρμόστε τα σημεία δεδομένων

Σε αυτό το βήμα, θα προσαρμόσουμε συγκεκριμένα σημεία δεδομένων. Εδώ, αλλάζουμε το χρώμα των σημείων δεδομένων και διαμορφώνουμε τις ρυθμίσεις ετικετών.

```java
// Προσαρμόστε το σημείο δεδομένων 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Προσαρμογή του σημείου δεδομένων 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Βήμα 5: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση με το προσαρμοσμένο γράφημα.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Προσθέσατε με επιτυχία χρώμα σε συγκεκριμένα σημεία δεδομένων σε μια διαφάνεια Java χρησιμοποιώντας το Aspose.Slides for Java.

## Ολοκληρώστε τον πηγαίο κώδικα για την προσθήκη χρώματος σε σημεία δεδομένων σε διαφάνειες Java

```java
Presentation pres = new Presentation();
try
{
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//ΝΑ ΚΑΝΩ
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθατε πώς να προσθέτετε χρώμα σε σημεία δεδομένων σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε περαιτέρω τα γραφήματα και τις παρουσιάσεις σας με βάση τις συγκεκριμένες απαιτήσεις σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το χρώμα άλλων σημείων δεδομένων;

Για να αλλάξετε το χρώμα άλλων σημείων δεδομένων, μπορείτε να ακολουθήσετε μια παρόμοια προσέγγιση όπως φαίνεται στο Βήμα 4. Αποκτήστε πρόσβαση στο σημείο δεδομένων που θέλετε να προσαρμόσετε και τροποποιήστε τις ρυθμίσεις χρώματος και ετικέτας.

### Μπορώ να προσαρμόσω άλλες πτυχές του γραφήματος;

 Ναι, μπορείτε να προσαρμόσετε διάφορες πτυχές του γραφήματος, όπως γραμματοσειρές, ετικέτες, τίτλους και άλλα. Αναφέρομαι στο[Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/) για λεπτομερείς επιλογές προσαρμογής.

### Πού μπορώ να βρω περισσότερα παραδείγματα και τεκμηρίωση;

 Μπορείτε να βρείτε περισσότερα παραδείγματα και λεπτομερή τεκμηρίωση σχετικά με τη χρήση του Aspose.Slides για Java στο[Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/java/) δικτυακός τόπος.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
