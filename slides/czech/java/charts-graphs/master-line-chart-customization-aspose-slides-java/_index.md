---
"date": "2025-04-17"
"description": "Naučte se, jak vytvářet a upravovat spojnicové grafy v Javě pomocí Aspose.Slides. Tato příručka se zabývá prvky grafu, značkami, popisky a styly pro profesionální prezentace."
"title": "Přizpůsobení hlavního spojnicového grafu v Javě pomocí Aspose.Slides"
"url": "/cs/java/charts-graphs/master-line-chart-customization-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Zvládnutí úpravy spojnicových grafů v Javě s Aspose.Slides

## Zavedení

Vytváření profesionálních prezentací, které kombinují srozumitelnost dat s vizuální přitažlivostí, může být náročné, zejména při úpravě spojnicových grafů v aplikacích Java. Tato příručka vám pomůže zvládnout používání nástroje „Aspose.Slides for Java“ pro snadné vytváření a úpravu spojnicových grafů. Naučíte se, jak vylepšit prvky grafu, jako jsou názvy, legendy, osy, značky, popisky, barvy, styly a další.

**Co se naučíte:**
- Vytvořte spojnicový graf pomocí Aspose.Slides pro Javu
- Přizpůsobení prvků grafu, jako je název, legenda a osy
- Úprava značek, popisků, barev a stylů čar v sérii
- Uložte prezentaci se všemi úpravami

Než se do toho pustíme, ujistěte se, že máte vše připravené k zahájení.

## Předpoklady

Abyste mohli pokračovat, ujistěte se, že máte:

- **Požadované knihovny:** Pro Javu potřebujete Aspose.Slides. Doporučujeme verzi 25.4.
- **Nastavení prostředí:** Vaše prostředí Java by mělo být správně nakonfigurováno s JDK16 nebo novějším.
- **Předpoklady znalostí:** Znalost programování v Javě a základních konceptů tvorby grafů bude užitečná.

## Nastavení Aspose.Slides pro Javu

Začněte integrací Aspose.Slides do svého projektu. Zde je návod, jak to provést pomocí různých nástrojů pro sestavení:

### Znalec
Přidejte tuto závislost do svého `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Zahrňte to do svého `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Nebo si stáhněte nejnovější verzi z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

#### Získání licence
- **Bezplatná zkušební verze:** Začněte s bezplatnou zkušební verzí a prozkoumejte funkce.
- **Dočasná licence:** Získejte dočasnou licenci pro plný přístup bez omezení.
- **Nákup:** Zvažte zakoupení licence pro trvalé používání.

Inicializujte prostředí nastavením Aspose.Slides a ujistěte se, že je knihovna ve vašem projektu správně nakonfigurována.

## Průvodce implementací

Pojďme si rozebrat proces vytváření a úpravy spojnicových grafů pomocí Aspose.Slides pro Javu do samostatných funkcí.

### Vytvoření a konfigurace spojnicového grafu

#### Přehled
Začněte přidáním nového snímku do prezentace a vložením spojnicového grafu se značkami.

```java
import com.aspose.slides.*;

// Inicializace třídy Presentation
class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            // Přístup k prvnímu snímku
            ISlide slide = pres.getSlides().get_Item(0);
            
            // Přidání spojnicového grafu se značkami
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento kód inicializuje prezentaci a přidá spojnicový graf na první snímek. Parametry určují typ grafu a jeho pozici na snímku.

### Skrýt název grafu

#### Přehled
Někdy lze odstraněním názvu grafu dosáhnout čistšího vzhledu.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Skrýt název grafu
            chart.getTitleFormat().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento úryvek skryje název grafu nastavením jeho viditelnosti na hodnotu false.

### Skrýt osy hodnot a kategorií

#### Přehled
Pro minimalistický design můžete chtít skrýt obě osy.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Skrýt svislé a vodorovné osy
            chart.getAxes().getVerticalAxis().setVisible(false);
            chart.getAxes().getHorizontalAxis().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento kód nastaví viditelnost obou os na hodnotu false.

### Skrýt legendu grafu

#### Přehled
Odeberte legendu, abyste se mohli zaměřit na samotná data.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Skrýt legendu
            chart.setHasLegend(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento úryvek skryje legendu grafu.

### Skrýt hlavní čáry mřížky na vodorovné ose

#### Přehled
Pro čistší vzhled odstraňte hlavní čáry mřížky.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Nastavit hlavní čáry mřížky na „Bez výplně“
            chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat()
                .getLine().getFillFormat().setFillType(FillType.NoFill);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento kód skryje hlavní čáry mřížky nastavením jejich typu výplně na `NoFill`.

### Odebrat všechny série z grafu

#### Přehled
Vymažte všechny datové řady pro nový začátek.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Odebrat všechny série z grafu
            for (int i = chart.getChartData().getSeries().size() - 1; i >= 0; i--) {
                chart.getChartData().getSeries().removeAt(i);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento úryvek odstraní z grafu všechny existující řady.

### Konfigurace značek a popisků řad

#### Přehled
Přizpůsobte si značky a popisky dat pro lepší reprezentaci dat.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Konfigurace značek a popisků pro první sérii
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "A1", "Sample Series"), chart.getType());
            series.getMarkerStyleType() = MarkerStyleType.Circle;
            for (int i = 0; i < series.getDataPoints().size(); i++) {
                IDataLabel lbl = series.getDataPoints().get_Item(i).getDataPointLevels().get(0).getLabel();
                lbl.getDataLabelFormat().setShowValue(true);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento kód konfiguruje značky a popisky pro řadu v grafu.

### Uložte si prezentaci

Po provedení všech úprav uložte prezentaci, aby se změny zachovaly.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Přizpůsobte si graf...

            // Uložit prezentaci
            pres.save("CustomizedLineChart.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Tento kód uloží vaši upravenou prezentaci jako soubor PPTX.

## Závěr

Dodržováním tohoto návodu můžete efektivně používat Aspose.Slides pro Javu k vytváření a úpravě spojnicových grafů ve vašich prezentacích. Experimentujte s různými prvky a styly grafů, abyste vylepšili vizuální atraktivitu vašich dat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}