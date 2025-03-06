---
title: Zvládnutí efektů po animaci v PowerPointu pomocí Aspose.Slides
linktitle: Kontrola po typu animace na snímku
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se ovládat efekty po animaci ve snímcích PowerPoint pomocí Aspose.Slides for .NET. Vylepšete své prezentace dynamickými vizuálními prvky.
weight: 11
url: /cs/net/slide-animation-control/control-after-animation-type/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
Vylepšení vašich prezentací pomocí dynamických animací je zásadním aspektem pro zapojení publika. Aspose.Slides for .NET poskytuje výkonné řešení pro ovládání efektů po animaci ve snímcích. V tomto tutoriálu vás provedeme procesem použití Aspose.Slides pro .NET k manipulaci s typem následné animace na snímcích. Podle tohoto podrobného průvodce budete moci vytvářet interaktivnější a vizuálně přitažlivější prezentace.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte na svém místě následující:
- Základní znalost programování v C# a .NET.
-  Nainstalovaná knihovna Aspose.Slides for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/slides/net/).
- Integrované vývojové prostředí (IDE), jako je Visual Studio.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů pro přístup k funkcím Aspose.Slides. Přidejte do kódu následující řádky:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
Nyní si pro lepší pochopení rozdělíme poskytnutý kód do několika kroků:
## Krok 1: Nastavte adresář dokumentů
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Ujistěte se, že zadaný adresář existuje, nebo jej vytvořte, pokud neexistuje.
## Krok 2: Definujte cestu k výstupnímu souboru
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
Zadejte cestu k výstupnímu souboru pro upravenou prezentaci.
## Krok 3: Načtěte prezentaci
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
Vytvořte instanci třídy Prezentace a načtěte existující prezentaci.
## Krok 4: Upravte efekty po animaci na snímku 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
Naklonujte první snímek, otevřete jeho časovou osu a nastavte efekt po animaci na „Skrýt při příštím kliknutí myší“.
## Krok 5: Upravte efekty po animaci na snímku 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
Znovu naklonujte první snímek, tentokrát změňte efekt po animaci na „Barva“ se zelenou barvou.
## Krok 6: Upravte efekty po animaci na snímku 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
Klonujte ještě jednou první snímek a nastavte efekt po animaci na „Skrýt po animaci“.
## Krok 7: Uložte upravenou prezentaci
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
Uložte upravenou prezentaci se zadanou cestou k výstupnímu souboru.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak ovládat efekty po animaci na snímcích pomocí Aspose.Slides for .NET. Experimentujte s různými typy následné animace a vytvořte dynamičtější a poutavější prezentace.
## Nejčastější dotazy
### Mohu na jednotlivé prvky snímku použít různé efekty po animaci?
Ano můžeš. Iterujte prvky a podle toho upravte jejich efekty po animaci.
### Je Aspose.Slides kompatibilní s nejnovějšími verzemi .NET?
Ano, Aspose.Slides je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi .NET frameworku.
### Jak mohu přidat vlastní animace do snímků pomocí Aspose.Slides?
 Viz dokumentace[tady](https://reference.aspose.com/slides/net/) pro podrobné informace o přidávání vlastních animací.
### Jaké formáty souborů podporuje Aspose.Slides pro ukládání prezentací?
Aspose.Slides podporuje různé formáty, včetně PPTX, PPT, PDF a dalších. Úplný seznam naleznete v dokumentaci.
### Kde mohu získat podporu nebo klást otázky týkající se Aspose.Slides?
 Navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) za podporu a interakci s komunitou.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
