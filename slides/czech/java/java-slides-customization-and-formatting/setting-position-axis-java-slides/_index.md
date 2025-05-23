---
"description": "Vylepšete své grafy s Aspose.Slides pro Javu. Naučte se, jak nastavit osu pozice v slidech v Javě, vytvářet úžasné prezentace a snadno přizpůsobovat rozvržení grafů."
"linktitle": "Nastavení osy pozice v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení osy pozice v Javě Slides"
"url": "/cs/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení osy pozice v Javě Slides


## Úvod do nastavení osy pozice v Aspose.Slides pro Javu

tomto tutoriálu se naučíme, jak nastavit osu polohy v grafu pomocí Aspose.Slides pro Javu. Umístění osy může být užitečné, pokud chcete přizpůsobit vzhled a rozvržení grafu. Vytvoříme klastrovaný sloupcový graf a upravíme polohu vodorovné osy mezi kategoriemi.

## Předpoklady

Než začneme, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvoření prezentace

Nejprve si vytvořme novou prezentaci, se kterou budeme pracovat:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Nezapomeňte vyměnit `"Your Document Directory"` se skutečnou cestou k adresáři dokumentů.

## Krok 2: Přidání grafu

Dále na snímek přidáme shlukový sloupcový graf. Určíme typ grafu, jeho polohu (souřadnice x, y) a rozměry (šířku a výšku):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Zde jsme na pozici (50, 50) přidali klastrovaný sloupcový graf o šířce 450 a výšce 300. Tyto hodnoty můžete podle potřeby upravit.

## Krok 3: Nastavení polohy osy

Pro nastavení osy pozice mezi kategoriemi můžete použít následující kód:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Tento kód nastaví vodorovnou osu pro zobrazení mezi kategoriemi, což může být užitečné pro určitá rozvržení grafu.

## Krok 4: Uložení prezentace

Nakonec uložme prezentaci s grafem:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

Nahradit `"AsposeClusteredColumnChart.pptx"` s požadovaným názvem souboru.

To je vše! Úspěšně jste vytvořili klastrovaný sloupcový graf a nastavili osu pozice mezi kategoriemi pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

tomto tutoriálu jsme prozkoumali, jak nastavit osu pozice v grafu pomocí Aspose.Slides pro Javu. Postupováním podle kroků popsaných v této příručce jste se naučili, jak vytvořit klastrovaný sloupcový graf a přizpůsobit jeho vzhled umístěním vodorovné osy mezi kategoriemi. Aspose.Slides pro Javu poskytuje výkonné funkce pro práci s grafy a prezentacemi, což z něj činí cenný nástroj pro vývojáře v Javě.

## Často kladené otázky

### Jak mohu graf dále přizpůsobit?

Můžete si přizpůsobit různé aspekty grafu, včetně datových řad, názvu grafu, legend a dalších. Viz [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/) pro podrobné pokyny a příklady.

### Mohu změnit typ grafu?

Ano, typ grafu můžete změnit úpravou `ChartType` parametr při přidávání grafu. Aspose.Slides pro Javu podporuje různé typy grafů, jako jsou sloupcové grafy, spojnicové grafy a další.

### Kde najdu další příklady a dokumentaci?

Podrobnou dokumentaci a další příklady naleznete na [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/) strana.

Nezapomeňte po dokončení práce s prezentačním objektem odstranit, abyste uvolnili systémové prostředky:

```java
if (pres != null) pres.dispose();
```

To je pro tento tutoriál vše. Naučili jste se, jak nastavit osu pozice v grafu pomocí Aspose.Slides pro Javu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}