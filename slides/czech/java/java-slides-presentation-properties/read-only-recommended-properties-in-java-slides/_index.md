---
title: Doporučené vlastnosti pouze pro čtení v Java Slides
linktitle: Doporučené vlastnosti pouze pro čtení v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Přečtěte si, jak povolit vlastnosti doporučené pouze pro čtení v prezentacích Java PowerPoint pomocí Aspose.Slides for Java. Postupujte podle našeho podrobného průvodce s příklady zdrojového kódu pro lepší zabezpečení prezentace.
weight: 17
url: /cs/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod k aktivaci doporučených vlastností pouze pro čtení v Java Slides

tomto tutoriálu prozkoumáme, jak povolit vlastnosti doporučené pouze pro čtení pro prezentace PowerPoint pomocí Aspose.Slides pro Java. Vlastnosti doporučené pouze pro čtení mohou být užitečné, když chcete povzbudit uživatele, aby si prohlíželi prezentaci bez provádění jakýchkoli změn. Tyto vlastnosti naznačují, že prezentace by měla být otevřena v režimu pouze pro čtení. Poskytneme vám průvodce krok za krokem spolu se zdrojovým kódem Java, jak toho dosáhnout.

## Předpoklady

 Než začneme, ujistěte se, že máte ve svém projektu nastavenou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[Aspose.Slides pro webové stránky Java](https://products.aspose.com/slides/java/).

## Krok 1: Vytvořte novou prezentaci v PowerPointu

Začneme vytvořením nové powerpointové prezentace pomocí Aspose.Slides for Java. Pokud již prezentaci máte, můžete tento krok přeskočit.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Ve výše uvedeném kódu jsme definovali cestu pro výstupní soubor PowerPoint a vytvořili nový objekt prezentace.

## Krok 2: Povolte doporučenou vlastnost pouze pro čtení

Nyní povolme vlastnost Doporučeno pouze pro čtení pro prezentaci.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 V tomto fragmentu kódu používáme`getProtectionManager().setReadOnlyRecommended(true)` metodu pro nastavení vlastnosti Doporučeno jen pro čtení na`true`. Tím je zajištěno, že když někdo otevře prezentaci, bude vyzván, aby ji otevřel v režimu pouze pro čtení.

## Krok 3: Uložte prezentaci

Nakonec prezentaci uložíme se zapnutou vlastností Read-Only Recommended.

## Kompletní zdrojový kód pro vlastnosti doporučené pouze pro čtení v Java Slides

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak aktivovat vlastnost Read-Only Recommended pro prezentaci PowerPoint pomocí Aspose.Slides for Java. Tato funkce může být užitečná, když chcete omezit úpravy a povzbudit diváky, aby používali prezentaci v režimu pouze pro čtení. Zabezpečení můžete dále zvýšit nastavením hesla pro prezentaci.

## FAQ

### Jak zakážu vlastnost Doporučeno pouze pro čtení?

Chcete-li zakázat vlastnost Doporučeno pouze pro čtení, jednoduše použijte následující kód:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Mohu nastavit heslo pro prezentaci doporučenou pouze pro čtení?

Ano, pomocí Aspose.Slides for Java můžete nastavit heslo pro prezentaci doporučenou pouze pro čtení. Můžete použít`setPassword` způsob nastavení hesla pro prezentaci. Pokud je nastaveno heslo, uživatelé jej budou muset zadat, aby mohli prezentaci otevřít, a to i v režimu pouze pro čtení.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Nezapomeňte vyměnit`"YourPassword"` s požadovaným heslem.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
