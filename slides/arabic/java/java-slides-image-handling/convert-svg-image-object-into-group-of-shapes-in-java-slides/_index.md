---
"description": "تعرّف على كيفية تحويل صور SVG إلى مجموعة أشكال في Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة برمجية."
"linktitle": "تحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java"
"url": "/ar/java/image-handling/convert-svg-image-object-into-group-of-shapes-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java


## مقدمة لتحويل كائنات صورة SVG إلى مجموعة من الأشكال في شرائح Java

في هذا الدليل الشامل، سنستكشف كيفية تحويل صورة SVG إلى مجموعة أشكال في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. تُمكّن هذه المكتبة القوية المطورين من التعامل مع عروض PowerPoint التقديمية برمجيًا، مما يجعلها أداة قيّمة لمختلف المهام، بما في ذلك التعامل مع الصور.

## المتطلبات الأساسية

قبل أن نتعمق في الكود والتعليمات خطوة بخطوة، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

الآن بعد أن قمنا بإعداد كل شيء، فلنبدأ.

## الخطوة 1: استيراد المكتبات الضرورية

للبدء، عليك استيراد المكتبات اللازمة لمشروع جافا. تأكد من تضمين Aspose.Slides لجافا.

```java
import com.aspose.slides.*;
```

## الخطوة 2: تحميل العرض التقديمي

بعد ذلك، ستحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على كائن صورة SVG. استبدل `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "image.pptx");
```

## الخطوة 3: استرداد صورة SVG

الآن، لنسترجع صورة SVG من عرض PowerPoint التقديمي. سنفترض أن صورة SVG موجودة في الشريحة الأولى، وهي الشكل الأول فيها.

```java
try
{
    PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
```

## الخطوة 4: تحويل صورة SVG إلى مجموعة من الأشكال

بعد أن أصبحت صورة SVG بين أيدينا، يُمكننا الآن تحويلها إلى مجموعة أشكال. يُمكن تحقيق ذلك بإضافة مجموعة أشكال جديدة إلى الشريحة وإزالة صورة SVG المصدر.

```java
    if (svgImage != null)
    {
        // تحويل صورة svg إلى مجموعة من الأشكال
        IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes()
                .addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                        pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());

        // إزالة صورة SVG المصدر من العرض التقديمي
        pres.getSlides().get_Item(0).getShapes().remove(pFrame);
    }
```

## الخطوة 5: حفظ العرض التقديمي المعدّل

بمجرد تحويل صورة SVG بنجاح إلى مجموعة من الأشكال، احفظ العرض التقديمي المعدل في ملف جديد.

```java
    pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
}
finally
{
    pres.dispose();
}
```

تهانينا! لقد تعلمت الآن كيفية تحويل صورة SVG إلى مجموعة أشكال في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java.

## كود المصدر الكامل لتحويل كائن صورة SVG إلى مجموعة من الأشكال في شرائح Java

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
                // إزالة صورة svg المصدر من العرض التقديمي
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

في هذا البرنامج التعليمي، استكشفنا عملية تحويل صورة SVG إلى مجموعة أشكال ضمن عرض تقديمي في PowerPoint باستخدام Java ومكتبة Aspose.Slides لـ Java. تتيح هذه الميزة إمكانيات عديدة لتحسين عروضك التقديمية بمحتوى ديناميكي.

## الأسئلة الشائعة

### هل يمكنني تحويل تنسيقات الصور الأخرى إلى مجموعة من الأشكال باستخدام Aspose.Slides؟

نعم، يدعم Aspose.Slides تنسيقات صور متنوعة، وليس فقط SVG. يمكنك تحويل تنسيقات مثل PNG وJPEG وغيرها إلى مجموعة من الأشكال ضمن عرض تقديمي في PowerPoint.

### هل Aspose.Slides مناسب لأتمتة عروض PowerPoint؟

بالتأكيد! يوفر Aspose.Slides ميزات فعّالة لأتمتة عروض PowerPoint التقديمية، مما يجعله أداة قيّمة لمهام مثل إنشاء الشرائح وتحريرها ومعالجتها برمجيًا.

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides لـ Java؟

نعم، يتطلب Aspose.Slides ترخيصًا ساريًا للاستخدام التجاري. يمكنك الحصول على الترخيص من موقع Aspose الإلكتروني. مع ذلك، يُقدم الموقع نسخة تجريبية مجانية لأغراض التقييم.

### هل يمكنني تخصيص مظهر الأشكال المحولة؟

بالتأكيد! يمكنك تخصيص مظهر وحجم وموضع الأشكال المُحوّلة حسب احتياجاتك. يوفر Aspose.Slides واجهات برمجة تطبيقات شاملة لمعالجة الأشكال.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}