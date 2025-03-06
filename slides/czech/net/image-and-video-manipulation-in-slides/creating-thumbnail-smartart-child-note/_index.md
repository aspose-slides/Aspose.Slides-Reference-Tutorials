---
title: Vytvoření miniatury pro podřízenou poznámku SmartArt v Aspose.Slides
linktitle: Vytvoření miniatury pro podřízenou poznámku SmartArt v Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se vytvářet úchvatné miniatury podřízených poznámek SmartArt pomocí Aspose.Slides for .NET. Pozvedněte své prezentace pomocí dynamických vizuálů!
weight: 15
url: /cs/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření miniatury pro podřízenou poznámku SmartArt v Aspose.Slides

## Úvod
oblasti dynamických prezentací vyniká Aspose.Slides for .NET jako výkonný nástroj, který vývojářům poskytuje možnost programově manipulovat a vylepšovat prezentace PowerPoint. Jednou ze zajímavých funkcí je schopnost generovat miniatury pro SmartArt Child Notes, které dodávají vašim prezentacím vrstvu vizuální přitažlivosti. Tento podrobný průvodce vás provede procesem vytváření miniatur pro SmartArt Child Notes pomocí Aspose.Slides pro .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Slides pro .NET: Ujistěte se, že máte knihovnu Aspose.Slides integrovanou do svého projektu .NET. Pokud ne, stáhněte si jej z[stránka vydání](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Nastavte funkční vývojové prostředí .NET a mějte základní znalosti o programování v C#.
- Ukázková prezentace: Vytvořte nebo získejte PowerPointovou prezentaci obsahující SmartArt s Child Notes pro testování.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu C#. Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro práci s Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Krok 1: Okamžitá prezentace
 Začněte vytvořením instance`Presentation` třídy, představující soubor PPTX, se kterým budete pracovat.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Krok 2: Přidejte SmartArt
 Nyní přidejte SmartArt na snímek v rámci prezentace. V tomto příkladu používáme`BasicCycle` rozložení.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Krok 3: Získejte referenci uzlu
Chcete-li pracovat s konkrétním uzlem v prvku SmartArt, získejte jeho referenci pomocí jeho indexu.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Krok 4: Získejte miniaturu
Načtěte obrázek miniatury podřízené poznámky v uzlu SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Krok 5: Uložte miniaturu
Uložte vygenerovanou miniaturu do určeného adresáře.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Opakujte tyto kroky pro každý uzel SmartArt v prezentaci a upravte rozvržení a styly podle potřeby.
## Závěr
Na závěr, Aspose.Slides for .NET umožňuje vývojářům snadno vytvářet poutavé prezentace. Možnost generovat miniatury pro SmartArt Child Notes zvyšuje vizuální přitažlivost vašich prezentací a poskytuje dynamické a interaktivní uživatelské prostředí.
## Často kladené otázky
### Otázka: Mohu přizpůsobit velikost a formát vygenerované miniatury?
Odpověď: Ano, můžete upravit rozměry a formát náhledu úpravou odpovídajících parametrů v kódu.
### Otázka: Podporuje Aspose.Slides další rozvržení SmartArt?
A: Rozhodně! Aspose.Slides nabízí řadu rozvržení SmartArt, což vám umožní vybrat si to, které nejlépe vyhovuje vašim potřebám prezentace.
### Otázka: Je k dispozici dočasná licence pro účely testování?
 Odpověď: Ano, můžete získat dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/) pro testování a hodnocení.
### Otázka: Kde mohu vyhledat pomoc nebo se spojit s komunitou Aspose.Slides?
 A: Navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) zapojit se do komunity, klást otázky a hledat řešení.
### Otázka: Mohu si zakoupit Aspose.Slides pro .NET?
 A: Určitě! Prozkoumejte možnosti nákupu[tady](https://purchase.aspose.com/buy) odemknout plný potenciál Aspose.Slides ve vašich projektech.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
