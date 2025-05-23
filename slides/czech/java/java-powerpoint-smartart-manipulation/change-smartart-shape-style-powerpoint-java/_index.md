---
"description": "Naučte se, jak změnit styly SmartArt v prezentacích PowerPointu pomocí Javy s Aspose.Slides pro Javu. Vylepšete své prezentace."
"linktitle": "Změna stylu tvaru SmartArt v PowerPointu pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Změna stylu tvaru SmartArt v PowerPointu pomocí Javy"
"url": "/cs/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Změna stylu tvaru SmartArt v PowerPointu pomocí Javy

## Zavedení
Ve světě vývoje v Javě je vytváření působivých prezentací často nutností. Ať už jde o obchodní prezentace, vzdělávací účely nebo prosté sdílení informací, prezentace v PowerPointu jsou běžným médiem. Někdy však výchozí styly a formáty poskytované PowerPointem nemusí plně vyhovovat našim potřebám. A právě zde přichází na řadu Aspose.Slides for Java.
Aspose.Slides pro Javu je robustní knihovna, která umožňuje vývojářům v Javě programově pracovat s prezentacemi v PowerPointu. Nabízí širokou škálu funkcí, včetně možnosti manipulace s tvary, styly, animacemi a mnoha dalšími. V tomto tutoriálu se zaměříme na jeden konkrétní úkol: změnu stylu tvaru SmartArt v prezentacích v PowerPointu pomocí Javy.
## Předpoklady
Než se pustíte do tutoriálu, je třeba splnit několik předpokladů:
1. Vývojová sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou sadu JDK. Nejnovější verzi si můžete stáhnout a nainstalovat z webových stránek společnosti Oracle.
2. Knihovna Aspose.Slides pro Java: Budete si muset stáhnout a zahrnout knihovnu Aspose.Slides pro Java do svého projektu. Odkaz pro stažení naleznete [zde](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si preferované IDE pro vývoj v Javě. Oblíbenou volbou jsou IntelliJ IDEA, Eclipse nebo NetBeans.

## Importovat balíčky
Než začneme s kódováním, importujme si do našeho projektu v Javě potřebné balíčky. Tyto balíčky nám umožní bezproblémově pracovat s funkcemi Aspose.Slides.
```java
import com.aspose.slides.*;
```
## Krok 1: Načtení prezentace
Nejprve musíme načíst prezentaci v PowerPointu, kterou chceme upravit.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## Krok 2: Procházení tvarů
Dále projdeme všechny tvary v prvním snímku prezentace.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## Krok 3: Zkontrolujte typ prvku SmartArt
U každého tvaru zkontrolujeme, zda se jedná o tvar SmartArt.
```java
if (shape instanceof ISmartArt)
```
## Krok 4: Přenesení do SmartArt
Pokud je tvar objekt SmartArt, přetypujeme ho do `ISmartArt` rozhraní.
```java
ISmartArt smart = (ISmartArt) shape;
```
## Krok 5: Zkontrolujte a změňte styl
Pak zkontrolujeme aktuální styl prvku SmartArt a v případě potřeby jej změníme.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## Krok 6: Uložení prezentace
Nakonec upravenou prezentaci uložíme do nového souboru.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak změnit styl tvaru SmartArt v prezentacích v PowerPointu pomocí Javy a knihovny Aspose.Slides pro Javu. Podle podrobného návodu si můžete snadno přizpůsobit vzhled tvarů SmartArt tak, aby lépe vyhovoval vašim potřebám při prezentaci.
## Často kladené otázky
### Mohu používat Aspose.Slides pro Javu s jinými knihovnami Java?
Ano, Aspose.Slides pro Javu lze bez problémů integrovat s dalšími knihovnami Java, a tím vylepšit funkčnost vašich aplikací.
### Je k dispozici bezplatná zkušební verze Aspose.Slides pro Javu?
Ano, můžete využít bezplatnou zkušební verzi Aspose.Slides pro Javu od [zde](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Slides pro Javu?
Podporu pro Aspose.Slides pro Javu můžete získat na adrese [forum](https://forum.aspose.com/c/slides/11).
### Mohu si zakoupit dočasnou licenci pro Aspose.Slides pro Javu?
Ano, dočasnou licenci pro Aspose.Slides pro Javu si můžete zakoupit od [zde](https://purchase.aspose.com/temporary-license/).
### Kde najdu podrobnou dokumentaci k Aspose.Slides pro Javu?
Podrobnou dokumentaci k Aspose.Slides pro Javu naleznete zde. [zde](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}