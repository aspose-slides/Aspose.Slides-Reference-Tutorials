---
"date": "2025-04-22"
"description": "Tanuld meg, hogyan jeleníthetsz meg könnyedén százalékos feliratokat a PowerPoint-bemutatók diagramjain az Aspose.Slides Pythonhoz segítségével. Tökéletes az adatvizualizáció fejlesztéséhez."
"title": "Százalékos címkék megjelenítése diagramokon az Aspose.Slides for Python használatával – Átfogó útmutató"
"url": "/hu/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan jelenítsünk meg százalékos címkéket diagramokon az Aspose.Slides for Python használatával

## Bevezetés

Az adatok hatékony vizualizációja kulcsfontosságú a prezentációkban és jelentésekben, különösen akkor, ha az arányokat vagy eloszlásokat egyértelműen ki szeretné emelni. De mi van akkor, ha ezeket a százalékokat közvetlenül a diagramokon kell megjelenítenie? Ez az átfogó útmutató végigvezeti Önt a használatán. **Aspose.Slides Pythonhoz** hogy a százalékos értékeket könnyedén feliratként jelenítse meg a diagramon.

### Amit tanulni fogsz:
- Hogyan hozhatok létre és ágyazhatok be diagramokat PowerPoint prezentációkba az Aspose.Slides for Python használatával.
- Adatpontok megjelenítése százalékos címkékként a diagramokon.
- PowerPoint prezentációk hatékony mentése és kezelése.

Készen állsz arra, hogy hasznos vizuális elemeket adj az adataidhoz? Először nézzük meg, mire van szükséged, mielőtt belevágnál a kódba!

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg róla, hogy a következőkkel rendelkezünk:
- **Aspose.Slides Pythonhoz**Ez a függvénykönyvtár elengedhetetlen a PowerPoint-bemutatók programozott létrehozásához és kezeléséhez.
- **Python környezet**A Python programozás és környezetbeállítás alapvető ismerete.
- **PIP csomagkezelő**Az Aspose.Slides telepítésére szolgál.

## Az Aspose.Slides beállítása Pythonhoz

Az Aspose.Slides használatának megkezdéséhez először telepítenie kell:

```bash
pip install aspose.slides
```

### Licenc megszerzésének lépései:
Ingyenes próbaverzióval kezdheted, vagy ideiglenes licencet szerezhetsz az Aspose.Slides teljes funkcionalitásának felfedezéséhez. Hosszabb távú használathoz érdemes előfizetést vásárolni.

#### Alapvető inicializálás és beállítás

A telepítés után a prezentációs környezetet a következőképpen kell inicializálni:

```python
import aspose.slides as slides

# Presentation objektum inicializálása
def create_presentation():
    with slides.Presentation() as presentation:
        # A kódod itt
```

## Megvalósítási útmutató

Most, hogy mindennel elkészültünk, nézzük meg a százalékok diagramokon való megjelenítését.

### Diagram létrehozása és adatok hozzáadása

#### Áttekintés
Létrehozunk egy halmozott oszlopdiagramot, amelyben minden adatponthoz százalékos címkék tartoznak, így a nézők egy pillantással láthatják a pontos arányokat.

##### 1. lépés: Diagram hozzáadása a diához

```python
# A prezentáció első diájának elérése
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Halmozott oszlopdiagram hozzáadása
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Ez a kódrészlet egy alapvető diagramot ad hozzá az első diához. A `add_chart` A metódus meghatározza a diagram típusát, pozícióját és méretét.

##### 2. lépés: Kategóriák teljes értékeinek kiszámítása

```python
def calculate_totals(chart):
    total_for_category = []
    # Összeadja az értékeket az összes sorozatban minden kategóriában
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Ez a ciklus kiszámítja az összes adatpont összegét az adatsorokon keresztül, ami kulcsfontosságú a százalékos számításokhoz.

#### Százalékos címkék beállítása

##### 3. lépés: Sorozat adatpontok konfigurálása

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Alapértelmezett címkebeállítások beállítása a nem létfontosságú információk elrejtéséhez
        series.labels.default_data_label_format.show_legend_key = False
        
        # Százalékos címkék kiszámítása és beállítása
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Hozz létre egy szövegrészt százalékos értékkel
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Törölje a meglévő címkéket, és adjon hozzá új százalékos címke
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Egyéb adatcímke-elemek elrejtése
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Ez a szegmens feldolgozza az egyes adatpontokat, kiszámítja az összesített érték százalékos arányát, és címkét rendel hozzájuk.

### A prezentáció mentése

```python
def save_presentation(presentation, output_directory):
    # Mentse el a prezentációt módosításokkal
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}