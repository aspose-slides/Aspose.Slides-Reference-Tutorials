---
"date": "2025-04-23"
"description": "Naučte se, jak přizpůsobit barvy hypertextových odkazů v prezentacích PowerPointu pomocí Aspose.Slides pro Python. Efektivně vylepšete své snímky pomocí personalizovaných stylů odkazů."
"title": "Jak nastavit barvy hypertextových odkazů v PowerPointu pomocí Aspose.Slides pro Python"
"url": "/cs/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak nastavit barvy hypertextových odkazů v PowerPointu pomocí Aspose.Slides pro Python

## Zavedení

Vylepšení vizuální atraktivity vašich prezentací v PowerPointu úpravou barev hypertextových odkazů je s Aspose.Slides pro Python snadné. Tato příručka vás provede nastavením hypertextových odkazů se specifickými barvami ve vašich slidech pomocí Pythonu.

**Co se naučíte:**
- Jak nastavit barvu hypertextového odkazu v textových obrazcích v PowerPointu.
- Kroky potřebné k vytvoření vizuálně poutavé prezentace.
- Klíčové vlastnosti Aspose.Slides pro Python, které usnadňují toto přizpůsobení.

Než začneme, pojďme se ponořit do potřebných předpokladů.

## Předpoklady

Než začnete, ujistěte se, že je vaše prostředí připraveno s následujícími funkcemi:
- **Knihovny a verze:** Instalovat `aspose.slides` knihovna. Ujistěte se, že máte na počítači nainstalovaný Python.
- **Požadavky na nastavení prostředí:** Tento tutoriál předpokládá základní nastavení Pythonu na Windows, Mac nebo Linux.
- **Předpoklady znalostí:** Znalost programování v Pythonu bude výhodou.

## Nastavení Aspose.Slides pro Python

Chcete-li začít používat Aspose.Slides pro Python, nainstalujte balíček pomocí pipu:

```bash
pip install aspose.slides
```

**Kroky pro získání licence:**
- **Bezplatná zkušební verze:** Stáhněte si zkušební verzi z [Stránka s vydáním Aspose](https://releases.aspose.com/slides/python-net/).
- **Dočasná licence:** Požádejte o dočasnou licenci na [stránka nákupu](https://purchase.aspose.com/temporary-license/) pro prodloužený přístup.
- **Nákup:** Chcete-li plně odemknout funkce bez omezení, zvažte zakoupení licence od [Nákupní stránka Aspose](https://purchase.aspose.com/buy).

**Základní inicializace:**
Po instalaci a licenci importujte Aspose.Slides do svého skriptu:

```python
import aspose.slides as slides
```

## Průvodce implementací

Tato část vás provede nastavením barev hypertextových odkazů v prezentaci PowerPoint.

### Funkce nastavení barvy hypertextového odkazu

#### Přehled

Upravte barvu hypertextových odkazů vložených do textových tvarů pomocí Aspose.Slides pro Python. Tím se zlepší čitelnost a vizuální atraktivita.

##### Krok 1: Vytvořte novou prezentaci

Vytvořte instanci prezentace:

```python
with slides.Presentation() as presentation:
    # Váš kód zde
```

##### Krok 2: Přidání tvaru s textem

Přidejte na první snímek obdélníkový tvar a vložte text, který obsahuje hypertextový odkaz.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Krok 3: Nastavení vlastností hypertextového odkazu

Přiřaďte hypertextový odkaz a nastavte jeho barvu. `hyperlink_click` Vlastnost určuje, kam se má odkaz po kliknutí přesunout.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Nastavte zdroj barev pro hypertextový odkaz na formát části a definujte typ a barvu výplně.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Krok 4: Uložte prezentaci

Uložte prezentaci do zadaného adresáře:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}