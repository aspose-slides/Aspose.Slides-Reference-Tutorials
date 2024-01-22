---
title: Aspose.Slides – Přidávání vložených videí do prezentací .NET
linktitle: Aspose.Slides – Přidávání vložených videí do prezentací .NET
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Vylepšete své prezentace pomocí vložených videí pomocí Aspose.Slides pro .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 19
url: /cs/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## Úvod
V dynamickém světě prezentací může integrace multimediálních prvků výrazně zvýšit zapojení. Aspose.Slides for .NET poskytuje výkonné řešení pro začlenění vložených snímků videa do snímků prezentace. Tento tutoriál vás provede celým procesem a rozebere každý krok, abyste zajistili bezproblémový zážitek.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
-  Aspose.Slides for .NET Library: Stáhněte a nainstalujte knihovnu z[stránka vydání](https://releases.aspose.com/slides/net/).
- Mediální obsah: Mějte video soubor (např. „Wildlife.mp4“), který chcete vložit do své prezentace.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Nastavení adresářů
Ujistěte se, že váš projekt má požadované adresáře pro soubory dokumentů a médií:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Vytvořte adresář, pokud ještě není přítomen.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Krok 2: Okamžitá prezentace
Vytvořte instanci třídy Presentation, která bude reprezentovat soubor PPTX:
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
## Krok 4: Přidejte rámeček videa
Nyní přidejte snímek videa na snímek:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Krok 5: Nastavte vlastnosti videa
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
Opakujte tyto kroky pro každé video, které chcete vložit do prezentace.
## Závěr
Gratulujeme! Pomocí Aspose.Slides for .NET jste do prezentace úspěšně přidali vložený snímek videa. Tato dynamická funkce může pozvednout vaše prezentace do nových výšin a zaujmout vaše publikum multimediálními prvky hladce integrovanými do vašich snímků.
## Nejčastější dotazy
### Mohu vložit videa do libovolného snímku prezentace?
 Ano, můžete si vybrat libovolný snímek úpravou indexu v`pres.Slides[index]`.
### Které video formáty jsou podporovány?
Aspose.Slides podporuje různé formáty videa, včetně MP4, AVI a WMV.
### Mohu přizpůsobit velikost a polohu rámečku videa?
 Absolutně! Upravte parametry v`AddVideoFrame(x, y, width, height, video)` podle potřeby.
### Existuje nějaký limit na počet videí, která mohu vložit?
Počet vložených videí je obvykle omezen kapacitou vašeho prezentačního softwaru.
### Jak mohu vyhledat další pomoc nebo sdílet své zkušenosti?
 Navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) za podporu komunity a diskuze.