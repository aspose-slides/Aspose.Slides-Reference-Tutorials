---
"date": "2025-04-24"
"description": "Naučte se, jak vytvářet a spravovat pravidla pro záložní písma pomocí Aspose.Slides pro Python, abyste zajistili konzistenci vašich prezentací napříč různými systémy."
"title": "Zvládnutí záložních fontů v Aspose.Slides pro Python&#58; Komplexní průvodce"
"url": "/cs/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Zvládnutí záložních fontů v Aspose.Slides pro Python: Komplexní průvodce

## Zavedení

Problémy s kompatibilitou písem mohou být při vytváření prezentací náročné, zejména u znaků Unicode, které primární písma nepodporují. **Aspose.Slides pro Python** poskytuje robustní řešení prostřednictvím pravidel pro záložní písma, které zajišťuje vizuální přitažlivost a čitelnost vaší prezentace napříč různými systémy.

této příručce se podíváme na to, jak vytvářet a spravovat pravidla pro záložní fonty pomocí Aspose.Slides pro Python. Naučíte se:
- Nastavení prostředí pomocí Aspose.Slides
- Vytvoření kolekce pravidel pro záložní písma
- Správa těchto pravidel přidáním nebo odebráním písem na základě rozsahů Unicode
- Aplikace pravidel na prezentace a vykreslování snímků jako obrázků

Začněme přípravou vašeho prostředí.

## Předpoklady

Ujistěte se, že je vaše prostředí pro tento úkol připraveno. Zde je to, co budete potřebovat:
1. **Aspose.Slides pro Python**Tato knihovna spravuje pravidla pro záložní fonty.
2. **Prostředí Pythonu**Ujistěte se, že je nainstalován Python (verze 3.6 nebo novější).
3. **Základní znalost Pythonu**Znalost syntaxe a konceptů Pythonu nám bude užitečná, když se ponoříme do úryvků kódu.

## Nastavení Aspose.Slides pro Python

### Instalace

Chcete-li začít, nainstalujte si knihovnu Aspose.Slides pomocí pipu:

```bash
pip install aspose.slides
```

### Získání licence

Aspose nabízí bezplatnou zkušební licenci pro prozkoumání jeho funkcí bez omezení. Zde je návod, jak ji získat:
- Návštěva [Nákupní stránka Aspose](https://purchase.aspose.com/buy) pro zakoupení doplňků nebo přístup k dočasné licenci.
- Nebo si stáhněte bezplatnou zkušební verzi z [Sekce ke stažení](https://releases.aspose.com/slides/python-net/).

### Základní inicializace

Po instalaci inicializujte Aspose.Slides ve vašem Python skriptu:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Průvodce implementací

### Vytváření a správa pravidel pro záložní písma

#### Přehled

Pravidla pro záložní písma zajišťují, že všechny znaky v prezentaci mají vhodné písmo, a tím zachovává čitelnost pro jazyky s jedinečnými znakovými sadami.

#### Kroky implementace

**1. Vytvořte kolekci pravidel pro záložní písma**

Začněte vytvořením kolekce pro definování záložních fontů:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Přidejte pravidlo pro záložní písmo**

Definujte pravidlo specifikující rozsah kódování Unicode a záložní písmo:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Parametry**: `0x400` je začátek rozsahu Unicode, `0x4FF` je konec a `"Times New Roman"` je záložní písmo.

**3. Správa stávajících pravidel**

Iterujte přes každé pravidlo a upravte ho podle potřeby:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Odstranění pravidla**

V případě potřeby odeberte první pravidlo ze své kolekce:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Použití pravidel pro záložní písma v prezentaci a vykreslení obrázku

#### Přehled

Jakmile jsou pravidla pro záložní písma nastavena, použijte je v prezentacích, abyste zajistili, že text v případě potřeby použije zadaná záložní písma.

#### Kroky implementace

**1. Inicializujte své prostředí**

Připravte adresáře pro vstup a výstup:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Použití záložních pravidel na prezentaci**

Načtěte soubor prezentace a použijte pravidla písma:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}