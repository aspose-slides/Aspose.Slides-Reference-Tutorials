---
"description": "Naučte se, jak přidávat a odebírat hypertextové odkazy v Aspose.Slides pro .NET. Snadno vylepšete své prezentace interaktivními odkazy."
"linktitle": "Manipulace s hypertextovými odkazy v Aspose.Slides"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Manipulace s hypertextovými odkazy v Aspose.Slides"
"url": "/cs/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Manipulace s hypertextovými odkazy v Aspose.Slides


Hypertextové odkazy jsou nezbytnými prvky v prezentacích, protože poskytují pohodlný způsob procházení mezi snímky nebo přístup k externím zdrojům. Aspose.Slides pro .NET nabízí výkonné funkce pro přidávání a odebírání hypertextových odkazů ve snímcích prezentace. V tomto tutoriálu vás provedeme procesem manipulace s hypertextovými odkazy pomocí Aspose.Slides pro .NET. Probereme přidávání hypertextových odkazů na snímek a jejich odebírání. Tak se do toho pusťme!

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Aspose.Slides pro .NET: Musíte mít nainstalovanou a nastavenou knihovnu Aspose.Slides pro .NET. Dokumentaci naleznete [zde](https://reference.aspose.com/slides/net/) a stáhněte si ho z [tento odkaz](https://releases.aspose.com/slides/net/).

2. Adresář dokumentů: Potřebujete adresář, kam budete ukládat soubory prezentací. Nezapomeňte ve svém kódu zadat cestu k tomuto adresáři.

3. Základní znalost C#: Tento tutoriál předpokládá, že máte základní znalosti programování v C#.

Nyní, když máte splněny všechny předpoklady, pojďme přejít k podrobnému návodu pro manipulaci s hypertextovými odkazy pomocí Aspose.Slides pro .NET.

## Přidání hypertextových odkazů do snímku

### Krok 1: Inicializace prezentace

Pro začátek je potřeba inicializovat prezentaci pomocí Aspose.Slides. Můžete to provést pomocí následujícího kódu:

```csharp
using (Presentation presentation = new Presentation())
{
    // Váš kód zde
}
```

### Krok 2: Přidání textového rámečku

Nyní přidejme textový rámeček na snímek. Tento kód vytvoří obdélníkový tvar s textem:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Krok 3: Přidání hypertextového odkazu

Dále přidáte hypertextový odkaz k textu ve vytvořeném tvaru. Zde je návod, jak to udělat:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Krok 4: Uložení prezentace

Nakonec uložte prezentaci s přidaným hypertextovým odkazem:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Gratulujeme! Úspěšně jste přidali hypertextový odkaz na snímek pomocí Aspose.Slides pro .NET.

## Odebrání hypertextových odkazů ze snímku

### Krok 1: Inicializace prezentace

Chcete-li ze snímku odstranit hypertextové odkazy, musíte otevřít existující prezentaci:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Krok 2: Odebrání hypertextových odkazů

Nyní odstraňte všechny hypertextové odkazy z prezentace pomocí následujícího kódu:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Krok 3: Uložení prezentace

Po odstranění hypertextových odkazů uložte prezentaci:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

A to je vše! Úspěšně jste odstranili hypertextové odkazy ze snímku pomocí Aspose.Slides pro .NET.

Závěrem lze říci, že Aspose.Slides pro .NET poskytuje efektivní způsob manipulace s hypertextovými odkazy ve vašich prezentacích a umožňuje vám vytvářet interaktivní a poutavé snímky. Ať už chcete přidat hypertextové odkazy na externí zdroje nebo je odebrat, Aspose.Slides zjednodušuje proces a vylepšuje vaše možnosti tvorby prezentací.

Děkujeme, že jste se k nám připojili v tomto tutoriálu o manipulaci s hypertextovými odkazy v Aspose.Slides pro .NET. Pokud máte jakékoli dotazy nebo potřebujete další pomoc, neváhejte se podívat na [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/net/) nebo se obraťte na komunitu Aspose na [fórum podpory](https://forum.aspose.com/).

---

## Závěr

V tomto tutoriálu jsme se naučili, jak manipulovat s hypertextovými odkazy v prezentacích pomocí Aspose.Slides pro .NET. Probrali jsme jak přidávání, tak odebírání hypertextových odkazů, což vám umožní vytvářet dynamické a interaktivní prezentace. Aspose.Slides zjednodušuje proces a usnadňuje vylepšování snímků hypertextovými odkazy na externí zdroje.

Máte další otázky ohledně práce s Aspose.Slides nebo jiných aspektů návrhu prezentací? Další informace naleznete v níže uvedených častých dotazech.

## Často kladené otázky (FAQ)

### Jaké jsou klíčové výhody používání Aspose.Slides pro .NET?
Aspose.Slides pro .NET nabízí širokou škálu funkcí pro vytváření, manipulaci a konverzi prezentací. Poskytuje komplexní sadu nástrojů pro přidávání obsahu, animací a interakcí do vašich snímků.

### Mohu v Aspose.Slides přidat hypertextové odkazy na jiné objekty než text?
Ano, Aspose.Slides umožňuje přidávat hypertextové odkazy na různé objekty, včetně tvarů, obrázků a textu, což vám dává flexibilitu při vytváření interaktivních prezentací.

### Je Aspose.Slides kompatibilní s různými formáty souborů PowerPointu?
Rozhodně. Aspose.Slides podporuje různé formáty PowerPointu, včetně PPT, PPTX, PPS a dalších. Zajišťuje kompatibilitu s různými verzemi Microsoft PowerPointu.

### Kde najdu další zdroje a podporu pro Aspose.Slides?
Podrobnou dokumentaci a podporu komunity naleznete na [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/net/) a [Fórum podpory Aspose](https://forum.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.Slides?
Pokud potřebujete dočasnou licenci pro Aspose.Slides, můžete si ji pořídit [zde](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}