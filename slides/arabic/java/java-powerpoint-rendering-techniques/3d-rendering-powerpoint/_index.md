---
"description": "تعلّم كيفية إنشاء عروض تقديمية ثلاثية الأبعاد مذهلة في PowerPoint باستخدام Aspose.Slides لجافا. ارتقِ بعروضك التقديمية إلى مستوى جديد."
"linktitle": "العرض ثلاثي الأبعاد في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "العرض ثلاثي الأبعاد في PowerPoint"
"url": "/ar/java/java-powerpoint-rendering-techniques/3d-rendering-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# العرض ثلاثي الأبعاد في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية دمج عرض ثلاثي الأبعاد مذهل في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. باتباع هذه التعليمات خطوة بخطوة، ستتمكن من إنشاء تأثيرات بصرية آسرة تُبهر جمهورك.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. بيئة تطوير جافا: تأكد من تثبيت جافا على نظامك. يمكنك تنزيل جافا وتثبيتها من [هنا](https://www.java.com/download/).
2. Aspose.Slides لمكتبة Java: قم بتنزيل مكتبة Aspose.Slides لمكتبة Java من [موقع إلكتروني](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المقدمة في الوثائق لإعداد المكتبة في مشروعك.
## استيراد الحزم
للبدء، قم باستيراد الحزم اللازمة إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.*;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: إنشاء عرض تقديمي جديد
أولاً، قم بإنشاء كائن عرض تقديمي جديد في PowerPoint:
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة شكل ثلاثي الأبعاد
الآن، دعونا نضيف شكلًا ثلاثي الأبعاد إلى الشريحة:
```java
IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 150, 200, 200);
shape.getTextFrame().setText("3D");
shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(64);
```
## الخطوة 3: تكوين إعدادات ثلاثية الأبعاد
بعد ذلك، قم بتكوين إعدادات ثلاثية الأبعاد للشكل:
```java
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getCamera().setRotation(20, 30, 40);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Flat);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
shape.getThreeDFormat().setMaterial(MaterialPresetType.Powder);
shape.getThreeDFormat().setExtrusionHeight(100);
shape.getThreeDFormat().getExtrusionColor().setColor(Color.BLUE);
```
## الخطوة 4: حفظ العرض التقديمي
بعد تكوين إعدادات ثلاثية الأبعاد، احفظ العرض التقديمي:
```java
String outPptxFile = "Your Output Directory" + "sandbox_3d.pptx";
String outPngFile = "Your Output Directory" + "sample_3d.png";
try {
    ImageIO.write(pres.getSlides().get_Item(0).getThumbnail(2, 2), "PNG", new File(outPngFile));
    pres.save(outPptxFile, SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## خاتمة
تهانينا! لقد نجحت في تعلّم كيفية إنشاء عروض تقديمية ثلاثية الأبعاد مذهلة في PowerPoint باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات البسيطة، يمكنك الارتقاء بعروضك التقديمية إلى مستوى جديد وجذب جمهورك بتأثيرات بصرية غامرة.
## الأسئلة الشائعة
### هل يمكنني تخصيص الشكل الثلاثي الأبعاد بشكل أكبر؟
نعم، يمكنك استكشاف الخصائص والطرق المختلفة التي يوفرها Aspose.Slides لتخصيص الشكل ثلاثي الأبعاد وفقًا لمتطلباتك.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يدعم Aspose.Slides تنسيقات PowerPoint المختلفة، مما يضمن التوافق بين الإصدارات المختلفة للبرنامج.
### هل يمكنني إضافة الرسوم المتحركة إلى الأشكال ثلاثية الأبعاد؟
بالتأكيد! يوفر Aspose.Slides دعمًا شاملاً لإضافة الرسوم المتحركة والانتقالات إلى عروض PowerPoint التقديمية، بما في ذلك الأشكال ثلاثية الأبعاد.
### هل هناك أي قيود على إمكانيات العرض ثلاثي الأبعاد؟
على الرغم من أن Aspose.Slides يوفر ميزات عرض ثلاثية الأبعاد متقدمة، فمن الضروري مراعاة التأثيرات على الأداء، خاصة عند العمل مع مشاهد معقدة أو عروض تقديمية كبيرة.
### أين يمكنني العثور على موارد ودعم إضافي لـ Aspose.Slides؟
يمكنك زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة والتوثيق ودعم المجتمع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}