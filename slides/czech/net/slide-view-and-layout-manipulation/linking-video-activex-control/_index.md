---
"description": "Naučte se, jak propojit videa se snímky PowerPointu pomocí Aspose.Slides pro .NET. Tato podrobná příručka obsahuje zdrojový kód a tipy pro vytváření interaktivních a poutavých prezentací s propojenými videi."
"linktitle": "Propojení videa pomocí ovládacího prvku ActiveX"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Propojení videa pomocí ovládacího prvku ActiveX v PowerPointu"
"url": "/cs/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propojení videa pomocí ovládacího prvku ActiveX v PowerPointu

Propojení videa pomocí ovládacího prvku ActiveX v prezentaci pomocí Aspose.Slides pro .NET

Aspose.Slides pro .NET můžete programově propojit video se snímkem prezentace pomocí ovládacího prvku ActiveX. To vám umožní vytvářet interaktivní prezentace, kde lze video obsah přehrávat přímo ve snímku. V tomto podrobném návodu vás provedeme procesem propojení videa se snímkem prezentace pomocí Aspose.Slides pro .NET.

## Předpoklady:
- Visual Studio (nebo jakékoli jiné vývojové prostředí pro .NET)
- Knihovna Aspose.Slides pro .NET. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/net/).

## Krok 1: Vytvořte nový projekt
Vytvořte nový projekt ve vámi preferovaném vývojovém prostředí .NET (např. Visual Studio) a přidejte odkazy na knihovnu Aspose.Slides pro .NET.

## Krok 2: Importujte potřebné jmenné prostory
Do projektu importujte potřebné jmenné prostory pro práci s Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Krok 3: Načtení prezentace
Načtěte prezentaci v PowerPointu, kam chcete přidat odkazované video:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Váš kód pro přidání odkazovaného videa bude zde
}
```

## Krok 4: Přidání ovládacího prvku ActiveX
Vytvořte instanci `IOleObjectFrame` rozhraní pro přidání ovládacího prvku ActiveX na snímek:

```csharp
ISlide slide = presentation.Slides[0]; // Vyberte snímek, kam chcete video přidat
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

Ve výše uvedeném kódu přidáváme do snímku rámec ovládacího prvku ActiveX o rozměrech 640x480. Zadáváme ProgID pro ovládací prvek ActiveX ShockwaveFlash, který se běžně používá pro vkládání videí.

## Krok 5: Nastavení vlastností ovládacího prvku ActiveX
Nastavte vlastnosti ovládacího prvku ActiveX tak, aby určovaly propojený zdroj videa:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Nahraďte skutečnou cestou k souboru videa
oleObjectFrame.AlternativeText = "Linked Video";
```

Nahradit `"YourVideoPathHere"` se skutečnou cestou k vašemu video souboru. `AlternativeText` Vlastnost poskytuje popis odkazovaného videa.

## Krok 6: Uložení prezentace
Uložte upravenou prezentaci:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Často kladené otázky:

### Jak mohu určit velikost a umístění odkazovaného videa na snímku?
Rozměry a polohu rámečku ovládacího prvku ActiveX můžete upravit pomocí parametrů `AddOleObjectFrame` metoda. Čtyři číselné argumenty představují souřadnice X a Y levého horního rohu a šířku a výšku rámečku.

### Mohu tímto způsobem propojit videa různých formátů?
Ano, můžete propojovat videa různých formátů, pokud je pro daný formát k dispozici příslušný ovládací prvek ActiveX. Například ovládací prvek ActiveX ShockwaveFlash použitý v této příručce je vhodný pro videa Flash (SWF). Pro jiné formáty může být nutné použít jiná ProgID.

### Existuje nějaký limit velikosti odkazovaného videa?
Velikost propojeného videa může ovlivnit celkovou velikost a výkon vaší prezentace. Před propojením s prezentací doporučujeme optimalizovat videa pro přehrávání na webu.

### Závěr:
Podle kroků uvedených v této příručce můžete snadno propojit video pomocí ovládacího prvku ActiveX v prezentaci s využitím Aspose.Slides pro .NET. Tato funkce vám umožňuje vytvářet poutavé a interaktivní prezentace, které bezproblémově zahrnují multimediální obsah.

Pro více informací a pokročilé možnosti se můžete podívat na [Dokumentace k Aspose.Slides pro .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}