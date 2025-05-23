---
"date": "2025-04-22"
"description": "Μάθετε πώς να δημιουργείτε γραφήματα ντόνατ με Python και Aspose.Slides. Αυτός ο οδηγός βήμα προς βήμα καλύπτει τη ρύθμιση, την προσαρμογή και τις βέλτιστες πρακτικές για τη βελτίωση των παρουσιάσεών σας."
"title": "Πώς να δημιουργήσετε γραφήματα ντόνατ σε Python χρησιμοποιώντας το Aspose.Slides - ένας οδηγός βήμα προς βήμα"
"url": "/el/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε γραφήματα ντόνατ σε Python χρησιμοποιώντας το Aspose.Slides: Ένας οδηγός βήμα προς βήμα

Στον τομέα της οπτικοποίησης δεδομένων, η αποτελεσματική παρουσίαση πληροφοριών μπορεί να επηρεάσει σημαντικά την κατανόηση και τη λήψη αποφάσεων. Είτε δημιουργείτε μια επιχειρηματική παρουσίαση είτε αναλύετε σύνθετα σύνολα δεδομένων, τα γραφήματα είναι απαραίτητα εργαλεία. Μεταξύ των διαφόρων τύπων γραφημάτων, τα γραφήματα ντόνατ παρέχουν έναν ελκυστικό τρόπο αναπαράστασης αναλογικών δεδομένων με μια εύχρηστη κεντρική τρύπα. Αυτός ο οδηγός βήμα προς βήμα θα σας καθοδηγήσει στη δημιουργία ενός γραφήματος ντόνατ σε Python χρησιμοποιώντας το Aspose.Slides - μια ισχυρή βιβλιοθήκη για τον χειρισμό παρουσιάσεων.

## Τι θα μάθετε
- Πώς να ρυθμίσετε και να χρησιμοποιήσετε το Aspose.Slides για Python
- Η διαδικασία προσθήκης ενός γραφήματος ντόνατ στις διαφάνειες της παρουσίασής σας
- Προσαρμογή σειρών και κατηγοριών μέσα στο γράφημα
- Προσαρμογή οπτικών στοιχείων όπως ετικέτες, χρώματα και εφέ έκρηξης
- Βέλτιστες πρακτικές για τη βελτιστοποίηση της απόδοσης με το Aspose.Slides

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε:
- **Περιβάλλον Python**: Η Python 3.x είναι εγκατεστημένη στον υπολογιστή σας.
- **Aspose.Slides για Python**Εγκαταστήστε αυτήν τη βιβλιοθήκη χρησιμοποιώντας το pip.
- **Βασική Κατανόηση Προγραμματισμού Python**Η εξοικείωση με τους βρόχους και τον αντικειμενοστρεφή προγραμματισμό θα είναι χρήσιμη.

## Ρύθμιση του Aspose.Slides για Python
Για να ξεκινήσετε, εγκαταστήστε τη βιβλιοθήκη Aspose.Slides μέσω του pip:

```bash
pip install aspose.slides
```

### Απόκτηση Άδειας
Το Aspose προσφέρει μια δωρεάν δοκιμαστική περίοδο για να δοκιμάσετε λειτουργίες χωρίς περιορισμούς για περιορισμένο χρονικό διάστημα. Για να το αποκτήσετε:
1. Επισκεφθείτε το [Δωρεάν δοκιμή](https://releases.aspose.com/slides/python-net/) σελίδα.
2. Ακολουθήστε τις οδηγίες για να κατεβάσετε και να εφαρμόσετε την προσωρινή σας άδεια χρήσης.

Για συνεχή χρήση, σκεφτείτε να αγοράσετε μια συνδρομή από το [Σελίδα αγοράς](https://purchase.aspose.com/buy).

### Βασική Αρχικοποίηση
Αφού ρυθμίσετε το Aspose.Slides, αρχικοποιήστε το ως εξής:

```python
import aspose.slides as slides

# Δημιουργήστε μια παρουσία της κλάσης Presentation.
with slides.Presentation() as pres:
    # Ο κώδικά σας για τον χειρισμό παρουσιάσεων βρίσκεται εδώ.

# Αποθηκεύστε την παρουσίαση αφού κάνετε αλλαγές.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Οδηγός Εφαρμογής
Αφού ρυθμίσετε το Aspose.Slides, ακολουθήστε αυτά τα βήματα για να προσθέσετε ένα γράφημα ντόνατ στην παρουσίασή σας, διαφάνεια προς διαφάνεια.

### Δημιουργία νέας παρουσίασης και προσθήκη διαφάνειας
Ξεκινήστε δημιουργώντας μια παρουσία του `Presentation` τάξη:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Αποκτήστε πρόσβαση ή δημιουργήστε διαφάνειες σε αυτό το πλαίσιο.
```

### Προσθήκη γραφήματος ντόνατ στην πρώτη διαφάνεια
Αποκτήστε πρόσβαση στην πρώτη διαφάνεια και χρησιμοποιήστε το `add_chart` μέθοδος. Καθορίστε τον τύπο γραφήματος ως `DOUGHNUT`, μαζί με τη θέση και το μέγεθος:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Ρύθμιση παραμέτρων δεδομένων γραφήματος
Διαγράψτε τα υπάρχοντα δεδομένα και διαμορφώστε ρυθμίσεις όπως η απόκρυψη του υπομνήματος:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Προσθήκη Σειρών και Κατηγοριών
Προσθέστε πολλές σειρές και κατηγορίες για ένα γράφημα ντόνατ. Δείτε πώς μπορείτε να δημιουργήσετε 15 σειρές με συγκεκριμένες ιδιότητες:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Προσθέστε κατηγορίες με παρόμοιο τρόπο:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Προσθέστε σημεία δεδομένων για κάθε σειρά.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Προσαρμόστε την εμφάνιση κάθε σημείου δεδομένων.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Διαμορφώστε τις ρυθμίσεις ετικέτας για την τελευταία σειρά.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Αποθήκευση της παρουσίασης
Τέλος, αποθηκεύστε την παρουσίασή σας σε έναν καθορισμένο κατάλογο:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Πρακτικές Εφαρμογές
Τα γραφήματα ντόνατ είναι ευέλικτα και μπορούν να χρησιμοποιηθούν σε διάφορα σενάρια, όπως:
1. **Κατανομή Προϋπολογισμού**: Εμφάνιση του τρόπου με τον οποίο τα διάφορα τμήματα χρησιμοποιούν τα κεφάλαια που τους έχουν διατεθεί.
2. **Ανάλυση Μεριδίου Αγοράς**Σύγκριση του μεριδίου αγοράς ανταγωνιστικών προϊόντων ή εταιρειών.
3. **Αποτελέσματα Έρευνας**Οπτικοποίηση απαντήσεων σε ερωτήσεις έρευνας σχετικά με τις προτιμήσεις ή τα επίπεδα ικανοποίησης.

## Παράγοντες Απόδοσης
Για να διασφαλίσετε τη βέλτιστη απόδοση κατά τη χρήση του Aspose.Slides:
- Ελαχιστοποιήστε τη χρήση μνήμης απορρίπτοντας τα αντικείμενα σωστά μετά τη χρήση.
- Φορτώστε παρουσιάσεις στη μνήμη μόνο όταν είναι απαραίτητο και κλείστε τες το συντομότερο δυνατό.
- Εξετάστε το ενδεχόμενο μαζικής επεξεργασίας διαφανειών εάν εργάζεστε με μεγάλο αριθμό γραφημάτων.

## Σύναψη
Ακολουθώντας αυτόν τον οδηγό, μάθατε πώς να δημιουργείτε δυναμικά γραφήματα ντόνατ χρησιμοποιώντας το Aspose.Slides για Python. Αυτές οι απεικονίσεις μπορούν να βελτιώσουν τις παρουσιάσεις σας κάνοντας τα δεδομένα πιο εύπεπτα και ελκυστικά. Συνεχίστε να εξερευνάτε τις λειτουργίες της βιβλιοθήκης για να προσαρμόσετε και να βελτιστοποιήσετε περαιτέρω τα γραφήματά σας.

## Ενότητα Συχνών Ερωτήσεων
1. **Μπορώ να χρησιμοποιήσω το Aspose.Slides χωρίς να αγοράσω άδεια χρήσης;**
   - Ναι, μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμαστική άδεια χρήσης για σκοπούς αξιολόγησης.
2. **Πώς μπορώ να αλλάξω τα χρώματα γραφήματος στο Aspose.Slides;**
   - Χρησιμοποιήστε το `fill_format` ιδιότητα για να ορίσετε το επιθυμητό χρώμα για τα στοιχεία του γραφήματος σας.
3. **Είναι δυνατή η εξαγωγή γραφημάτων ως εικόνες;**
   - Ναι, μπορείτε να αποδώσετε διαφάνειες που περιέχουν γραφήματα σε μορφές εικόνας χρησιμοποιώντας τις δυνατότητες απόδοσης της βιβλιοθήκης.
4. **Ποια είναι μερικά συνηθισμένα προβλήματα κατά την προσθήκη γραφημάτων;**
   - Βεβαιωθείτε ότι όλα τα σημεία δεδομένων και οι κατηγορίες έχουν προστεθεί σωστά πριν επιχειρήσετε να αποθηκεύσετε ή να εμφανίσετε το γράφημά σας.
5. **Μπορώ να ενσωματώσω το Aspose.Slides με άλλες βιβλιοθήκες Python;**
   - Απολύτως! Μπορείτε να το χρησιμοποιήσετε παράλληλα με βιβλιοθήκες όπως το Pandas για βελτιωμένες δυνατότητες χειρισμού δεδομένων.

## Πόροι
- [Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Λήψη Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Αγοράστε μια άδεια χρήσης](https://purchase.aspose.com/buy)
- [Δωρεάν δοκιμή και προσωρινή άδεια χρήσης](https://releases.aspose.com/slides/python-net/)
- [Φόρουμ Κοινότητας Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}