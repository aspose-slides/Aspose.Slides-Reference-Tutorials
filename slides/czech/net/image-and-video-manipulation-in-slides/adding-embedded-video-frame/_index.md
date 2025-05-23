---
"description": "Vylepšete své prezentace vloženými videi pomocí Aspose.Slides pro .NET. Pro bezproblémovou integraci postupujte podle našeho podrobného návodu."
"linktitle": "Aspose.Slides - Přidávání vložených videí do prezentací .NET"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Aspose.Slides - Přidávání vložených videí do prezentací .NET"
"url": "/cs/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Přidávání vložených videí do prezentací .NET

## Zavedení
V dynamickém světě prezentací může integrace multimediálních prvků výrazně zvýšit zapojení. Aspose.Slides pro .NET nabízí výkonné řešení pro začlenění vložených video snímků do snímků vaší prezentace. Tento tutoriál vás provede celým procesem a rozebere jednotlivé kroky, aby byl zajištěn bezproblémový zážitek.
## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte následující:
- Knihovna Aspose.Slides pro .NET: Stáhněte a nainstalujte knihovnu z [stránka s vydáním](https://releases.aspose.com/slides/net/).
- Mediální obsah: Mějte video soubor (např. „Wildlife.mp4“), který chcete vložit do prezentace.
## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů do vašeho projektu .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Nastavení adresářů
Ujistěte se, že váš projekt obsahuje požadované adresáře pro dokumenty a mediální soubory:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Vytvořte adresář, pokud ještě neexistuje.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Krok 2: Vytvoření instance třídy prezentací
Vytvořte instanci třídy Presentation pro reprezentaci souboru PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Získejte první snímek
    ISlide sld = pres.Slides[0];
```
## Krok 3: Vložení videa do prezentace
Pro vložení videa do prezentace použijte následující kód:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Krok 4: Přidání videorámečku
Nyní přidejte do snímku videorámeček:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Krok 5: Nastavení vlastností videa
Nastavte video na snímek videa a nakonfigurujte režim přehrávání a hlasitost:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Krok 6: Uložte prezentaci
Nakonec uložte soubor PPTX na disk:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Tyto kroky opakujte pro každé video, které chcete vložit do prezentace.
## Závěr
Gratulujeme! Úspěšně jste do své prezentace přidali vložený videorámeček pomocí Aspose.Slides pro .NET. Tato dynamická funkce dokáže pozvednout vaše prezentace na novou úroveň a zaujmout publikum multimediálními prvky bezproblémově integrovanými do vašich snímků.
## Často kladené otázky
### Mohu vložit videa do libovolného snímku prezentace?
Ano, můžete si vybrat libovolný snímek úpravou indexu v `pres.Slides[index]`.
### Které formáty videa jsou podporovány?
Aspose.Slides podporuje řadu video formátů, včetně MP4, AVI a WMV.
### Mohu si přizpůsobit velikost a polohu videozáznamu?
Rozhodně! Upravte parametry v `AddVideoFrame(x, y, width, height, video)` podle potřeby.
### Existuje nějaký limit pro počet videí, která můžu vložit?
Počet vložených videí je obvykle omezen kapacitou vašeho prezentačního softwaru.
### Jak mohu vyhledat další pomoc nebo se podělit o své zkušenosti?
Navštivte [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) pro podporu a diskuze v komunitě.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}