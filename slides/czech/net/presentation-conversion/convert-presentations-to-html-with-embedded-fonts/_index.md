---
"description": "Převeďte prezentace PowerPointu do HTML s vloženými fonty pomocí Aspose.Slides pro .NET. Zachovejte si originalitu bez problémů."
"linktitle": "Převod prezentací do HTML s vloženými fonty"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Převod prezentací do HTML s vloženými fonty"
"url": "/cs/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Převod prezentací do HTML s vloženými fonty


dnešní digitální době se sdílení prezentací a dokumentů online stalo běžnou praxí. Často však vzniká problém s zajištěním správného zobrazení písem při převodu prezentací do formátu HTML. Tento podrobný návod vás provede procesem použití Aspose.Slides pro .NET k převodu prezentací do formátu HTML s vloženými písmy a zajistí, že vaše dokumenty budou vypadat přesně tak, jak jste zamýšleli.

## Úvod do Aspose.Slides pro .NET

Než se pustíme do tutoriálu, pojďme si stručně představit Aspose.Slides pro .NET. Jedná se o výkonnou knihovnu, která umožňuje vývojářům pracovat s prezentacemi PowerPoint v aplikacích .NET. S Aspose.Slides můžete programově vytvářet, upravovat a převádět soubory PowerPoint.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

- Aspose.Slides pro .NET: Měli byste mít ve svém projektu nainstalovanou knihovnu Aspose.Slides. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/net/).

## Krok 1: Nastavení projektu

1. Vytvořte nový projekt nebo otevřete existující ve vámi preferovaném vývojovém prostředí .NET.

2. Přidejte do projektu odkaz na knihovnu Aspose.Slides.

3. Importujte potřebné jmenné prostory do kódu:

   ```csharp
   using Aspose.Slides;
   ```

## Krok 2: Načtěte prezentaci

Nejprve je třeba načíst prezentaci, kterou chcete převést do formátu HTML. Nahraďte `"Your Document Directory"` se skutečným adresářem, kde se nachází soubor s prezentací.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Váš kód patří sem
}
```

## Krok 3: Vyloučení výchozích prezentačních písem

V tomto kroku můžete určit libovolná výchozí prezentační písma, která chcete vyloučit z vkládání. To může pomoci optimalizovat velikost výsledného souboru HTML.

```csharp
string[] fontNameExcludeList = { };
```

## Krok 4: Vyberte HTML kontroler

Nyní máte dvě možnosti, jak vložit písma do HTML:

### Možnost 1: Vložit všechna písma

Chcete-li vložit všechna písma použitá v prezentaci, použijte `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Možnost 2: Propojit všechna písma

Chcete-li propojit všechna písma použitá v prezentaci, použijte `LinkAllFontsHtmlController`Měli byste zadat adresář, kde se písma nacházejí ve vašem systému.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Krok 5: Definování možností HTML

Vytvořte `HtmlOptions` objekt a nastavte formátovač HTML na ten, který jste vybrali v předchozím kroku.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Pro vkládání všech písem použijte embedFontsController
};
```

## Krok 6: Uložit jako HTML

Nakonec uložte prezentaci jako soubor HTML. Můžete si vybrat jednu z možností `SaveFnebomat.Html` or `SaveFormat.Html5` v závislosti na vašich požadavcích.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Závěr

Gratulujeme! Úspěšně jste převedli svou prezentaci do HTML s vloženými fonty pomocí Aspose.Slides pro .NET. Tím je zajištěno, že se vaše fonty budou při sdílení prezentací online zobrazovat správně.

Nyní můžete snadno a s jistotou sdílet své krásně naformátované prezentace s vědomím, že je vaše publikum uvidí přesně tak, jak jste zamýšleli.

Pro více informací a podrobné reference API se podívejte na [Dokumentace k Aspose.Slides pro .NET](https://reference.aspose.com/slides/net/).

## Často kladené otázky

### 1. Mohu převést prezentace PowerPointu do HTML pomocí Aspose.Slides pro .NET v dávkovém režimu?

Ano, můžete dávkově převést více prezentací do HTML pomocí Aspose.Slides pro .NET tak, že projdete soubory prezentace a na každý z nich aplikujete proces převodu.

### 2. Existuje způsob, jak si přizpůsobit vzhled HTML výstupu?

Jistě! Aspose.Slides pro .NET nabízí různé možnosti pro přizpůsobení vzhledu a formátování HTML výstupu, například úpravu barev, písem a rozvržení.

### 3. Existují nějaká omezení pro vkládání písem do HTML pomocí Aspose.Slides pro .NET?

Přestože Aspose.Slides pro .NET nabízí vynikající možnosti vkládání písem, mějte na paměti, že velikost vašich HTML souborů se při vkládání písem může zvětšit. Nezapomeňte optimalizovat výběr písem pro použití na webu.

### 4. Mohu pomocí Aspose.Slides pro .NET převést prezentace v PowerPointu do jiných formátů?

Ano, Aspose.Slides pro .NET podporuje širokou škálu výstupních formátů, včetně PDF, obrázků a dalších. Své prezentace můžete snadno převést do formátu dle vlastního výběru.

### 5. Kde najdu další zdroje a podporu pro Aspose.Slides pro .NET?

K dispozici je široká škála zdrojů, včetně dokumentace, na [Referenční příručka k Aspose.Slides pro .NET API](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}