---
"date": "2025-04-22"
"description": "Erfahren Sie, wie Sie TextBox-Text, Schaltflächenbeschriftungen und Bilder in PowerPoint mit Aspose.Slides und Python bearbeiten. Optimieren Sie Ihre Präsentationen mit interaktiven Elementen."
"title": "Master Aspose.Slides für Python – Einfaches Ändern von PowerPoint ActiveX-Steuerelementen"
"url": "/de/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides für Python meistern: PowerPoint ActiveX-Steuerelemente ändern

In der heutigen dynamischen digitalen Welt ist die Anpassung von Microsoft PowerPoint-Präsentationen für die Erstellung ansprechender Inhalte unerlässlich. Ob Sie interaktive Schulungsmodule entwickeln oder Geschäftspräsentationen mit Benutzereingabefunktionen erweitern – die Anpassung von PowerPoint ActiveX-Steuerelementen kann die Funktionalität Ihrer Präsentation deutlich steigern. Dieses Tutorial erläutert die Verwendung von Aspose.Slides für Python zum Ändern von TextBox-Text und Schaltflächenbeschriftungen, zum Ersetzen von Bildern, zum Neupositionieren oder Entfernen von ActiveX-Steuerelementen aus Folien.

## Was Sie lernen werden
- So ändern Sie TextBox-Text und Schaltflächenbeschriftungen in PowerPoint-Präsentationen.
- Techniken zum Ersetzen von Bildern in ActiveX-Steuerelementen.
- Methoden zum effektiven Neupositionieren oder Entfernen von ActiveX-Steuerelementen.
- Praktische Anwendungen dieser Funktionen in realen Szenarien.

Bevor wir uns in Aspose.Slides für Python vertiefen, sehen wir uns die Voraussetzungen an.

## Voraussetzungen
Um diesem Tutorial folgen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Python**: Auf Ihrem System ist Version 3.6 oder höher installiert.
- **Aspose.Slides für Python über .NET**: Dies kann mit Pip installiert werden.
- Grundlegende Kenntnisse der Python-Programmierung und Vertrautheit mit der Struktur von PowerPoint.

### Anforderungen für die Umgebungseinrichtung
1. **Installieren Sie Aspose.Slides**:
   Verwenden Sie den folgenden Befehl, um Aspose.Slides für Python über .NET zu installieren:

   ```bash
   pip install aspose.slides
   ```

2. **Lizenzerwerb**: 
   Beginnen Sie mit dem Erwerb eines [kostenlose Testlizenz](https://releases.aspose.com/slides/python-net/) oder beantragen Sie eine temporäre Lizenz, um alle Funktionen ohne Einschränkungen zu nutzen.

3. **Grundlegende Initialisierung**:
   Importieren Sie die erforderlichen Module und laden Sie Ihr PowerPoint-Dokument wie unten gezeigt:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # Ihr Code wird hier eingefügt.
   ```

## Implementierungshandbuch
### Funktion: Textfeldtext ändern und Bild ersetzen
#### Überblick
Mit dieser Funktion können Sie den Text in einem TextBox-ActiveX-Steuerelement aktualisieren und das zugehörige Bild ersetzen. Dies ist nützlich, um Präsentationen zu personalisieren oder Inhalte dynamisch zu aktualisieren.

##### Schritt-für-Schritt-Anleitung
1. **Laden Sie die Präsentation**:
   Beginnen Sie mit dem Laden Ihrer PowerPoint-Präsentation mit den ActiveX-Steuerelementen.

   ```python
def change_textbox_and_image():
    mit slides.Presentation("IHR_DOKUMENTENVERZEICHNIS/activex_master.pptm") als Präsentation:
        Folie = Präsentation.Folien[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **Ersatzbild erstellen**:
   Generieren Sie ein Bild, um den ursprünglichen Inhalt während der ActiveX-Aktivierung zu ersetzen.

   ```python
            import aspose.pydrawing as drawing

            # Erstellen Sie ein Bild mit angegebenen Abmessungen
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # Fügen Sie Randlinien für ein elegantes Aussehen hinzu
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Funktion: Schaltflächenbeschriftung ändern und Bild ersetzen
#### Überblick
Aktualisieren Sie die Schaltflächenbeschriftungen in den ActiveX-Steuerelementen Ihrer Präsentation und bieten Sie so dynamische Möglichkeiten zur Benutzerinteraktion.

##### Schritt-für-Schritt-Anleitung
1. **Laden Sie die Präsentation**:
   Beginnen Sie wie zuvor mit dem Laden der PowerPoint-Datei.

   ```python
def change_button_caption_and_image():
    mit slides.Presentation("IHR_DOKUMENTENVERZEICHNIS/activex_master.pptm") als Präsentation:
        Folie = Präsentation.Folien[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **Ersatzbild erstellen**:
   Generieren Sie ein Bild zum visuellen Ersetzen.

   ```python
            # Erstellen Sie eine Bitmap für die Abmessungen der Schaltfläche
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # Fügen Sie aus ästhetischen Gründen Randlinien hinzu
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Funktion: ActiveX-Steuerelemente nach unten verschieben und Präsentation speichern
#### Überblick
Erfahren Sie, wie Sie ActiveX-Steuerelemente innerhalb einer Folie neu positionieren und so die Layoutflexibilität verbessern.

##### Schritt-für-Schritt-Anleitung
1. **Laden Sie die Präsentation**:
   Öffnen Sie Ihr PowerPoint-Dokument zur Bearbeitung.

   ```python
def move_active_x_controls_and_save():
    mit slides.Presentation("IHR_DOKUMENTENVERZEICHNIS/activex_master.pptm") als Präsentation:
        Folie = Präsentation.Folien[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**Abschluss:**
Mit dieser Anleitung können Sie PowerPoint-ActiveX-Steuerelemente mit Aspose.Slides für Python effektiv anpassen. Dies verbessert die Interaktivität und Individualisierung Ihrer Präsentationen und macht sie für Ihr Publikum ansprechender.

## Keyword-Empfehlungen
- „PowerPoint ActiveX-Steuerelemente ändern“
- „Aspose.Slides für Python“
- „TextBox-Text in PowerPoint ändern“
- "Bilder in ActiveX-Steuerelementen ersetzen"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}