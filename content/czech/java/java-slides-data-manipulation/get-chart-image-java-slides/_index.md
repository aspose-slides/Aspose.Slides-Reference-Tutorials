---
title: Získejte obrázek grafu v Java Slides
linktitle: Získejte obrázek grafu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak získat obrázky grafů v Java Slides pomocí Aspose.Slides for Java. Tento průvodce krok za krokem poskytuje zdrojový kód a tipy pro bezproblémovou integraci.
type: docs
weight: 19
url: /cs/java/data-manipulation/get-chart-image-java-slides/
---

## Úvod k získání obrázku grafu v Java Slides

Aspose.Slides for Java je výkonná knihovna, která umožňuje programově pracovat s prezentacemi PowerPoint. Pomocí této knihovny můžete vytvářet, manipulovat a extrahovat různé prvky z prezentací, včetně grafů. Jedním z běžných požadavků je získat obrázky grafu ze snímků a v této příručce si ukážeme, jak to udělat.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte splněny následující předpoklady:

- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Knihovna Aspose.Slides for Java stažená a nakonfigurovaná ve vašem projektu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Nastavte svůj projekt

Začněte vytvořením projektu Java ve vámi preferovaném integrovaném vývojovém prostředí (IDE). Ujistěte se, že jste do závislostí svého projektu přidali knihovnu Aspose.Slides for Java.

## Krok 2: Inicializujte prezentaci

Chcete-li začít, musíte inicializovat prezentaci PowerPoint. V tomto příkladu předpokládáme, že máte v adresáři dokumentů soubor PowerPoint s názvem "test.pptx".

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Přidejte graf a získejte obrázek

Dále můžete na snímek přidat graf a získat jeho obrázek. V tomto příkladu přidáme seskupený sloupcový graf.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

V tomto fragmentu kódu vytvoříme seskupený sloupcový graf na prvním snímku prezentace a poté získáme jeho miniaturu. Obrázek se uloží jako "image.png" do určeného adresáře.

## Kompletní zdrojový kód pro získání obrázku grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
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

Získávání obrázků grafu z Java Slides pomocí Aspose.Slides pro Java je jednoduchý proces. Pomocí poskytnutého kódu můžete tuto funkci snadno integrovat do svých aplikací Java, což vám umožní efektivně pracovat s prezentacemi v PowerPointu.

## FAQ

### Jak nainstaluji Aspose.Slides for Java?

 Instalace Aspose.Slides pro Java je jednoduchá. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/) postupujte podle pokynů k instalaci uvedených v dokumentaci.

### Mohu upravit graf před získáním jeho obrázku?

Ano, před získáním obrázku můžete upravit vzhled, data a další vlastnosti grafu. Aspose.Slides for Java poskytuje rozsáhlé možnosti přizpůsobení grafu.

### Jaké další funkce nabízí Aspose.Slides for Java?

Aspose.Slides for Java nabízí širokou škálu funkcí pro práci s PowerPoint prezentacemi, včetně vytváření snímků, manipulace s textem, úprav tvarů a mnoha dalších. Podrobné informace najdete v dokumentaci.

### Je Aspose.Slides for Java vhodný pro komerční použití?

Ano, Aspose.Slides for Java lze použít pro komerční účely. Poskytuje možnosti licencování, které vyhovují jak jednotlivým vývojářům, tak podnikům.

### Mohu uložit obrázek grafu v jiném formátu?

Rozhodně! Obrázek grafu můžete uložit v různých formátech, jako je JPEG nebo GIF, zadáním příslušné přípony souboru v`ImageIO.write` metoda.