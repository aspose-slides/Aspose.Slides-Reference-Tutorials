---
title: Přidejte uživatelské vlastnosti dokumentu do snímků Java
linktitle: Přidejte uživatelské vlastnosti dokumentu do snímků Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak vylepšit prezentace v PowerPointu pomocí vlastních vlastností dokumentu v Java Slides. Podrobný průvodce s příklady kódu pomocí Aspose.Slides pro Javu.
weight: 13
url: /cs/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte uživatelské vlastnosti dokumentu do snímků Java


## Úvod do přidávání uživatelských vlastností dokumentu v Java Slides

V tomto tutoriálu vás provedeme procesem přidávání vlastních vlastností dokumentu do prezentace PowerPoint pomocí Aspose.Slides for Java. Vlastní vlastnosti dokumentu vám umožňují uložit další informace o prezentaci pro referenci nebo kategorizaci.

## Předpoklady

Než začnete, ujistěte se, že máte v projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java.

## Krok 1: Importujte požadované balíčky

```java
import com.aspose.slides.*;
```

## Krok 2: Vytvořte novou prezentaci

Nejprve musíte vytvořit nový objekt prezentace. Můžete to udělat následovně:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Vytvořte instanci třídy Prezentace
Presentation presentation = new Presentation();
```

## Krok 3: Získání vlastností dokumentu

Dále načtete vlastnosti dokumentu prezentace. Tyto vlastnosti zahrnují vestavěné vlastnosti, jako je název, autor a uživatelské vlastnosti, které můžete přidat.

```java
// Získání vlastností dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Krok 4: Přidání uživatelských vlastností

Nyní do prezentace přidáme vlastní vlastnosti. Uživatelské vlastnosti se skládají z názvu a hodnoty. Můžete je použít k uložení jakýchkoli informací, které chcete.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Krok 5: Získání názvu vlastnosti u konkrétního indexu

Můžete také načíst název uživatelské vlastnosti na konkrétním indexu. To může být užitečné, pokud potřebujete pracovat s konkrétními vlastnostmi.

```java
// Získání názvu vlastnosti na konkrétním indexu
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Krok 6: Odstranění vybrané vlastnosti

Pokud chcete odebrat uživatelskou vlastnost, můžete tak učinit zadáním jejího názvu. Zde odstraňujeme vlastnost, kterou jsme získali v kroku 5.

```java
// Odebírání vybrané vlastnosti
documentProperties.removeCustomProperty(getPropertyName);
```

## Krok 7: Uložení prezentace

Nakonec uložte prezentaci s přidanými a odebranými uživatelskými vlastnostmi do souboru.

```java
// Ukládání prezentace
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro přidání uživatelských vlastností dokumentu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Prezentace
Presentation presentation = new Presentation();
// Získání vlastností dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Přidání uživatelských vlastností
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Získání názvu vlastnosti na konkrétním indexu
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Odebírání vybrané vlastnosti
documentProperties.removeCustomProperty(getPropertyName);
// Ukládání prezentace
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Závěr

Naučili jste se, jak přidat vlastní vlastnosti dokumentu do PowerPointové prezentace v Javě pomocí Aspose.Slides. Vlastní vlastnosti mohou být cenné pro ukládání dalších informací souvisejících s vašimi prezentacemi. Tyto znalosti můžete rozšířit tak, aby zahrnovaly více vlastních vlastností podle potřeby pro váš konkrétní případ použití.

## FAQ

### Jak získám hodnotu vlastní vlastnosti?

 Chcete-li načíst hodnotu uživatelské vlastnosti, můžete použít`get_Item` metoda na`documentProperties` objekt. Například:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Mohu přidat vlastní vlastnosti různých typů dat?

Ano, můžete přidat vlastní vlastnosti různých typů dat, včetně čísel, řetězců, dat a dalších, jak je znázorněno v příkladu. Aspose.Slides pro Java bez problémů zvládá různé typy dat.

### Existuje omezení počtu vlastních vlastností, které mohu přidat?

Počet vlastních vlastností, které můžete přidat, není striktně omezen. Mějte však na paměti, že přidání nadměrného počtu vlastností může ovlivnit výkon a velikost souboru prezentace.

### Jak mohu uvést všechny uživatelské vlastnosti v prezentaci?

Můžete procházet všechny uživatelské vlastnosti a vypsat je. Zde je příklad, jak to udělat:

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
