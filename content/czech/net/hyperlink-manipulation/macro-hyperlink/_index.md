---
title: Jak nastavit makro hypertextový odkaz Klikněte v Aspose.Slides pro .NET
linktitle: Správa hypertextových odkazů pomocí maker
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak nastavit makro hypertextové odkazy v prezentacích pomocí Aspose.Slides pro .NET. Vylepšete interaktivitu a zapojte své publikum.
type: docs
weight: 13
url: /cs/net/hyperlink-manipulation/macro-hyperlink/
---

Ve světě moderního vývoje softwaru je klíčovým aspektem vytváření dynamických a interaktivních prezentací. Aspose.Slides for .NET je výkonná knihovna, která vám umožní bezproblémově pracovat s prezentacemi. Ať už vytváříte obchodní prezentaci nebo vzdělávací slideshow, možnost nastavit makro kliknutí na hypertextový odkaz může výrazně zlepšit uživatelský zážitek. V tomto podrobném průvodci vás provedeme procesem nastavení kliknutí na makro hypertextový odkaz pomocí Aspose.Slides pro .NET. 

## Předpoklady

Než se ponoříme do podrobného tutoriálu, měli byste mít splněno několik předpokladů:

1.Visual Studio: Ujistěte se, že máte na svém počítači nainstalované Visual Studio, protože to bude naše vývojové prostředí.

 2.Apose.Slides for .NET: Budete muset mít nainstalovanou knihovnu Aspose.Slides for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).

3.Základní znalost C#: Znalost programovacího jazyka C# je nezbytná pro dodržení tohoto návodu.

## Importovat jmenné prostory

V prvním kroku naimportujeme potřebné jmenné prostory pro práci s Aspose.Slides:

### Krok 1: Import jmenných prostorů

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Dovezli jsme`Aspose.Slides` jmenný prostor, který je základním jmenným prostorem pro práci s prezentacemi, a`Aspose.Slides.Export` jmenný prostor.

## Nastavení makra Hypertextový odkaz Klikněte

Nyní přejdeme k hlavní části tohoto tutoriálu – nastavení kliknutí na makro hypertextový odkaz ve vaší prezentaci.

### Krok 2: Inicializujte prezentaci

Nejprve musíme inicializovat novou prezentaci.

```csharp
using (Presentation presentation = new Presentation())
{
    // Váš kód půjde sem.
}
```

rámci tohoto příkazu using vytvoříte nový objekt prezentace a provedete v něm všechny své operace.

### Krok 3: Přidejte automatický tvar

Chcete-li nastavit kliknutí na hypertextový odkaz makra, budete potřebovat objekt, na který může uživatel kliknout. V tomto příkladu použijeme jako klikací prvek automatický tvar.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Zde vytvoříme automatický tvar s typem "Prázdné tlačítko" na konkrétních souřadnicích (20, 20) a o rozměrech 80x30. Tyto hodnoty můžete přizpůsobit tak, aby vyhovovaly rozvržení vaší prezentace.

### Krok 4: Klepněte na hypertextový odkaz na makro

Nyní přichází část, kde nastavíte kliknutí na makro hypertextový odkaz. Jako parametr budete muset zadat název makra.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

V tomto příkladu jsme nastavili kliknutí na hypertextový odkaz makra na "TestMacro". Když uživatel klikne na automatický tvar, spustí se toto makro.

### Krok 5: Získejte informace

Můžete také získat informace o hypertextovém odkazu, který jste nastavili.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Tyto řádky kódu umožňují vytisknout externí adresu URL a typ akce hypertextového odkazu.

A to je vše! Úspěšně jste nastavili makro kliknutím na hypertextový odkaz ve vaší prezentaci pomocí Aspose.Slides pro .NET.

## Závěr

V tomto tutoriálu jsme se naučili, jak nastavit makro kliknutí na hypertextový odkaz v prezentaci pomocí Aspose.Slides pro .NET. To může být cenná funkce pro vytváření interaktivních a dynamických prezentací, které zaujmou vaše publikum. S Aspose.Slides pro .NET máte k dispozici výkonný nástroj, který posune vývoj vašich prezentací na další úroveň.

 Nyní je čas, abyste experimentovali a vytvořili poutavé prezentace s vlastními hypertextovými odkazy na makro. Neváhejte a prozkoumejte[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net/) pro podrobnější informace a možnosti.

## Často kladené otázky (FAQ)

### Mohu používat Aspose.Slides pro .NET s jinými programovacími jazyky?
Aspose.Slides je primárně navržen pro .NET, ale Aspose nabízí podobné knihovny pro jiné programovací jazyky, jako je Java.

### Je Aspose.Slides for .NET bezplatná knihovna?
Aspose.Slides for .NET je komerční knihovna s bezplatnou zkušební verzí. Můžete si jej stáhnout z[tady](https://releases.aspose.com/).

### Existují nějaká omezení pro použití maker v prezentacích vytvořených pomocí Aspose.Slides pro .NET?
Aspose.Slides for .NET vám umožňuje pracovat s makry, ale při používání maker v prezentacích byste si měli být vědomi aspektů bezpečnosti a kompatibility.

### Mohu upravit vzhled automatického tvaru použitého pro hypertextový odkaz?
Ano, vzhled automatického tvaru můžete upravit úpravou jeho vlastností, jako je velikost, barva a písmo.

### Kde mohu získat pomoc nebo podporu pro Aspose.Slides pro .NET?
 Pokud narazíte na problémy nebo máte dotazy, můžete vyhledat pomoc na fóru podpory Aspose[tady](https://forum.aspose.com/).