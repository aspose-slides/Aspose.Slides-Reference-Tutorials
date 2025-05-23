---
"date": "2025-04-16"
"description": "Naučte se, jak implementovat pravidla pro záložní písma v Aspose.Slides pro .NET, abyste zajistili správné zobrazení textu v prezentacích v různých jazycích a písmech."
"title": "Jak nastavit pravidla pro záložní písma v Aspose.Slides pro .NET – Komplexní průvodce"
"url": "/cs/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak nastavit pravidla pro záložní písma v Aspose.Slides pro .NET: Komplexní průvodce

## Zavedení

Vytváření prezentací pomocí Aspose.Slides pro .NET někdy vyžaduje práci se znaky, které určitá písma nepodporují, například tamilštinu nebo japonskou hiraganu. Nastavení pravidel pro záložní písma je nezbytné pro zajištění správného zobrazení textu v různých jazycích a symbolech v prezentaci.

V tomto tutoriálu vás provedeme implementací pravidel pro záložní fonty pomocí Aspose.Slides pro .NET. Od instalace až po praktické aplikace, tato příručka zajistí, že vaše prezentace si zachovají vizuální konzistenci bez ohledu na obsah.

**Co se naučíte:**
- Definujte rozsahy Unicode pro různé skripty.
- Nastavte záložní písma pro nepodporované znaky.
- Používejte záložní písma v reálných prezentačních scénářích.
- Tipy pro optimalizaci výkonu a integraci s jinými systémy.

Začněme přezkoumáním předpokladů.

## Předpoklady

Než začnete, ujistěte se, že máte:

- **Aspose.Slides pro .NET** Knihovna je nainstalována. Instalaci můžete provést některou z těchto metod:
  - **Rozhraní příkazového řádku .NET**Běh `dotnet add package Aspose.Slides`
  - **Správce balíčků**Provést `Install-Package Aspose.Slides`
  - **Uživatelské rozhraní Správce balíčků NuGet**: Vyhledejte a nainstalujte nejnovější verzi.
- Vývojové prostředí s .NET Core nebo .NET Framework (verze 4.5 nebo novější).
- Základní znalost programování v C#.

## Nastavení Aspose.Slides pro .NET

Chcete-li začít používat Aspose.Slides, získejte licenci od [Webové stránky Aspose](https://purchase.aspose.com/buy)Zde je návod, jak to nastavit:

1. **Instalace**Postupujte podle výše uvedených kroků instalace.
2. **Nastavení licence**:
   - Načtěte licenční soubor do projektu pomocí:
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

Toto nastavení vám umožní začít pracovat s Aspose.Slides pro .NET.

## Průvodce implementací

V této části si v jasných krocích nastíníme proces nastavení pravidel pro záložní písma.

### 1. Definujte rozsahy Unicode a záložní písma

Každý skript nebo sada symbolů vyžaduje specifické rozsahy Unicode a odpovídající záložní písma, aby bylo zajištěno správné zobrazení.

#### Tamilské písmo

- **Přehled**: Pokud primární písmo není podporováno, použijte pro tamilské znaky písmo „Vijaya“.

**Kroky implementace:**

##### Krok 1: Definování rozsahu Unicode
```csharp
uint startUnicodeIndexTamil = 0x0B80; // Začátek tamilského pohoří
uint endUnicodeIndexTamil = 0x0BFF;   // Konec tamilského pohoří
```
Tento úryvek definuje rozsah Unicode pro tamilské znaky.

##### Krok 2: Vytvořte záložní pravidlo
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
Zde vytvoříme záložní pravidlo s použitím písma „Vijaya“ jako alternativního písma.

#### Japonská hiragana

- **Přehled**Pro nepodporované hiraganové znaky použijte „MS Mincho“ nebo „MS Gothic“.

**Kroky implementace:**

##### Krok 1: Definování rozsahu Unicode
```csharp
uint startUnicodeIndexHiragana = 0x3040; // Začátek pohoří Hiragana
uint endUnicodeIndexHiragana = 0x309F;   // Konec hiraganaského pohoří
```
Tento úryvek nastavuje hranice Unicode pro hiraganu.

##### Krok 2: Vytvořte záložní pravidlo
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
Toto pravidlo určuje více záložních písem pro znaky hiragana.

#### Emoji postavy

- **Přehled**: Zajistěte zobrazení emoji pomocí vhodných fontů, jako například „Segoe UI Emoji“.

**Kroky implementace:**

##### Krok 1: Definování rozsahu Unicode
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // Začátek řady emoji
uint endUnicodeIndexEmoji = 0x1F64F;   // Konec rozsahu emotikonů
```
Toto definuje rozsah Unicode pro emoji.

##### Krok 2: Vytvořte záložní pravidlo
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}