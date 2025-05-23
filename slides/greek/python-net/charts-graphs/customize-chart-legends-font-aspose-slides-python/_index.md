---
"date": "2025-04-22"
"description": "Μάθετε πώς να προσαρμόζετε τις ιδιότητες γραμματοσειράς των υπομνημάτων γραφημάτων χρησιμοποιώντας το Aspose.Slides για Python. Βελτιώστε τις παρουσιάσεις σας με έντονη, πλάγια και έγχρωμες γραμματοσειρές για μεμονωμένες καταχωρίσεις υπομνημάτων."
"title": "Προσαρμόστε τη γραμματοσειρά των υπομνημάτων γραφημάτων χρησιμοποιώντας το Aspose.Slides για Python&#58; Ένας ολοκληρωμένος οδηγός"
"url": "/el/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Προσαρμογή γραμματοσειράς υπομνημάτων γραφημάτων σε παρουσιάσεις χρησιμοποιώντας το Aspose.Slides για Python

## Εισαγωγή
Η δημιουργία οπτικά ελκυστικών παρουσιάσεων είναι απαραίτητη, ιδιαίτερα κατά την προβολή δεδομένων μέσω γραφημάτων. Μια συνηθισμένη πρόκληση είναι η προσαρμογή των υπομνημάτων των γραφημάτων ώστε να ευθυγραμμίζονται με το στυλ παρουσίασης ή τις ανάγκες επωνυμίας σας. Αυτός ο οδηγός δείχνει πώς να προσαρμόσετε τις ιδιότητες γραμματοσειράς, όπως η έντονη γραφή, η πλάγια γραφή, το μέγεθος και το χρώμα, για μεμονωμένες καταχωρίσεις υπομνημάτων σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Python.

**Τι θα μάθετε:**
- Ρύθμιση και χρήση του Aspose.Slides για Python
- Προσαρμογή ιδιοτήτων γραμματοσειράς υπομνημάτων γραφημάτων
- Εφαρμογή συγκεκριμένων στυλ γραμματοσειράς όπως έντονη γραφή, πλάγια γραφή και αλλαγή χρωμάτων
- Πρακτικά παραδείγματα βελτίωσης γραφημάτων με προσαρμοσμένες γραμματοσειρές

Ας εξερευνήσουμε πώς μπορείτε να επιτύχετε αυτήν την προσαρμογή.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
- **Βιβλιοθήκες**: Aspose.Slides για Python. Εγκαταστήστε το χρησιμοποιώντας pip.
- **Περιβάλλο**Ένα περιβάλλον Python (κατά προτίμηση Python 3.x) εγκατεστημένο στον υπολογιστή σας.
- **Γνώση**Βασική κατανόηση προγραμματισμού σε Python και εξοικείωση με τον προγραμματισμό παρουσιάσεων.

## Ρύθμιση του Aspose.Slides για Python
### Εγκατάσταση
Για να ξεκινήσετε, εγκαταστήστε τη βιβλιοθήκη Aspose.Slides εκτελώντας την ακόλουθη εντολή στο τερματικό σας:

```bash
pip install aspose.slides
```

### Απόκτηση Άδειας
Το Aspose.Slides είναι ένα εμπορικό προϊόν με διάφορες επιλογές αδειοδότησης:
- **Δωρεάν δοκιμή**Αποκτήστε μια προσωρινή άδεια χρήσης για πλήρη λειτουργικότητα.
- **Προσωρινή Άδεια**: Υποβάλετε αίτηση για προσωρινή άδεια χρήσης για να δοκιμάσετε όλες τις λειτουργίες χωρίς περιορισμούς.
- **Αγορά**Αγοράστε μια συνδρομή ή μια αόριστη άδεια χρήσης με βάση τις ανάγκες σας.

### Βασική Αρχικοποίηση
Δείτε πώς μπορείτε να αρχικοποιήσετε και να ρυθμίσετε το Aspose.Slides στο Python script σας:

```python
import aspose.slides as slides

# Αρχικοποίηση μιας παρουσίας παρουσίασης\με slides.Presentation() ως pres:
    # Ο κωδικός σας εδώ
```

## Οδηγός Εφαρμογής
Σε αυτήν την ενότητα, θα δούμε πώς να προσαρμόζουμε τις ιδιότητες γραμματοσειράς μεμονωμένων καταχωρήσεων υπομνήματος.

### Προσθήκη και πρόσβαση σε γράφημα
Αρχικά, ας προσθέσουμε ένα γράφημα ομαδοποιημένων στηλών στη διαφάνειά σας:

```python
# Προσθέστε ένα γράφημα ομαδοποιημένων στηλών στη θέση (50, 50) με πλάτος 600 και ύψος 400
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # Αυτό είναι απλώς ένα σύμβολο κράτησης θέσης για την πραγματική μέθοδο Aspose.Slides.
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# Προσομοίωση προ-διαφανειών[0].σχημάτων
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### Προσαρμογή ιδιοτήτων γραμματοσειράς υπομνήματος
#### Πρόσβαση στη μορφή κειμένου της καταχώρησης υπομνήματος
Για να τροποποιήσετε τις ιδιότητες γραμματοσειράς μιας συγκεκριμένης καταχώρησης υπομνήματος:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# Προσομοίωση chart.legend.entries[1].text_format
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### Ορισμός ιδιοτήτων γραμματοσειράς
Εδώ, προσαρμόζουμε στοιχεία όπως έντονη γραφή, μέγεθος, πλάγια γραφή και χρώμα:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# Ορισμός μεγέθους γραμματοσειράς σε 20 στιγμές
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# Ορίστε το χρώμα της γραμματοσειράς σε μπλε χρησιμοποιώντας τον τύπο συμπαγούς γεμίσματος
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### Αποθήκευση της παρουσίασης
Τέλος, αποθηκεύστε την παρουσίασή σας με αυτές τις προσαρμογές:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}