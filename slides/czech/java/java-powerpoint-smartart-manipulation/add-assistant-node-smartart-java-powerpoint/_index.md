---
title: Přidejte uzel asistenta k obrázku SmartArt v aplikaci Java PowerPoint
linktitle: Přidejte uzel asistenta k obrázku SmartArt v aplikaci Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak přidat uzel asistenta k obrázku SmartArt v prezentacích Java PowerPoint pomocí Aspose.Slides. Vylepšete své schopnosti upravovat PowerPoint.
weight: 17
url: /cs/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V tomto tutoriálu vás provedeme procesem přidání uzlu asistenta do SmartArt v prezentacích Java PowerPoint pomocí Aspose.Slides.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu. Nejnovější JDK si můžete stáhnout a nainstalovat z[tady](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Stáhněte si a nainstalujte knihovnu Aspose.Slides for Java z[tento odkaz](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do kódu Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Nastavte prezentaci
Začněte vytvořením instance prezentace pomocí cesty k vašemu souboru PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Krok 2: Procházejte tvary
Projděte každý tvar v prvním snímku prezentace:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Krok 3: Zkontrolujte tvary SmartArt
Zkontrolujte, zda je tvar typu SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Krok 4: Procházení uzlů SmartArt
Projděte všemi uzly tvaru SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Krok 5: Vyhledejte uzel Assistant
Zkontrolujte, zda je uzel pomocný uzel:
```java
if (node.isAssistant())
```
## Krok 6: Nastavte Assistant Node na Normální
Pokud je uzel pomocný uzel, nastavte jej na normální uzel:
```java
node.setAssistant(false);
```
## Krok 7: Uložte prezentaci
Uložte upravenou prezentaci:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Závěr
Gratulujeme! Úspěšně jste přidali uzel asistenta k obrázku SmartArt ve své prezentaci Java PowerPoint pomocí Aspose.Slides.

## FAQ
### Mohu k obrázku SmartArt v prezentaci přidat více uzlů asistenta?
Ano, můžete přidat více uzlů asistenta opakováním procesu pro každý uzel.
### Funguje tento návod pro PowerPoint i PowerPoint šablony?
Ano, tento výukový program můžete použít jak na prezentace v PowerPointu, tak na šablony.
### Je Aspose.Slides kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides podporuje verze aplikace PowerPoint od 97-2003 po nejnovější verzi.
### Mohu přizpůsobit vzhled uzlu asistenta?
Ano, vzhled můžete přizpůsobit pomocí různých vlastností a metod poskytovaných Aspose.Slides.
### Existuje nějaké omezení počtu uzlů v obrázku SmartArt?
SmartArt v PowerPointu podporuje velký počet uzlů, ale pro lepší čitelnost se doporučuje ponechat jej v rozumné míře.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
