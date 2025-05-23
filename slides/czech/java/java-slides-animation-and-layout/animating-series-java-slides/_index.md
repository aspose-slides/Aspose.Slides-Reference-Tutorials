---
"description": "Optimalizujte své prezentace pomocí sériových animací v Aspose.Slides pro Javu. Postupujte podle našeho podrobného návodu s příklady zdrojového kódu a vytvořte poutavé animace v PowerPointu."
"linktitle": "Animace série v Javě - Slidy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Animace série v Javě - Slidy"
"url": "/cs/java/animation-and-layout/animating-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animace série v Javě - Slidy


## Úvod do animace sérií v Aspose.Slides pro Javu

V této příručce vás provedeme procesem animace sérií v Javě pomocí Aspose.Slides for Java API. Tato knihovna umožňuje programově pracovat s prezentacemi v PowerPointu.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Aspose.Slides pro knihovnu Java.
- Nastavení vývojového prostředí v Javě.

## Krok 1: Načtení prezentace

Nejprve musíme načíst existující prezentaci v PowerPointu, která obsahuje graf. Nahraďte `"Your Document Directory"` se skutečnou cestou k souboru prezentace.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation, která reprezentuje soubor prezentace 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## Krok 2: Přístup k grafu

Dále si otevřeme graf v prezentaci. V tomto příkladu předpokládáme, že graf je na prvním snímku a je prvním tvarem na tomto snímku.

```java
// Získání odkazu na objekt grafu
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## Krok 3: Přidání animací

Nyní přidáme animace k sériím v grafu. Použijeme efekt zeslabování a jednotlivé série se budou zobrazovat postupně.

```java
// Animace celého grafu
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Přidejte animace do každé série (za předpokladu, že jsou série 4)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

Ve výše uvedeném kódu používáme efekt zeslabování (fade-in) pro celý graf a poté pomocí smyčky přidáváme efekt „Objevení“ do každé série po sobě.

## Krok 4: Uložte prezentaci

Nakonec upravenou prezentaci uložte na disk.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro animaci seriálů v Aspose.Slides pro Javu

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation, která reprezentuje soubor prezentace 
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Získání odkazu na objekt grafu
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

Úspěšně jste animovali sérii v grafu PowerPointu pomocí Aspose.Slides pro Javu. Díky tomu mohou být vaše prezentace poutavější a vizuálně přitažlivější. Prozkoumejte další možnosti animací a podle potřeby dolaďte své prezentace.

## Často kladené otázky

### Jak mohu ovládat pořadí animací série?

Pro ovládání pořadí animací série použijte `EffectTriggerType.AfterPrevious` parametr při přidávání efektů. Díky tomu se každá animace série spustí až po skončení předchozí.

### Mohu na každou sérii použít různé animace?

Ano, na každou sérii můžete použít různé animace zadáním různých `EffectType` a `EffectSubtype` hodnoty při přidávání efektů.

### Co když má moje prezentace více než čtyři série?

Smyčku můžete v kroku 3 prodloužit a přidat animace pro všechny série v grafu. Stačí odpovídajícím způsobem upravit podmínku smyčky.

### Jak mohu přizpůsobit délku a zpoždění animace?

Délku a zpoždění animace můžete přizpůsobit nastavením vlastností animačních efektů. Podrobnosti o dostupných možnostech přizpůsobení naleznete v dokumentaci k Aspose.Slides pro Javu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}