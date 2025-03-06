---
title: إضافة نص موجه مخصص في Java PowerPoint
linktitle: إضافة نص موجه مخصص في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة نص مطالبة مخصص في Java PowerPoint باستخدام Aspose.Slides. عزز تفاعل المستخدم بسهولة مع هذا البرنامج التعليمي.
weight: 12
url: /ar/java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في العصر الرقمي الحالي، يعد إنشاء عروض تقديمية ديناميكية وجذابة أمرًا بالغ الأهمية للتواصل الفعال. يمكّن Aspose.Slides for Java المطورين من التعامل مع عروض PowerPoint التقديمية برمجياً، ويقدم ميزات واسعة النطاق لتخصيص الشرائح والأشكال والنصوص والمزيد. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة نص مطالبة مخصص إلى العناصر النائبة في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على نظامك.
-  تم تثبيت Aspose.Slides لـ Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- إعداد بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
للبدء، قم باستيراد فئات Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.*;
```

## الخطوة 1: قم بتحميل العرض التقديمي
أولاً، قم بتحميل عرض PowerPoint التقديمي حيث تريد إضافة نص مطالبة مخصص إلى العناصر النائبة.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
```
## الخطوة 2: التكرار من خلال أشكال الشرائح
قم بالوصول إلى الشريحة وتصفح أشكالها للعثور على العناصر النائبة.
```java
try {
    ISlide slide = pres.getSlides().get_Item(0);
    for (IShape shape : slide.getShapes()) {
        if (shape.getPlaceholder() != null && shape instanceof AutoShape) {
            // معالجة العناصر النائبة للشكل التلقائي فقط
            String text = "";
            if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) {
                text = "Click to add custom title";
            } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) {
                text = "Click to add custom subtitle";
            }
            
            // قم بتعيين نص المطالبة المخصص
            ((IAutoShape) shape).getTextFrame().setText(text);
            
            // اطبع نص العنصر النائب للتحقق
            System.out.println(String.format("Placeholder with text: %s", text));
        }
    }
    
    //احفظ العرض التقديمي المعدل
    pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## خاتمة
في الختام، Aspose.Slides for Java يبسط مهمة تخصيص عروض PowerPoint التقديمية برمجياً. باتباع هذا البرنامج التعليمي، يمكنك تحسين تفاعل المستخدم عن طريق إضافة نص مطالبة ذو معنى إلى العناصر النائبة دون عناء.
## الأسئلة الشائعة
### هل يمكنني إضافة نص موجه إلى أي عنصر نائب في شريحة PowerPoint باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تعيين نص مطالبة مخصص لأنواع مختلفة من العناصر النائبة برمجيًا.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق والموثوقية.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides لـ Java؟
 قم بزيارة[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) للحصول على أدلة وأمثلة شاملة.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) لتقييم الميزات الكاملة لـ Aspose.Slides.
### هل يدعم Aspose.Slides for Java إضافة رسوم متحركة مخصصة إلى الشرائح؟
نعم، يوفر Aspose.Slides واجهات برمجة التطبيقات لإدارة الرسوم المتحركة للشرائح برمجيًا.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
