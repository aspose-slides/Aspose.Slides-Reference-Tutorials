---
"date": "2025-04-23"
"description": "Tanuld meg, hogyan állíthatod be a diagramcímek elforgatási szögét a prezentációkban az Aspose.Slides Pythonhoz használatával, javítva az olvashatóságot és az esztétikát."
"title": "Hogyan állítsuk be egy diagram függőleges tengelyének címforgatását az Aspose.Slides Pythonban"
"url": "/hu/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan állítsuk be egy diagram függőleges tengelyének címforgatását az Aspose.Slides Pythonban

## Bevezetés

Az adatprezentációkban a diagramok olvashatóságának javítása kulcsfontosságú. Az Aspose.Slides Pythonhoz készült verziójával a diagram függőleges tengelyének címének elforgatási szögének módosításával a címek szépen illeszkedhetnek vagy kiemelkedhetnek a diákon. Ez az oktatóanyag végigvezet az elforgatási szög beállításán, hogy javítsa mind a funkcionalitást, mind a vizuális megjelenést.

**Amit tanulni fogsz:**
- Az Aspose.Slides telepítése és konfigurálása Pythonhoz.
- Lépések diagramok hozzáadásához és testreszabásához a diákon belül.
- Diagramcímek elforgatási szögének beállítására szolgáló technikák.
- Valós alkalmazások ezekhez a funkciókhoz az adatvizualizációban.

Kezdjük az előfeltételek áttekintésével, mielőtt belevágnánk a megvalósításba.

## Előfeltételek

Kezdés előtt győződjön meg arról, hogy rendelkezik a következőkkel:
- **Python környezet**Telepítse a Python 3.x-et innen: [python.org](https://www.python.org/).
- **Aspose.Slides könyvtár**Telepítés pip-en keresztül a prezentációk hatékony kezeléséhez.
- **Python programozási alapismeretek**A Python szintaxisának és fájlműveleteinek ismerete segíteni fog a haladásban.

## Az Aspose.Slides beállítása Pythonhoz

Az Aspose.Slides használatához telepítsd a pip paranccsal. Nyisd meg a terminált vagy a parancssort, és futtasd a következőt:

```bash
pip install aspose.slides
```

### Licencbeszerzés lépései

Az Aspose különböző licencelési lehetőségeket kínál:
- **Ingyenes próbaverzió**: Tölts le egy próbaverziót innen: [Az Aspose kiadási oldala](https://releases.aspose.com/slides/python-net/).
- **Ideiglenes engedély**: Szerezzen be ideiglenes licencet a kibővített funkciókhoz a következő címen: [vásárlási portál](https://purchase.aspose.com/temporary-license/).
- **Vásárlás**: Érdemes megfontolni a megvásárlását, ha nélkülözhetetlennek találja az eszközt, és beszerezhető a [Aspose vásárlási oldal](https://purchase.aspose.com/buy).

#### Alapvető inicializálás és beállítás

Így inicializálhatod az Aspose.Slides-t a Python szkriptedben:

```python
import aspose.slides as slides

# Bemutató objektum létrehozása
def main():
    with slides.Presentation() as pres:
        # A kódod ide fog kerülni
        pass

if __name__ == "__main__":
    main()
```

## Megvalósítási útmutató

### Diagramok hozzáadása és testreszabása

#### Áttekintés

Ebben a szakaszban egy csoportos oszlopdiagramot adunk a diához, és testreszabjuk a függőleges tengely címének elforgatási szögének beállításával.

#### Lépések:

##### 1. lépés: Fürtözött oszlopdiagram hozzáadása

Kezdésként adj hozzá egy diagramot adott koordinátákon, meghatározott méretekkel:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Csoportos oszlopdiagram hozzáadása az 1. diához
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### 2. lépés: A függőleges tengely címének konfigurálása

Engedélyezze és állítsa be a függőleges tengely címének elforgatási szögét:

```python
def configure_chart(chart):
    # Függőleges tengely címének engedélyezése
    chart.axes.vertical_axis.has_title = True
    
    # Állítsd be a forgási szöget 90 fokra
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### 3. lépés: Mentse el a prezentációját

Végül mentsd el a prezentációdat a módosításokkal:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Mentse el a prezentációt
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}