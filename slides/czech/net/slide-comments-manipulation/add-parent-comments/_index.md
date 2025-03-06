---
title: Přidejte komentáře rodiče ke snímku pomocí Aspose.Slides
linktitle: Přidejte ke snímku komentáře rodičů
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se přidávat interaktivní komentáře a odpovědi do prezentací PowerPoint pomocí Aspose.Slides for .NET. Zvyšte zapojení a spolupráci.
weight: 12
url: /cs/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Chcete vylepšit své prezentace v PowerPointu interaktivními funkcemi? Aspose.Slides for .NET vám umožňuje začlenit komentáře a odpovědi a vytvořit tak pro vaše publikum dynamický a poutavý zážitek. V tomto podrobném tutoriálu vám ukážeme, jak přidat nadřazené komentáře ke snímkům pomocí Aspose.Slides for .NET. Pojďme se ponořit a prozkoumat tuto vzrušující funkci.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovaný Aspose.Slides for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/slides/net/).

2. Visual Studio: K vytvoření a spuštění aplikace .NET budete potřebovat Visual Studio.

3. Základní znalost C#: Tento tutoriál předpokládá, že máte základní znalosti o programování v C#.

Nyní, když máme pokryty předpoklady, přistoupíme k importu potřebných jmenných prostorů.

## Import jmenných prostorů

Nejprve budete muset do projektu importovat příslušné jmenné prostory. Tyto jmenné prostory poskytují třídy a metody potřebné pro práci s Aspose.Slides pro .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

S předpoklady a jmennými prostory na místě rozdělme proces do několika kroků pro přidávání nadřazených komentářů na snímek.

## Krok 1: Vytvořte prezentaci

Chcete-li začít, musíte vytvořit novou prezentaci pomocí Aspose.Slides for .NET. Tato prezentace bude plátnem, na které budete přidávat své komentáře.

```csharp
// Cesta k výstupnímu adresáři.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Sem bude umístěn váš kód pro přidávání komentářů.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 Ve výše uvedeném kódu nahraďte`"Output Path"` s požadovanou cestou pro vaši výstupní prezentaci.

## Krok 2: Přidejte autory komentáře

Před přidáním komentářů je třeba definovat autory těchto komentářů. V tomto příkladu máme dva autory, „Author_1“ a „Author_2“, z nichž každý je reprezentován instancí`ICommentAuthor`.

```csharp
// Přidat komentář
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Přidat odpověď na komentář 1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

V tomto kroku vytvoříme dva autory komentáře a přidáme počáteční komentář a odpověď na komentář.

## Krok 3: Přidejte další odpovědi

Chcete-li vytvořit hierarchickou strukturu komentářů, můžete k existujícím komentářům přidat další odpovědi. Zde přidáme druhou odpověď na "komentář1."

```csharp
// Přidat odpověď na komentář 1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Tím se vytvoří tok konverzace ve vaší prezentaci.

## Krok 4: Přidejte vnořené odpovědi

Komentáře mohou mít také vnořené odpovědi. Abychom to demonstrovali, přidáme odpověď na „odpověď 2 na komentář 1“, čímž vytvoříme dílčí odpověď.

```csharp
// Přidat odpověď k odpovědi
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Tento krok zdůrazňuje všestrannost Aspose.Slides pro .NET při správě hierarchií komentářů.

## Krok 5: Další komentáře a odpovědi

Podle potřeby můžete i nadále přidávat další komentáře a odpovědi. V tomto příkladu přidáme další dva komentáře a odpověď na jeden z nich.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Tento krok ukazuje, jak můžete vytvořit poutavý a interaktivní obsah pro vaše prezentace.

## Krok 6: Zobrazte hierarchii

Chcete-li vizualizovat hierarchii komentářů, můžete ji zobrazit na konzole. Tento krok je volitelný, ale může být užitečný pro ladění a pochopení struktury.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## Krok 7: Odstraňte komentáře

V některých případech může být nutné odstranit komentáře a jejich odpovědi. Níže uvedený fragment kódu ukazuje, jak odstranit „comment1“ a všechny jeho odpovědi.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Tento krok je užitečný pro správu a aktualizaci obsahu prezentace.

Pomocí těchto kroků můžete pomocí Aspose.Slides for .NET vytvářet prezentace s interaktivními komentáři a odpověďmi. Ať už chcete zaujmout své publikum nebo spolupracovat se členy týmu, tato funkce nabízí širokou škálu možností.

## Závěr

Aspose.Slides for .NET poskytuje výkonnou sadu nástrojů pro vylepšení vašich prezentací v PowerPointu. Díky možnosti přidávat komentáře a odpovědi můžete vytvářet dynamický a interaktivní obsah, který zaujme vaše publikum. Tento podrobný průvodce vám ukázal, jak přidat nadřazené komentáře ke snímkům, vytvořit hierarchii a dokonce v případě potřeby komentáře odstranit. Postupujte podle těchto kroků a prozkoumejte dokumentaci Aspose.Slides[tady](https://reference.aspose.com/slides/net/), můžete posunout své prezentace na další úroveň.

## Nejčastější dotazy

### Mohu přidávat komentáře ke konkrétním snímkům v rámci mé prezentace?
Ano, můžete přidávat komentáře k libovolnému snímku prezentace zadáním cílového snímku při vytváření komentáře.

### Je možné upravit vzhled komentářů v prezentaci?
Aspose.Slides for .NET umožňuje přizpůsobit vzhled komentářů, včetně jejich textu, informací o autorovi a umístění na snímku.

### Mohu exportovat komentáře a odpovědi do samostatného souboru?
Ano, můžete exportovat komentáře a odpovědi do samostatného souboru prezentace, jak je ukázáno v kroku 7.

### Je Aspose.Slides for .NET kompatibilní s nejnovějšími verzemi PowerPointu?
Aspose.Slides for .NET je navržen pro práci s širokou škálou verzí aplikace PowerPoint a zajišťuje kompatibilitu s nejnovějšími verzemi.

### Jsou pro Aspose.Slides pro .NET k dispozici nějaké možnosti licencování?
 Ano, na webu Aspose můžete prozkoumat možnosti licencování, včetně dočasných licencí[tady](https://purchase.aspose.com/buy) nebo vyzkoušejte bezplatnou zkušební verzi[tady](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
