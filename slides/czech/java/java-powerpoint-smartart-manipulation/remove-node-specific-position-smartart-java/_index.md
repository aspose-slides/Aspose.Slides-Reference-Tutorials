---
title: Odebrat uzel na konkrétní pozici v obrázku SmartArt
linktitle: Odebrat uzel na konkrétní pozici v obrázku SmartArt
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak odstranit uzel na konkrétní pozici v rámci SmartArt pomocí Aspose.Slides for Java. Vylepšete přizpůsobení prezentace bez námahy.
weight: 15
url: /cs/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odebrat uzel na konkrétní pozici v obrázku SmartArt

## Úvod
oblasti vývoje Java se Aspose.Slides ukazuje jako mocný nástroj pro programovou manipulaci s prezentacemi. Ať už se jedná o vytváření, úpravu nebo správu snímků, Aspose.Slides for Java poskytuje robustní sadu funkcí pro efektivní zefektivnění těchto úloh. Jednou z takových běžných operací je odebrání uzlu na určité pozici v objektu SmartArt. Tento tutoriál se ponoří do procesu krok za krokem, jak toho dosáhnout pomocí Aspose.Slides for Java.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte nastaveny následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[tady](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Získejte knihovnu Aspose.Slides pro Java. Můžete si jej stáhnout z[tento odkaz](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Mějte nainstalované IDE jako IntelliJ IDEA nebo Eclipse pro bezproblémové psaní a spouštění kódu Java.

## Importujte balíčky
Do svého projektu Java zahrňte potřebné balíčky pro využití funkcí Aspose.Slides:
```java
import com.aspose.slides.*;
```
## Krok 1: Načtěte prezentaci
Začněte načtením souboru prezentace, kde existuje objekt SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## Krok 2: Procházejte tvary SmartArt
Procházejte jednotlivé tvary v prezentaci a identifikujte objekty SmartArt:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## Krok 3: Přístup k SmartArt Node
Otevřete uzel SmartArt na požadované pozici:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Krok 4: Odeberte podřízený uzel
Odeberte podřízený uzel na zadané pozici:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## Krok 5: Uložte prezentaci
Nakonec upravenou prezentaci uložte:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Závěr
S Aspose.Slides for Java se manipulace s objekty SmartArt v rámci prezentací stává přímočarým úkolem. Podle nastíněných kroků můžete hladce odstranit uzly na konkrétních pozicích a vylepšit tak možnosti přizpůsobení prezentace.
## FAQ
### Je Aspose.Slides for Java zdarma k použití?
 Aspose.Slides for Java je komerční knihovna, ale její funkce můžete prozkoumat pomocí bezplatné zkušební verze. Návštěva[tento odkaz](https://releases.aspose.com/) začít.
### Kde najdu podporu pro dotazy související s Aspose.Slides?
 Pro jakoukoli pomoc nebo dotazy můžete navštívit fórum Aspose.Slides[tady](https://forum.aspose.com/c/slides/11).
### Mohu získat dočasnou licenci pro Aspose.Slides?
 Ano, můžete získat dočasnou licenci od[tady](https://purchase.aspose.com/temporary-license/) pro účely hodnocení.
### Jak si mohu zakoupit Aspose.Slides pro Java?
 Chcete-li zakoupit Aspose.Slides pro Java, navštivte stránku nákupu[tady](https://purchase.aspose.com/buy).
### Kde najdu podrobnou dokumentaci k Aspose.Slides pro Javu?
 Máte přístup ke komplexní dokumentaci[tady](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
