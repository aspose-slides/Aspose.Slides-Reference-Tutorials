---
"description": "Naučte se, jak vylepšit prezentace v PowerPointu pomocí vlastních vlastností dokumentů v Java Slides. Podrobný návod s příklady kódu pomocí Aspose.Slides pro Javu."
"linktitle": "Přidání vlastních vlastností dokumentu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání vlastních vlastností dokumentu v Java Slides"
"url": "/cs/java/presentation-properties/add-custom-document-properties-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání vlastních vlastností dokumentu v Java Slides


## Úvod do přidávání vlastních vlastností dokumentu v Java Slides

V tomto tutoriálu vás provedeme procesem přidání vlastních vlastností dokumentu do prezentace v PowerPointu pomocí Aspose.Slides pro Javu. Vlastní vlastnosti dokumentu vám umožňují ukládat další informace o prezentaci pro účely reference nebo kategorizace.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java.

## Krok 1: Importujte požadované balíčky

```java
import com.aspose.slides.*;
```

## Krok 2: Vytvořte novou prezentaci

Nejprve je třeba vytvořit nový prezentační objekt. Můžete to provést následovně:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 3: Získání vlastností dokumentu

Dále načtete vlastnosti dokumentu prezentace. Mezi tyto vlastnosti patří vestavěné vlastnosti, jako je název, autor a vlastní vlastnosti, které můžete přidat.

```java
// Získání vlastností dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Krok 4: Přidání vlastních vlastností

Nyní si do prezentace přidejme vlastní vlastnosti. Vlastní vlastnosti se skládají z názvu a hodnoty. Můžete je použít k uložení libovolných informací.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Krok 5: Získání názvu vlastnosti na konkrétním indexu

Název vlastní vlastnosti můžete také načíst v určitém indexu. To může být užitečné, pokud potřebujete pracovat s konkrétními vlastnostmi.

```java
// Získání názvu vlastnosti na konkrétním indexu
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Krok 6: Odebrání vybrané vlastnosti

Pokud chcete odebrat vlastní vlastnost, můžete tak učinit zadáním jejího názvu. Zde odstraňujeme vlastnost, kterou jsme získali v kroku 5.

```java
// Odebrání vybrané vlastnosti
documentProperties.removeCustomProperty(getPropertyName);
```

## Krok 7: Uložení prezentace

Nakonec uložte prezentaci s přidanými a odebranými uživatelskými vlastnostmi do souboru.

```java
// Ukládání prezentace
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro přidání vlastních vlastností dokumentu v Java Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
// Získání vlastností dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Přidávání vlastních vlastností
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Získání názvu vlastnosti na konkrétním indexu
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Odebrání vybrané vlastnosti
documentProperties.removeCustomProperty(getPropertyName);
// Ukládání prezentace
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Závěr

Naučili jste se, jak přidat vlastní vlastnosti dokumentu do prezentace v PowerPointu v Javě pomocí Aspose.Slides. Vlastní vlastnosti mohou být cenné pro ukládání dalších informací souvisejících s vašimi prezentacemi. Tyto znalosti můžete rozšířit a podle potřeby zahrnout další vlastní vlastnosti pro váš konkrétní případ použití.

## Často kladené otázky

### Jak načtu hodnotu vlastní vlastnosti?

Chcete-li načíst hodnotu vlastní vlastnosti, můžete použít `get_Item` metoda na `documentProperties` objekt. Například:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Mohu přidat vlastní vlastnosti různých datových typů?

Ano, můžete přidat vlastní vlastnosti různých datových typů, včetně čísel, řetězců, dat a dalších, jak je znázorněno v příkladu. Aspose.Slides pro Javu bez problémů zpracovává různé datové typy.

### Existuje omezení počtu vlastních vlastností, které mohu přidat?

Neexistuje žádný striktní limit pro počet vlastních vlastností, které můžete přidat. Mějte však na paměti, že přidání nadměrného počtu vlastností může ovlivnit výkon a velikost souboru prezentace.

### Jak mohu v prezentaci zobrazit seznam všech uživatelských vlastností?

Všechny uživatelské vlastnosti můžete procházet a zobrazit je. Zde je příklad, jak to udělat:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Tento kód zobrazí názvy a hodnoty všech uživatelských vlastností v prezentaci.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}