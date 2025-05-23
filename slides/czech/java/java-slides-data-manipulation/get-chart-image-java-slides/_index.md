---
"description": "Naučte se, jak získat obrázky grafů v Java Slides pomocí Aspose.Slides pro Javu. Tato podrobná příručka poskytuje zdrojový kód a tipy pro bezproblémovou integraci."
"linktitle": "Získejte obrázek grafu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Získejte obrázek grafu v Java Slides"
"url": "/cs/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Získejte obrázek grafu v Java Slides


## Úvod do získání obrázku grafu v Javě Slides

Aspose.Slides pro Javu je výkonná knihovna, která umožňuje programově pracovat s prezentacemi v PowerPointu. S touto knihovnou můžete vytvářet, manipulovat a extrahovat různé prvky z prezentací, včetně grafů. Jedním z běžných požadavků je získání obrázků grafů ze snímků a v této příručce si ukážeme, jak to udělat.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte splněny následující předpoklady:

- Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
- Knihovna Aspose.Slides pro Java byla stažena a nakonfigurována ve vašem projektu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Nastavení projektu

Začněte vytvořením projektu Java ve vašem preferovaném integrovaném vývojovém prostředí (IDE). Ujistěte se, že jste do závislostí projektu přidali knihovnu Aspose.Slides for Java.

## Krok 2: Inicializace prezentace

Nejprve je třeba inicializovat prezentaci v PowerPointu. V tomto příkladu předpokládáme, že máte v adresáři dokumentů soubor PowerPoint s názvem „test.pptx“.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Přidání grafu a získání obrázku

Dále můžete na snímek přidat graf a získat jeho obrázek. V tomto příkladu přidáme klastrovaný sloupcový graf.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

V tomto úryvku kódu vytvoříme na prvním snímku prezentace klastrovaný sloupcový graf a poté získáme jeho náhledový obrázek. Obrázek se uloží jako „image.png“ do zadaného adresáře.

## Kompletní zdrojový kód pro získání obrázku grafu v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Získání obrázků grafů z Java Slides pomocí Aspose.Slides pro Javu je jednoduchý proces. S poskytnutým kódem můžete tuto funkci snadno integrovat do vašich Java aplikací, což vám umožní efektivně pracovat s prezentacemi v PowerPointu.

## Často kladené otázky

### Jak nainstaluji Aspose.Slides pro Javu?

Instalace Aspose.Slides pro Javu je jednoduchá. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/) a postupujte podle pokynů k instalaci uvedených v dokumentaci.

### Mohu si graf upravit před získáním jeho obrázku?

Ano, vzhled grafu, data a další vlastnosti si můžete přizpůsobit před získáním jeho obrázku. Aspose.Slides pro Javu nabízí rozsáhlé možnosti přizpůsobení grafu.

### Jaké další funkce nabízí Aspose.Slides pro Javu?

Aspose.Slides pro Javu nabízí širokou škálu funkcí pro práci s prezentacemi v PowerPointu, včetně vytváření snímků, manipulace s textem, úpravy tvarů a mnoha dalších. Podrobné informace naleznete v dokumentaci.

### Je Aspose.Slides pro Javu vhodný pro komerční použití?

Ano, Aspose.Slides pro Javu lze použít pro komerční účely. Nabízí možnosti licencování, které uspokojí jak individuální vývojáře, tak i podniky.

### Mohu uložit obrázek grafu v jiném formátu?

Jistě! Obrázek grafu můžete uložit v různých formátech, například JPEG nebo GIF, zadáním příslušné přípony souboru v `ImageIO.write` metoda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}