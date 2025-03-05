---
title: Přidejte vlastní text výzvy v Java PowerPointu
linktitle: Přidejte vlastní text výzvy v Java PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak přidat vlastní text výzvy v Java PowerPoint pomocí Aspose.Slides. Vylepšete interakci s uživatelem bez námahy pomocí tohoto výukového programu.
type: docs
weight: 12
url: /cs/java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/
---
## Úvod
dnešní digitální době je vytváření dynamických a poutavých prezentací zásadní pro efektivní komunikaci. Aspose.Slides for Java umožňuje vývojářům programově manipulovat s prezentacemi PowerPoint a nabízí rozsáhlé funkce pro přizpůsobení snímků, tvarů, textu a dalších. Tento výukový program vás provede procesem přidávání vlastního textu výzvy k zástupným symbolům v prezentacích Java PowerPoint pomocí Aspose.Slides.
## Předpoklady
Než se pustíte do tohoto návodu, ujistěte se, že máte následující:
- Základní znalost programování v Javě.
- JDK (Java Development Kit) nainstalovaný ve vašem systému.
-  Aspose.Slides for Java nainstalovány. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
- Nastavení integrovaného vývojového prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse.

## Importujte balíčky
Chcete-li začít, importujte potřebné třídy Aspose.Slides do svého souboru Java:
```java
import com.aspose.slides.*;
```

## Krok 1: Načtěte prezentaci
Nejprve načtěte prezentaci PowerPoint, do které chcete přidat vlastní text výzvy k zástupným symbolům.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
```
## Krok 2: Iterujte tvary snímků
Otevřete snímek a procházejte jeho tvary, abyste našli zástupné symboly.
```java
try {
    ISlide slide = pres.getSlides().get_Item(0);
    for (IShape shape : slide.getShapes()) {
        if (shape.getPlaceholder() != null && shape instanceof AutoShape) {
            // Zpracujte pouze zástupné symboly automatického tvaru
            String text = "";
            if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) {
                text = "Click to add custom title";
            } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) {
                text = "Click to add custom subtitle";
            }
            
            // Nastavte vlastní text výzvy
            ((IAutoShape) shape).getTextFrame().setText(text);
            
            // Pro ověření vytiskněte zástupný text
            System.out.println(String.format("Placeholder with text: %s", text));
        }
    }
    
    //Uložte upravenou prezentaci
    pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Závěr
Závěrem lze říci, že Aspose.Slides for Java zjednodušuje úkol programového přizpůsobení prezentací PowerPoint. Podle tohoto výukového programu můžete zlepšit interakci uživatele tím, že do zástupných symbolů bez námahy přidáte smysluplný text výzvy.
## FAQ
### Mohu přidat text výzvy do libovolného zástupného symbolu na snímku aplikace PowerPoint pomocí Aspose.Slides for Java?
Ano, můžete programově nastavit vlastní text výzvy pro různé typy zástupných symbolů.
### Je Aspose.Slides for Java kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides podporuje širokou škálu verzí aplikace PowerPoint, což zajišťuje kompatibilitu a spolehlivost.
### Kde najdu další příklady a dokumentaci k Aspose.Slides pro Javu?
 Navštivte[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) pro komplexní návody a příklady.
### Jak mohu získat dočasnou licenci pro Aspose.Slides for Java?
 Můžete získat a[dočasná licence](https://purchase.aspose.com/temporary-license/) k vyhodnocení všech funkcí Aspose.Slides.
### Podporuje Aspose.Slides for Java přidávání vlastních animací do snímků?
Ano, Aspose.Slides poskytuje rozhraní API pro programovou správu animací snímků.