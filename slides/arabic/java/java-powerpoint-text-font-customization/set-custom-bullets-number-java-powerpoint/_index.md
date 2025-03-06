---
title: قم بتعيين رقم نقطي مخصص في Java PowerPoint
linktitle: قم بتعيين رقم نقطي مخصص في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين أرقام نقطية مخصصة في Java PowerPoint باستخدام Aspose.Slides، مما يعزز وضوح العرض التقديمي وبنيته برمجيًا.
weight: 15
url: /ar/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في العصر الرقمي الحالي، يعد إنشاء عروض تقديمية ديناميكية أمرًا ضروريًا لتوصيل الأفكار والبيانات بشكل فعال. يوفر Aspose.Slides for Java مجموعة أدوات قوية للتعامل مع عروض PowerPoint التقديمية برمجيًا، مما يوفر ميزات شاملة لتحسين عملية إنشاء العرض التقديمي. تتعمق هذه المقالة في إعداد أرقام نقطية مخصصة في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. سواء كنت مطورًا متمرسًا أو وافدًا جديدًا، سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال العملية، مما يضمن أنه يمكنك الاستفادة من هذه الإمكانية بكفاءة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية في بيئة التطوير الخاصة بك:
- تم تثبيت مجموعة أدوات تطوير Java (JDK).
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/)
- الفهم الأساسي للغة برمجة Java والمفاهيم الموجهة للكائنات

## حزم الاستيراد
أولاً، قم باستيراد فئات Aspose.Slides الضرورية ومكتبات Java القياسية الأخرى:
```java
import com.aspose.slides.*;
```
## الخطوة 1: إنشاء كائن العرض التقديمي
ابدأ بإنشاء عرض تقديمي جديد لبرنامج PowerPoint باستخدام Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## الخطوة 2: إضافة شكل تلقائي مع النص
قم بإدراج شكل تلقائي (مستطيل) على الشريحة وقم بالوصول إلى إطار النص الخاص بها.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## الخطوة 3: إزالة الفقرة الافتراضية
قم بإزالة الفقرة الافتراضية الموجودة من إطار النص.
```java
textFrame.getParagraphs().removeAt(0);
```
## الخطوة 4: إضافة تعداد نقطي مرقمة
أضف فقرات ذات تعداد نقطي مخصص بدءًا من أرقام محددة.
```java
// مثال للفقرة التي تحتوي على رمز نقطي يبدأ من 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// مثال للفقرة التي تحتوي على رمز نقطي يبدأ من 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// مثال على الفقرة ذات التعداد النقطي الذي يبدأ من الرقم 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## الخطوة 5: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل في الموقع الذي تريده.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## خاتمة
في الختام، يعمل Aspose.Slides for Java على تبسيط عملية إعداد أرقام نقطية مخصصة في عروض PowerPoint التقديمية برمجيًا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحسين الوضوح البصري وبنية العروض التقديمية الخاصة بك بكفاءة.
## الأسئلة الشائعة
### هل يمكنني تخصيص مظهر الرصاص بشكل أكبر؟
نعم، يوفر Aspose.Slides خيارات واسعة لتخصيص نوع التعداد النقطي وحجمه ولونه والمزيد.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides تنسيقات PowerPoint من 97-2003 إلى أحدث الإصدارات.
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides؟
 يزور[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة الفنية.
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني شراء Aspose.Slides؟
 يمكنك شراء Aspose.Slides من[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
