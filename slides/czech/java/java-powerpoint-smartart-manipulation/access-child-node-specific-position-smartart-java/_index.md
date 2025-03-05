---
title: Přístup k podřízenému uzlu na konkrétní pozici v prvku SmartArt
linktitle: Přístup k podřízenému uzlu na konkrétní pozici v prvku SmartArt
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se manipulovat s obrázky SmartArt v Aspose.Slides for Java pomocí tohoto podrobného průvodce. Obsahuje podrobné pokyny, příklady a osvědčené postupy.
type: docs
weight: 11
url: /cs/java/java-powerpoint-smartart-manipulation/access-child-node-specific-position-smartart-java/
---
## Úvod
Chcete posunout své prezentace na další úroveň pomocí sofistikované grafiky SmartArt? Už nehledejte! Aspose.Slides for Java nabízí výkonnou sadu pro vytváření, manipulaci a správu prezentačních snímků, včetně možnosti pracovat s objekty SmartArt. V tomto komplexním tutoriálu vás provedeme přístupem a manipulací s podřízeným uzlem na konkrétní pozici v grafice SmartArt pomocí knihovny Aspose.Slides for Java.

## Předpoklady
Než začneme, je třeba splnit několik předpokladů:
1.  Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK. Můžete si jej stáhnout z[Stránka Oracle JDK](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Knihovna Aspose.Slides for Java: Stáhněte si knihovnu Aspose.Slides for Java z[stránka ke stažení](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Použijte libovolné Java IDE podle svého výběru. Populární možnosti jsou IntelliJ IDEA, Eclipse nebo NetBeans.
4.  Aspose License: I když můžete začít s bezplatnou zkušební verzí, pro plné funkce zvažte získání a[dočasná licence](https://purchase.aspose.com/temporary-license/) nebo zakoupením plné licence od[tady](https://purchase.aspose.com/buy).
## Importujte balíčky
Nejprve importujme potřebné balíčky do vašeho projektu Java. To je klíčové pro používání funkcí Aspose.Slides.
```java
import com.aspose.slides.*;
import java.io.File;
```
Nyní si příklad rozdělíme na podrobné kroky:
## Krok 1: Vytvořte adresář
Prvním krokem je nastavení adresáře, do kterého budou uloženy vaše prezentační soubory. Tím zajistíte, že vaše aplikace bude mít vyhrazený prostor pro správu souborů.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
Zde kontrolujeme, zda adresář existuje, a pokud ne, vytváříme jej. Toto je běžný osvědčený postup, jak se vyhnout chybám při manipulaci se soubory.
## Krok 2: Vytvořte instanci prezentace

Dále vytvoříme novou instanci prezentace. Toto je páteř našeho projektu, kde budou přidány všechny snímky a tvary.
```java
//Vytvořte instanci prezentace
Presentation pres = new Presentation();
```
Tento řádek kódu inicializuje nový objekt prezentace pomocí Aspose.Slides.
## Krok 3: Otevřete první snímek

Nyní potřebujeme přístup k prvnímu snímku prezentace. Snímky jsou místa, kde je umístěn veškerý obsah prezentace.
```java
// Přístup k prvnímu snímku
ISlide slide = pres.getSlides().get_Item(0);
```
Tím se dostaneme k prvnímu snímku v prezentaci, což nám umožní přidat do něj obsah.
## Krok 4: Přidejte tvar SmartArt
### Přidejte tvar SmartArt
Dále na snímek přidáme tvar SmartArt. SmartArt je skvělý způsob, jak vizuálně reprezentovat informace.
```java
// Přidání tvaru SmartArt na první snímek
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
 Zde určíme polohu a rozměry tvaru SmartArt a zvolíme typ rozvržení, v tomto případě`StackedList`.
## Krok 5: Přístup k SmartArt Node

Nyní přistupujeme ke konkrétnímu uzlu v rámci grafiky SmartArt. Uzly jsou jednotlivé prvky v rámci tvaru SmartArt.
```java
// Přístup k uzlu SmartArt na indexu 0
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Tím se načte první uzel v obrázku SmartArt, se kterým budeme dále manipulovat.
## Krok 6: Přístup k podřízenému uzlu

V tomto kroku přistupujeme k podřízenému uzlu na konkrétní pozici v rámci nadřazeného uzlu.
```java
// Přístup k podřízenému uzlu na pozici 1 v nadřazeném uzlu
int position = 1;
SmartArtNode chNode = (SmartArtNode) node.getChildNodes().get_Item(position);
```
Tím se načte podřízený uzel na zadané pozici, což nám umožní manipulovat s jeho vlastnostmi.
## Krok 7: Tisk parametrů podřízeného uzlu

Nakonec vytiskněme parametry podřízeného uzlu, abychom ověřili naše manipulace.
```java
// Tisk parametrů podřízeného uzlu SmartArt
String outString = String.format("j = {0},.Text{1},  Level = {2}, Position = {3}", position, chNode.getTextFrame().getText(), chNode.getLevel(), chNode.getPosition());
System.out.println(outString);
```
Tento řádek kódu formátuje a tiskne podrobnosti o podřízeném uzlu, jako je jeho text, úroveň a pozice.
## Závěr
Gratulujeme! Úspěšně jste přistoupili a manipulovali s podřízeným uzlem v rámci grafiky SmartArt pomocí Aspose.Slides for Java. Tento průvodce vás krok za krokem provede nastavením projektu, přidáním SmartArt a manipulací s jeho uzly. S těmito znalostmi nyní můžete vytvářet dynamičtější a vizuálně přitažlivější prezentace.
 Pro další čtení a zkoumání pokročilejších funkcí se podívejte na[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) Pokud máte nějaké dotazy nebo potřebujete podporu,[Aspose komunitní fórum](https://forum.aspose.com/c/slides/11) je skvělé místo, kde hledat pomoc.
## FAQ
### Jak mohu nainstalovat Aspose.Slides for Java?
 Můžete si jej stáhnout z[stránka ke stažení](https://releases.aspose.com/slides/java/) a postupujte podle dodaných pokynů k instalaci.
### Mohu si Aspose.Slides for Java před nákupem vyzkoušet?
 Ano, můžete získat a[zkušební verze zdarma](https://releases.aspose.com/) nebo a[dočasná licence](https://purchase.aspose.com/temporary-license/) k testování funkcí.
### Jaké typy rozvržení SmartArt jsou dostupné v Aspose.Slides?
 Aspose.Slides podporuje různá rozložení SmartArt, jako je seznam, proces, cyklus, hierarchie a další. Podrobné informace najdete v[dokumentace](https://reference.aspose.com/slides/java/).
### Jak získám podporu pro Aspose.Slides pro Java?
 Můžete získat podporu od[Aspose komunitní fórum](https://forum.aspose.com/c/slides/11) nebo odkazovat na rozsáhlé[dokumentace](https://reference.aspose.com/slides/java/).
### Mohu si koupit plnou licenci pro Aspose.Slides pro Javu?
 Ano, můžete si zakoupit plnou licenci od[nákupní stránku](https://purchase.aspose.com/buy).