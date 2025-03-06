---
title: Převést prezentaci do formátu SWF
linktitle: Převést prezentaci do formátu SWF
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se převádět prezentace PowerPoint do formátu SWF pomocí Aspose.Slides for .NET. Vytvářejte dynamický obsah bez námahy!
weight: 28
url: /cs/net/presentation-conversion/convert-presentation-to-swf-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


V dnešní digitální době jsou multimediální prezentace mocným komunikačním prostředkem. Někdy můžete chtít sdílet své prezentace dynamičtějším způsobem, například je převést do formátu SWF (Shockwave Flash). Tato příručka vás provede procesem převodu prezentace do formátu SWF pomocí Aspose.Slides for .NET.

## Co budete potřebovat

Než se pustíme do výukového programu, ujistěte se, že máte následující:

-  Aspose.Slides pro .NET: Pokud jej ještě nemáte, můžete[stáhněte si to zde](https://releases.aspose.com/slides/net/).

- Soubor prezentace: Budete potřebovat soubor prezentace PowerPoint, který chcete převést do formátu SWF.

## Krok 1: Nastavte své prostředí

Chcete-li začít, vytvořte adresář pro svůj projekt. Říkejme tomu „Váš projektový adresář“. Do tohoto adresáře budete muset umístit následující zdrojový kód:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Vytvořte instanci objektu Presentation, který představuje soubor prezentace
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // Ukládání stránek prezentace a poznámek
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

 Ujistěte se, že vyměníte`"Your Document Directory"` a`"Your Output Directory"` se skutečnými cestami, kde se nachází váš soubor prezentace a kam chcete uložit soubory SWF.

## Krok 2: Načtení prezentace

V tomto kroku načteme prezentaci PowerPoint pomocí Aspose.Slides:

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

 Nahradit`"HelloWorld.pptx"` s názvem souboru vaší prezentace.

## Krok 3: Nakonfigurujte možnosti převodu SWF

Konfigurujeme možnosti převodu SWF pro přizpůsobení výstupu:

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

Tyto možnosti můžete upravit podle svých požadavků.

## Krok 4: Uložit jako SWF

Nyní uložíme prezentaci jako soubor SWF:

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

Tento řádek uloží hlavní prezentaci jako soubor SWF.

## Krok 5: Uložte pomocí poznámek

Pokud chcete zahrnout poznámky, použijte tento kód:

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

Tento kód uloží prezentaci s poznámkami ve formátu SWF.

## Závěr

Gratulujeme! Úspěšně jste převedli prezentaci PowerPoint do formátu SWF pomocí Aspose.Slides for .NET. To může být užitečné zejména tehdy, když potřebujete sdílet své prezentace online nebo je vložit do webových stránek.

 Pro více informací a podrobnou dokumentaci můžete navštívit[Aspose.Slides pro referenci .NET](https://reference.aspose.com/slides/net/).

## Nejčastější dotazy

### Co je formát SWF?
SWF (Shockwave Flash) je multimediální formát používaný pro animace, hry a interaktivní obsah na webu.

### Je Aspose.Slides for .NET zdarma k použití?
 Aspose.Slides for .NET nabízí bezplatnou zkušební verzi, ale pro plnou funkčnost si možná budete muset zakoupit licenci. Můžete zkontrolovat ceny a podrobnosti o licencích[tady](https://purchase.aspose.com/buy).

### Mohu vyzkoušet Aspose.Slides pro .NET před zakoupením licence?
 Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides pro .NET[tady](https://releases.aspose.com/).

### Potřebuji znalosti programování, abych mohl používat Aspose.Slides pro .NET?
Ano, měli byste mít určité znalosti programování v C#, abyste mohli Aspose.Slides efektivně používat.

### Kde mohu získat podporu pro Aspose.Slides pro .NET?
 Pokud máte nějaké dotazy nebo potřebujete pomoc, můžete navštívit stránku[Aspose.Slides for .NET fórum](https://forum.aspose.com/)za podporu a pomoc komunity.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
