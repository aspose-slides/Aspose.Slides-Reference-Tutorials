---
"description": "Prozkoumejte sílu Aspose.Slides pro .NET a snadno propojujte tvary ve svých prezentacích. Pozdvihněte úroveň svých snímků pomocí dynamických spojnic."
"linktitle": "Propojení tvarů pomocí spojnic v prezentaci"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Aspose.Slides - Bezproblémové propojení tvarů v .NET"
"url": "/cs/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Bezproblémové propojení tvarů v .NET

## Zavedení
V dynamickém světě prezentací dodává možnost propojovat tvary pomocí spojnic vašim snímkům vrstvu sofistikovanosti. Aspose.Slides pro .NET umožňuje vývojářům toho bezproblémově dosáhnout. Tento tutoriál vás provede celým procesem a rozebere každý krok, abyste mu vše dobře porozuměli.
## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte následující:
- Základní znalost C# a .NET frameworku.
- Aspose.Slides pro .NET je nainstalován. Pokud ne, stáhněte si ho. [zde](https://releases.aspose.com/slides/net/).
- Nastavení vývojového prostředí.
## Importovat jmenné prostory
V kódu C# začněte importem potřebných jmenných prostorů:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Nastavení adresáře dokumentů
Začněte definováním adresáře pro váš dokument:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Vytvoření instance třídy prezentací
Vytvořte instanci třídy Presentation, která bude reprezentovat váš soubor PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Přístup ke kolekci tvarů pro vybraný snímek
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Přidání tvarů do snímku
Přidejte do snímku potřebné tvary, například elipsu a obdélník:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Přidání tvaru spojnice
Zahrnout tvar spojnice do kolekce tvarů snímku:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Propojení tvarů pomocí spojnice
Určete tvary, které mají být propojeny spojnicí:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Přesměrovat konektor
Voláním metody reroute nastavíte automatickou nejkratší cestu mezi tvary:
```csharp
connector.Reroute();
```
## 7. Uložit prezentaci
Uložte si prezentaci, abyste si mohli prohlédnout propojené tvary:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Závěr
Gratulujeme! Úspěšně jste propojili tvary pomocí spojnic v prezentačních snímcích pomocí Aspose.Slides pro .NET. Vylepšete své prezentace touto pokročilou funkcí a zaujměte své publikum.
## Často kladené otázky
### Je Aspose.Slides pro .NET kompatibilní s nejnovějším frameworkem .NET?
Ano, Aspose.Slides pro .NET je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi frameworku .NET.
### Mohu propojit více než dva tvary pomocí jedné spojnice?
Rozhodně můžete propojit více tvarů rozšířením logiky konektoru ve vašem kódu.
### Existují nějaká omezení ohledně tvarů, které mohu propojit?
Aspose.Slides pro .NET podporuje propojování různých tvarů, včetně základních tvarů, inteligentních prvků a vlastních tvarů.
### Jak si mohu přizpůsobit vzhled konektoru?
Prostudujte si dokumentaci k Aspose.Slides, kde najdete metody pro přizpůsobení vzhledu spojnice, jako je styl a barva čáry.
### Existuje nějaké komunitní fórum pro podporu Aspose.Slides?
Ano, můžete najít pomoc a podělit se o své zkušenosti v [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}