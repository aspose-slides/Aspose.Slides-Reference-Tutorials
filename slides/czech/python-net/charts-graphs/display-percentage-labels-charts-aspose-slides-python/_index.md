---
"date": "2025-04-22"
"description": "Naučte se, jak snadno zobrazit procentuální popisky v grafech v prezentacích PowerPointu pomocí Aspose.Slides pro Python. Ideální pro vylepšení vizualizace dat."
"title": "Jak zobrazit procentuální popisky v grafech pomocí Aspose.Slides pro Python – Komplexní průvodce"
"url": "/cs/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak zobrazit procentuální popisky v grafech pomocí Aspose.Slides pro Python

## Zavedení

Efektivní vizualizace dat je v prezentacích a zprávách klíčová, zejména pokud chcete jasně zvýraznit proporce nebo rozdělení. Co když ale potřebujete tato procenta zobrazit přímo v grafech? Tato komplexní příručka vás provede používáním... **Aspose.Slides pro Python** snadno zobrazit procentuální hodnoty jako popisky v grafu.

### Co se naučíte:
- Jak vytvářet a vkládat grafy do prezentací v PowerPointu pomocí Aspose.Slides pro Python.
- Zobrazování datových bodů jako procentuálních popisků v grafech.
- Efektivní ukládání a správa prezentací v PowerPointu.

Jste připraveni začít s přidáváním užitečných vizuálů do vašich dat? Než se pustíme do kódu, podívejme se nejprve na to, co potřebujete!

## Předpoklady

Než začneme, ujistěte se, že máte následující:
- **Aspose.Slides pro Python**Tato knihovna je nezbytná pro programovou tvorbu a manipulaci s prezentacemi v PowerPointu.
- **Prostředí Pythonu**Základní znalost programování v Pythonu a nastavení prostředí.
- **Správce balíčků PIP**Používá se k instalaci Aspose.Slides.

## Nastavení Aspose.Slides pro Python

Abyste mohli začít používat Aspose.Slides, musíte si jej nejprve nainstalovat:

```bash
pip install aspose.slides
```

### Kroky pro získání licence:
Můžete začít s bezplatnou zkušební verzí nebo si pořídit dočasnou licenci, abyste mohli prozkoumat všechny funkce Aspose.Slides. Pro delší používání zvažte zakoupení předplatného.

#### Základní inicializace a nastavení

Po instalaci inicializujete prezentační prostředí takto:

```python
import aspose.slides as slides

# Inicializace objektu Presentation
def create_presentation():
    with slides.Presentation() as presentation:
        # Váš kód zde
```

## Průvodce implementací

Nyní, když jsme si vše nastavili, se pojďme ponořit do zobrazování procent v grafech.

### Vytvoření grafu a přidání dat

#### Přehled
Vytvoříme skládaný sloupcový graf s procentuálními popisky pro každý datový bod, což divákům umožní na první pohled vidět přesné proporce.

##### Krok 1: Přidání grafu do snímku

```python
# Přístup k prvnímu snímku v prezentaci
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Přidání skládaného sloupcového grafu
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Tento úryvek kódu přidá na první snímek základní graf. `add_chart` Metoda určuje typ grafu, jeho polohu a velikost.

##### Krok 2: Výpočet celkových hodnot pro kategorie

```python
def calculate_totals(chart):
    total_for_category = []
    # Sečtěte hodnoty napříč všemi sériemi pro každou kategorii
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Tato smyčka vypočítává součet všech datových bodů v celé řadě, což je klíčové pro procentuální výpočty.

#### Nastavení procentuálních popisků

##### Krok 3: Konfigurace datových bodů řady

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Nastavení výchozích možností popisků pro skrytí nepodstatných informací
        series.labels.default_data_label_format.show_legend_key = False
        
        # Výpočet a nastavení procentuálních popisků
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Vytvořte textovou část s procentuální hodnotou
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Vymazat stávající popisky a přidat nový procentuální popisek
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Skrýt další prvky popisků dat
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Tento segment zpracovává každý datový bod, vypočítává jeho procento z celkového počtu a přiřazuje mu popisek.

### Uložení prezentace

```python
def save_presentation(presentation, output_directory):
    # Uložte prezentaci s úpravami
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}