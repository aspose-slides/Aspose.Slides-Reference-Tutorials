---
"date": "2025-04-22"
"description": "Naučte se, jak vytvářet prstencové grafy pomocí Pythonu a Aspose.Slides. Tato podrobná příručka zahrnuje nastavení, přizpůsobení a osvědčené postupy pro vylepšení vašich prezentací."
"title": "Jak vytvořit prstencové grafy v Pythonu pomocí Aspose.Slides – Podrobný návod"
"url": "/cs/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit prstencové grafy v Pythonu pomocí Aspose.Slides: Podrobný návod

oblasti vizualizace dat může efektivní prezentace informací významně ovlivnit porozumění a rozhodování. Ať už vytváříte obchodní prezentaci nebo analyzujete složité datové sady, grafy jsou nezbytnými nástroji. Mezi různými typy grafů poskytují prstencové grafy atraktivní způsob, jak reprezentovat proporcionální data s intuitivním středovým otvorem. Tato podrobná příručka vás provede vytvořením prstencového grafu v Pythonu pomocí Aspose.Slides – výkonné knihovny pro manipulaci s prezentacemi.

## Co se naučíte
- Jak nastavit a používat Aspose.Slides pro Python
- Proces přidání prstencového grafu do snímků prezentace
- Přizpůsobení řad a kategorií v grafu
- Úprava vizuálních prvků, jako jsou popisky, barvy a efekty exploze
- Nejlepší postupy pro optimalizaci výkonu s Aspose.Slides

## Předpoklady
Než začnete, ujistěte se, že máte:
- **Prostředí Pythonu**Na vašem počítači je nainstalován Python 3.x.
- **Aspose.Slides pro Python**Nainstalujte tuto knihovnu pomocí pipu.
- **Základní znalost programování v Pythonu**Znalost smyček a objektově orientovaného programování bude užitečná.

## Nastavení Aspose.Slides pro Python
Chcete-li začít, nainstalujte si knihovnu Aspose.Slides pomocí pipu:

```bash
pip install aspose.slides
```

### Získání licence
Aspose nabízí bezplatnou zkušební verzi pro testování funkcí bez omezení po omezenou dobu. Chcete-li ji získat:
1. Navštivte [Bezplatná zkušební verze](https://releases.aspose.com/slides/python-net/) strana.
2. Postupujte podle pokynů ke stažení a použití dočasné licence.

Pro další používání zvažte zakoupení předplatného od [Stránka nákupu](https://purchase.aspose.com/buy).

### Základní inicializace
Po nastavení Aspose.Slides jej inicializujte takto:

```python
import aspose.slides as slides

# Vytvořte instanci třídy Presentation.
with slides.Presentation() as pres:
    # Sem vložte kód pro manipulaci s prezentacemi.

# Po provedení změn prezentaci uložte.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Průvodce implementací
Po nastavení Aspose.Slides postupujte podle těchto kroků a přidejte do prezentace prstencový graf snímek po snímku.

### Vytvoření nové prezentace a přidání snímku
Začněte vytvořením instance `Presentation` třída:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # V tomto kontextu můžete otevírat nebo vytvářet snímky.
```

### Přidání prstencového grafu na první snímek
Otevřete první snímek a použijte `add_chart` metoda. Zadejte typ grafu jako `DOUGHNUT`, spolu s polohou a velikostí:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Konfigurace dat grafu
Vymazat existující data a nakonfigurovat nastavení, například skrýt legendu:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Přidávání sérií a kategorií
Přidejte více řad a kategorií pro prstencový graf. Zde je návod, jak vytvořit 15 řad se specifickými vlastnostmi:

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

Podobně přidejte kategorie:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Přidejte datové body pro každou sérii.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Přizpůsobte si vzhled každého datového bodu.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Nakonfigurujte nastavení popisků pro poslední sérii.
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

### Uložení prezentace
Nakonec uložte prezentaci do určeného adresáře:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Praktické aplikace
Prstencové grafy jsou všestranné a lze je použít v různých scénářích, například:
1. **Rozpočtové rozdělení**Zobrazení toho, jak různá oddělení využívají přidělené finanční prostředky.
2. **Analýza podílu na trhu**Porovnání tržního podílu konkurenčních produktů nebo společností.
3. **Výsledky průzkumu**Vizualizace odpovědí na otázky z průzkumu týkající se preferencí nebo úrovně spokojenosti.

## Úvahy o výkonu
Pro zajištění optimálního výkonu při používání Aspose.Slides:
- Minimalizujte využití paměti správnou likvidací objektů po použití.
- Prezentace načítajte do paměti pouze v nezbytných případech a co nejdříve je zavřete.
- Pokud pracujete s velkým počtem grafů, zvažte dávkové zpracování snímků.

## Závěr
Dodržováním tohoto návodu jste se naučili, jak vytvářet dynamické prstencové grafy pomocí knihovny Aspose.Slides pro Python. Tyto vizualizace mohou vylepšit vaše prezentace tím, že učiní data srozumitelnějšími a poutavějšími. Pokračujte v prozkoumávání funkcí knihovny, abyste si mohli grafy dále přizpůsobit a optimalizovat.

## Sekce Často kladených otázek
1. **Mohu používat Aspose.Slides bez zakoupení licence?**
   - Ano, můžete začít s bezplatnou zkušební licencí pro účely vyhodnocení.
2. **Jak změním barvy grafu v Aspose.Slides?**
   - Použijte `fill_format` vlastnost pro nastavení požadované barvy pro prvky grafu.
3. **Je možné exportovat grafy jako obrázky?**
   - Ano, snímky obsahující grafy můžete vykreslit do obrazových formátů pomocí vykreslovacích funkcí knihovny.
4. **Jaké jsou některé běžné problémy při přidávání grafů?**
   - Před uložením nebo zobrazením grafu se ujistěte, že jsou všechny datové body a kategorie správně přidány.
5. **Mohu integrovat Aspose.Slides s jinými knihovnami Pythonu?**
   - Rozhodně! Můžete ho použít spolu s knihovnami jako Pandas pro vylepšené možnosti manipulace s daty.

## Zdroje
- [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Stáhnout Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)
- [Bezplatná zkušební verze a dočasná licence](https://releases.aspose.com/slides/python-net/)
- [Fórum komunity Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}