---
title: Jak extrahovat video ze snímku pomocí Aspose.Slides pro .NET
linktitle: Extrahujte video ze snímku
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se extrahovat videa ze snímků aplikace PowerPoint pomocí Aspose.Slides for .NET. Tento podrobný průvodce vám celý proces zjednoduší.
weight: 14
url: /cs/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak extrahovat video ze snímku pomocí Aspose.Slides pro .NET


Aspose.Slides for .NET je výkonná knihovna, která umožňuje pracovat s prezentacemi aplikace PowerPoint v prostředí .NET. Jednou z užitečných funkcí, které poskytuje, je možnost extrahovat videa ze snímků. V tomto podrobném průvodci vám ukážeme, jak extrahovat video ze snímku aplikace PowerPoint pomocí Aspose.Slides for .NET.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Slides for .NET: Musíte mít nainstalovaný Aspose.Slides for .NET. Můžete jej získat z[webová stránka](https://purchase.aspose.com/buy).

- PowerPointová prezentace: Připravte si PowerPointovou prezentaci (např. Video.pptx), která obsahuje video, které chcete extrahovat.

## Importovat jmenné prostory

Pro práci s Aspose.Slides for .NET musíte importovat potřebné jmenné prostory. Můžete to udělat takto:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Nyní si proces extrahování videa ze snímku rozdělíme do několika kroků.

## Krok 1: Nastavte adresář dokumentů

```csharp
string dataDir = "Your Document Directory";
```

 Nahradit`"Your Document Directory"` s cestou k adresáři, kde je umístěna vaše prezentace PowerPoint.

## Krok 2: Načtěte prezentaci

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Tento kód inicializuje objekt Presentation představující soubor prezentace PowerPoint.

## Krok 3: Iterujte snímky a tvary

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Zde procházíme každý snímek v prezentaci a poté procházíme tvary v prvním snímku (upravíme podle potřeby).

## Krok 4: Zkontrolujte, zda je Shape Video Frame

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Tento krok zkontroluje, zda je obrazec na snímku snímek videa.

## Krok 5: Extrahujte data videa

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Tento kód extrahuje informace o videu, včetně jeho typu obsahu a binárních dat.

## Krok 6: Uložte video

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Nakonec tento krok uloží video do nového souboru v určeném adresáři.

Po dokončení těchto kroků budete úspěšně extrahovat video ze snímku aplikace PowerPoint pomocí Aspose.Slides for .NET.

## Závěr

Aspose.Slides for .NET zjednodušuje proces práce s PowerPoint prezentacemi a umožňuje vám snadno provádět úkoly, jako je extrahování videí ze snímků. Dodržováním tohoto podrobného průvodce a používáním knihovny Aspose.Slides můžete vylepšit své aplikace .NET pomocí výkonných funkcí aplikace PowerPoint.

## Často kladené otázky (FAQ)

### Co je Aspose.Slides pro .NET?
Aspose.Slides for .NET je knihovna, která umožňuje aplikacím .NET pracovat s prezentacemi PowerPoint, včetně vytváření, úprav a extrahování obsahu.

### Kde najdu dokumentaci k Aspose.Slides pro .NET?
 Dokumentaci najdete[tady](https://reference.aspose.com/slides/net/).

### Je Aspose.Slides pro .NET k dispozici pro bezplatnou zkušební verzi?
 Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.Slides pro .NET?
 Můžete požádat o dočasnou licenci z[tento odkaz](https://purchase.aspose.com/temporary-license/).

### Kde mohu získat podporu pro Aspose.Slides pro .NET?
 Podporu najdete na[Fórum Aspose.Slides](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
