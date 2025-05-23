---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie PowerPoint-Präsentationen schreibgeschützt machen und Folien mit Aspose.Slides für Python programmgesteuert zählen. Perfekt für sicheren Dokumentenaustausch und automatisierte Berichterstattung."
"title": "Setzen Sie PowerPoint auf schreibgeschützt und zählen Sie Folien mit Python mithilfe von Aspose.Slides"
"url": "/de/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint schreibgeschützt machen und Folien mit Python zählen

## Einführung
Standen Sie schon einmal vor der Herausforderung, eine Präsentation unverändert zu verteilen? Oder wollten Sie schon immer einfach überprüfen, wie viele Folien Ihre Präsentation enthält, ohne sie öffnen zu müssen? Mit **Aspose.Slides für Python**, werden diese Aufgaben unkompliziert. Dieses Tutorial führt Sie durch das Festlegen des Schreibschutzes für PowerPoint-Präsentationen und das Zählen von Folien mit Aspose.Slides und bietet eine robuste Lösung für die programmgesteuerte Verwaltung Ihrer PowerPoint-Dateien.

**Was Sie lernen werden:**
- So richten Sie einen Schreibschutz für eine PowerPoint-Präsentation ein.
- So speichern Sie eine PowerPoint-Datei mit schreibgeschützten Einschränkungen.
- So laden Sie eine Präsentation und zählen die Anzahl der Folien effizient.

Lassen Sie uns einen Blick darauf werfen, wie Sie diese Aufgaben nahtlos in Python erledigen können.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:
- **Python 3.6+** auf Ihrem System installiert.
- Zugriff auf eine Befehlszeilenschnittstelle zum Installieren von Paketen.

Sie müssen außerdem Aspose.Slides für Python installieren. Diese leistungsstarke Bibliothek ermöglicht die erweiterte Bearbeitung von PowerPoint-Dateien direkt in Ihrer Python-Umgebung. Die kostenlose Version bietet zwar eingeschränkte Funktionen, der Erwerb einer Lizenz (entweder durch eine kostenlose Testversion oder einen Kauf) erweitert die Möglichkeiten jedoch erheblich.

## Einrichten von Aspose.Slides für Python
Um mit Aspose.Slides in Python arbeiten zu können, müssen Sie es zuerst installieren. So geht's:

### pip-Installation
Führen Sie den folgenden Befehl in Ihrem Terminal oder Ihrer Eingabeaufforderung aus:

```bash
pip install aspose.slides
```

Dadurch wird die neueste Version von Aspose.Slides für Python heruntergeladen und installiert.

### Schritte zum Lizenzerwerb
1. **Kostenlose Testversion**: Beginnen Sie mit einer kostenlosen Testversion, um die grundlegenden Funktionen kennenzulernen.
2. **Temporäre Lizenz**: Erwerben Sie eine temporäre Lizenz, um während Ihres Evaluierungszeitraums alle Funktionen freizuschalten.
3. **Kaufen**: Erwägen Sie den Kauf einer Lizenz für fortlaufenden Zugriff und Support.

Sobald Sie Ihre Lizenzdatei haben, laden Sie sie wie folgt in Ihr Skript:

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## Implementierungshandbuch
In diesem Abschnitt unterteilen wir die Implementierung in zwei Hauptfunktionen: Festlegen des schreibgeschützten Zustands einer Präsentation und Zählen der Folien.

### Funktion 1: Präsentation schreibgeschützt speichern
#### Überblick
Mit dieser Funktion können Sie eine PowerPoint-Datei schreibschützen und so sicherstellen, dass sie ohne Kennworteingabe nicht geändert werden kann. Dies ist besonders nützlich für die Verteilung von Präsentationen, die vom Empfänger unverändert bleiben sollen.

#### Schritte
##### Schritt 1: Instanziieren eines Präsentationsobjekts
Beginnen Sie mit der Erstellung eines `Presentation` Objekt. Dies stellt Ihre PPT-Datei in Python dar.

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}