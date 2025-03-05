---
title: Aspose.Slides - Bezproblémové propojení tvarů v .NET
linktitle: Spojování tvarů pomocí konektorů v prezentaci
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Prozkoumejte sílu Aspose.Slides pro .NET, spojující tvary bez námahy ve vašich prezentacích. Pozvedněte své snímky pomocí dynamických konektorů.
type: docs
weight: 29
url: /cs/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Úvod
V dynamickém světě prezentací přidává možnost spojovat tvary pomocí konektorů na vaše snímky na sofistikovanosti. Aspose.Slides for .NET umožňuje vývojářům dosáhnout tohoto hladce. Tento tutoriál vás provede celým procesem a rozebere každý krok, abyste zajistili jasné porozumění.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
- Základní znalost C# a .NET frameworku.
-  Aspose.Slides pro .NET nainstalován. Pokud ne, stáhněte si jej[tady](https://releases.aspose.com/slides/net/).
- Vytvořeno vývojové prostředí.
## Importovat jmenné prostory
V kódu C# začněte importováním potřebných jmenných prostorů:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Nastavte adresář dokumentů
Začněte definováním adresáře pro váš dokument:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Třída okamžité prezentace
Vytvořte instanci třídy Presentation, která bude reprezentovat váš soubor PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Přístup ke kolekci tvarů pro vybraný snímek
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Přidejte na snímek tvary
Přidejte na snímek potřebné tvary, jako je elipsa a obdélník:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Přidejte tvar konektoru
Zahrnout tvar konektoru do kolekce tvarů snímku:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Spojte tvary s konektorem
Určete tvary, které mají být spojeny spojnicí:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Přesměrovat konektor
Voláním metody přesměrování nastavte automatickou nejkratší cestu mezi tvary:
```csharp
connector.Reroute();
```
## 7. Uložit prezentaci
Chcete-li zobrazit připojené tvary, uložte prezentaci:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Závěr
Gratulujeme! Úspěšně jste spojili tvary pomocí konektorů na snímcích prezentace pomocí Aspose.Slides pro .NET. Vylepšete své prezentace pomocí této pokročilé funkce a upoutejte své publikum.
## Nejčastější dotazy
### Je Aspose.Slides for .NET kompatibilní s nejnovějším rámcem .NET?
Ano, Aspose.Slides for .NET je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi .NET frameworku.
### Mohu připojit více než dva tvary pomocí jednoho konektoru?
Rozhodně můžete propojit více obrazců rozšířením logiky konektoru v kódu.
### Existují nějaká omezení tvarů, které mohu připojit?
Aspose.Slides for .NET podporuje spojování různých tvarů, včetně základních tvarů, chytrého umění a vlastních tvarů.
### Jak mohu přizpůsobit vzhled konektoru?
Prozkoumejte dokumentaci Aspose.Slides pro metody přizpůsobení vzhledu konektoru, jako je styl a barva čáry.
### Existuje komunitní fórum pro podporu Aspose.Slides?
 Ano, můžete najít pomoc a sdílet své zkušenosti v[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).