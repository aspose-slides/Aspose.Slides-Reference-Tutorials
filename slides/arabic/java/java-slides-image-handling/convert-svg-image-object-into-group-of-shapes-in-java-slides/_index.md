---
title: تحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java
linktitle: تحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل صور SVG إلى مجموعة من الأشكال في Java Slides باستخدام Aspose.Slides for Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
weight: 13
url: /ar/java/image-handling/convert-svg-image-object-into-group-of-shapes-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java


## مقدمة لتحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java

في هذا الدليل الشامل، سوف نستكشف كيفية تحويل كائن صورة SVG إلى مجموعة من الأشكال في Java Slides باستخدام Aspose.Slides for Java API. تمكن هذه المكتبة القوية المطورين من التعامل مع عروض PowerPoint التقديمية برمجياً، مما يجعلها أداة قيمة لمختلف المهام، بما في ذلك التعامل مع الصور.

## المتطلبات الأساسية

قبل أن نتعمق في التعليمات البرمجية والتعليمات خطوة بخطوة، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

الآن بعد أن قمنا بإعداد كل شيء، فلنبدأ.

## الخطوة 1: استيراد المكتبات الضرورية

للبدء، تحتاج إلى استيراد المكتبات المطلوبة لمشروع Java الخاص بك. تأكد من تضمين Aspose.Slides لـ Java.

```java
import com.aspose.slides.*;
```

## الخطوة 2: قم بتحميل العرض التقديمي

 بعد ذلك، ستحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على كائن صورة SVG. يستبدل`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "image.pptx");
```

## الخطوة 3: استرداد صورة SVG

الآن، دعونا نستعيد كائن صورة SVG من عرض PowerPoint التقديمي. سنفترض أن صورة SVG موجودة في الشريحة الأولى وهي الشكل الأول في تلك الشريحة.

```java
try
{
    PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
```

## الخطوة 4: تحويل صورة SVG إلى مجموعة من الأشكال

مع وجود صورة SVG في متناول اليد، يمكننا الآن تحويلها إلى مجموعة من الأشكال. يمكن تحقيق ذلك عن طريق إضافة شكل مجموعة جديد إلى الشريحة وإزالة صورة SVG المصدر.

```java
    if (svgImage != null)
    {
        // تحويل صورة svg إلى مجموعة من الأشكال
        IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes()
                .addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                        pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());

        // قم بإزالة صورة SVG المصدر من العرض التقديمي
        pres.getSlides().get_Item(0).getShapes().remove(pFrame);
    }
```

## الخطوة 5: احفظ العرض التقديمي المعدل

بمجرد نجاحك في تحويل صورة SVG إلى مجموعة من الأشكال، احفظ العرض التقديمي المعدل في ملف جديد.

```java
    pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
}
finally
{
    pres.dispose();
}
```

تهانينا! لقد تعلمت الآن كيفية تحويل كائن صورة SVG إلى مجموعة من الأشكال في Java Slides باستخدام Aspose.Slides for Java API.

## أكمل كود المصدر لتحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java

```java
        // المسار إلى دليل المستندات.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "image.pptx");
        try
        {
            PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
            if (svgImage != null)
            {
                // تحويل صورة svg إلى مجموعة من الأشكال
                IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes().
                        addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                                pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());
                // إزالة صورة Svg المصدر من العرض التقديمي
                pres.getSlides().get_Item(0).getShapes().remove(pFrame);
            }
            pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
        }
        finally
        {
            pres.dispose();
        }
```

## خاتمة

في هذا البرنامج التعليمي، استكشفنا عملية تحويل كائن صورة SVG إلى مجموعة من الأشكال ضمن عرض تقديمي لـ PowerPoint باستخدام Java ومكتبة Aspose.Slides لـ Java. تفتح هذه الوظيفة إمكانيات عديدة لتحسين عروضك التقديمية بمحتوى ديناميكي.

## الأسئلة الشائعة

### هل يمكنني تحويل تنسيقات صور أخرى إلى مجموعة من الأشكال باستخدام Aspose.Slides؟

نعم، يدعم Aspose.Slides تنسيقات الصور المختلفة، وليس SVG فقط. يمكنك تحويل تنسيقات مثل PNG وJPEG وغيرها إلى مجموعة من الأشكال داخل عرض PowerPoint التقديمي.

### هل Aspose.Slides مناسب لأتمتة عروض PowerPoint التقديمية؟

قطعاً! يوفر Aspose.Slides ميزات قوية لأتمتة عروض PowerPoint التقديمية، مما يجعله أداة قيمة لمهام مثل إنشاء الشرائح وتحريرها ومعالجتها برمجيًا.

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides لـ Java؟

نعم، يتطلب Aspose.Slides ترخيصًا صالحًا للاستخدام التجاري. يمكنك الحصول على ترخيص من موقع Aspose. ومع ذلك، فهو يقدم نسخة تجريبية مجانية لأغراض التقييم.

### هل يمكنني تخصيص مظهر الأشكال المحولة؟

بالتأكيد! يمكنك تخصيص مظهر الأشكال المحولة وحجمها وموضعها وفقًا لمتطلباتك. يوفر Aspose.Slides واجهات برمجة تطبيقات واسعة النطاق لمعالجة الأشكال.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
