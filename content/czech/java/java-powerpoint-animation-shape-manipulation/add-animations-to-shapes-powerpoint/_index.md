---
title: Přidejte animace do obrazců v PowerPointu
linktitle: Přidejte animace do obrazců v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat animace do tvarů v PowerPointu pomocí Aspose.Slides pro Java v tomto podrobném výukovém programu. Ideální pro vytváření poutavých prezentací.
type: docs
weight: 10
url: /cs/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---
## Úvod
Vytváření poutavých prezentací často vyžaduje přidání animací do tvarů a textu. Animace mohou vaše snímky učinit dynamičtějšími a podmanivějšími, což zajistí, že vaše publikum bude stále zajímat. V tomto tutoriálu vás provedeme procesem přidávání animací do tvarů v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Na konci tohoto článku budete schopni bez námahy vytvářet profesionální animace.
## Předpoklady
Než se vrhneme na tutoriál, ujistěte se, že máte vše, co potřebujete:
1.  Knihovna Aspose.Slides for Java: Musíte mít nainstalovanou knihovnu Aspose.Slides for Java. Můžeš[stáhněte si to zde](https://releases.aspose.com/slides/java/).
2. Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK.
3. Integrované vývojové prostředí (IDE): Použijte jakékoli Java IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.
4. Základní znalost Javy: Tento tutoriál předpokládá, že máte základní znalosti o programování v Javě.
## Importujte balíčky
Chcete-li začít, budete muset importovat potřebné balíčky pro Aspose.Slides a další požadované třídy Java.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## Krok 1: Nastavte adresář projektu
Nejprve vytvořte adresář pro soubory projektu.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Krok 2: Inicializujte objekt prezentace
 Dále vytvořte instanci`Presentation` třídy, která bude reprezentovat váš soubor PowerPoint.
```java
// Třída okamžité prezentace, která představuje PPTX
Presentation pres = new Presentation();
```
## Krok 3: Otevřete první snímek
Nyní otevřete první snímek v prezentaci, kam přidáte animace.
```java
// Otevřete první snímek
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Přidejte na snímek tvar
Přidejte na snímek tvar obdélníku a vložte do něj nějaký text.
```java
// Přidejte na snímek tvar obdélníku
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## Krok 5: Použijte efekt animace
Aplikujte na tvar efekt animace „PathFootball“.
```java
// Přidejte efekt animace PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Krok 6: Vytvořte interaktivní spouštěč
Vytvořte tvar tlačítka, který po kliknutí spustí animaci.
```java
// Vytvořte tvar tlačítka pro spuštění animace
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Krok 7: Definujte interaktivní sekvenci
Definujte sekvenci efektů pro tlačítko.
```java
// Vytvořte sekvenci efektů pro tlačítko
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## Krok 8: Přidejte vlastní cestu uživatele
Přidejte do tvaru vlastní animaci cesty uživatele.
```java
// Přidejte vlastní efekt animace uživatelské cesty
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// Vytvořte pohybový efekt
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// Definujte body cesty
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## Krok 9: Uložte prezentaci
Nakonec prezentaci uložte na požadované místo.
```java
// Uložte prezentaci jako soubor PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// Zlikvidujte předmět prezentace
if (pres != null) pres.dispose();
```
## Závěr
tady to máte! Úspěšně jste přidali animace do obrazců v prezentaci PowerPoint pomocí Aspose.Slides for Java. Tato výkonná knihovna usnadňuje vylepšování vašich prezentací dynamickými efekty a zajišťuje, že vaše publikum zůstane v kontaktu. Pamatujte, že cvičení dělá mistra, takže pokračujte v experimentování s různými efekty a spouštěči, abyste zjistili, co nejlépe vyhovuje vašim potřebám.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonné rozhraní API pro vytváření, úpravu a manipulaci s prezentacemi PowerPoint programově.
### Mohu používat Aspose.Slides zdarma?
 Aspose.Slides můžete zdarma vyzkoušet s a[dočasná licence](https://purchase.aspose.com/temporary-license/). Pro další používání je vyžadována placená licence.
### Které verze Java jsou kompatibilní s Aspose.Slides?
Aspose.Slides podporuje Java SE 6 a vyšší.
### Jak přidám různé animace k více tvarům?
K více tvarům můžete přidat různé animace opakováním kroků pro každý tvar a zadáním různých efektů podle potřeby.
### Kde najdu další příklady a dokumentaci?
 Podívejte se na[dokumentace](https://reference.aspose.com/slides/java/) a[Fórum podpory](https://forum.aspose.com/c/slides/11)pro další příklady a pomoc.