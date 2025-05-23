---
"date": "2025-04-22"
"description": "Μάθετε πώς να εμφανίζετε εύκολα ετικέτες ποσοστών σε γραφήματα σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Python. Ιδανικό για τη βελτίωση της οπτικοποίησης δεδομένων."
"title": "Πώς να εμφανίσετε ετικέτες ποσοστού σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Python&#58; Ένας ολοκληρωμένος οδηγός"
"url": "/el/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να εμφανίσετε ετικέτες ποσοστού σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Python

## Εισαγωγή

Η αποτελεσματική οπτικοποίηση δεδομένων είναι ζωτικής σημασίας σε παρουσιάσεις και αναφορές, ειδικά όταν θέλετε να επισημάνετε με σαφήνεια τις αναλογίες ή τις κατανομές. Τι γίνεται όμως αν χρειάζεστε αυτά τα ποσοστά να εμφανίζονται απευθείας στα γραφήματά σας; Αυτός ο ολοκληρωμένος οδηγός θα σας καθοδηγήσει στη χρήση **Aspose.Slides για Python** για να εμφανίσετε ποσοστιαίες τιμές ως ετικέτες σε ένα γράφημα χωρίς κόπο.

### Τι θα μάθετε:
- Πώς να δημιουργήσετε και να ενσωματώσετε γραφήματα σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Python.
- Εμφάνιση σημείων δεδομένων ως ετικέτες ποσοστού στα γραφήματά σας.
- Αποτελεσματική αποθήκευση και διαχείριση παρουσιάσεων PowerPoint.

Είστε έτοιμοι να ξεκινήσετε να προσθέτετε χρήσιμα γραφικά στα δεδομένα σας; Ας δούμε πρώτα τι χρειάζεστε πριν εμβαθύνουμε στον κώδικα!

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
- **Aspose.Slides για Python**Αυτή η βιβλιοθήκη είναι απαραίτητη για τη δημιουργία και τον χειρισμό παρουσιάσεων PowerPoint μέσω προγραμματισμού.
- **Περιβάλλον Python**Βασική κατανόηση του προγραμματισμού Python και της ρύθμισης περιβάλλοντος.
- **Διαχειριστής πακέτων PIP**Χρησιμοποιείται για την εγκατάσταση του Aspose.Slides.

## Ρύθμιση του Aspose.Slides για Python

Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides, θα πρέπει πρώτα να το εγκαταστήσετε:

```bash
pip install aspose.slides
```

### Βήματα απόκτησης άδειας:
Μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμαστική έκδοση ή να αποκτήσετε μια προσωρινή άδεια χρήσης για να εξερευνήσετε όλες τις δυνατότητες του Aspose.Slides. Για εκτεταμένη χρήση, σκεφτείτε να αγοράσετε μια συνδρομή.

#### Βασική Αρχικοποίηση και Ρύθμιση

Μόλις εγκατασταθεί, θα αρχικοποιήσετε το περιβάλλον παρουσίασής σας ως εξής:

```python
import aspose.slides as slides

# Αρχικοποίηση αντικειμένου παρουσίασης
def create_presentation():
    with slides.Presentation() as presentation:
        # Ο κωδικός σας εδώ
```

## Οδηγός Εφαρμογής

Τώρα που είμαστε έτοιμοι, ας δούμε πώς να εμφανίζουμε ποσοστά σε γραφήματα.

### Δημιουργία του γραφήματος και προσθήκη δεδομένων

#### Επισκόπηση
Θα δημιουργήσουμε ένα γράφημα στοιβαγμένων στηλών με ετικέτες ποσοστών για κάθε σημείο δεδομένων, επιτρέποντας στους θεατές να βλέπουν τις ακριβείς αναλογίες με μια ματιά.

##### Βήμα 1: Προσθήκη γραφήματος στη διαφάνειά σας

```python
# Πρόσβαση στην πρώτη διαφάνεια της παρουσίασής σας
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Προσθήκη γραφήματος σωρευμένων στηλών
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Αυτό το απόσπασμα κώδικα προσθέτει ένα βασικό γράφημα στην πρώτη διαφάνεια. `add_chart` Η μέθοδος καθορίζει τον τύπο του γραφήματος, τη θέση και το μέγεθός του.

##### Βήμα 2: Υπολογισμός συνολικών τιμών για κατηγορίες

```python
def calculate_totals(chart):
    total_for_category = []
    # Αθροίστε τις τιμές σε όλες τις σειρές για κάθε κατηγορία
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Αυτός ο βρόχος υπολογίζει το σύνολο όλων των σημείων δεδομένων σε όλες τις σειρές, κάτι που είναι κρίσιμο για τους υπολογισμούς ποσοστών.

#### Ορισμός ετικετών ποσοστού

##### Βήμα 3: Ρύθμιση παραμέτρων σημείων δεδομένων σειράς

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Ορίστε τις προεπιλεγμένες επιλογές ετικέτας για την απόκρυψη μη απαραίτητων πληροφοριών
        series.labels.default_data_label_format.show_legend_key = False
        
        # Υπολογισμός και ορισμός ετικετών ποσοστού
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Δημιουργήστε ένα τμήμα κειμένου με την ποσοστιαία τιμή
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Διαγραφή υπαρχουσών ετικετών και προσθήκη νέας ετικέτας ποσοστού
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Απόκρυψη άλλων στοιχείων ετικέτας δεδομένων
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Αυτό το τμήμα επεξεργάζεται κάθε σημείο δεδομένων για να υπολογίσει το ποσοστό του επί του συνόλου και του αντιστοιχίζει ως ετικέτα.

### Αποθήκευση της παρουσίασής σας

```python
def save_presentation(presentation, output_directory):
    # Αποθήκευση της παρουσίασής σας με τροποποιήσεις
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}