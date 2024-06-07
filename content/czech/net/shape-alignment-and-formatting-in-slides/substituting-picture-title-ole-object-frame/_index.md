---
title: Průvodce vkládáním objektů OLE s Aspose.Slides pro .NET
linktitle: Nahrazení názvu obrázku rámečku objektu OLE v prezentačních snímcích
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak vylepšit snímky prezentace pomocí dynamických objektů OLE pomocí Aspose.Slides for .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 15
url: /cs/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## Úvod
Vytváření dynamických a poutavých prezentačních snímků často zahrnuje začlenění různých multimediálních prvků. V tomto tutoriálu prozkoumáme, jak nahradit název obrázku OLE (Object Linking and Embedding) Object Frame ve snímcích prezentace pomocí výkonné knihovny Aspose.Slides for .NET. Aspose.Slides zjednodušuje proces manipulace s objekty OLE a poskytuje vývojářům nástroje pro snadné vylepšení jejich prezentací.
## Předpoklady
Než se pustíme do podrobného průvodce, ujistěte se, že máte splněny následující předpoklady:
-  Knihovna Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides for .NET. Můžete si jej stáhnout z[Dokumentace Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- Ukázková data: Připravte si ukázkový soubor aplikace Excel (např. "ExcelObject.xlsx"), který chcete vložit jako objekt OLE do prezentace. Navíc mějte obrazový soubor (např. "Image.png"), který bude sloužit jako ikona pro objekt OLE.
- Vývojové prostředí: Nastavte vývojové prostředí s nezbytnými nástroji, jako je Visual Studio nebo jakékoli jiné preferované IDE pro vývoj .NET.
## Importovat jmenné prostory
Ve svém projektu .NET se ujistěte, že importujete požadované jmenné prostory pro práci s Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Krok 1: Nastavte adresář dokumentů
```csharp
string dataDir = "Your Document Directory";
```
Ujistěte se, že jste nahradili "Your Document Directory" skutečnou cestou k vašemu adresáři dokumentů.
## Krok 2: Definujte cesty zdrojového souboru OLE a souboru ikon
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Aktualizujte tyto cesty skutečnými cestami k vašemu ukázkovému souboru Excel a souboru obrázku.
## Krok 3: Vytvořte instanci prezentace
```csharp
using (Presentation pres = new Presentation())
{
    // Zde bude uveden kód pro následující kroky
}
```
 Inicializujte novou instanci souboru`Presentation` třída.
## Krok 4: Přidejte rámeček objektu OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Přidejte na snímek rámeček objektu OLE s určením jeho polohy a rozměrů.
## Krok 5: Přidejte objekt obrázku
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Přečtěte si soubor obrázku a přidejte jej do prezentace jako objekt obrázku.
## Krok 6: Nastavte titulek na ikonu OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Nastavte požadovaný titulek pro ikonu OLE.
## Závěr
Začlenění objektů OLE do snímků prezentace pomocí Aspose.Slides for .NET je jednoduchý proces. Tento výukový program vás provede základními kroky, od nastavení adresáře dokumentů až po přidávání a přizpůsobení objektů OLE. Experimentujte s různými typy souborů a titulky, abyste zvýšili vizuální přitažlivost svých prezentací.
## Nejčastější dotazy
### Mohu pomocí Aspose.Slides vložit jiné typy souborů jako objekty OLE?
Ano, Aspose.Slides podporuje vkládání různých typů souborů, jako jsou tabulky Excel, dokumenty Word a další.
### Je ikona objektu OLE přizpůsobitelná?
Absolutně. Výchozí ikonu můžete nahradit libovolným obrázkem podle svého výběru, aby lépe vyhovoval tématu vaší prezentace.
### Poskytuje Aspose.Slides podporu pro animace s objekty OLE?
Od nejnovější verze se Aspose.Slides zaměřuje na vkládání a zobrazování objektů OLE a nezpracovává přímo animace v rámci objektů OLE.
### Mohu programově manipulovat s objekty OLE po jejich přidání na snímek?
Rozhodně. Máte plnou programovou kontrolu nad objekty OLE, což vám umožňuje upravovat jejich vlastnosti a vzhled podle potřeby.
### Existují nějaká omezení velikosti vložených objektů OLE?
I když existují omezení velikosti, jsou obecně velkorysé. Pro zajištění optimálního výkonu se doporučuje testovat s vaším konkrétním případem použití.