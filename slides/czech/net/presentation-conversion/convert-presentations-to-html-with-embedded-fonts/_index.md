---
title: Převeďte prezentace do HTML pomocí vložených písem
linktitle: Převeďte prezentace do HTML pomocí vložených písem
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Převeďte PowerPointové prezentace do HTML pomocí vložených písem pomocí Aspose.Slides for .NET. Bezproblémově udržujte originalitu.
weight: 13
url: /cs/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převeďte prezentace do HTML pomocí vložených písem


V dnešní digitální době se sdílení prezentací a dokumentů online stalo běžnou praxí. Jedním z problémů, který se často objevuje, je zajistit, aby se vaše písma při převodu prezentací do HTML správně zobrazovala. Tento podrobný návod vás provede procesem používání Aspose.Slides for .NET k převodu prezentací do HTML s vloženými fonty, čímž zajistíte, že vaše dokumenty budou vypadat přesně tak, jak jste zamýšleli.

## Úvod do Aspose.Slides pro .NET

Než se vrhneme na tutoriál, pojďme si krátce představit Aspose.Slides pro .NET. Jedná se o výkonnou knihovnu, která umožňuje vývojářům pracovat s PowerPointovými prezentacemi v aplikacích .NET. S Aspose.Slides můžete vytvářet, upravovat a převádět soubory PowerPoint programově.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Slides for .NET: Měli byste mít ve svém projektu nainstalovanou knihovnu Aspose.Slides. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).

## Krok 1: Nastavte svůj projekt

1. Vytvořte nový projekt nebo otevřete stávající ve vámi preferovaném vývojovém prostředí .NET.

2. Přidejte odkaz na knihovnu Aspose.Slides ve svém projektu.

3. Importujte potřebné jmenné prostory do kódu:

   ```csharp
   using Aspose.Slides;
   ```

## Krok 2: Načtěte svou prezentaci

 Chcete-li začít, musíte načíst prezentaci, kterou chcete převést do HTML. Nahradit`"Your Document Directory"` se skutečným adresářem, kde je umístěn soubor vaší prezentace.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Váš kód je zde
}
```

## Krok 3: Vyloučení výchozích prezentačních písem

V tomto kroku můžete určit libovolná výchozí prezentační písma, která chcete vyloučit z vkládání. To může pomoci optimalizovat velikost výsledného souboru HTML.

```csharp
string[] fontNameExcludeList = { };
```

## Krok 4: Vyberte ovladač HTML

Nyní máte dvě možnosti pro vkládání písem do HTML:

### Možnost 1: Vložit všechna písma

 Chcete-li vložit všechna písma použitá v prezentaci, použijte`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Možnost 2: Propojit všechna písma

 Chcete-li vytvořit odkaz na všechna písma použitá v prezentaci, použijte`LinkAllFontsHtmlController`. Měli byste zadat adresář, ve kterém jsou ve vašem systému umístěny fonty.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Krok 5: Definujte možnosti HTML

 Vytvořit`HtmlOptions` objekt a nastavte formátovač HTML na ten, který jste vybrali v předchozím kroku.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Pro vložení všech písem použijte embedFontsController
};
```

## Krok 6: Uložit jako HTML

 Nakonec uložte prezentaci jako soubor HTML. Můžete si vybrat buď`SaveFormat.Html` nebo`SaveFormat.Html5` v závislosti na vašich požadavcích.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Závěr

Gratulujeme! Úspěšně jste převedli svou prezentaci do HTML s vloženými fonty pomocí Aspose.Slides for .NET. Tím zajistíte, že se vaše písma budou při sdílení prezentací online zobrazovat správně.

Nyní můžete snadno sdílet své krásně formátované prezentace s jistotou, protože víte, že je vaše publikum uvidí přesně tak, jak jste zamýšleli.

 Další informace a podrobné reference API naleznete na[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net/).

## Nejčastější dotazy

### 1. Mohu převést PowerPointové prezentace do HTML pomocí Aspose.Slides for .NET v dávkovém režimu?

Ano, můžete dávkově převést více prezentací do HTML pomocí Aspose.Slides for .NET procházením souborů prezentací a aplikací procesu převodu na každou z nich.

### 2. Existuje způsob, jak upravit vzhled výstupu HTML?

Rozhodně! Aspose.Slides for .NET poskytuje různé možnosti přizpůsobení vzhledu a formátování výstupu HTML, jako je úprava barev, písem a rozvržení.

### 3. Existují nějaká omezení pro vkládání písem do HTML pomocí Aspose.Slides pro .NET?

Zatímco Aspose.Slides for .NET nabízí vynikající možnosti vkládání písem, mějte na paměti, že velikost vašich souborů HTML se může při vkládání písem zvětšit. Ujistěte se, že jste optimalizovali výběr písem pro použití na webu.

### 4. Mohu pomocí Aspose.Slides for .NET převést PowerPointové prezentace do jiných formátů?

Ano, Aspose.Slides for .NET podporuje širokou škálu výstupních formátů, včetně PDF, obrázků a dalších. Své prezentace můžete snadno převést do vámi zvoleného formátu.

### 5. Kde najdu další zdroje a podporu pro Aspose.Slides pro .NET?

 Na webu máte přístup k velkému množství zdrojů, včetně dokumentace[Aspose.Slides for .NET API Reference](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
