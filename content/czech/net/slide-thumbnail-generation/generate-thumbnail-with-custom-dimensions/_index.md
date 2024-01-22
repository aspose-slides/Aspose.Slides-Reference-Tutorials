---
title: Generovat miniaturu v snímcích s vlastními dimenzemi
linktitle: Generování miniatur s vlastními dimenzemi
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se generovat vlastní miniatury z prezentací PowerPoint pomocí Aspose.Slides for .NET. Vylepšete uživatelskou zkušenost a funkčnost.
type: docs
weight: 13
url: /cs/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

Vytváření vlastních miniatur vašich prezentací v PowerPointu může být cenným přínosem, ať už vytváříte interaktivní aplikaci, vylepšujete uživatelskou zkušenost nebo optimalizujete obsah pro různé platformy. V tomto tutoriálu vás provedeme procesem generování vlastních miniatur obrázků z prezentací PowerPoint pomocí knihovny Aspose.Slides for .NET. Tato výkonná knihovna vám umožňuje manipulovat, převádět a vylepšovat soubory PowerPoint programově v aplikacích .NET.

## Předpoklady

Než se vrhneme na generování vlastních miniatur, ujistěte se, že máte splněny následující předpoklady:

### 1. Aspose.Slides pro .NET

 V projektu musíte mít nainstalovanou knihovnu Aspose.Slides for .NET. Pokud jste to ještě neudělali, můžete najít potřebnou dokumentaci a odkazy ke stažení[tady](https://reference.aspose.com/slides/net/).

### 2. PowerPointová prezentace

Ujistěte se, že máte prezentaci PowerPoint, ze které chcete vygenerovat vlastní miniaturu. Tato prezentace by měla být přístupná v adresáři vašeho projektu.

### 3. Vývojové prostředí

Abyste mohli postupovat podle tohoto kurzu, měli byste mít pracovní znalosti programování .NET pomocí C# a nastavené vývojové prostředí, jako je Visual Studio.

Nyní, když jsme pokryli předpoklady, pojďme si proces generování vlastních miniatur rozdělit na podrobné pokyny.

## Importovat jmenné prostory

Nejprve musíte do kódu C# zahrnout požadované jmenné prostory. Tyto jmenné prostory vám umožňují pracovat s Aspose.Slides a manipulovat s prezentacemi v PowerPointu.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Krok 1: Načtěte prezentaci

Chcete-li začít, načtěte prezentaci PowerPoint, ze které chcete vygenerovat vlastní miniaturu. Toho je dosaženo pomocí knihovny Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Vytvořte instanci třídy Presentation, která představuje soubor prezentace
using (Presentation pres = new Presentation(srcFileName))
{
    // Sem bude umístěn váš kód pro generování náhledů
}
```

## Krok 2: Otevřete snímek

V rámci načtené prezentace musíte přistupovat ke konkrétnímu snímku, ze kterého chcete vygenerovat vlastní miniaturu. Snímek si můžete vybrat podle indexu.

```csharp
// Přístup k prvnímu snímku (index můžete podle potřeby změnit)
ISlide sld = pres.Slides[0];
```

## Krok 3: Definujte vlastní rozměry miniatur

Zadejte požadované rozměry pro vlastní obrázek miniatury. Můžete definovat šířku a výšku v pixelech podle požadavků vaší aplikace.

```csharp
int desiredX = 1200; // Šířka
int desiredY = 800;  // Výška
```

## Krok 4: Vypočítejte škálovací faktory

Chcete-li zachovat poměr stran snímku, vypočítejte faktory měřítka pro rozměry X a Y na základě velikosti snímku a požadovaných rozměrů.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Krok 5: Vygenerujte obrázek miniatury

Vytvořte snímek snímku v plném měřítku se zadanými vlastními rozměry a uložte jej na disk ve formátu JPEG.

```csharp
// Vytvořte obrázek v plném měřítku
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Uložte obrázek na disk ve formátu JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nyní, když jste provedli tyto kroky, měli byste úspěšně vygenerovat vlastní miniaturu z prezentace PowerPoint.

## Závěr

Generování vlastních miniatur obrázků z prezentací PowerPoint pomocí Aspose.Slides for .NET je cenná dovednost, která může vylepšit uživatelskou zkušenost a funkčnost vašich aplikací. Podle kroků uvedených v tomto kurzu můžete snadno vytvořit vlastní miniatury, které splňují vaše specifické požadavky.

---

## Často kladené otázky (FAQ)

### Co je Aspose.Slides pro .NET?
Aspose.Slides for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s PowerPointovými prezentacemi programově v aplikacích .NET.

### Kde najdu dokumentaci k Aspose.Slides pro .NET?
 Dokumentaci najdete[tady](https://reference.aspose.com/slides/net/).

### Je Aspose.Slides for .NET zdarma k použití?
 Aspose.Slides for .NET je komerční knihovna. Můžete najít informace o cenách a licencích[tady](https://purchase.aspose.com/buy).

### Potřebuji pokročilé znalosti programování, abych mohl používat Aspose.Slides pro .NET?
Zatímco určitá znalost programování .NET je prospěšná, Aspose.Slides for .NET poskytuje uživatelsky přívětivé rozhraní API, které zjednodušuje práci s prezentacemi v PowerPointu.

### Je k dispozici technická podpora pro Aspose.Slides pro .NET?
 Ano, máte přístup k technické podpoře a komunitním fórům[tady](https://forum.aspose.com/).