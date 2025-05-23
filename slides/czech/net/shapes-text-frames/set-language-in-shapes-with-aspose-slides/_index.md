---
"date": "2025-04-16"
"description": "Naučte se, jak nastavit atributy jazyka pro text v obrazcích pomocí Aspose.Slides pro .NET. Tato příručka se zabývá přidáváním automatických obrazců, nastavením ID jazyků a ukládáním prezentací."
"title": "Jak nastavit jazyk v obrazcích PowerPointu pomocí Aspose.Slides pro .NET"
"url": "/cs/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak nastavit jazyk v obrazcích PowerPointu pomocí Aspose.Slides pro .NET

Ve světě digitálních prezentací může být zajištění přístupnosti a správného formátování obsahu v různých jazycích náročné. S Aspose.Slides pro .NET můžete snadno nastavit jazykové atributy pro text v obrazcích v PowerPointových snímcích. Tato funkce je obzvláště užitečná při přípravě vícejazyčných dokumentů nebo zajištění konzistence v globální komunikaci.

**Co se naučíte:**
- Přidávání automatických tvarů a vkládání textu do nich.
- Nastavení ID jazyka pro textové části pomocí Aspose.Slides.
- Ukládání prezentací s vlastními konfiguracemi.

Pojďme se ponořit do toho, jak můžete tuto funkci bezproblémově implementovat.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- **Knihovny a závislosti**Musíte mít nainstalovanou knihovnu Aspose.Slides pro .NET. Tato knihovna je nezbytná pro práci s prezentacemi v PowerPointu v jazyce C#.
  
- **Nastavení prostředí**Je vyžadováno vývojové prostředí s .NET Core nebo .NET Framework.

- **Předpoklady znalostí**Znalost základních konceptů programování v C# a pochopení principů objektově orientovaného programování bude užitečná.

## Nastavení Aspose.Slides pro .NET

Pro začátek je potřeba nainstalovat knihovnu Aspose.Slides. Můžete to provést jednou z následujících metod:

**Rozhraní příkazového řádku .NET**
```shell
dotnet add package Aspose.Slides
```

**Správce balíčků**
```powershell
Install-Package Aspose.Slides
```

**Uživatelské rozhraní Správce balíčků NuGet**
Vyhledejte „Aspose.Slides“ a nainstalujte nejnovější verzi.

### Získání licence

Můžete začít s bezplatnou zkušební verzí stažením dočasné licence z [zde](https://purchase.aspose.com/temporary-license/)Pro trvalé používání zvažte zakoupení licence prostřednictvím [tento odkaz](https://purchase.aspose.com/buy).

Jakmile budete mít nastavení připravené, inicializujte Aspose.Slides ve vašem projektu:

```csharp
using Aspose.Slides;
```

## Průvodce implementací

Nyní, když jsme vše nastavili, implementujme funkci pro nastavení jazyka pro text tvaru.

### Přehled funkcí: Nastavení jazyka textu tvaru

Tato funkce umožňuje určit jazyk textu v obrazci PowerPointu. Nastavením ID jazyka zajistíte správné použití kontroly pravopisu a dalších funkcí specifických pro daný jazyk.

#### Krok 1: Inicializace prezentace

Začněte vytvořením instance `Presentation` třída.

```csharp
using (Presentation pres = new Presentation())
{
    // Váš kód zde
}
```

Tím se inicializuje nový objekt prezentace v PowerPointu, se kterým budeme manipulovat.

#### Krok 2: Přidání automatického tvaru a textového rámečku

Přidejte na snímek obdélníkový tvar a vložte do něj text:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Zde, `AddAutoShape` přidá obdélník k prvnímu snímku. Parametry definují jeho polohu a velikost.

#### Krok 3: Nastavení ID jazyka

Nastavte jazyk pro textovou část v obrazci:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Tím se jako jazyk pro kontrolu pravopisu nastaví angličtina (UK).

#### Krok 4: Uložte prezentaci

Nakonec uložte prezentaci do zadané cesty:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}