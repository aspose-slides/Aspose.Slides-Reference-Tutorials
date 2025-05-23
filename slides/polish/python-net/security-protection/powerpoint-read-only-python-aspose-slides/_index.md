---
"date": "2025-04-23"
"description": "Dowiedz się, jak ustawić prezentacje PowerPoint jako tylko do odczytu i programowo zliczać slajdy za pomocą Aspose.Slides dla Pythona. Idealne do bezpiecznego udostępniania dokumentów i automatycznego raportowania."
"title": "Ustaw PowerPoint jako tylko do odczytu i zlicz slajdy za pomocą Pythona używając Aspose.Slides"
"url": "/pl/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Ustaw PowerPoint jako tylko do odczytu i zlicz slajdy za pomocą Pythona

## Wstęp
Czy kiedykolwiek stanąłeś przed wyzwaniem dystrybucji prezentacji, zapewniając jednocześnie, że pozostanie niezmieniona? A może chciałeś mieć łatwy sposób na sprawdzenie, ile slajdów jest w prezentacji bez jej otwierania? Dzięki **Aspose.Slides dla Pythona**, te zadania stają się proste. Ten samouczek przeprowadzi Cię przez ustawianie prezentacji PowerPoint jako tylko do odczytu i liczenie slajdów za pomocą Aspose.Slides, oferując solidne rozwiązanie do zarządzania plikami PowerPoint programowo.

**Czego się nauczysz:**
- Jak ustawić ochronę przed zapisem w prezentacji programu PowerPoint.
- Jak zapisać plik programu PowerPoint z ograniczeniami tylko do odczytu.
- Jak wczytać prezentację i sprawnie policzyć slajdy.

Przyjrzyjmy się bliżej, jak można bezproblemowo realizować te zadania w Pythonie.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:
- **Python 3.6+** zainstalowany w Twoim systemie.
- Dostęp do interfejsu wiersza poleceń umożliwiającego instalację pakietów.

Będziesz także musiał zainstalować Aspose.Slides dla Pythona. Ta potężna biblioteka umożliwia zaawansowaną manipulację plikami PowerPoint bezpośrednio z Twojego środowiska Pythona. Podczas gdy darmowa wersja oferuje ograniczoną funkcjonalność, nabycie licencji (poprzez bezpłatną wersję próbną lub zakup) znacznie rozszerza możliwości.

## Konfigurowanie Aspose.Slides dla Pythona
Aby rozpocząć pracę z Aspose.Slides w Pythonie, musisz go najpierw zainstalować. Oto jak to zrobić:

### Instalacja pip
Uruchom następujące polecenie w terminalu lub wierszu poleceń:

```bash
pip install aspose.slides
```

Spowoduje to pobranie i zainstalowanie najnowszej wersji Aspose.Slides dla języka Python.

### Etapy uzyskania licencji
1. **Bezpłatna wersja próbna**: Zacznij od bezpłatnego okresu próbnego, aby poznać podstawowe funkcje.
2. **Licencja tymczasowa**:Uzyskaj tymczasową licencję, aby odblokować wszystkie funkcje na czas trwania okresu próbnego.
3. **Zakup**: Rozważ zakup licencji, aby uzyskać ciągły dostęp i wsparcie.

Gdy już masz plik licencji, załaduj go do skryptu w następujący sposób:

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## Przewodnik wdrażania
W tej sekcji omówimy implementację na dwie główne funkcje: ustawienie prezentacji jako tylko do odczytu i zliczanie slajdów.

### Funkcja 1: Zapisz prezentację jako tylko do odczytu
#### Przegląd
Ta funkcja umożliwia ustawienie ochrony przed zapisem w pliku PowerPoint, zapewniając, że nie można go modyfikować bez podania hasła. Jest to szczególnie przydatne w przypadku dystrybucji prezentacji, które powinny pozostać niezmienione przez odbiorcę.

#### Kroki
##### Krok 1: Utwórz obiekt prezentacji
Zacznij od utworzenia `Presentation` obiekt. To reprezentuje twój plik PPT w Pythonie.

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