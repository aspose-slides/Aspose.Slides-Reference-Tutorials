---
"date": "2025-04-23"
"description": "Naučte se, jak vytvářet a upravovat grafiku SmartArt v PowerPointu pomocí Aspose.Slides pro Python a vylepšit tak své prezentace dynamickými organizačními diagramy."
"title": "Jak vytvořit a přizpůsobit SmartArt v PowerPointu pomocí Aspose.Slides pro Python"
"url": "/cs/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit a přizpůsobit SmartArt v PowerPointu pomocí Aspose.Slides pro Python

## Zavedení

Prezentace jsou důležitým nástrojem pro vizuální znázornění organizačních struktur nebo brainstormingových sezení. S Aspose.Slides pro Python můžete bez námahy vytvářet a upravovat grafiku SmartArt. Tento tutoriál vás provede přidáním grafiky SmartArt s organizačním diagramem do vašich snímků v PowerPointu.

**Co se naučíte:**
- Přidání grafiky SmartArt v PowerPointu pomocí Aspose.Slides pro Python.
- Přizpůsobení rozvržení uzlu SmartArt.
- Efektivní ukládání a export prezentací.

Pojďme začít s nastavením vašeho prostředí!

## Předpoklady

Než se pustíte do vytváření obrázků SmartArt, ujistěte se, že máte následující předpoklady:

### Požadované knihovny
- **Aspose.Slides pro Python**Pokud jste tak ještě neučinili, nainstalujte tuto knihovnu pomocí pipu.

### Požadavky na nastavení prostředí
- Funkční instalace Pythonu (doporučeno 3.x).
- Základní znalost programování v Pythonu.
- Znalost Microsoft PowerPointu je užitečná, ale není nutná.

## Nastavení Aspose.Slides pro Python

Chcete-li začít, nastavte si knihovnu Aspose.Slides ve svém prostředí Pythonu:

**Instalace potrubí:**
```bash
pip install aspose.slides
```

### Kroky získání licence
Aspose nabízí různé možnosti licencování:
- **Bezplatná zkušební verze**Stáhněte si dočasnou licenci pro vyzkoušení všech funkcí.
- **Dočasná licence**Získejte bezplatnou dočasnou licenci pro krátkodobé užívání.
- **Nákup**Zvažte zakoupení předplatného pro dlouhodobé projekty.

### Základní inicializace a nastavení

Po instalaci inicializujte svůj Python skript pomocí Aspose.Slides takto:

```python
import aspose.slides as slides

# Inicializujte třídu Presentation s metodou slides.Presentation() jako prezentaci:
    # Váš kód pro přidání SmartArt bude zde
```

## Průvodce implementací

Nyní si rozebereme proces přidávání a úpravy SmartArt v PowerPointu pomocí Aspose.Slides pro Python.

### Přidání obrázku SmartArt

#### Přehled
Vytvořte nový snímek a přidejte do něj obrázek SmartArt typu organizační diagram:

```python
import aspose.slides as slides

# Vytvořte instanci prezentace s metodou slides.Presentation() jako prezentací:
    # Přidat SmartArt se zadanými rozměry na pozici (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parametry a účel metody
- **x, y**: Pozice obrázku SmartArt na snímku.
- **šířka, výška**Rozměry pro správnou viditelnost.
- **typ_rozvržení**Určuje typ rozvržení SmartArt, v tomto případě organizační diagram.

### Přizpůsobení rozvržení organizačního diagramu

#### Přehled
První uzel v našem obrázku SmartArt upravte nastavením jeho rozvržení na možnost LEFT_HANGING (VISÍCÍ_DOLEVA):

```python
# Nastavte první uzel na rozvržení s levým zavěšením
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Vysvětlení možností konfigurace klíčů
- **Typ rozvržení organizačního grafu**Určuje, jak se uzly zobrazují, čímž se zlepšuje čitelnost a estetická přitažlivost.

### Uložení prezentace

Nakonec uložte prezentaci do určeného adresáře:

```python
# Uložte prezentaci pomocí SmartArt\presentation.save("VÁŠ_VÝSTUPNÍ_ADRESÁŘ/rozvržení_grafu_organizace_smart_art.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}