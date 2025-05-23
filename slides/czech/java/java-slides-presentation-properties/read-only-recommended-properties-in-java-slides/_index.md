---
"description": "Naučte se, jak povolit vlastnosti „Jen pro čtení“ (Recommended-Only Recommended) v prezentacích v Javě PowerPoint pomocí Aspose.Slides pro Javu. Pro zvýšení zabezpečení prezentací postupujte podle našeho podrobného návodu s příklady zdrojového kódu."
"linktitle": "Doporučené vlastnosti pouze pro čtení v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Doporučené vlastnosti pouze pro čtení v Java Slides"
"url": "/cs/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Doporučené vlastnosti pouze pro čtení v Java Slides


## Úvod do povolení doporučených vlastností pouze pro čtení v Java Slides

V tomto tutoriálu se podíváme na to, jak povolit vlastnosti „Doporučeno pouze pro čtení“ pro prezentace v PowerPointu pomocí Aspose.Slides pro Javu. Vlastnosti „Doporučeno pouze pro čtení“ mohou být užitečné, když chcete povzbudit uživatele k prohlížení prezentace bez provedení jakýchkoli změn. Tyto vlastnosti naznačují, že by prezentace měla být otevřena v režimu „jen pro čtení“. Poskytneme vám podrobný návod spolu se zdrojovým kódem Javy, jak toho dosáhnout.

## Předpoklady

Než začneme, ujistěte se, že máte ve svém projektu nastavenou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [Web Aspose.Slides pro Javu](https://products.aspose.com/slides/java/).

## Krok 1: Vytvořte novou prezentaci v PowerPointu

Začneme vytvořením nové prezentace v PowerPointu pomocí Aspose.Slides pro Javu. Pokud již prezentaci máte, můžete tento krok přeskočit.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Ve výše uvedeném kódu jsme definovali cestu k výstupnímu souboru PowerPointu a vytvořili nový objekt prezentace.

## Krok 2: Povolení doporučené vlastnosti pouze pro čtení

Nyní povolme pro prezentaci vlastnost Doporučeno pouze pro čtení.

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

V tomto úryvku kódu používáme `getProtectionManager().setReadOnlyRecommended(true)` metoda pro nastavení vlastnosti Doporučeno pouze pro čtení na `true`Díky tomu bude při otevření prezentace vyzván k jejímu otevření v režimu pouze pro čtení.

## Krok 3: Uložte prezentaci

Nakonec uložíme prezentaci s povolenou vlastností Doporučeno pouze pro čtení.

## Kompletní zdrojový kód pro doporučené vlastnosti pouze pro čtení v Javě Slides

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

V tomto tutoriálu jste se naučili, jak povolit vlastnost „Doporučeno pouze pro čtení“ pro prezentaci v PowerPointu pomocí Aspose.Slides pro Javu. Tato funkce může být užitečná, pokud chcete omezit úpravy a povzbudit diváky k používání prezentace v režimu pouze pro čtení. Zabezpečení můžete dále zvýšit nastavením hesla pro prezentaci.

## Často kladené otázky

### Jak zakážu vlastnost „Doporučeno pouze pro čtení“?

Chcete-li zakázat vlastnost Doporučeno pouze pro čtení, jednoduše použijte následující kód:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Mohu nastavit heslo pro prezentaci s možností doporučení pouze pro čtení?

Ano, pro doporučenou prezentaci s přístupem pouze ke čtení můžete nastavit heslo pomocí Aspose.Slides pro Javu. Můžete použít `setPassword` metoda pro nastavení hesla pro prezentaci. Pokud je heslo nastaveno, uživatelé ho budou muset zadat pro otevření prezentace, a to i v režimu pouze pro čtení.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Nezapomeňte vyměnit `"YourPassword"` s požadovaným heslem.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}