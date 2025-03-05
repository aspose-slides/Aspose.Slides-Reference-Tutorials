---
title: Aplikujte efekty vnějšího stínu v Java PowerPointu
linktitle: Aplikujte efekty vnějšího stínu v Java PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak snadno aplikovat efekty vnějšího stínu v prezentacích Java PowerPoint pomocí Aspose.Slides s naším podrobným průvodcem krok za krokem.
type: docs
weight: 11
url: /cs/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---
## Úvod
Vytváření poutavých prezentací často vyžaduje přidání různých efektů ke zvýšení vizuální přitažlivosti vašich snímků. Jedním z takových efektů je vnější stín, díky kterému mohou vaše prvky vyskočit a přidat vašemu obsahu hloubku. V tomto tutoriálu projdeme procesem aplikace efektů vnějšího stínu na tvary v prezentaci PowerPoint pomocí Aspose.Slides for Java.
## Předpoklady
Než se ponoříme do podrobného průvodce, ujistěte se, že máte vše, co potřebujete:
1.  Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK. Můžete si jej stáhnout z[Web společnosti Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides pro Javu Library: Stáhněte si nejnovější verzi z[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Použijte IDE jako IntelliJ IDEA nebo Eclipse pro psaní a spouštění kódu Java.
4.  Platná licence Aspose: Můžete si zakoupit licenci od[Aspose](https://purchase.aspose.com/buy) nebo získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro hodnocení.
## Importujte balíčky
Nejprve budete muset importovat potřebné balíčky pro Aspose.Slides. To vytváří podmínky pro využití výkonných funkcí, které knihovna poskytuje.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Pojďme si rozdělit proces aplikace efektů vnějšího stínu do zvládnutelných kroků:
## Krok 1: Nastavte adresář projektu
Než začnete psát svůj kód, musíte nastavit adresář projektu, kde se budou ukládat vaše PowerPoint soubory a kde k nim budete přistupovat.
Ujistěte se, že adresář vašeho projektu existuje. Pokud tomu tak není, vytvořte jej pomocí následujícího kódu:
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Krok 2: Inicializujte prezentaci
Nyní musíme inicializovat prezentaci, do které přidáme naše tvary a efekty.

 Vytvořte novou instanci souboru`Presentation` třídy, abyste mohli začít pracovat s novým souborem PowerPoint.
```java
// Vytvořte třídu PPTX
Presentation pres = new Presentation();
```
## Krok 3: Přidejte snímek a tvar
Dále do prezentace přidejte snímek a poté přidejte tvar, na který použijete efekt stínu.
### Získejte odkaz na snímek
Získejte odkaz na první snímek v prezentaci.
```java
// Získejte referenci na snímek
ISlide sld = pres.getSlides().get_Item(0);
```
### Přidat automatický tvar
Přidejte na snímek automatický tvar obdélníku na zadaných souřadnicích.
```java
// Přidejte automatický tvar typu Obdélník
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Krok 4: Přizpůsobte tvar
Přidejte do tvaru text a upravte jeho nastavení výplně, aby byl stínový efekt viditelnější.
### Přidejte TextFrame do tvaru
Vložte text do tvaru obdélníku.
```java
// Přidejte TextFrame do obdélníku
aShp.addTextFrame("Aspose TextBox");
```
### Zakázat výplň tvaru
Zakažte výplň tvaru, abyste zdůraznili stín textu.
```java
// V případě, že chceme získat stín textu, vypněte tvarovou výplň
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Krok 5: Aplikujte efekt vnějšího stínu
Nyní je čas aplikovat efekt vnějšího stínu na tvar.
### Povolit efekt vnějšího stínu
Povolte efekt vnějšího stínu pro tvar.
```java
// Přidejte vnější stín a nastavte všechny potřebné parametry
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Konfigurace parametrů stínu
Nastavte různé vlastnosti stínu, jako je poloměr rozostření, směr, vzdálenost, zarovnání a barva.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Krok 6: Uložte prezentaci
Nakonec prezentaci uložte na disk.
```java
//Napište prezentaci na disk
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Krok 7: Zlikvidujte zdroje
Ujistěte se, že jste uvolnili prostředky likvidací objektu prezentace.
```java
// Vyčistěte zdroje
if (pres != null) pres.dispose();
```
## Závěr
A tady to máte! Úspěšně jste použili efekt vnějšího stínu na tvar v prezentaci PowerPoint pomocí Aspose.Slides for Java. Tento efekt může výrazně zlepšit vizuální přitažlivost vašich snímků, takže váš obsah vynikne.
 Pokud narazíte na nějaké problémy nebo potřebujete další pomoc, neváhejte se podívat na[Dokumentace Aspose.Slides](https://reference.aspose.com/slides/java/) nebo navštivte[Fórum podpory](https://forum.aspose.com/c/slides/11). Šťastné kódování!
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonná knihovna, která umožňuje vytvářet, manipulovat a převádět PowerPointové prezentace v aplikacích Java.
### Jak mohu získat bezplatnou zkušební verzi Aspose.Slides for Java?
 Můžete si stáhnout bezplatnou zkušební verzi z[Aspose webové stránky](https://releases.aspose.com/).
### Mohu použít Aspose.Slides pro Javu s jakýmkoli IDE?
Ano, Aspose.Slides pro Javu můžete použít s jakýmkoli Java IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.
### Jak získám dočasnou licenci pro Aspose.Slides?
 Dočasnou licenci můžete získat od[Aspose webové stránky](https://purchase.aspose.com/temporary-license/).
### Kde najdu další příklady a dokumentaci pro Aspose.Slides?
 Další příklady a podrobnou dokumentaci naleznete na[Dokumentační stránka Aspose.Slides](https://reference.aspose.com/slides/java/).