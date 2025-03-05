---
title: Animační série v Java Slides
linktitle: Animační série v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Optimalizujte své prezentace pomocí animací série v Aspose.Slides pro Java. Postupujte podle našeho podrobného průvodce s příklady zdrojového kódu a vytvořte poutavé animace PowerPoint.
type: docs
weight: 11
url: /cs/java/animation-and-layout/animating-series-java-slides/
---

## Úvod do Animace Series v Aspose.Slides pro Java

V této příručce vás provedeme procesem animace sérií na snímcích Java pomocí Aspose.Slides for Java API. Tato knihovna umožňuje programově pracovat s prezentacemi PowerPoint.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Aspose.Slides pro knihovnu Java.
- Nastavení vývojového prostředí Java.

## Krok 1: Načtěte prezentaci

 Nejprve musíme načíst existující PowerPoint prezentaci, která obsahuje graf. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Instantiate Prezentační třída, která představuje soubor prezentace
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## Krok 2: Přístup k grafu

Dále se dostaneme k grafu v rámci prezentace. V tomto příkladu předpokládáme, že graf je na prvním snímku a je prvním obrazcem na tomto snímku.

```java
// Získejte odkaz na objekt grafu
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## Krok 3: Přidejte animace

Nyní přidejte animace do série v grafu. Použijeme efekt roztmívání a zajistíme, aby se každá série zobrazovala jedna po druhé.

```java
// Animujte celý graf
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Přidejte animace do každé série (za předpokladu, že existují 4 série)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

Ve výše uvedeném kódu používáme efekt fade-in pro celý graf a poté pomocí smyčky přidáme efekt "Objevit se" ke každé sérii jeden po druhém.

## Krok 4: Uložte prezentaci

Nakonec upravenou prezentaci uložte na disk.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro animované série v Aspose.Slides pro Javu

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Instantiate Prezentační třída, která představuje soubor prezentace
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Získejte odkaz na objekt grafu
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Animujte seriál
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Zapište upravenou prezentaci na disk
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

Úspěšně jste animovali sérii v grafu PowerPoint pomocí Aspose.Slides pro Java. Vaše prezentace tak mohou být poutavější a vizuálně přitažlivější. Prozkoumejte další možnosti animace a dolaďte své prezentace podle potřeby.

## FAQ

### Jak mohu ovládat pořadí animací série?

 Chcete-li ovládat pořadí animací série, použijte`EffectTriggerType.AfterPrevious` parametr při přidávání efektů. To způsobí, že každá animace série začne poté, co skončí předchozí.

### Mohu na každou sérii použít různé animace?

 Ano, na každou sérii můžete použít různé animace zadáním jiných`EffectType` a`EffectSubtype` hodnoty při přidávání efektů.

### Co když má moje prezentace více než čtyři série?

V kroku 3 můžete prodloužit smyčku a přidat animace pro všechny řady v grafu. Stačí podle toho upravit stav smyčky.

### Jak mohu přizpůsobit trvání a zpoždění animace?

Dobu trvání animace a zpoždění můžete přizpůsobit nastavením vlastností efektů animace. Podrobnosti o dostupných možnostech přizpůsobení najdete v dokumentaci Aspose.Slides for Java.