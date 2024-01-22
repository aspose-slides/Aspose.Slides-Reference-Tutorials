---
title: Uložit jako předdefinovaný typ zobrazení v Java Slides
linktitle: Uložit jako předdefinovaný typ zobrazení v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit předdefinované typy zobrazení v Java Slides pomocí Aspose.Slides for Java. Podrobný průvodce s příklady kódu a často kladenými dotazy.
type: docs
weight: 10
url: /cs/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

## Úvod do Uložit jako předdefinovaný typ zobrazení v Java Slides

V tomto podrobném průvodci prozkoumáme, jak uložit prezentaci s předdefinovaným typem zobrazení pomocí Aspose.Slides for Java. Poskytneme vám nezbytný kód a vysvětlení k úspěšnému provedení tohoto úkolu.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Základní znalost programování v Javě.
- Nainstalovaná knihovna Aspose.Slides for Java.
- Integrované vývojové prostředí (IDE) dle vašeho výběru.

## Nastavení vašeho prostředí

Chcete-li začít, postupujte podle následujících kroků a nastavte vývojové prostředí:

1. Vytvořte nový Java projekt ve vašem IDE.
2. Přidejte knihovnu Aspose.Slides for Java do svého projektu jako závislost.

Nyní, když je vaše prostředí nastaveno, pojďme pokračovat s kódem.

## Krok 1: Vytvoření prezentace

Abychom předvedli uložení prezentace s předdefinovaným typem pohledu, nejprve vytvoříme novou prezentaci. Zde je kód pro vytvoření prezentace:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Otevření souboru prezentace
Presentation presentation = new Presentation();
```

 V tomto kódu vytvoříme nový`Presentation` objekt, který představuje naši prezentaci v PowerPointu.

## Krok 2: Nastavení typu zobrazení

Dále nastavíme typ zobrazení pro naši prezentaci. Typy zobrazení definují, jak se prezentace zobrazí při otevření. V tomto příkladu jej nastavíme na "Slide Master View". Zde je kód:

```java
// Nastavení typu zobrazení
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Ve výše uvedeném kódu používáme`setLastView` metoda`ViewProperties` třídy, na kterou chcete nastavit typ zobrazení`SlideMasterView`. Podle potřeby můžete zvolit jiné typy zobrazení.

## Krok 3: Uložení prezentace

Nyní, když jsme vytvořili naši prezentaci a nastavili typ zobrazení, je čas prezentaci uložit. Uložíme jej ve formátu PPTX. Zde je kód:

```java
// Ukládání prezentace
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 V tomto kódu používáme`save` metoda`Presentation` třídy k uložení prezentace se zadaným názvem souboru a formátem.

## Kompletní zdrojový kód pro uložení jako předdefinovaný typ zobrazení v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Otevření souboru prezentace
Presentation presentation = new Presentation();
try
{
	// Nastavení typu zobrazení
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Ukládání prezentace
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak uložit prezentaci s předdefinovaným typem zobrazení v Javě pomocí Aspose.Slides for Java. Podle poskytnutého kódu a kroků můžete snadno nastavit typ zobrazení vašich prezentací a uložit je v požadovaném formátu.

## FAQ

### Jak změním typ zobrazení na něco jiného než "Předlohové zobrazení snímku"?

 Chcete-li změnit typ zobrazení na něco jiného než "Předlohové zobrazení snímku", jednoduše nahraďte`ViewType.SlideMasterView` s požadovaným typem pohledu, jako je např`ViewType.NormalView` nebo`ViewType.SlideSorterView`, v kódu, kde nastavujeme typ pohledu.

### Mohu nastavit vlastnosti zobrazení pro jednotlivé snímky v prezentaci?

Ano, můžete nastavit vlastnosti zobrazení pro jednotlivé snímky pomocí Aspose.Slides for Java. Můžete přistupovat a manipulovat s vlastnostmi pro každý snímek samostatně procházením snímků v prezentaci.

### V jakých dalších formátech mohu svou prezentaci uložit?

Aspose.Slides for Java podporuje různé výstupní formáty, včetně PPTX, PDF, TIFF, HTML a dalších. Požadovaný formát můžete určit při ukládání prezentace pomocí příslušného`SaveFormat` hodnotu enum.

### Je Aspose.Slides for Java vhodný pro dávkové zpracování prezentací?

Ano, Aspose.Slides for Java se dobře hodí pro úlohy dávkového zpracování. Pomocí kódu Java můžete automatizovat zpracování více prezentací, aplikovat změny a hromadně je uložit.

### Kde najdu další informace a dokumentaci k Aspose.Slides for Java?

 Pro komplexní dokumentaci a reference související s Aspose.Slides for Java navštivte prosím webovou stránku s dokumentací:[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).