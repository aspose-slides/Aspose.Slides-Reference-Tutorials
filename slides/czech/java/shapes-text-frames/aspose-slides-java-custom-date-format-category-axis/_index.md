---
"date": "2025-04-17"
"description": "Naučte se, jak přizpůsobit formáty data pro osy kategorií pomocí Aspose.Slides pro Javu. Vylepšete své grafy o vlastní prezentaci dat, ideální pro výroční zprávy a další."
"title": "Jak nastavit vlastní formát data na ose kategorií v Aspose.Slides v Javě | Průvodce vizualizací dat"
"url": "/cs/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak nastavit vlastní formát data na ose kategorií v Aspose.Slides v Javě | Průvodce vizualizací dat

V dnešním světě založeném na datech je srozumitelná prezentace informací klíčová pro efektivní rozhodování. Při vytváření grafů pomocí Aspose.Slides pro Javu může úprava formátu data na ose kategorií výrazně zlepšit jak porozumění, tak kvalitu prezentace. Tato příručka vás provede nastavením vlastního formátu data v Aspose.Slides, který vylepší vizuální atraktivitu vašich snímků a srozumitelnost dat.

**Co se naučíte:**
- Nastavení Aspose.Slides pro Javu
- Implementace vlastních formátů data na ose kategorií
- Převod dat GregorianCalendar do formátu data OLE Automation
- Praktické aplikace těchto funkcí v reálných situacích

Pojďme se ponořit do toho, jak toho můžete snadno dosáhnout!

## Předpoklady

Než začneme, ujistěte se, že jste splnili následující předpoklady:

### Požadované knihovny a verze:
- **Aspose.Slides pro Javu**Budete potřebovat verzi 25.4 nebo novější.

### Požadavky na nastavení prostředí:
- Vývojové prostředí schopné spouštět kód v Javě (například IntelliJ IDEA, Eclipse nebo NetBeans).
- Maven nebo Gradle nakonfigurované ve vašem projektu pro správu závislostí.

### Předpoklady znalostí:
- Základní znalost programování v Javě.
- Znalost používání grafických prvků v prezentacích.

## Nastavení Aspose.Slides pro Javu

Pro práci s Aspose.Slides pro Javu jej zahrňte jako závislost do svého projektu. Níže jsou uvedeny pokyny k instalaci:

**Znalec:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Případně můžete [stáhněte si nejnovější verzi](https://releases.aspose.com/slides/java/) přímo z oficiálních stránek Aspose.

### Získání licence:
- **Bezplatná zkušební verze**Začněte s bezplatnou zkušební verzí a prozkoumejte funkce.
- **Dočasná licence**Požádejte o dočasnou licenci pro prodloužené testování.
- **Nákup**Pro dlouhodobé užívání zvažte zakoupení předplatného. Navštivte [Nákup Aspose](https://purchase.aspose.com/buy) pro podrobnosti.

### Základní inicializace:

Zde je návod, jak inicializovat Aspose.Slides ve vašem projektu:
```java
import com.aspose.slides.Presentation;
// Vytvoření instance objektu Presentation, který představuje soubor prezentace.
Presentation pres = new Presentation();
```

A teď se přesuňme k jádru tohoto průvodce!

## Průvodce implementací

### Nastavení formátu data pro osu kategorií

Tato funkce vám umožňuje přizpůsobit způsob zobrazení dat na ose kategorií grafu. Níže je uveden podrobný návod:

#### 1. Vytvořte novou prezentaci a graf
Začněte vytvořením instance `Presentation` a přidání nového plošného grafu.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // Inicializovat prezentaci
        Presentation pres = new Presentation();
        
        try {
            // Přidat plošný graf na první snímek na zadané pozici a velikosti
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // Sešit s daty grafů v aplikaci Access pro manipulaci s daty grafů
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // Vymazat všechna existující data v grafu

            // Odstraňte všechny již existující kategorie a série
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // Přidání dat na osu kategorií pomocí převedených dat automatizace OLE
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // Vytvořte novou řadu a přidejte do ní datové body
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // Nastavte typ osy kategorií na Datum a nakonfigurujte její číselný formát
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // Formátovat data pouze jako rok

            // Uložit prezentaci do zadaného adresáře
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Základní datum pro konverzi automatizace OLE
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // Převést na datum automatizace OLE
        return String.valueOf(oaDate);
    }
}
```

#### 2. Převod data z GregorianCalendar do formátu data OLE Automation

Aspose.Slides vyžaduje data ve formátu OLE Automation, což je standardní formát data v Excelu. Zde je návod, jak převést data v Javě. `GregorianCalendar` data:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 15. ledna 2021
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Základní datum pro automatizaci OLE v Excelu
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### Tipy pro řešení problémů:
- Zajistěte základní datum pro konverzi (`30 Dec 1899`) je správně analyzován.
- Ověřte, zda vaše prostředí Java podporuje potřebné knihovny a třídy.
- Pokud se vyskytnou problémy, zkontrolujte, zda nejsou k dispozici nějaké aktualizace nebo záplaty pro Aspose.Slides.

### Praktické aplikace

Přizpůsobení formátů data může být obzvláště užitečné v situacích, jako jsou:
- **Výroční zprávy:** Jasné zobrazení ročních trendů dat.
- **Finanční grafy:** Přesné prezentování fiskálních období.
- **Harmonogramy projektu:** Zvýraznění konkrétních časových rámců nebo milníků.

Dodržováním tohoto návodu budete moci vylepšit své prezentace přesnými a vizuálně atraktivními formáty data pomocí Aspose.Slides pro Javu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}