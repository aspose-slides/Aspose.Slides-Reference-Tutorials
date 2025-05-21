---
"description": "تعرف على كيفية تعيين أرقام نقطية مخصصة في Java PowerPoint باستخدام Aspose.Slides، مما يعزز وضوح العرض التقديمي وبنيته برمجيًا."
"linktitle": "تعيين أرقام النقاط المخصصة في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين أرقام النقاط المخصصة في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين أرقام النقاط المخصصة في Java PowerPoint

## مقدمة
في عصرنا الرقمي، يُعدّ إنشاء عروض تقديمية ديناميكية أمرًا بالغ الأهمية لتوصيل الأفكار والبيانات بفعالية. يوفر Aspose.Slides لجافا مجموعة أدوات فعّالة لإدارة عروض PowerPoint التقديمية برمجيًا، مع ميزات شاملة تُحسّن عملية إنشاء العرض التقديمي. تتناول هذه المقالة كيفية ضبط أرقام نقطية مخصصة في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides. سواءً كنت مطورًا متمرسًا أو جديدًا، سيرشدك هذا البرنامج التعليمي خطوة بخطوة خلال العملية، مما يضمن لك الاستفادة القصوى من هذه الإمكانية.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية في بيئة التطوير الخاصة بك:
- تم تثبيت Java Development Kit (JDK)
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/)
- فهم أساسي للغة برمجة جافا ومفاهيم البرمجة الكائنية التوجه

## استيراد الحزم
أولاً، قم باستيراد فئات Aspose.Slides الضرورية ومكتبات Java القياسية الأخرى:
```java
import com.aspose.slides.*;
```
## الخطوة 1: إنشاء كائن عرض تقديمي
ابدأ بإنشاء عرض تقديمي جديد في PowerPoint باستخدام Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## الخطوة 2: إضافة شكل تلقائي مع نص
قم بإدراج شكل تلقائي (مستطيل) على الشريحة والوصول إلى إطار النص الخاص به.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## الخطوة 3: إزالة الفقرة الافتراضية
إزالة الفقرة الافتراضية الموجودة من إطار النص.
```java
textFrame.getParagraphs().removeAt(0);
```
## الخطوة 4: إضافة نقاط مرقمة
أضف فقرات تحتوي على نقاط مرقمة مخصصة تبدأ من أرقام محددة.
```java
// مثال على فقرة تبدأ بالرقم 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// مثال على فقرة تبدأ بالرقم 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// مثال على فقرة تبدأ بالرقم 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل في الموقع المطلوب.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## خاتمة
في الختام، يُبسّط Aspose.Slides for Java عملية تعيين أرقام نقطية مخصصة في عروض PowerPoint التقديمية برمجيًا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تحسين وضوح العرض التقديمي وهيكليته بكفاءة.
## الأسئلة الشائعة
### هل يمكنني تخصيص مظهر الرصاصات بشكل أكبر؟
نعم، يوفر Aspose.Slides خيارات واسعة لتخصيص نوع الرصاصة وحجمها ولونها والمزيد.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides تنسيقات PowerPoint من 97 إلى 2003 إلى الإصدارات الأحدث.
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides؟
يزور [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة الفنية.
### هل يمكنني تجربة Aspose.Slides قبل الشراء؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني شراء Aspose.Slides؟
يمكنك شراء Aspose.Slides من [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}