---
"description": "Naučte se v tomto podrobném tutoriálu, jak vkládat video snímky do PowerPointu pomocí Aspose.Slides pro Javu. Snadno vylepšete své prezentace."
"linktitle": "Přidání vloženého videorámečku v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání vloženého videorámečku v PowerPointu"
"url": "/cs/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání vloženého videorámečku v PowerPointu

## Zavedení
Přidání videí do vašich prezentací v PowerPointu je může učinit poutavějšími a informativnějšími. Pomocí Aspose.Slides pro Javu můžete snadno vkládat videa přímo do svých snímků. V tomto tutoriálu vás krok za krokem provedeme celým procesem a ujistíme se, že rozumíte každé části kódu a tomu, jak funguje. Ať už jste zkušený vývojář, nebo teprve začínáte, tento průvodce vám pomůže vylepšit vaše prezentace pomocí vložených videí.
## Předpoklady
Než se pustíte do kódu, ujistěte se, že máte splněny následující předpoklady:
1. Vývojová sada Java (JDK): Ujistěte se, že máte na svém počítači nainstalovanou JDK.
2. Aspose.Slides pro Javu: Stáhněte a nainstalujte knihovnu Aspose.Slides pro Javu.
3. Integrované vývojové prostředí (IDE): Pro lepší vývojový zážitek použijte IDE, jako je IntelliJ IDEA nebo Eclipse.
4. Videosoubor: Mějte videosoubor, který chcete vložit do prezentace v PowerPointu.
## Importovat balíčky
Nejprve budete muset importovat potřebné balíčky pro práci s Aspose.Slides. Tyto importy vám pomohou spravovat snímky, videa a prezentační soubory.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Krok 1: Nastavení prostředí
Než začnete s kódováním, ujistěte se, že je vaše prostředí správně nastaveno. To zahrnuje vytvoření potřebných adresářů a přípravu video souboru.
```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Vytvořte adresář, pokud ještě neexistuje.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Krok 2: Vytvoření instance třídy prezentací
Vytvořte instanci `Presentation` třída. Tato třída představuje váš soubor PowerPoint.
```java
// Vytvořte instanci třídy Presentation, která reprezentuje PPTX
Presentation pres = new Presentation();
```
## Krok 3: Získejte první snímek
Otevřete první snímek v prezentaci, kam vložíte video.
```java
// Získejte první snímek
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Přidání videa do prezentace
Vložte video soubor do prezentace. Ujistěte se, že je správně zadána cesta k videu.
```java
// Vložení videa do prezentace
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Krok 5: Přidání videosnímku do snímku
Vytvořte na snímku videorámeček a nastavte jeho rozměry a umístění.
```java
// Přidat videorámeček
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Krok 6: Konfigurace vlastností video snímku
Nastavte video na snímek videa a nakonfigurujte jeho nastavení přehrávání, jako je režim přehrávání a hlasitost.
```java
// Nastavit video na videorámeček
vf.setEmbeddedVideo(vid);
// Nastavení režimu přehrávání a hlasitosti videa
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Krok 7: Uložte prezentaci
Uložte prezentaci s vloženým videem do vámi určeného adresáře.
```java
// Zapište soubor PPTX na disk
pres.save(resultPath, SaveFormat.Pptx);
```
## Krok 8: Vyčištění zdrojů
Nakonec zlikvidujte prezentační objekt, abyste uvolnili prostředky.
```java
// Zlikvidujte prezentační objekt
if (pres != null) pres.dispose();
```
## Závěr
Vkládání videa do vašich prezentací v PowerPointu pomocí Aspose.Slides pro Javu je jednoduchý proces. Dodržováním kroků uvedených v této příručce můžete své prezentace vylepšit poutavým video obsahem. Nezapomeňte, že cvičení dělá mistra, proto zkuste vkládat různá videa a upravovat jejich vlastnosti, abyste zjistili, co nejlépe vyhovuje vašim potřebám.
## Často kladené otázky
### Mohu vložit více videí do jednoho snímku?
Ano, do jednoho snímku můžete vložit více videí přidáním více videosnímků.
### Jak mohu ovládat přehrávání videa?
Přehrávání můžete ovládat pomocí `setPlayMode` a `setVolume` metody `IVideoFrame` třída.
### Jaké video formáty podporuje Aspose.Slides?
Aspose.Slides podporuje různé video formáty včetně MP4, AVI a WMV.
### Potřebuji licenci k používání Aspose.Slides?
Ano, k používání Aspose.Slides potřebujete platnou licenci. Pro účely vyhodnocení můžete získat dočasnou licenci.
### Mohu si přizpůsobit velikost a polohu videozáznamu?
Ano, velikost a polohu můžete přizpůsobit nastavením příslušných parametrů při přidávání video snímku.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}