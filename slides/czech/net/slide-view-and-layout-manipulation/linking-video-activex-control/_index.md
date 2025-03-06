---
title: Propojení videa pomocí ovládacího prvku ActiveX v aplikaci PowerPoint
linktitle: Propojení videa pomocí ovládacího prvku ActiveX
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Přečtěte si, jak propojit videa se snímky aplikace PowerPoint pomocí Aspose.Slides for .NET. Tento podrobný průvodce obsahuje zdrojový kód a tipy pro vytváření interaktivních a poutavých prezentací s propojenými videi.
weight: 12
url: /cs/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

Propojení videa přes ovládací prvek ActiveX v prezentaci pomocí Aspose.Slides pro .NET

V Aspose.Slides for .NET můžete programově propojit video se snímkem prezentace pomocí ovládacího prvku ActiveX. To vám umožní vytvářet interaktivní prezentace, kde lze obsah videa přehrávat přímo na snímku. V tomto podrobném průvodci vás provedeme procesem propojení videa se snímkem prezentace pomocí Aspose.Slides for .NET.

## Předpoklady:
- Visual Studio (nebo jakékoli jiné vývojové prostředí .NET)
-  Aspose.Slides pro knihovnu .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).

## Krok 1: Vytvořte nový projekt
Vytvořte nový projekt ve vámi preferovaném vývojovém prostředí .NET (např. Visual Studio) a přidejte odkazy na knihovnu Aspose.Slides for .NET.

## Krok 2: Importujte potřebné jmenné prostory
Do svého projektu importujte potřebné jmenné prostory pro práci s Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Krok 3: Načtěte prezentaci
Načtěte prezentaci PowerPoint, kam chcete přidat propojené video:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Váš kód pro přidání odkazovaného videa bude umístěn zde
}
```

## Krok 4: Přidejte ovládací prvek ActiveX
 Vytvořte instanci souboru`IOleObjectFrame` rozhraní pro přidání ovládacího prvku ActiveX na snímek:

```csharp
ISlide slide = presentation.Slides[0]; // Vyberte snímek, kam chcete přidat video
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

V kódu výše přidáváme na snímek ovládací rámeček ActiveX o rozměrech 640x480. Určujeme ProgID pro ovládací prvek ShockwaveFlash ActiveX, který se běžně používá pro vkládání videí.

## Krok 5: Nastavte vlastnosti ovládacího prvku ActiveX
Nastavte vlastnosti ovládacího prvku ActiveX, abyste určili propojený zdroj videa:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Nahraďte skutečnou cestou k souboru videa
oleObjectFrame.AlternativeText = "Linked Video";
```

 Nahradit`"YourVideoPathHere"` se skutečnou cestou k vašemu video souboru. The`AlternativeText` vlastnost poskytuje popis propojeného videa.

## Krok 6: Uložte prezentaci
Uložte upravenou prezentaci:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Nejčastější dotazy:

### Jak mohu určit velikost a polohu propojeného videa na snímku?
Rozměry a polohu ovládacího rámečku ActiveX můžete upravit pomocí parametrů`AddOleObjectFrame` metoda. Čtyři číselné argumenty představují souřadnice X a Y levého horního rohu a šířku a výšku rámečku.

### Mohu pomocí tohoto přístupu propojit videa různých formátů?
Ano, můžete propojit videa různých formátů, pokud je pro daný formát k dispozici příslušný ovládací prvek ActiveX. Například ovládací prvek ShockwaveFlash ActiveX použitý v této příručce je vhodný pro videa Flash (SWF). Pro jiné formáty možná budete muset použít jiné ProgID.

### Existuje omezení velikosti odkazovaného videa?
Velikost propojeného videa může ovlivnit celkovou velikost a výkon vaší prezentace. Před propojením videí s prezentací se doporučuje optimalizovat videa pro přehrávání na webu.

### Závěr:
Podle kroků uvedených v této příručce můžete snadno propojit video prostřednictvím ovládacího prvku ActiveX v prezentaci pomocí Aspose.Slides for .NET. Tato funkce umožňuje vytvářet poutavé a interaktivní prezentace, které hladce zahrnují multimediální obsah.

 Další podrobnosti a pokročilé možnosti naleznete na[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
