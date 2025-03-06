---
title: Προσθήκη κινούμενων εικόνων στα σχήματα στο PowerPoint
linktitle: Προσθήκη κινούμενων εικόνων στα σχήματα στο PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε κινούμενα σχέδια σε σχήματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java με αυτό το λεπτομερές σεμινάριο. Ιδανικό για τη δημιουργία συναρπαστικών παρουσιάσεων.
type: docs
weight: 10
url: /el/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---
## Εισαγωγή
Η δημιουργία συναρπαστικών παρουσιάσεων απαιτεί συχνά την προσθήκη κινούμενων εικόνων σε σχήματα και κείμενο. Τα κινούμενα σχέδια μπορούν να κάνουν τις διαφάνειές σας πιο δυναμικές και σαγηνευτικές, διασφαλίζοντας ότι το κοινό σας θα συνεχίσει να ενδιαφέρεται. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσθήκης κινούμενων εικόνων σε σχήματα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μέχρι το τέλος αυτού του άρθρου, θα μπορείτε να δημιουργείτε επαγγελματικά κινούμενα σχέδια χωρίς κόπο.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, ας βεβαιωθούμε ότι έχετε όλα όσα χρειάζεστε:
1.  Aspose.Slides for Java Library: Πρέπει να έχετε εγκατεστημένη τη βιβλιοθήκη Aspose.Slides for Java. Μπορείς[κατεβάστε το εδώ](https://releases.aspose.com/slides/java/).
2. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στον υπολογιστή σας.
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Χρησιμοποιήστε οποιοδήποτε Java IDE όπως το IntelliJ IDEA, το Eclipse ή το NetBeans.
4. Βασική γνώση Java: Αυτό το σεμινάριο προϋποθέτει ότι έχετε βασική κατανόηση του προγραμματισμού Java.
## Εισαγωγή πακέτων
Για να ξεκινήσετε, θα χρειαστεί να εισαγάγετε τα απαραίτητα πακέτα για το Aspose.Slides και άλλες απαιτούμενες κλάσεις Java.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## Βήμα 1: Ρυθμίστε τον κατάλογο του έργου σας
Αρχικά, δημιουργήστε έναν κατάλογο για τα αρχεία του έργου σας.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Βήμα 2: Αρχικοποίηση αντικειμένου παρουσίασης
 Στη συνέχεια, δημιουργήστε το`Presentation` κλάση για να αντιπροσωπεύει το αρχείο σας PowerPoint.
```java
// Κλάση Instantiate Presentation που αντιπροσωπεύει το PPTX
Presentation pres = new Presentation();
```
## Βήμα 3: Πρόσβαση στην Πρώτη Διαφάνεια
Τώρα, αποκτήστε πρόσβαση στην πρώτη διαφάνεια της παρουσίασης όπου θα προσθέσετε τα κινούμενα σχέδια.
```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide sld = pres.getSlides().get_Item(0);
```
## Βήμα 4: Προσθέστε ένα σχήμα στη διαφάνεια
Προσθέστε ένα ορθογώνιο σχήμα στη διαφάνεια και εισαγάγετε λίγο κείμενο σε αυτήν.
```java
// Προσθέστε ένα ορθογώνιο σχήμα στη διαφάνεια
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## Βήμα 5: Εφαρμόστε ένα εφέ κινούμενης εικόνας
Εφαρμόστε το εφέ κίνησης "PathFootball" στο σχήμα.
```java
// Προσθήκη εφέ κίνησης PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Βήμα 6: Δημιουργήστε ένα διαδραστικό έναυσμα
Δημιουργήστε ένα σχήμα κουμπιού που θα ενεργοποιεί την κίνηση όταν κάνετε κλικ.
```java
// Δημιουργήστε ένα σχήμα "κουμπιού" για να ενεργοποιήσετε την κινούμενη εικόνα
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Βήμα 7: Καθορίστε τη διαδραστική ακολουθία
Καθορίστε μια ακολουθία εφέ για το κουμπί.
```java
// Δημιουργήστε μια ακολουθία εφέ για το κουμπί
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## Βήμα 8: Προσθέστε μια προσαρμοσμένη διαδρομή χρήστη
Προσθέστε μια προσαρμοσμένη κίνηση διαδρομής χρήστη στο σχήμα.
```java
// Προσθήκη εφέ κίνησης προσαρμοσμένης διαδρομής χρήστη
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// Δημιουργία εφέ κίνησης
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// Καθορίστε τα σημεία διαδρομής
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## Βήμα 9: Αποθηκεύστε την παρουσίαση
Τέλος, αποθηκεύστε την παρουσίαση στη θέση που επιθυμείτε.
```java
// Αποθηκεύστε την παρουσίαση ως αρχείο PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// Απορρίψτε το αντικείμενο παρουσίασης
if (pres != null) pres.dispose();
```
## συμπέρασμα
Και εκεί το έχετε! Προσθέσατε με επιτυχία κινούμενα σχέδια σε σχήματα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η ισχυρή βιβλιοθήκη διευκολύνει τη βελτίωση των παρουσιάσεών σας με δυναμικά εφέ, διασφαλίζοντας ότι το κοινό σας παραμένει αφοσιωμένο. Θυμηθείτε, η πρακτική κάνει τέλεια, γι' αυτό συνεχίστε να πειραματίζεστε με διαφορετικά εφέ και ενεργοποιητές για να δείτε τι λειτουργεί καλύτερα για τις ανάγκες σας.
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides for Java είναι ένα ισχυρό API για τη δημιουργία, τροποποίηση και χειρισμό παρουσιάσεων του PowerPoint μέσω προγραμματισμού.
### Μπορώ να χρησιμοποιήσω το Aspose.Slides δωρεάν;
 Μπορείτε να δοκιμάσετε το Aspose.Slides δωρεάν με ένα[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/). Για συνεχή χρήση, απαιτείται άδεια επί πληρωμή.
### Ποιες εκδόσεις Java είναι συμβατές με το Aspose.Slides;
Το Aspose.Slides υποστηρίζει Java SE 6 και νεότερη έκδοση.
### Πώς μπορώ να προσθέσω διαφορετικά κινούμενα σχέδια σε πολλά σχήματα;
Μπορείτε να προσθέσετε διαφορετικά κινούμενα σχέδια σε πολλά σχήματα επαναλαμβάνοντας τα βήματα για κάθε σχήμα και προσδιορίζοντας διαφορετικά εφέ, όπως απαιτείται.
### Πού μπορώ να βρω περισσότερα παραδείγματα και τεκμηρίωση;
 Ελέγξτε το[τεκμηρίωση](https://reference.aspose.com/slides/java/) και[φόρουμ υποστήριξης](https://forum.aspose.com/c/slides/11)για περισσότερα παραδείγματα και βοήθεια.