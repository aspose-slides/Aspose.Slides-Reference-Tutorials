---
title: Nastavení osy polohy v Java Slides
linktitle: Nastavení osy polohy v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vylepšete své grafy pomocí Aspose.Slides pro Java. Naučte se, jak nastavit poziční osu na snímcích Java, vytvářet úžasné prezentace a snadno přizpůsobit rozvržení grafu.
weight: 16
url: /cs/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení osy polohy v Java Slides


## Úvod do nastavení osy polohy v Aspose.Slides pro Java

tomto tutoriálu se naučíme, jak nastavit poziční osu v grafu pomocí Aspose.Slides pro Java. Umístění osy může být užitečné, když chcete upravit vzhled a rozvržení grafu. Vytvoříme seskupený sloupcový graf a upravíme polohu vodorovné osy mezi kategoriemi.

## Předpoklady

 Než začneme, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvoření prezentace

Nejprve vytvořte novou prezentaci, se kterou budeme pracovat:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou k vašemu adresáři dokumentů.

## Krok 2: Přidání grafu

Dále na snímek přidáme seskupený sloupcový graf. Určujeme typ grafu, polohu (souřadnice x, y) a rozměry (šířku a výšku) grafu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Zde jsme přidali seskupený sloupcový graf na pozici (50, 50) o šířce 450 a výšce 300. Tyto hodnoty můžete upravit podle potřeby.

## Krok 3: Nastavení osy polohy

Chcete-li nastavit poziční osu mezi kategoriemi, můžete použít následující kód:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Tento kód nastavuje zobrazení vodorovné osy mezi kategoriemi, což může být užitečné pro určitá rozložení grafu.

## Krok 4: Uložení prezentace

Nakonec uložíme prezentaci s grafem:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Nahradit`"AsposeClusteredColumnChart.pptx"` s požadovaným názvem souboru.

A je to! Úspěšně jste vytvořili seskupený sloupcový graf a nastavili poziční osu mezi kategoriemi pomocí Aspose.Slides for Java.

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

V tomto tutoriálu jsme prozkoumali, jak nastavit poziční osu v grafu pomocí Aspose.Slides pro Java. Podle kroků uvedených v této příručce jste se naučili, jak vytvořit seskupený sloupcový graf a upravit jeho vzhled umístěním vodorovné osy mezi kategoriemi. Aspose.Slides for Java poskytuje výkonné funkce pro práci s grafy a prezentacemi, díky čemuž je cenným nástrojem pro vývojáře v jazyce Java.

## FAQ

### Jak si graf dále přizpůsobím?

Můžete přizpůsobit různé aspekty grafu, včetně datových řad, názvu grafu, legend a dalších. Odkazovat na[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) pro podrobné pokyny a příklady.

### Mohu změnit typ grafu?

 Ano, typ grafu můžete změnit úpravou`ChartType` parametr při přidávání grafu. Aspose.Slides for Java podporuje různé typy grafů, jako jsou sloupcové grafy, spojnicové grafy a další.

### Kde najdu další příklady a dokumentaci?

 Kompletní dokumentaci a další příklady naleznete na[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) strana.

Nezapomeňte zlikvidovat objekt prezentace, když s ním skončíte, abyste uvolnili systémové prostředky:

```java
if (pres != null) pres.dispose();
```

To je pro tento tutoriál vše. Naučili jste se, jak nastavit poziční osu v grafu pomocí Aspose.Slides for Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
