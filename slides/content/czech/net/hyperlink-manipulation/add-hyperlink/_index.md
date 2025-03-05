---
title: Přidání hypertextových odkazů na snímky v .NET pomocí Aspose.Slides
linktitle: Přidat hypertextový odkaz na snímek
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se přidávat hypertextové odkazy na snímky aplikace PowerPoint pomocí Aspose.Slides for .NET. Vylepšete své prezentace interaktivními prvky.
type: docs
weight: 12
url: /cs/net/hyperlink-manipulation/add-hyperlink/
---

Ve světě digitálních prezentací je interaktivita klíčová. Přidáním hypertextových odkazů do snímků může být vaše prezentace poutavější a informativnější. Aspose.Slides for .NET je výkonná knihovna, která vám umožňuje programově vytvářet, upravovat a manipulovat s prezentacemi PowerPoint. V tomto tutoriálu vám ukážeme, jak přidat hypertextové odkazy na vaše snímky pomocí Aspose.Slides for .NET. 

## Předpoklady

Než se pustíme do přidávání hypertextových odkazů na snímky, ujistěte se, že máte splněny následující předpoklady:

1. Visual Studio: Abyste mohli psát a spouštět kód .NET, měli byste mít na svém počítači nainstalované Visual Studio.

2. Aspose.Slides for .NET: Musíte mít nainstalovanou knihovnu Aspose.Slides for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).

3. Základní znalost C#: Výhodou bude znalost programování v C#.

## Importovat jmenné prostory

Chcete-li začít, musíte do svého projektu C# importovat potřebné jmenné prostory. V tomto případě budete z knihovny Aspose.Slides vyžadovat následující jmenné prostory:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Nyní si rozdělme proces přidávání hypertextových odkazů na snímky do několika kroků.

## Krok 1: Inicializujte prezentaci

Nejprve vytvořte novou prezentaci pomocí Aspose.Slides. Můžete to udělat takto:

```csharp
using (Presentation presentation = new Presentation())
{
    // Váš kód je zde
}
```

Tento kód inicializuje novou prezentaci PowerPoint.

## Krok 2: Přidejte textový rámeček

Nyní do snímku přidáme textový rámeček. Tento textový rámeček bude sloužit jako klikací prvek ve vašem snímku. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Výše uvedený kód vytvoří obdélníkový automatický tvar a přidá textový rámeček s textem "Aspose: File Format APIs."

## Krok 3: Přidejte hypertextový odkaz

Dále přidáme hypertextový odkaz do textového rámečku, který jste vytvořili. Díky tomu bude text klikatelný.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

V tomto kroku nastavíme URL hypertextového odkazu na „https://www.aspose.com/“ a poskytneme nápovědu pro další informace. Můžete také formátovat vzhled hypertextového odkazu, jak je uvedeno výše.

## Krok 4: Uložte prezentaci

Nakonec prezentaci uložte s přidaným hypertextovým odkazem.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Tento kód uloží prezentaci jako "prezentace-out.pptx."

Nyní jste úspěšně přidali hypertextový odkaz na snímek pomocí Aspose.Slides for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak přidat hypertextové odkazy na snímky v prezentacích PowerPoint pomocí Aspose.Slides for .NET. Dodržením těchto kroků můžete své prezentace učinit interaktivnějšími a poutavějšími a poskytnout cenné odkazy na další zdroje nebo informace.

 Pro podrobnější informace a dokumentaci navštivte[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net/).

## Nejčastější dotazy

### 1. Mohu přidat hypertextové odkazy na jiné tvary kromě textových rámečků?

Ano, pomocí Aspose.Slides for .NET můžete přidávat hypertextové odkazy na různé tvary, jako jsou obdélníky, obrázky a další.

### 2. Jak mohu odstranit hypertextový odkaz z obrazce na snímku aplikace PowerPoint?

 Můžete odebrat hypertextový odkaz z tvaru nastavením`HyperlinkClick` majetek do`null`.

### 3. Mohu ve svém kódu dynamicky změnit adresu URL hypertextového odkazu?

 Absolutně! Adresu URL hypertextového odkazu můžete aktualizovat v libovolném bodě kódu úpravou souboru`Hyperlink` vlastnictví.

### 4. Jaké další interaktivní prvky mohu přidat do snímků PowerPoint pomocí Aspose.Slides?

Aspose.Slides nabízí širokou škálu interaktivních funkcí, včetně akčních tlačítek, multimediálních prvků a animací.

### 5. Je Aspose.Slides dostupný pro jiné programovací jazyky?

Ano, Aspose.Slides je k dispozici pro různé programovací jazyky, včetně Javy a Pythonu.