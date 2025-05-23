---
"description": "Naučte se, jak v PowerPointu pomocí Aspose.Slides pro Javu aplikovat 3D rotační efekty na tvary v tomto komplexním návodu krok za krokem."
"linktitle": "Použití efektu 3D rotace na tvary v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Použití efektu 3D rotace na tvary v PowerPointu"
"url": "/cs/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Použití efektu 3D rotace na tvary v PowerPointu

## Zavedení
Jste připraveni posunout své prezentace v PowerPointu na další úroveň? Přidání 3D efektů rotace může vaše snímky učinit dynamičtějšími a poutavějšími. Ať už jste zkušený vývojář, nebo teprve začínáte, tento podrobný návod vám ukáže, jak aplikovat 3D efekty rotace na tvary v PowerPointu pomocí Aspose.Slides pro Javu. Pojďme se do toho pustit!
## Předpoklady
Než začneme, ujistěte se, že máte připraveno následující:
1. Vývojářská sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou JDK. Můžete si ji stáhnout z [Webové stránky společnosti Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides pro Javu: Stáhněte si nejnovější verzi Aspose.Slides pro Javu z [odkaz ke stažení](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Pro kódování použijte IDE, jako je IntelliJ IDEA nebo Eclipse.
4. Platný řidičský průkaz: Pokud řidičský průkaz nemáte, můžete si jej pořídit [dočasná licence](https://purchase.aspose.com/temporary-license/) vyzkoušet funkce.
## Importovat balíčky
Nejprve si do vašeho projektu v Javě importujeme potřebné balíčky. Tyto importy vám pomohou s prezentacemi a tvary pomocí Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Krok 1: Nastavení projektu
Než se ponoříte do kódu, nastavte si prostředí projektu. Ujistěte se, že jste do závislostí projektu přidali Aspose.Slides pro Javu.
Přidejte Aspose.Slides do svého projektu:
1. Stáhněte si soubory JAR Aspose.Slides z [stránka ke stažení](https://releases.aspose.com/slides/java/).
2. Přidejte tyto soubory JAR do cesty sestavení vašeho projektu.
## Krok 2: Vytvořte novou prezentaci v PowerPointu
V tomto kroku vytvoříme novou prezentaci v PowerPointu.
```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation pres = new Presentation();
```
Tento úryvek kódu inicializuje nový objekt prezentace, kam přidáme naše tvary.
## Krok 3: Přidání obdélníkového tvaru
Dále přidáme na první snímek obdélníkový tvar.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Tento kód přidá obdélníkový tvar na zadanou pozici a velikosti na prvním snímku.
## Krok 4: Použití 3D rotace na obdélník
Nyní aplikujme na obdélníkový tvar efekt 3D rotace.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Zde nastavíme hloubku, úhly natočení kamery, typ kamery a typ osvětlení, abychom našemu obdélníku dodali 3D vzhled.
## Krok 5: Přidání tvaru čáry
Přidejme na snímek další tvar, tentokrát čáru.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Tento kód umístí na snímek tvar čáry.
## Krok 6: Použití 3D rotace na čáru
Nakonec na tvar čáry aplikujeme efekt 3D rotace.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Podobně jako u obdélníku nastavujeme 3D vlastnosti pro tvar čáry.
## Krok 7: Uložte prezentaci
Po přidání a konfiguraci tvarů prezentaci uložte.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Tento kód uloží vaši prezentaci se zadaným názvem souboru v požadovaném formátu.
## Závěr
Gratulujeme! Úspěšně jste aplikovali 3D efekty rotace na tvary v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Dodržováním těchto kroků můžete vytvářet vizuálně přitažlivé a dynamické prezentace. Další možnosti přizpůsobení a pokročilejší funkce naleznete v [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/java/).
## Často kladené otázky
### Co je Aspose.Slides pro Javu?
Aspose.Slides pro Javu je výkonné API pro programovou tvorbu, úpravu a manipulaci s prezentacemi v PowerPointu.
### Mohu si Aspose.Slides pro Javu vyzkoušet zdarma?
Ano, můžete získat [bezplatná zkušební verze](https://releases.aspose.com/) nebo a [dočasná licence](https://purchase.aspose.com/temporary-license/) otestovat funkce.
### Do jakých typů tvarů mohu v Aspose.Slides přidat 3D efekty?
3D efekty můžete přidat k různým tvarům, jako jsou obdélníky, čáry, elipsy a vlastní tvary.
### Jak získám podporu pro Aspose.Slides pro Javu?
Můžete navštívit [fórum podpory](https://forum.aspose.com/c/slides/11) o pomoc a projednání jakýchkoli problémů.
### Mohu použít Aspose.Slides pro Javu v komerčních projektech?
Ano, ale musíte si zakoupit licenci. Můžete si ji koupit od [stránka nákupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}