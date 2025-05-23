---
"description": "Naučte se, jak odstranit uzel na určité pozici v rámci SmartArt pomocí Aspose.Slides pro Javu. Vylepšete si přizpůsobení prezentace bez námahy."
"linktitle": "Odebrání uzlu na určité pozici v okně SmartArt"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Odebrání uzlu na určité pozici v okně SmartArt"
"url": "/cs/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Odebrání uzlu na určité pozici v okně SmartArt

## Zavedení
oblasti vývoje v Javě se Aspose.Slides jeví jako výkonný nástroj pro programovou manipulaci s prezentacemi. Ať už jde o vytváření, úpravu nebo správu snímků, Aspose.Slides pro Javu poskytuje robustní sadu funkcí pro efektivní zefektivnění těchto úkolů. Jednou z takových běžných operací je odstranění uzlu na určité pozici v objektu SmartArt. Tento tutoriál se ponoří do podrobného procesu, jak toho dosáhnout pomocí Aspose.Slides pro Javu.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte nastaveny následující předpoklady:
1. Vývojářská sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou JDK. Můžete si ji stáhnout z [zde](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides pro Javu: Získejte knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [tento odkaz](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Mějte nainstalované IDE, jako je IntelliJ IDEA nebo Eclipse, pro bezproblémový psaní a spouštění kódu Java.

## Importovat balíčky
Ve svém projektu v Javě zahrňte potřebné balíčky pro využití funkcí Aspose.Slides:
```java
import com.aspose.slides.*;
```
## Krok 1: Načtení prezentace
Začněte načtením souboru prezentace, ve kterém se nachází objekt SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## Krok 2: Procházení tvarů SmartArt
Procházejte jednotlivé tvary v prezentaci a identifikujte objekty SmartArt:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## Krok 3: Přístup k uzlu SmartArt
Přejděte k uzlu SmartArt na požadované pozici:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Krok 4: Odebrání podřízeného uzlu
Odeberte podřízený uzel na zadané pozici:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## Krok 5: Uložení prezentace
Nakonec uložte upravenou prezentaci:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Závěr
S Aspose.Slides pro Javu se manipulace s objekty SmartArt v prezentacích stává jednoduchým úkolem. Dodržováním popsaných kroků můžete bez problémů odebrat uzly na konkrétních pozicích, čímž si vylepšíte možnosti přizpůsobení prezentací.
## Často kladené otázky
### Je Aspose.Slides pro Javu zdarma?
Aspose.Slides pro Javu je komerční knihovna, ale její funkce si můžete prozkoumat s bezplatnou zkušební verzí. Navštivte [tento odkaz](https://releases.aspose.com/) začít.
### Kde najdu podporu pro dotazy týkající se Aspose.Slides?
V případě potřeby pomoci nebo dotazů můžete navštívit fórum Aspose.Slides. [zde](https://forum.aspose.com/c/slides/11).
### Mohu získat dočasnou licenci pro Aspose.Slides?
Ano, můžete získat dočasnou licenci od [zde](https://purchase.aspose.com/temporary-license/) pro účely hodnocení.
### Jak si mohu zakoupit Aspose.Slides pro Javu?
Chcete-li zakoupit Aspose.Slides pro Javu, navštivte stránku nákupu [zde](https://purchase.aspose.com/buy).
### Kde najdu podrobnou dokumentaci k Aspose.Slides pro Javu?
Můžete získat přístup k komplexní dokumentaci [zde](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}