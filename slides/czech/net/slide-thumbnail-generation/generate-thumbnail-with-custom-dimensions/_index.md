---
"description": "Naučte se, jak generovat vlastní miniatury obrázků z prezentací v PowerPointu pomocí Aspose.Slides pro .NET. Vylepšete uživatelský zážitek a funkčnost."
"linktitle": "Generovat miniaturu s vlastními rozměry"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Generování miniatur ve slidech s vlastními rozměry"
"url": "/cs/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Generování miniatur ve slidech s vlastními rozměry


Vytváření vlastních miniatur vašich prezentací v PowerPointu může být cenným přínosem, ať už vytváříte interaktivní aplikaci, vylepšujete uživatelský zážitek nebo optimalizujete obsah pro různé platformy. V tomto tutoriálu vás provedeme procesem generování vlastních miniatur z prezentací v PowerPointu pomocí knihovny Aspose.Slides pro .NET. Tato výkonná knihovna umožňuje programově manipulovat, převádět a vylepšovat soubory PowerPointu v aplikacích .NET.

## Předpoklady

Než se pustíme do generování vlastních miniaturních obrázků, ujistěte se, že máte splněny následující předpoklady:

### 1. Aspose.Slides pro .NET

Ve svém projektu musíte mít nainstalovanou knihovnu Aspose.Slides pro .NET. Pokud ji ještě nemáte, naleznete zde potřebnou dokumentaci a odkazy ke stažení. [zde](https://reference.aspose.com/slides/net/).

### 2. Prezentace v PowerPointu

Ujistěte se, že máte prezentaci v PowerPointu, ze které chcete vygenerovat vlastní náhledový obrázek. Tato prezentace by měla být dostupná v adresáři vašeho projektu.

### 3. Vývojové prostředí

Abyste mohli tento tutoriál zvládnout, měli byste mít pracovní znalost programování v .NET s použitím jazyka C# a nastavené vývojové prostředí, například Visual Studio.

Nyní, když jsme si probrali předpoklady, pojďme si rozebrat proces generování vlastních miniatur do podrobných pokynů.

## Importovat jmenné prostory

Nejprve je třeba do kódu C# zahrnout požadované jmenné prostory. Tyto jmenné prostory vám umožní pracovat s Aspose.Slides a manipulovat s prezentacemi v PowerPointu.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Krok 1: Načtení prezentace

Nejprve načtěte prezentaci v PowerPointu, ze které chcete vygenerovat vlastní náhledový obrázek. Toho dosáhnete pomocí knihovny Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Vytvořte instanci třídy Presentation, která reprezentuje soubor s prezentací.
using (Presentation pres = new Presentation(srcFileName))
{
    // Váš kód pro generování miniatur bude zde
}
```

## Krok 2: Přístup ke snímku

V načtené prezentaci musíte přistupovat ke konkrétnímu snímku, ze kterého chcete vygenerovat vlastní náhledový obrázek. Snímek můžete vybrat podle jeho indexu.

```csharp
// Přístup k prvnímu snímku (index můžete dle potřeby změnit)
ISlide sld = pres.Slides[0];
```

## Krok 3: Definování vlastních rozměrů miniatur

Zadejte požadované rozměry pro vlastní miniaturu. Šířku a výšku můžete definovat v pixelech podle požadavků vaší aplikace.

```csharp
int desiredX = 1200; // Šířka
int desiredY = 800;  // Výška
```

## Krok 4: Výpočet faktorů škálování

Chcete-li zachovat poměr stran snímku, vypočítejte faktory měřítka pro rozměry X a Y na základě velikosti snímku a požadovaných rozměrů.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Krok 5: Vytvoření miniatury

Vytvořte obrázek snímku v plné velikosti se zadanými vlastními rozměry a uložte jej na disk ve formátu JPEG.

```csharp
// Vytvořte obrázek v plné velikosti
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Uložte obrázek na disk ve formátu JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nyní, když jste provedli tyto kroky, měli byste úspěšně vygenerovat vlastní miniaturu z vaší prezentace v PowerPointu.

## Závěr

Generování vlastních miniatur z prezentací v PowerPointu pomocí Aspose.Slides pro .NET je cenná dovednost, která může vylepšit uživatelský zážitek a funkčnost vašich aplikací. Dodržováním kroků uvedených v tomto tutoriálu můžete snadno vytvořit vlastní miniatury, které splňují vaše specifické požadavky.

---

## Často kladené otázky (FAQ)

### Co je Aspose.Slides pro .NET?
Aspose.Slides pro .NET je výkonná knihovna, která umožňuje vývojářům programově pracovat s prezentacemi v PowerPointu v aplikacích .NET.

### Kde najdu dokumentaci k Aspose.Slides pro .NET?
Dokumentaci najdete [zde](https://reference.aspose.com/slides/net/).

### Je Aspose.Slides pro .NET zdarma?
Aspose.Slides pro .NET je komerční knihovna. Informace o cenách a licencích naleznete zde [zde](https://purchase.aspose.com/buy).

### Potřebuji pokročilé programátorské dovednosti k používání Aspose.Slides pro .NET?
I když je znalost programování v .NET výhodou, Aspose.Slides pro .NET poskytuje uživatelsky přívětivé API, které zjednodušuje práci s prezentacemi v PowerPointu.

### Je k dispozici technická podpora pro Aspose.Slides pro .NET?
Ano, máte přístup k technické podpoře a komunitním fórům [zde](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}