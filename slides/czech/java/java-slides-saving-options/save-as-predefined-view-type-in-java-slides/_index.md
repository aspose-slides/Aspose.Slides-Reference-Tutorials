---
"description": "Naučte se, jak nastavit předdefinované typy zobrazení v Java Slides pomocí Aspose.Slides pro Javu. Podrobný návod s příklady kódu a častými dotazy."
"linktitle": "Uložit jako předdefinovaný typ zobrazení v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Uložit jako předdefinovaný typ zobrazení v Java Slides"
"url": "/cs/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Uložit jako předdefinovaný typ zobrazení v Java Slides


## Úvod do předdefinovaného typu zobrazení Uložit jako v Java Slides

V tomto podrobném návodu se podíváme na to, jak uložit prezentaci s předdefinovaným typem zobrazení pomocí Aspose.Slides pro Javu. Poskytneme vám potřebný kód a vysvětlení pro úspěšné provedení tohoto úkolu.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Základní znalost programování v Javě.
- Nainstalována knihovna Aspose.Slides pro Javu.
- Integrované vývojové prostředí (IDE) dle vašeho výběru.

## Nastavení prostředí

Chcete-li začít, nastavte si vývojové prostředí podle těchto kroků:

1. Vytvořte nový projekt Java ve vašem IDE.
2. Přidejte do projektu knihovnu Aspose.Slides pro Javu jako závislost.

Nyní, když je vaše prostředí nastavené, pojďme pokračovat s kódem.

## Krok 1: Vytvoření prezentace

Abychom demonstrovali uložení prezentace s předdefinovaným typem zobrazení, nejprve vytvoříme novou prezentaci. Zde je kód pro vytvoření prezentace:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Otevření souboru prezentace
Presentation presentation = new Presentation();
```

V tomto kódu vytvoříme nový `Presentation` objekt, který představuje naši prezentaci v PowerPointu.

## Krok 2: Nastavení typu zobrazení

Dále nastavíme typ zobrazení pro naši prezentaci. Typy zobrazení definují, jak se prezentace zobrazí po otevření. V tomto příkladu ji nastavíme na „Zobrazení předlohy snímků“. Zde je kód:

```java
// Nastavení typu zobrazení
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

Ve výše uvedeném kódu používáme `setLastView` metoda `ViewProperties` třída pro nastavení typu zobrazení `SlideMasterView`V případě potřeby si můžete zvolit i jiné typy zobrazení.

## Krok 3: Uložení prezentace

Nyní, když jsme si vytvořili prezentaci a nastavili typ zobrazení, je čas ji uložit. Uložíme ji ve formátu PPTX. Zde je kód:

```java
// Ukládání prezentace
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

V tomto kódu používáme `save` metoda `Presentation` třída pro uložení prezentace se zadaným názvem souboru a formátem.

## Kompletní zdrojový kód pro uložení jako předdefinovaný typ zobrazení v Java Slides

```java
// Cesta k adresáři s dokumenty.
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

tomto tutoriálu jsme se naučili, jak uložit prezentaci s předdefinovaným typem zobrazení v Javě pomocí Aspose.Slides pro Javu. Dodržením poskytnutého kódu a kroků můžete snadno nastavit typ zobrazení vašich prezentací a uložit je v požadovaném formátu.

## Často kladené otázky

### Jak změním typ zobrazení na jiný než „Zobrazení předlohy snímků“?

Chcete-li změnit typ zobrazení na jiný než „Zobrazení předlohy snímků“, jednoduše nahraďte `ViewType.SlideMasterView` s požadovaným typem zobrazení, například `ViewType.NnebomalView` or `ViewType.SlideSorterView`, v kódu, kde nastavujeme typ zobrazení.

### Mohu nastavit vlastnosti zobrazení pro jednotlivé snímky v prezentaci?

Ano, vlastnosti zobrazení pro jednotlivé snímky můžete nastavit pomocí Aspose.Slides pro Javu. Vlastnosti každého snímku můžete procházet a upravovat je samostatně iterací mezi snímky v prezentaci.

### V jakých dalších formátech mohu uložit svou prezentaci?

Aspose.Slides pro Javu podporuje různé výstupní formáty, včetně PPTX, PDF, TIFF, HTML a dalších. Požadovaný formát můžete při ukládání prezentace určit pomocí příslušných `SaveFormat` hodnota výčtu.

### Je Aspose.Slides pro Javu vhodný pro dávkové zpracování prezentací?

Ano, Aspose.Slides pro Javu je vhodný pro dávkové zpracování. Můžete automatizovat zpracování více prezentací, aplikovat změny a hromadně je ukládat pomocí kódu Java.

### Kde najdu více informací a dokumentaci k Aspose.Slides pro Javu?

Úplnou dokumentaci a reference týkající se Aspose.Slides pro Javu naleznete na webových stránkách s dokumentací: [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}