---
"date": "2025-04-15"
"description": "Tanulja meg, hogyan hozhat létre dinamikus és vizuálisan vonzó fánkdiagramokat PowerPoint-bemutatókban a hatékony Aspose.Slides for .NET könyvtár segítségével."
"title": "Hogyan készítsünk fánkdiagramot PowerPointban az Aspose.Slides for .NET használatával"
"url": "/hu/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan készítsünk fánkdiagramot PowerPointban az Aspose.Slides for .NET használatával
A vizuálisan lebilincselő diagramok készítése elengedhetetlen a hatékony adatprezentációhoz. A fánkdiagramok tökéletesek egy egész részeinek szemléltetésére, így ideálisak a százalékos alapú adatvizualizációhoz. Ez az oktatóanyag végigvezeti Önt egy dinamikus fánkdiagram létrehozásán PowerPointban a hatékony Aspose.Slides for .NET könyvtár használatával.

## Bevezetés
prezentációk gyakran igénylik az összetett adathalmazok vizuális ábrázolását, ahol a hagyományos sáv- vagy vonaldiagramok nem feltétlenül elegendőek. A fánkdiagram sokoldalú eszközként jelenik meg a százalékos alapú adatok stílusos és érthető módon történő hatékony közvetítésében. Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan egyszerűsíti az Aspose.Slides for .NET ezen diagramok létrehozásának folyamatát közvetlenül a PowerPointban.

**Amit tanulni fogsz:**
- Az Aspose.Slides beállítása .NET-hez
- Lépésről lépésre útmutató fánkdiagram létrehozásához
- Sorozatok és kategóriák hozzáadása a diagramhoz
- Adatcímkék konfigurálása a jobb áttekinthetőség érdekében
- A végleges prezentáció mentése

Merüljünk el abban, hogyan használhatod az Aspose.Slides for .NET-et a prezentációid egyéni fánkdiagramokkal való kiegészítéséhez.

## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg róla, hogy a következők megvannak:
- **Aspose.Slides .NET könyvtárhoz**Elérhető NuGet-en keresztül vagy közvetlenül letölthető.
- **Fejlesztői környezet**.NET projektekhez a Visual Studio ajánlott.
- C# alapismeretek és a PowerPoint felépítésének ismerete.

## Az Aspose.Slides beállítása .NET-hez
Diagramok létrehozásának megkezdéséhez először be kell állítania az Aspose.Slides könyvtárat a projektjében. Íme néhány módszer a telepítésére:

**.NET parancssori felület használata:**

```bash
dotnet add package Aspose.Slides
```

**A csomagkezelő konzol használata:**

```powershell
Install-Package Aspose.Slides
```

**A NuGet csomagkezelő felhasználói felületén keresztül:**
Keresd meg az „Aspose.Slides” fájlt, és telepítsd a legújabb verziót.

A telepítés után elkezdheti a projekt beállítását. Ha még nem ismeri az Aspose.Slides-t, érdemes lehet ideiglenes licencet vagy ingyenes próbaverziót beszereznie, hogy korlátozások nélkül felfedezhesse a program összes funkcióját.

### Projekt inicializálása
Így inicializálhatod az Aspose.Slides-t az alkalmazásodban:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Hozz létre egy példányt a Presentation osztályból
        Presentation presentation = new Presentation();
        
        // Ide kerül a prezentáció manipulálásához szükséges kód.
        
        // Mentse el a prezentációt
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Megvalósítási útmutató
### Fánkdiagram létrehozása
#### Áttekintés
Először egy üres fánkdiagramot fogunk létrehozni egy PowerPoint dián. Ez szolgál alapul az adatok hozzáadásához és a megjelenésének testreszabásához.

**1. lépés: Fánkdiagram hozzáadása**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Fánkdiagram hozzáadása az első diához a (10, 10) pozícióban, (500, 500) méretben.
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Meglévő sorozatok és kategóriák törlése
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // A jelmagyarázat letiltása a letisztultabb megjelenés érdekében
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Magyarázat:**
- **hozzáadásdiagram**: Új fánkdiagramot szúr be a diára.
- **getChartDataWorkbook**: Hozzáférést biztosít a diagram adatcelláihoz a kezelésükhöz.

### Sorozatok és kategóriák hozzáadása
#### Áttekintés
Ezután értelmes adatokkal töltjük fel a diagramot sorozatok és kategóriák hozzáadásával.

**2. lépés: Adatsorok hozzáadása**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Sorozat hozzáadása
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // A fánklyuk és a kezdőszög testreszabása
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Kategóriák hozzáadása
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Az adatpont kitöltésének és vonalának formázása
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Magyarázat:**
- **hozzáadás**: Új sorozatokat és kategóriákat szúr be a diagramba.
- **FánkLyukMéret beállítása**A fánk lyukának méretét konfigurálja, fokozva annak vizuális vonzerejét.

### Adatcímkék konfigurálása
#### Áttekintés
Az adatcímkék kontextust biztosítanak a diagram adataihoz. Javítsuk az olvashatóságot testreszabásukkal.

**3. lépés: Adatcímkék testreszabása**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Adatcímkék testreszabása
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Magyarázat:**
- **IDataLabel**: Testreszabja az adatcímkéket az áttekinthetőség és a megjelenítés érdekében.
- **KözépsőText beállítása**, **százalékos arány megjelenítése**: A címke olvashatóságának javítása a szöveg középre igazításával és százalékos értékek megjelenítésével.

## Következtetés
Az útmutató követésével megtanultad, hogyan hozhatsz létre dinamikus fánkdiagramot PowerPointban az Aspose.Slides for .NET használatával. Ez a hatékony függvénytár széleskörű testreszabási lehetőségeket kínál, így a diagramokat pontosan a prezentációs igényeidhez igazíthatod.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}