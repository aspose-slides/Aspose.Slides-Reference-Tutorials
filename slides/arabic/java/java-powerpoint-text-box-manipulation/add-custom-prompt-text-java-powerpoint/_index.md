---
"description": "تعلّم كيفية إضافة نص موجه مخصص في جافا باوربوينت باستخدام Aspose.Slides. حسّن تفاعل المستخدم بسهولة مع هذا البرنامج التعليمي."
"linktitle": "إضافة نص موجه مخصص في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة نص موجه مخصص في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة نص موجه مخصص في Java PowerPoint

## مقدمة
في عصرنا الرقمي، يُعدّ إنشاء عروض تقديمية ديناميكية وجذابة أمرًا بالغ الأهمية للتواصل الفعال. يُمكّن Aspose.Slides for Java المطورين من إدارة عروض PowerPoint التقديمية برمجيًا، مُقدّمًا ميزات شاملة لتخصيص الشرائح والأشكال والنصوص وغيرها. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص مُوجّه مُخصّص إلى العناصر النائبة في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على نظامك.
- تم تثبيت Aspose.Slides لجافا. يمكنك تنزيله من [هنا](https://releases.aspose.com/slides/java/).
- تم إعداد بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
للبدء، قم باستيراد فئات Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.*;
```

## الخطوة 1: تحميل العرض التقديمي
أولاً، قم بتحميل عرض PowerPoint حيث تريد إضافة نص موجه مخصص إلى العناصر النائبة.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
```
## الخطوة 2: التكرار عبر أشكال الشريحة
قم بالوصول إلى الشريحة وتصفح أشكالها للعثور على العناصر النائبة.
```java
try {
    ISlide slide = pres.getSlides().get_Item(0);
    for (IShape shape : slide.getShapes()) {
        if (shape.getPlaceholder() != null && shape instanceof AutoShape) {
            // معالجة عناصر نائبة للأشكال التلقائية فقط
            String text = "";
            if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) {
                text = "Click to add custom title";
            } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) {
                text = "Click to add custom subtitle";
            }
            
            // تعيين نص المطالبة المخصص
            ((IAutoShape) shape).getTextFrame().setText(text);
            
            // اطبع نص العنصر النائب للتحقق
            System.out.println(String.format("Placeholder with text: %s", text));
        }
    }
    
    // حفظ العرض التقديمي المعدل
    pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## خاتمة
في الختام، يُبسّط Aspose.Slides for Java عملية تخصيص عروض PowerPoint التقديمية برمجيًا. باتباع هذا البرنامج التعليمي، يمكنك تحسين تفاعل المستخدم بإضافة نصّ إرشادي ذي معنى إلى العناصر النائبة بسهولة.
## الأسئلة الشائعة
### هل يمكنني إضافة نص موجه إلى أي عنصر نائب في شريحة PowerPoint باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تعيين نص موجه مخصص لأنواع مختلفة من العناصر النائبة برمجيًا.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق والموثوقية.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides لـ Java؟
قم بزيارة [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) للحصول على أدلة وأمثلة شاملة.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
يمكنك الحصول على [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لتقييم الميزات الكاملة لـ Aspose.Slides.
### هل يدعم Aspose.Slides for Java إضافة رسوم متحركة مخصصة إلى الشرائح؟
نعم، يوفر Aspose.Slides واجهات برمجة التطبيقات لإدارة رسوم متحركة للشرائح برمجيًا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}