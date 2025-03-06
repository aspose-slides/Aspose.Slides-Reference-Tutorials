---
title: Vygenerujte miniaturu z Slide in Notes
linktitle: Vygenerujte miniaturu z Slide in Notes
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se generovat miniatury ze snímků v sekci poznámek vaší prezentace pomocí Aspose.Slides for .NET. Vylepšete svůj vizuální obsah!
weight: 12
url: /cs/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Ve světě moderních prezentací je vizuální obsah králem. Vytváření atraktivních diapozitivů je nezbytné pro efektivní komunikaci. Jedním ze způsobů, jak vylepšit své prezentace, je generování miniatur ze snímků, zvláště když chcete zdůraznit konkrétní detaily nebo sdílet přehled. Aspose.Slides for .NET je výkonný nástroj, který vám toho může pomoci bez problémů dosáhnout. V tomto podrobném průvodci vás provedeme procesem generování miniatur ze snímků v sekci poznámek prezentace pomocí Aspose.Slides for .NET.

## Předpoklady

Než se ponoříme do podrobností, měli byste mít splněny následující předpoklady:

### 1. Aspose.Slides pro .NET

 Ujistěte se, že máte Aspose.Slides for .NET nainstalované a nastavené. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).

### 2. Prostředí .NET

V systému byste měli mít připravené vývojové prostředí .NET.

### 3. Soubor prezentace

 Mít soubor prezentace (např.`ThumbnailFromSlideInNotes.pptx`), ze kterého chcete generovat náhledy.

Nyní si celý proces rozdělíme na kroky:

## Krok 1: Import jmenných prostorů

Nejprve musíte importovat potřebné jmenné prostory pro práci s Aspose.Slides. Na začátek skriptu C# přidejte následující kód:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Krok 2: Načtěte prezentaci

 Dále budete muset načíst soubor prezentace, který obsahuje snímky s poznámkami. Pomocí následujícího kódu vytvořte instanci a`Presentation` třída:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Váš kód je zde
}
```

## Krok 3: Otevřete snímek

Můžete si vybrat, pro který snímek v prezentaci chcete vygenerovat miniaturu. V tomto příkladu přistoupíme k prvnímu snímku:

```csharp
ISlide sld = pres.Slides[0];
```

## Krok 4: Definujte požadované rozměry

Zadejte rozměry (šířku a výšku) pro miniaturu, kterou chcete vygenerovat. Například:

```csharp
int desiredX = 1200; // Šířka
int desiredY = 800;  // Výška
```

## Krok 5: Vypočítejte škálovací faktory

Chcete-li zajistit, aby miniatura odpovídala požadovaným rozměrům, vypočítejte faktory měřítka následovně:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Krok 6: Vytvořte miniaturu

Nyní vytvořte miniaturu obrázku v plném měřítku pomocí vypočtených faktorů měřítka:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Krok 7: Uložte miniaturu

Nakonec uložte vygenerovanou miniaturu jako obrázek JPEG:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

je to! Úspěšně jste vygenerovali miniaturu ze snímku v sekci poznámek vaší prezentace pomocí Aspose.Slides for .NET.

## Závěr

Začlenění miniatur do vašich prezentací může výrazně zlepšit jejich vizuální přitažlivost a efektivitu. Aspose.Slides for .NET činí tento proces přímočarým a umožňuje vám snadno vytvářet přizpůsobené miniatury z vašich snímků.

## Často kladené otázky (FAQ)

### V jakých formátech mohu uložit vygenerované náhledy?
Miniatury můžete uložit v různých formátech, včetně JPEG, PNG a dalších, v závislosti na vašich požadavcích.

### Mohu generovat náhledy pro více snímků najednou?
Ano, můžete procházet snímky v prezentaci a vytvářet miniatury pro každý z nich.

### Je Aspose.Slides for .NET kompatibilní s různými .NET frameworky?
Ano, Aspose.Slides for .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Framework.

### Mohu upravit vzhled generovaných miniatur?
Absolutně! Aspose.Slides for .NET poskytuje možnosti pro přizpůsobení vzhledu miniatur, jako jsou rozměry, kvalita a další.

### Kde mohu získat podporu nebo další pomoc s Aspose.Slides pro .NET?
 Můžete najít pomoc a zapojit se do komunity Aspose na adrese[Aspose Support Forum](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
