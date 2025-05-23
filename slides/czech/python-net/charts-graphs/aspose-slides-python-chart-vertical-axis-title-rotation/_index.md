---
"date": "2025-04-23"
"description": "Naučte se, jak upravit úhel natočení názvů grafů v prezentacích pomocí Aspose.Slides pro Python, a vylepšit tak čitelnost a estetiku."
"title": "Jak nastavit rotaci názvu svislé osy grafu v Aspose.Slides pro Python"
"url": "/cs/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak nastavit rotaci názvu svislé osy grafu v Aspose.Slides pro Python

## Zavedení

V datových prezentacích je zlepšení čitelnosti grafu zásadní. Úpravou úhlu natočení názvu svislé osy grafu pomocí Aspose.Slides pro Python můžete dosáhnout toho, aby názvy na slidech úhledně zapadly nebo vynikly. Tento tutoriál vás provede nastavením úhlu natočení pro zvýšení funkčnosti i vizuální atraktivity.

**Co se naučíte:**
- Jak nainstalovat a nakonfigurovat Aspose.Slides pro Python.
- Kroky pro přidání a přizpůsobení grafů v rámci snímků.
- Techniky pro nastavení úhlu natočení názvů grafů.
- Reálné aplikace těchto funkcí ve vizualizaci dat.

Začněme tím, že si probereme předpoklady, než se pustíme do implementace.

## Předpoklady

Než začnete, ujistěte se, že máte:
- **Prostředí Pythonu**Nainstalujte Python 3.x z [python.org](https://www.python.org/).
- **Knihovna Aspose.Slides**Instalace přes PIP pro efektivní manipulaci s prezentacemi.
- **Základní znalost programování v Pythonu**Znalost syntaxe Pythonu a operací se soubory vám pomůže s nácvikem.

## Nastavení Aspose.Slides pro Python

Chcete-li použít Aspose.Slides, nainstalujte jej pomocí pip. Otevřete terminál nebo příkazový řádek a spusťte:

```bash
pip install aspose.slides
```

### Kroky získání licence

Aspose nabízí různé možnosti licencování:
- **Bezplatná zkušební verze**Stáhněte si zkušební verzi z [Stránka s vydáním Aspose](https://releases.aspose.com/slides/python-net/).
- **Dočasná licence**Získejte dočasnou licenci pro rozšířené funkce prostřednictvím [nákupní portál](https://purchase.aspose.com/temporary-license/).
- **Nákup**Zvažte koupi, pokud považujete nástroj za nepostradatelný a je k dispozici od [Nákupní stránka Aspose](https://purchase.aspose.com/buy).

#### Základní inicializace a nastavení

Zde je návod, jak inicializovat Aspose.Slides ve vašem Python skriptu:

```python
import aspose.slides as slides

# Vytvoření prezentačního objektu
def main():
    with slides.Presentation() as pres:
        # Váš kód bude zde
        pass

if __name__ == "__main__":
    main()
```

## Průvodce implementací

### Přidávání a úprava grafů

#### Přehled

V této části přidáme do snímku klastrovaný sloupcový graf a upravíme ho nastavením úhlu natočení jeho svislé osy.

#### Kroky:

##### Krok 1: Přidání shlukového sloupcového grafu

Začněte přidáním grafu na konkrétních souřadnicích s definovanými rozměry:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Přidání seskupeného sloupcového grafu na snímek 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Krok 2: Konfigurace názvu svislé osy

Povolte a nastavte úhel natočení pro název svislé osy:

```python
def configure_chart(chart):
    # Povolit název svislé osy
    chart.axes.vertical_axis.has_title = True
    
    # Nastavte úhel otočení na 90 stupňů
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Krok 3: Uložte prezentaci

Nakonec uložte prezentaci se změnami:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Uložit prezentaci
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}