---
"description": "Naučte se, jak nastavit makro hypertextové odkazy ve vašich prezentacích pomocí Aspose.Slides pro .NET. Vylepšete interaktivitu a zaujměte své publikum."
"linktitle": "Správa hypertextových odkazů pomocí maker"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Jak nastavit makro pro kliknutí na hypertextový odkaz v Aspose.Slides pro .NET"
"url": "/cs/net/hyperlink-manipulation/macro-hyperlink/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit makro pro kliknutí na hypertextový odkaz v Aspose.Slides pro .NET


Ve světě moderního vývoje softwaru je vytváření dynamických a interaktivních prezentací klíčovým aspektem. Aspose.Slides pro .NET je výkonná knihovna, která vám umožňuje bezproblémově pracovat s prezentacemi. Ať už vytváříte firemní prezentaci nebo vzdělávací prezentaci, možnost nastavit kliknutí na makro hypertextové odkazy může výrazně vylepšit uživatelský zážitek. V tomto podrobném návodu vás provedeme procesem nastavení kliknutí na makro hypertextové odkazy pomocí Aspose.Slides pro .NET. 

## Předpoklady

Než se ponoříme do podrobného tutoriálu, měli byste mít splněno několik předpokladů:

1. Visual Studio: Ujistěte se, že máte na počítači nainstalované Visual Studio, protože to bude naše vývojové prostředí.

2. Aspose.Slides pro .NET: Budete potřebovat nainstalovanou knihovnu Aspose.Slides pro .NET. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/net/).

3. Základní znalost jazyka C#: Znalost programovacího jazyka C# je nezbytná pro absolvování tohoto tutoriálu.

## Importovat jmenné prostory

V prvním kroku importujme potřebné jmenné prostory pro práci s Aspose.Slides:

### Krok 1: Import jmenných prostorů

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Importovali jsme `Aspose.Slides` jmenný prostor, což je základní jmenný prostor pro práci s prezentacemi, a `Aspose.Slides.Export` jmenný prostor.

## Nastavení makra Kliknutí na hypertextový odkaz

Nyní se přesuňme k hlavní části tohoto tutoriálu – nastavení makra hypertextového odkazu „kliknutí“ ve vaší prezentaci.

### Krok 2: Inicializace prezentace

Nejprve musíme inicializovat novou prezentaci.

```csharp
using (Presentation presentation = new Presentation())
{
    // Váš kód bude zde.
}
```

V rámci tohoto příkazu using vytvoříte nový prezentační objekt a provedete všechny operace uvnitř něj.

### Krok 3: Přidání automatického tvaru

Chcete-li nastavit makro pro kliknutí na hypertextový odkaz, budete potřebovat objekt, na který může uživatel kliknout. V tomto příkladu použijeme jako klikatelný prvek automatický tvar.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Zde vytvoříme automatický tvar typu „PrázdnéTlačítko“ na specifických souřadnicích (20, 20) a s rozměry 80x30. Tyto hodnoty můžete upravit tak, aby odpovídaly rozvržení vaší prezentace.

### Krok 4: Nastavení makra pro hypertextový odkaz Kliknutí

Nyní přichází část, kde nastavíte makro hypertextový odkaz kliknutí. Jako parametr budete muset zadat název makra.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

V tomto příkladu jsme nastavili makro hypertextový odkaz click na „TestMacro“. Když uživatel klikne na automatický tvar, toto makro se spustí.

### Krok 5: Získání informací

Můžete také načíst informace o nastaveném hypertextovém odkazu.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Tyto řádky kódu umožňují vypsat externí URL a typ akce hypertextového odkazu.

A to je vše! Úspěšně jste nastavili makro hypertextový odkaz kliknutí ve vaší prezentaci pomocí Aspose.Slides pro .NET.

## Závěr

V tomto tutoriálu jsme se naučili, jak nastavit makro pro kliknutí na hypertextový odkaz v prezentaci pomocí Aspose.Slides pro .NET. To může být cenná funkce pro vytváření interaktivních a dynamických prezentací, které zaujmou vaše publikum. S Aspose.Slides pro .NET máte k dispozici výkonný nástroj, který posune vývoj vašich prezentací na další úroveň.

Nyní je čas experimentovat a vytvářet poutavé prezentace s vlastními makro hypertextovými odkazy. Neváhejte a prozkoumejte [Dokumentace k Aspose.Slides pro .NET](https://reference.aspose.com/slides/net/) pro podrobnější informace a možnosti.

## Často kladené otázky (FAQ)

### Mohu používat Aspose.Slides pro .NET s jinými programovacími jazyky?
Aspose.Slides je primárně navržen pro .NET, ale Aspose nabízí podobné knihovny i pro jiné programovací jazyky, například Java.

### Je Aspose.Slides pro .NET bezplatná knihovna?
Aspose.Slides pro .NET je komerční knihovna s bezplatnou zkušební verzí. Můžete si ji stáhnout z [zde](https://releases.aspose.com/).

### Existují nějaká omezení pro používání maker v prezentacích vytvořených pomocí Aspose.Slides pro .NET?
Aspose.Slides pro .NET umožňuje pracovat s makry, ale při jejich používání v prezentacích byste si měli být vědomi bezpečnostních a kompatibilitních aspektů.

### Mohu si přizpůsobit vzhled automatického tvaru použitého pro hypertextový odkaz?
Ano, vzhled automatického tvaru můžete přizpůsobit úpravou jeho vlastností, jako je velikost, barva a písmo.

### Kde mohu získat pomoc nebo podporu pro Aspose.Slides pro .NET?
Pokud narazíte na problémy nebo máte dotazy, můžete vyhledat pomoc na fóru podpory Aspose. [zde](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}