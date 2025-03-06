---
title: Zvládnutí animací PowerPoint s Aspose.Slides .NET
linktitle: Opakujte animaci na snímku
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Vylepšete prezentace PowerPoint pomocí Aspose.Slides pro .NET. Ovládejte animace bez námahy, upoutejte své publikum a zanechte trvalý dojem.
weight: 12
url: /cs/net/slide-animation-control/repeat-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V dynamickém světě prezentací hraje schopnost ovládat animace klíčovou roli při upoutání a upoutání pozornosti publika. Aspose.Slides for .NET umožňuje vývojářům převzít odpovědnost za typy animací v rámci snímků, což umožňuje interaktivnější a vizuálně přitažlivější prezentaci. V tomto tutoriálu krok za krokem prozkoumáme, jak ovládat typy animací na snímku pomocí Aspose.Slides for .NET.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.Slides for .NET Library: Stáhněte a nainstalujte knihovnu z[tady](https://releases.aspose.com/slides/net/).
2. Vývojové prostředí .NET: Nastavte na svém počítači vývojové prostředí .NET.
## Importovat jmenné prostory
Ve svém projektu .NET začněte importováním potřebných jmenných prostorů, abyste mohli využít funkce poskytované Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Krok 1: Nastavte projekt
Vytvořte nový adresář pro svůj projekt a vytvořte instanci třídy Presentation, která bude reprezentovat soubor prezentace.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Váš kód je zde
}
```
## Krok 2: Přístup k sekvenci efektů
Načtěte sekvenci efektů pro první snímek pomocí vlastnosti MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Krok 3: Přístup k prvnímu efektu
Získejte první efekt hlavní sekvence pro manipulaci s jejími vlastnostmi.
```csharp
IEffect effect = effectsSequence[0];
```
## Krok 4: Upravte nastavení opakování
Změňte vlastnost časování/opakování efektu na "Do konce snímku."
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Krok 5: Uložte prezentaci
Uložte upravenou prezentaci a vizualizujte změny.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Opakujte tyto kroky pro další efekty nebo je upravte podle vašich požadavků na prezentaci.
## Závěr
Začlenění dynamických animací do prezentací aplikace PowerPoint nebylo s Aspose.Slides pro .NET nikdy jednodušší. Tento podrobný průvodce vás vybaví znalostmi pro ovládání typů animací a zajistí, že vaše snímky zanechají na vaše publikum trvalý dojem.
## Často kladené otázky
### Mohu tyto animace použít na konkrétní objekty na snímku?
Ano, můžete cílit na konkrétní objekty přístupem k jejich jednotlivým efektům v rámci sekvence.
### Je Aspose.Slides kompatibilní s nejnovějšími verzemi aplikace PowerPoint?
Aspose.Slides poskytuje podporu pro širokou škálu verzí aplikace PowerPoint a zajišťuje kompatibilitu se starými i novými verzemi.
### Kde najdu další příklady a zdroje?
 Prozkoumat[dokumentace](https://reference.aspose.com/slides/net/) pro vyčerpávající příklady a podrobná vysvětlení.
### Jak mohu získat dočasnou licenci pro Aspose.Slides?
 Návštěva[tady](https://purchase.aspose.com/temporary-license/) informace o získání dočasné licence.
### Potřebujete pomoc nebo máte další otázky?
 Zapojte se do komunity Aspose.Slides na[Fórum podpory](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
