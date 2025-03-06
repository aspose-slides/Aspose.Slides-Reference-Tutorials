---
title: Export prezentace do formátu XAML
linktitle: Export prezentace do formátu XAML
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se exportovat prezentace do formátu XAML pomocí Aspose.Slides for .NET. Vytvářejte interaktivní obsah bez námahy!
weight: 27
url: /cs/net/presentation-conversion/export-presentation-to-xaml-format/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Ve světě vývoje softwaru je nezbytné mít nástroje, které mohou zjednodušit složité úkoly. Aspose.Slides for .NET je jedním z takových nástrojů, který vám umožňuje programově pracovat s prezentacemi PowerPoint. V tomto podrobném tutoriálu prozkoumáme, jak exportovat prezentaci do formátu XAML pomocí Aspose.Slides for .NET. 

## Úvod do Aspose.Slides pro .NET

Než se vrhneme na tutoriál, pojďme si krátce představit Aspose.Slides pro .NET. Je to výkonná knihovna, která umožňuje vývojářům vytvářet, upravovat, převádět a spravovat prezentace PowerPoint, aniž by vyžadovali samotný Microsoft PowerPoint. S Aspose.Slides for .NET můžete automatizovat různé úkoly související s prezentacemi v PowerPointu a zefektivnit tak proces vývoje.

## Předpoklady

Abyste mohli pokračovat v tomto tutoriálu, budete potřebovat následující:

1. Aspose.Slides for .NET: Ujistěte se, že máte knihovnu Aspose.Slides for .NET nainstalovanou a připravenou k použití ve vašem projektu .NET.

2. Zdrojová prezentace: Připravte si PowerPointovou prezentaci (PPTX), kterou chcete exportovat do formátu XAML. Ujistěte se, že znáte cestu k této prezentaci.

3. Výstupní adresář: Vyberte adresář, kam chcete uložit vygenerované soubory XAML.

## Krok 1: Nastavte svůj projekt

V tomto prvním kroku nastavíme náš projekt a ujistíme se, že máme připraveny všechny potřebné komponenty. Ujistěte se, že jste do projektu přidali odkaz na knihovnu Aspose.Slides for .NET.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// Cesta ke zdrojové prezentaci
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 Nahradit`"Your Document Directory"` s cestou k adresáři obsahujícímu zdrojovou PowerPoint prezentaci. Určete také výstupní adresář, kam se uloží vygenerované soubory XAML.

## Krok 2: Export prezentace do XAML

Nyní přistoupíme k exportu prezentace PowerPoint do formátu XAML. K dosažení tohoto cíle použijeme Aspose.Slides pro .NET. 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // Vytvořte možnosti převodu
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // Definujte si vlastní službu pro úsporu výstupu
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // Převést snímky
    pres.Save(xamlOptions);

    // Uložte soubory XAML do výstupního adresáře
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 V tomto fragmentu kódu načteme zdrojovou prezentaci, vytvoříme možnosti převodu XAML a definujeme vlastní službu pro úsporu výstupu pomocí`NewXamlSaver`. Soubory XAML pak uložíme do zadaného výstupního adresáře.

## Krok 3: Vlastní třída XAML Saver

 Abychom implementovali vlastní spořič XAML, vytvoříme třídu s názvem`NewXamlSaver` která implementuje`IXamlOutputSaver` rozhraní.

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

Tato třída se postará o ukládání souborů XAML do výstupního adresáře.

## Závěr

Gratulujeme! Úspěšně jste se naučili exportovat prezentaci PowerPoint do formátu XAML pomocí Aspose.Slides for .NET. To může být cenná dovednost při práci na projektech, které zahrnují manipulaci s prezentacemi.

Neváhejte a prozkoumejte další funkce a možnosti Aspose.Slides pro .NET, abyste vylepšili své úkoly automatizace aplikace PowerPoint.

## Nejčastější dotazy

1. ### Co je Aspose.Slides pro .NET?
Aspose.Slides for .NET je knihovna .NET pro programovou práci s prezentacemi PowerPoint.

2. ### Kde mohu získat Aspose.Slides pro .NET?
 Aspose.Slides pro .NET si můžete stáhnout z[tady](https://purchase.aspose.com/buy).

3. ### Je k dispozici bezplatná zkušební verze?
 Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides pro .NET[tady](https://releases.aspose.com/).

4. ### Jak mohu získat dočasnou licenci pro Aspose.Slides pro .NET?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).

5. ### Kde mohu získat podporu pro Aspose.Slides pro .NET?
 Můžete najít podporu a komunitní diskuse[tady](https://forum.aspose.com/).

 Další návody a zdroje naleznete na adrese[Dokumentace API Aspose.Slides](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
