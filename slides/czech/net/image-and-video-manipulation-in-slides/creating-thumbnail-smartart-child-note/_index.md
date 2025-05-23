---
"description": "Naučte se, jak vytvářet poutavé miniatury podřízených poznámek SmartArt pomocí Aspose.Slides pro .NET. Pozdvihněte své prezentace na vyšší úroveň dynamickými vizuály!"
"linktitle": "Vytvoření miniatury pro podřízenou poznámku SmartArt v Aspose.Slides"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Vytvoření miniatury pro podřízenou poznámku SmartArt v Aspose.Slides"
"url": "/cs/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření miniatury pro podřízenou poznámku SmartArt v Aspose.Slides

## Zavedení
oblasti dynamických prezentací vyniká Aspose.Slides pro .NET jako výkonný nástroj, který vývojářům umožňuje programově manipulovat s prezentacemi v PowerPointu a vylepšovat je. Jednou ze zajímavých funkcí je možnost generovat miniatury pro podřízené poznámky SmartArt, což vašim prezentacím dodává vizuální atraktivitu. Tento podrobný návod vás provede procesem vytváření miniatur pro podřízené poznámky SmartArt pomocí Aspose.Slides pro .NET.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Aspose.Slides pro .NET: Ujistěte se, že máte knihovnu Aspose.Slides integrovanou do svého .NET projektu. Pokud ne, stáhněte si ji z [stránka s vydáními](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Nastavit funkční vývojové prostředí .NET a mít základní znalosti programování v C#.
- Ukázková prezentace: Vytvořte nebo si stáhněte prezentaci v PowerPointu obsahující prvky SmartArt s podřízenými poznámkami pro testování.
## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů do vašeho projektu v C#. Tyto jmenné prostory poskytují přístup ke třídám a metodám potřebným pro práci s Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Krok 1: Vytvoření instance třídy prezentací
Začněte vytvořením instance `Presentation` třída, která představuje soubor PPTX, se kterým budete pracovat.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Krok 2: Přidání prvku SmartArt
Nyní přidejte SmartArt na snímek v prezentaci. V tomto příkladu používáme `BasicCycle` rozvržení.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Krok 3: Získání reference uzlu
Chcete-li pracovat s konkrétním uzlem v prvku SmartArt, získejte jeho referenci pomocí jeho indexu.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Krok 4: Získejte miniaturu
Načte miniaturu podřízené poznámky v uzlu SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Krok 5: Uložení miniatury
Uložte vygenerovaný náhledový obrázek do zadaného adresáře.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Tyto kroky opakujte pro každý uzel grafiky SmartArt v prezentaci a podle potřeby upravte rozvržení a styly.
## Závěr
Závěrem lze říci, že Aspose.Slides pro .NET umožňuje vývojářům snadno vytvářet poutavé prezentace. Možnost generovat miniatury pro podřízené poznámky SmartArt zvyšuje vizuální atraktivitu vašich prezentací a poskytuje dynamický a interaktivní uživatelský zážitek.
## Často kladené otázky
### Otázka: Mohu si přizpůsobit velikost a formát vygenerované miniatury?
A: Ano, rozměry a formát miniatury můžete upravit úpravou odpovídajících parametrů v kódu.
### Otázka: Podporuje Aspose.Slides i jiná rozvržení SmartArt?
A: Rozhodně! Aspose.Slides nabízí řadu rozvržení SmartArt, takže si můžete vybrat to, které nejlépe vyhovuje vašim potřebám při prezentaci.
### Otázka: Je k dispozici dočasná licence pro testovací účely?
A: Ano, můžete získat dočasnou licenci od [zde](https://purchase.aspose.com/temporary-license/) pro testování a hodnocení.
### Otázka: Kde mohu vyhledat pomoc nebo se spojit s komunitou Aspose.Slides?
A: Navštivte [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) komunikovat s komunitou, klást otázky a hledat řešení.
### Otázka: Mohu si zakoupit Aspose.Slides pro .NET?
A: Jistě! Prozkoumejte možnosti nákupu [zde](https://purchase.aspose.com/buy) abyste ve svých projektech plně využili potenciál Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}