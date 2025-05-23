---
"description": "Naučte se, jak vytvářet úžasné organizační diagramy v Java Slides s podrobnými tutoriály Aspose.Slides. Přizpůsobte si a vizualizujte svou organizační strukturu bez námahy."
"linktitle": "Organizační schéma v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Organizační schéma v Javě Slides"
"url": "/cs/java/chart-data-manipulation/organization-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Organizační schéma v Javě Slides


## Úvod do vytváření organizačního diagramu v Java Slides pomocí Aspose.Slides

V tomto tutoriálu si ukážeme, jak vytvořit organizační schéma v Java Slides pomocí rozhraní Aspose.Slides for Java API. Organizační schéma je vizuální znázornění hierarchické struktury organizace, obvykle používané k ilustraci vztahů a hierarchie mezi zaměstnanci nebo odděleními.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- [Aspose.Slides pro Javu](https://products.aspose.com/slides/java) knihovna nainstalovaná ve vašem projektu Java.
- Integrované vývojové prostředí (IDE) v Javě, jako je IntelliJ IDEA nebo Eclipse.

## Krok 1: Nastavení projektu v jazyce Java

1. Vytvořte nový projekt Java ve vámi preferovaném IDE.
2. Přidejte do svého projektu knihovnu Aspose.Slides pro Javu. Knihovnu si můžete stáhnout z [Webové stránky Aspose](https://products.aspose.com/slides/java) a zahrnout to jako závislost.

## Krok 2: Importujte požadované knihovny
Ve vaší třídě Java importujte potřebné knihovny pro práci s Aspose.Slides:

```java
import com.aspose.slides.*;
```

## Krok 3: Vytvořte organizační schéma

Nyní si vytvořme organizační schéma pomocí Aspose.Slides. Postupujeme podle těchto kroků:

1. Zadejte cestu k adresáři s dokumenty.
2. Načtěte existující prezentaci v PowerPointu nebo vytvořte novou.
3. Přidání obrazce organizačního diagramu na snímek.
4. Uložte prezentaci s organizačním schématem.

Zde je kód, jak toho dosáhnout:

```java
// Zadejte cestu k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Načtěte existující prezentaci nebo vytvořte novou.
Presentation pres = new Presentation(dataDir + "test.pptx");
try {
    // Přidejte na první snímek obrazec organizačního diagramu.
    ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);

    // Uložte prezentaci s organizačním schématem.
    pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Nahradit `"Your Document Directory"` se skutečnou cestou k adresáři s dokumenty a `"test.pptx"` názvem vaší vstupní prezentace v PowerPointu.

## Krok 4: Spusťte kód

Nyní, když jste přidali kód pro vytvoření organizačního diagramu, spusťte aplikaci Java. Ujistěte se, že je knihovna Aspose.Slides správně přidána do projektu a že jsou vyřešeny potřebné závislosti.

## Kompletní zdrojový kód pro organizační schéma v Javě - Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);
	pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak vytvořit organizační schéma v Java Slides pomocí rozhraní Aspose.Slides for Java API. Vzhled a obsah organizačního schématu si můžete přizpůsobit podle svých specifických požadavků. Aspose.Slides nabízí širokou škálu funkcí pro práci s prezentacemi v PowerPointu, což z něj činí výkonný nástroj pro správu a vytváření vizuálního obsahu.

## Často kladené otázky

### Jak si mohu přizpůsobit vzhled organizačního diagramu?

Vzhled organizačního diagramu si můžete přizpůsobit úpravou jeho vlastností, jako jsou barvy, styly a písma. Podrobnosti o přizpůsobení tvarů SmartArt naleznete v dokumentaci k Aspose.Slides.

### Mohu do organizačního diagramu přidat další tvary nebo text?

Ano, do organizačního diagramu můžete přidat další tvary, text a spojnice, které přesně reprezentují vaši organizační strukturu. K přidávání a formátování tvarů v diagramu SmartArt použijte rozhraní API Aspose.Slides.

### Jak mohu exportovat organizační schéma do jiných formátů, například PDF nebo obrázku?

Prezentaci obsahující organizační schéma můžete exportovat do různých formátů pomocí Aspose.Slides. Například pro export do PDF použijte `SaveFormat.Pdf` možnost při ukládání prezentace. Podobně můžete exportovat do obrazových formátů, jako je PNG nebo JPEG.

### Je možné vytvořit složité organizační struktury s více úrovněmi?

Ano, Aspose.Slides umožňuje vytvářet složité organizační struktury s více úrovněmi přidáváním a uspořádáním tvarů v rámci organizačního diagramu. Mezi tvary můžete definovat hierarchické vztahy, které reprezentují požadovanou strukturu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}