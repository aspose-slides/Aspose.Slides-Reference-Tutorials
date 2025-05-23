---
"date": "2025-04-17"
"description": "Naučte se, jak vyloučit výchozí písma během převodu HTML pomocí Aspose.Slides pro Javu a zajistit tak konzistentní typografii napříč platformami."
"title": "Jak vyloučit výchozí písma z HTML konverze pomocí Aspose.Slides pro Javu"
"url": "/cs/java/export-conversion/exclude-default-fonts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vyloučit výchozí písma z převodu HTML pomocí Aspose.Slides pro Javu
## Zavedení
Při převodu prezentací do HTML je zachování vlastních písem klíčové kvůli výchozímu nastavení písem. Tato příručka ukazuje, jak vám Aspose.Slides pro Javu může pomoci vyloučit tato výchozí nastavení a zajistit konzistentní typografii napříč různými platformami.
**Co se naučíte:**
- Nastavení prostředí s Aspose.Slides pro Javu
- Techniky pro vyloučení výchozích písem během převodu HTML
- Klíčové možnosti konfigurace a jejich vliv na výstup
- Praktické aplikace v reálných situacích
Začněme diskusí o předpokladech, než se ponoříme do implementační příručky.
## Předpoklady
Abyste mohli tento tutoriál efektivně sledovat, ujistěte se, že máte:
- **Aspose.Slides pro knihovnu Java**Nainstalujte verzi 25.4 nebo novější.
- **Vývojová sada pro Javu (JDK)**Tento příklad kódu je zaměřen na JDK 16; ujistěte se, že je nainstalován na vašem počítači.
- **Základní znalosti programování v Javě**Předpokládá se znalost syntaxe jazyka Java a základních programovacích konceptů.
## Nastavení Aspose.Slides pro Javu
### Instalace závislostí
**Znalec:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
Nebo si knihovnu stáhněte přímo z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).
### Získání licence
Začněte s bezplatnou zkušební verzí nebo si požádejte o dočasnou licenci, abyste mohli prozkoumat všechny funkce bez omezení. Pro dlouhodobé používání se doporučuje zakoupení licence.
**Základní nastavení:**
Inicializace Aspose.Slides ve vašem projektu:
```java
import com.aspose.slides.Presentation;

public class Main {
    public static void main(String[] args) {
        Presentation pres = new Presentation("your-pptx-file-path");
        // Váš kód pro manipulaci s prezentací
    }
}
```
## Průvodce implementací
### Přehled funkcí: Vyloučení výchozích písem z převodu HTML
Tato funkce pomáhá přizpůsobit zpracování písem během převodu souborů PowerPoint do HTML, čímž zlepšuje branding a konzistenci.
#### Krok 1: Připravte si prostředí
Ujistěte se, že je soubor Aspose.Slides správně nastaven podle výše uvedených pokynů. To zahrnuje přidání závislostí nebo stažení souboru JAR přímo do vašeho projektu.
#### Krok 2: Načtení prezentace
Načtěte prezentaci pomocí `Presentation` třída:
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/presentation.pptx";
try {
    Presentation pres = new Presentation(dataDir);
```
#### Krok 3: Definování výjimek písem
Vytvořte pole pro určení písem, která chcete vyloučit. V tomto příkladu začínáme s prázdným seznamem jako zástupným symbolem:
```java
String[] fontNameExcludeList = {};
```
#### Krok 4: Inicializace vlastního HTML kontroleru
Ten/Ta/To `LinkAllFontsHtmlController` Třída se používá pro vlastní zpracování písem během procesu převodu.
```java
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "YOUR_DOCUMENT_DIRECTORY");
```
#### Krok 5: Konfigurace možností HTML
Nastavte si `HtmlOptions` použití vlastního formátovače:
```java
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
```
#### Krok 6: Uložit jako HTML
Nakonec uložte převedenou prezentaci ve formátu HTML:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/pres.html", SaveFormat.Html, htmlOptionsEmbed);
} catch (Exception e) {
    e.printStackTrace();
}
```
**Vysvětlení:** Tento úryvek kódu ukazuje, jak vyloučit výchozí písma konfigurací vlastního formátovače během převodu HTML.
## Praktické aplikace
1. **Webové prezentace**Vkládejte prezentace na firemní webové stránky a zároveň zachovávejte konzistenci značky.
2. **Přenositelnost dokumentů**Zajistěte, aby dokumenty vypadaly stejně na různých zařízeních a platformách.
3. **Integrace s redakčním systémem (CMS)**Bezproblémová integrace do systémů pro správu obsahu, kde jsou vlastní písma nezbytná.
## Úvahy o výkonu
- **Optimalizace využití paměti**Využijte funkce správy paměti v Aspose.Slides k efektivnímu zpracování velkých prezentací.
- **Správa zdrojů**Po operacích řádně uzavřete streamy, abyste uvolnili zdroje.
- **Nejlepší postupy**Pravidelně aktualizujte verzi knihovny pro vylepšení výkonu a opravy chyb.
## Závěr
Naučili jste se, jak vyloučit výchozí písma během převodu HTML pomocí Aspose.Slides pro Javu. Tato funkce zvyšuje konzistenci prezentace napříč různými platformami, což je klíčové pro branding a profesionální dokumentaci.
Chcete-li si dále vylepšit své dovednosti, prozkoumejte další funkce Aspose.Slides nebo tuto funkcionalitu integrujte do větších projektů.
**Další kroky:**
Experimentujte s různými vyloučeními písem a sledujte, jak ovlivňují konečný HTML výstup. Zvažte integraci těchto technik do automatizovaných pracovních postupů pro zefektivnění procesů převodu dokumentů.
## Sekce Často kladených otázek
1. **Co je Aspose.Slides pro Javu?**
   - Výkonná knihovna pro manipulaci s prezentacemi v aplikacích Java.
2. **Jak získám licenci pro dlouhodobé užívání?**
   - Navštivte [stránka nákupu](https://purchase.aspose.com/buy) koupit nebo se informovat o možnostech licencování.
3. **Mohu vyloučit více písem současně?**
   - Ano, přidejte všechny názvy písem, které chcete vyloučit, do `fontNameExcludeList` pole.
4. **Co mám dělat, když v mém HTML výstupu chybí písma?**
   - Ujistěte se, že je váš vlastní HTML kontroler správně nakonfigurován a cesty jsou přesně nastaveny.
5. **Má vyloučení písem nějaký dopad na výkon?**
   - Výkon může být ovlivněn velkými knihovnami písem; v případě potřeby optimalizujte pomocí funkcí správy paměti Aspose.
## Zdroje
- [Dokumentace](https://reference.aspose.com/slides/java/)
- [Stáhnout knihovnu](https://releases.aspose.com/slides/java/)
- [Zakoupit licenci](https://purchase.aspose.com/buy)
- [Bezplatná zkušební verze](https://releases.aspose.com/slides/java/)
- [Dočasná licence](https://purchase.aspose.com/temporary-license/)
- [Fórum podpory](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}