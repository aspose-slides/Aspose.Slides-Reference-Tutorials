---
title: Přidejte rámeček Embedded Video Frame v PowerPointu
linktitle: Přidejte rámeček Embedded Video Frame v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak vkládat snímky videa do PowerPointu pomocí Aspose.Slides for Java, pomocí tohoto podrobného kurzu. Vylepšete své prezentace snadno.
weight: 21
url: /cs/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
Přidáním videí do prezentací v PowerPointu mohou být poutavější a informativnější. Pomocí Aspose.Slides for Java můžete snadno vkládat videa přímo do svých snímků. V tomto tutoriálu vás provedeme procesem krok za krokem a zajistíme, že porozumíte každé části kódu a tomu, jak funguje. Ať už jste zkušený vývojář nebo teprve začínáte, tento průvodce vám pomůže vylepšit vaše prezentace pomocí vložených videí.
## Předpoklady
Než se ponoříte do kódu, ujistěte se, že máte splněny následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK.
2. Aspose.Slides for Java: Stáhněte si a nainstalujte knihovnu Aspose.Slides for Java.
3. Integrované vývojové prostředí (IDE): Použijte IDE jako IntelliJ IDEA nebo Eclipse pro lepší vývoj.
4. Video soubor: Připravte si video soubor, který chcete vložit do prezentace PowerPoint.
## Importujte balíčky
Nejprve budete muset importovat potřebné balíčky pro práci s Aspose.Slides. Tyto importy vám pomohou spravovat snímky, videa a soubory prezentací.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Krok 1: Nastavte své prostředí
Než začnete kódovat, ujistěte se, že je vaše prostředí správně nastaveno. To zahrnuje vytvoření potřebných adresářů a přípravu video souboru.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Vytvořte adresář, pokud ještě není přítomen.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Krok 2: Okamžitá prezentace
 Vytvořte instanci souboru`Presentation` třída. Tato třída představuje váš soubor PowerPoint.
```java
// Třída okamžité prezentace, která představuje PPTX
Presentation pres = new Presentation();
```
## Krok 3: Získejte první snímek
Otevřete první snímek prezentace, kam vložíte video.
```java
// Získejte první snímek
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Přidejte video do prezentace
Vložte video soubor do prezentace. Ujistěte se, že je správně zadána cesta videa.
```java
// Vložte video do prezentace
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Krok 5: Přidejte video rámeček do snímku
Vytvořte snímek videa na snímku a nastavte jeho rozměry a polohu.
```java
// Přidat video rámeček
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Krok 6: Konfigurace vlastností video rámečku
Nastavte video na snímek videa a nakonfigurujte jeho nastavení přehrávání, jako je režim přehrávání a hlasitost.
```java
// Nastavte video na Video Frame
vf.setEmbeddedVideo(vid);
// Nastavte režim přehrávání a hlasitost videa
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Krok 7: Uložte prezentaci
Uložte prezentaci s vloženým videem do vámi určeného adresáře.
```java
// Zapište soubor PPTX na disk
pres.save(resultPath, SaveFormat.Pptx);
```
## Krok 8: Vyčistěte zdroje
Nakonec zlikvidujte objekt prezentace, abyste uvolnili zdroje.
```java
// Zlikvidujte předmět prezentace
if (pres != null) pres.dispose();
```
## Závěr
Vkládání videa do prezentací PowerPoint pomocí Aspose.Slides pro Java je jednoduchý proces. Podle kroků uvedených v této příručce můžete své prezentace vylepšit poutavým videoobsahem. Pamatujte, že praxe dělá mistra, takže zkuste vložit různá videa a upravit jejich vlastnosti, abyste viděli, co nejlépe vyhovuje vašim potřebám.
## FAQ
### Mohu do jednoho snímku vložit více videí?
Ano, přidáním více snímků videa můžete do jednoho snímku vložit více videí.
### Jak mohu ovládat přehrávání videa?
 Přehrávání můžete ovládat pomocí`setPlayMode` a`setVolume` metody`IVideoFrame` třída.
### Jaké video formáty podporuje Aspose.Slides?
Aspose.Slides podporuje různé video formáty včetně MP4, AVI a WMV.
### Potřebuji licenci k používání Aspose.Slides?
Ano, k používání Aspose.Slides potřebujete platnou licenci. Můžete získat dočasnou licenci pro vyzkoušení.
### Mohu přizpůsobit velikost a polohu rámečku videa?
Ano, velikost a polohu můžete přizpůsobit nastavením příslušných parametrů při přidávání rámečku videa.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
