---
title: Animovat sérii grafů s Aspose.Slides pro .NET
linktitle: Animace série v grafu
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se animovat řady grafů pomocí Aspose.Slides pro .NET. Zaujměte své publikum dynamickými prezentacemi. Začněte hned!
type: docs
weight: 12
url: /cs/net/chart-formatting-and-animation/animating-series/
---

Chcete svým prezentacím dodat šmrnc pomocí animovaných grafů? Aspose.Slides pro .NET je tu, aby vaše grafy ožily. V tomto podrobném průvodci vám ukážeme, jak animovat řady v grafu pomocí Aspose.Slides pro .NET. Než se ale vrhneme do akce, pojďme si pokrýt předpoklady.

## Předpoklady

Chcete-li úspěšně animovat řady v grafu pomocí Aspose.Slides pro .NET, budete potřebovat následující:

### 1. Aspose.Slides pro knihovnu .NET

 Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides for .NET. Pokud jste tak ještě neučinili, můžete si jej stáhnout z[Web Aspose.Slides for .NET](https://releases.aspose.com/slides/net/).

### 2. Stávající prezentace s grafem

Připravte si PowerPointovou prezentaci (PPTX) s existujícím grafem, který chcete animovat.

Nyní, když máme pokryty předpoklady, rozdělíme proces do série kroků k animaci řady grafů.


## Krok 1: Importujte potřebné jmenné prostory

Chcete-li pracovat s Aspose.Slides pro .NET, budete muset do svého kódu C# importovat požadované jmenné prostory:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Krok 2: Načtěte existující prezentaci

V tomto kroku načtěte existující PowerPoint prezentaci (PPTX), která obsahuje graf, který chcete animovat.

```csharp
// Cesta k adresáři dokumentů
string dataDir = "Your Document Directory";

// Instantiate Prezentační třída, která představuje soubor prezentace
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Váš kód je zde
}
```

## Krok 3: Získejte odkaz na objekt grafu

Chcete-li v prezentaci pracovat s grafem, musíte získat odkaz na objekt grafu:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Krok 4: Animujte sérii

Nyní je čas přidat do série grafů efekty animace. Do celého grafu přidáme efekt roztmívání a každou řadu zobrazíme jednu po druhé.

```csharp
// Animujte graf
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Ke každé sérii přidejte animaci
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Krok 5: Uložte upravenou prezentaci

Jakmile do grafu přidáte efekty animace, uložte upravenou prezentaci na disk.

```csharp
//Uložte upravenou prezentaci
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste animovali série v grafu pomocí Aspose.Slides pro .NET.

## Závěr

V tomto tutoriálu jsme vás provedli procesem animace série v grafu pomocí Aspose.Slides pro .NET. Pomocí této výkonné knihovny můžete vytvářet poutavé a dynamické prezentace, které zaujmou vaše publikum.

 Pokud máte nějaké dotazy nebo potřebujete další pomoc, neváhejte se obrátit na komunitu Aspose.Slides na jejich[Fórum podpory](https://forum.aspose.com/).

## Nejčastější dotazy

### Mohu pomocí Aspose.Slides for .NET animovat další prvky grafu kromě řad?
Ano, pomocí Aspose.Slides for .NET můžete animovat různé prvky grafu, včetně datových bodů, os a legend.

### Je Aspose.Slides for .NET kompatibilní s nejnovějšími verzemi PowerPointu?
Aspose.Slides for .NET podporuje různé verze aplikace PowerPoint, včetně aplikace PowerPoint 2007 a novější, což zajišťuje kompatibilitu s nejnovějšími verzemi.

### Mohu přizpůsobit efekty animace pro každou řadu grafů samostatně?
Ano, můžete přizpůsobit efekty animace pro každou řadu grafů a vytvořit tak jedinečné a poutavé prezentace.

### Je k dispozici zkušební verze pro Aspose.Slides pro .NET?
 Ano, můžete si knihovnu vyzkoušet pomocí bezplatné zkušební verze od[Web Aspose.Slides for .NET](https://releases.aspose.com/).

### Kde si mohu zakoupit licenci pro Aspose.Slides pro .NET?
 Licenci na Aspose.Slides for .NET můžete získat na nákupní stránce[tady](https://purchase.aspose.com/buy).