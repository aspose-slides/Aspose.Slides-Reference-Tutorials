---
"description": "Naučte se, jak exportovat prezentace do formátu XAML pomocí Aspose.Slides pro .NET. Vytvářejte interaktivní obsah bez námahy!"
"linktitle": "Export prezentace do formátu XAML"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Export prezentace do formátu XAML"
"url": "/cs/net/presentation-conversion/export-presentation-to-xaml-format/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Export prezentace do formátu XAML


Ve světě vývoje softwaru je nezbytné mít nástroje, které dokáží zjednodušit složité úkoly. Aspose.Slides pro .NET je jeden z takových nástrojů, který vám umožňuje programově pracovat s prezentacemi v PowerPointu. V tomto podrobném tutoriálu se podíváme na to, jak exportovat prezentaci do formátu XAML pomocí Aspose.Slides pro .NET. 

## Úvod do Aspose.Slides pro .NET

Než se pustíme do tutoriálu, pojďme si stručně představit Aspose.Slides pro .NET. Je to výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat, převádět a spravovat prezentace v PowerPointu bez nutnosti samotného Microsoft PowerPointu. S Aspose.Slides pro .NET můžete automatizovat různé úkoly související s prezentacemi v PowerPointu, čímž zefektivníte proces vývoje.

## Předpoklady

Abyste mohli pokračovat v tomto tutoriálu, budete potřebovat následující:

1. Aspose.Slides pro .NET: Ujistěte se, že máte knihovnu Aspose.Slides pro .NET nainstalovanou a připravenou k použití ve vašem projektu .NET.

2. Zdrojová prezentace: Máte prezentaci v PowerPointu (PPTX), kterou chcete exportovat do formátu XAML. Ujistěte se, že znáte cestu k této prezentaci.

3. Výstupní adresář: Vyberte adresář, kam chcete uložit vygenerované soubory XAML.

## Krok 1: Nastavení projektu

V tomto prvním kroku nastavíme náš projekt a ujistíme se, že máme připravené všechny potřebné komponenty. Ujistěte se, že jste do projektu přidali odkaz na knihovnu Aspose.Slides pro .NET.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Cesta ke zdrojové prezentaci
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

Nahradit `"Your Document Directory"` s cestou k adresáři obsahujícímu vaši zdrojovou prezentaci v PowerPointu. Také zadejte výstupní adresář, kam budou uloženy vygenerované soubory XAML.

## Krok 2: Export prezentace do XAML

Nyní se pustíme do exportu prezentace v PowerPointu do formátu XAML. K tomu použijeme Aspose.Slides for .NET. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Vytvořte možnosti konverze
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Definujte si vlastní službu pro úsporu výkonu
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Převod snímků
    pres.Save(xamlOptions);

    // Uložení souborů XAML do výstupního adresáře
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

tomto úryvku kódu načteme zdrojovou prezentaci, vytvoříme možnosti konverze XAML a definujeme vlastní službu pro ukládání výstupu pomocí `NewXamlSaver`Poté uložíme soubory XAML do zadaného výstupního adresáře.

## Krok 3: Vlastní třída XAML Saver

Pro implementaci vlastního spořiče XAML vytvoříme třídu s názvem `NewXamlSaver` který implementuje `IXamlOutputSaver` rozhraní.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

Tato třída se postará o ukládání XAML souborů do výstupního adresáře.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak exportovat prezentaci v PowerPointu do formátu XAML pomocí Aspose.Slides pro .NET. To může být cenná dovednost při práci na projektech, které zahrnují manipulaci s prezentacemi.

Neváhejte a prozkoumejte další funkce a možnosti Aspose.Slides pro .NET, které vám pomohou vylepšit vaše automatizované úlohy v PowerPointu.

## Často kladené otázky

1. ### Co je Aspose.Slides pro .NET?
Aspose.Slides pro .NET je knihovna .NET pro programovou práci s prezentacemi v PowerPointu.

2. ### Kde mohu získat Aspose.Slides pro .NET?
Aspose.Slides pro .NET si můžete stáhnout z [zde](https://purchase.aspose.com/buy).

3. ### Je k dispozici bezplatná zkušební verze?
Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides pro .NET. [zde](https://releases.aspose.com/).

4. ### Jak mohu získat dočasnou licenci pro Aspose.Slides pro .NET?
Můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

5. ### Kde mohu získat podporu pro Aspose.Slides pro .NET?
Můžete najít podporu a diskuze v komunitě [zde](https://forum.aspose.com/).

Další návody a zdroje naleznete na [Dokumentace k API Aspose.Slides](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}