---
title: Manipulace s hypertextovými odkazy v Aspose.Slides
linktitle: Manipulace s hypertextovými odkazy v Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se přidávat a odstraňovat hypertextové odkazy v Aspose.Slides pro .NET. Snadno vylepšete své prezentace pomocí interaktivních odkazů.
weight: 10
url: /cs/net/hyperlink-manipulation/hyperlink-manipulation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manipulace s hypertextovými odkazy v Aspose.Slides


Hypertextové odkazy jsou základními prvky prezentací, protože poskytují pohodlný způsob navigace mezi snímky nebo přístupu k externím zdrojům. Aspose.Slides for .NET nabízí výkonné funkce pro přidávání a odstraňování hypertextových odkazů ve snímcích prezentace. V tomto tutoriálu vás provedeme procesem manipulace s hypertextovými odkazy pomocí Aspose.Slides for .NET. Budeme se zabývat přidáváním hypertextových odkazů na snímek a odstraňováním hypertextových odkazů ze snímku. Takže, pojďme se ponořit!

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Slides for .NET: Musíte mít nainstalovanou a nastavenou knihovnu Aspose.Slides for .NET. Dokumentaci najdete[tady](https://reference.aspose.com/slides/net/) a stáhněte si jej z[tento odkaz](https://releases.aspose.com/slides/net/).

2. Adresář dokumentů: Potřebujete adresář, kam budete ukládat soubory prezentace. Ujistěte se, že jste ve svém kódu zadali cestu k tomuto adresáři.

3. Základní znalost C#: Tento tutoriál předpokládá, že máte základní znalosti o programování v C#.

Nyní, když máte své předpoklady na místě, přejděme k podrobnému průvodci pro manipulaci s hypertextovými odkazy pomocí Aspose.Slides for .NET.

## Přidání hypertextových odkazů na snímek

### Krok 1: Inicializujte prezentaci

Chcete-li začít, musíte inicializovat prezentaci pomocí Aspose.Slides. Můžete to udělat pomocí následujícího kódu:

```csharp
using (Presentation presentation = new Presentation())
{
    // Váš kód zde
}
```

### Krok 2: Přidejte textový rámeček

Nyní přidáme na snímek textový rámeček. Tento kód vytvoří obdélníkový tvar s textem:

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### Krok 3: Přidejte hypertextový odkaz

Dále přidáte hypertextový odkaz na text ve tvaru, který jste vytvořili. Můžete to udělat takto:

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### Krok 4: Uložte prezentaci

Nakonec uložte prezentaci s přidaným hypertextovým odkazem:

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Gratulujeme! Úspěšně jste přidali hypertextový odkaz na snímek pomocí Aspose.Slides for .NET.

## Odebrání hypertextových odkazů ze snímku

### Krok 1: Inicializujte prezentaci

Chcete-li odebrat hypertextové odkazy ze snímku, musíte otevřít existující prezentaci:

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### Krok 2: Odstraňte hypertextové odkazy

Nyní odstraňte všechny hypertextové odkazy z prezentace pomocí následujícího kódu:

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### Krok 3: Uložte prezentaci

Po odstranění hypertextových odkazů prezentaci uložte:

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

A to je vše! Úspěšně jste odstranili hypertextové odkazy ze snímku pomocí Aspose.Slides for .NET.

Závěrem lze říci, že Aspose.Slides for .NET poskytuje efektivní způsob manipulace s hypertextovými odkazy ve vašich prezentacích a umožňuje vám vytvářet interaktivní a poutavé snímky. Ať už chcete přidat hypertextové odkazy na externí zdroje nebo je odstranit, Aspose.Slides zjednoduší proces a vylepší vaše možnosti vytváření prezentací.

 Děkujeme, že jste se k nám připojili v tomto tutoriálu o manipulaci s hypertextovými odkazy v Aspose.Slides pro .NET. Pokud máte nějaké dotazy nebo potřebujete další pomoc, neváhejte prozkoumat[Dokumentace Aspose.Slides](https://reference.aspose.com/slides/net/) nebo se obraťte na komunitu Aspose na[Fórum podpory](https://forum.aspose.com/).

---

## Závěr

V tomto tutoriálu jsme se naučili, jak manipulovat s hypertextovými odkazy v prezentacích pomocí Aspose.Slides for .NET. Zabývali jsme se přidáváním a odstraňováním hypertextových odkazů, které vám umožňují vytvářet dynamické a interaktivní prezentace. Aspose.Slides zjednodušuje proces a usnadňuje vylepšení vašich snímků pomocí hypertextových odkazů na externí zdroje.

Máte nějaké další otázky ohledně práce s Aspose.Slides nebo jiných aspektů designu prezentací? Další informace najdete v častých dotazech níže.

## Často kladené otázky (FAQ)

### Jaké jsou klíčové výhody používání Aspose.Slides pro .NET?
Aspose.Slides for .NET nabízí širokou škálu funkcí pro vytváření, manipulaci a konverzi prezentací. Poskytuje komplexní sadu nástrojů pro přidávání obsahu, animací a interakcí do vašich snímků.

### Mohu v Aspose.Slides přidat hypertextové odkazy na jiné objekty než text?
Ano, Aspose.Slides vám umožňuje přidávat hypertextové odkazy na různé objekty, včetně tvarů, obrázků a textu, což vám dává flexibilitu při vytváření interaktivních prezentací.

### Je Aspose.Slides kompatibilní s různými formáty souborů PowerPoint?
Absolutně. Aspose.Slides podporuje různé formáty PowerPoint, včetně PPT, PPTX, PPS a dalších. Zajišťuje kompatibilitu s různými verzemi aplikace Microsoft PowerPoint.

### Kde najdu další zdroje a podporu pro Aspose.Slides?
 Pro podrobnou dokumentaci a podporu komunity navštivte stránku[Dokumentace Aspose.Slides](https://reference.aspose.com/slides/net/) a[Aspose fórum podpory](https://forum.aspose.com/).

### Jak mohu získat dočasnou licenci pro Aspose.Slides?
 Pokud potřebujete dočasnou licenci pro Aspose.Slides, můžete si ji pořídit[tady](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
