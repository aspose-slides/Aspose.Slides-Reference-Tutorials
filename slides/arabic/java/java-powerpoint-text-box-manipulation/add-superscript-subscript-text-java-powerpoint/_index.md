---
"description": "تعلّم كيفية إضافة نص علوي وسفلي في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides لجافا. مثالي لتحسين عروضك التقديمية."
"linktitle": "إضافة نص علوي وسفلي في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة نص علوي وسفلي في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة نص علوي وسفلي في Java PowerPoint

## مقدمة
غالبًا ما يتطلب إنشاء عروض PowerPoint جذابة وغنية بالمعلومات استخدام ميزات التنسيق، مثل النص العلوي والسفلي. سيرشدك هذا البرنامج التعليمي خلال عملية دمج النص العلوي والسفلي في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse تم إعدادها لتطوير Java.
- المعرفة الأساسية ببرمجة Java وعروض PowerPoint.

## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة من Aspose.Slides لـ Java:
```java
import com.aspose.slides.*;
```
## الخطوة 1: إعداد العرض التقديمي
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة
```java
// احصل على الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: إنشاء مربع نص
```java
// إنشاء شكل تلقائي ليكون بمثابة مربع نص
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## الخطوة 4: إضافة نص علوي
```java
// إنشاء فقرة للنص الرئيسي
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// إنشاء جزء للنص العلوي
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // تعيين الإفلات للنص العلوي
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// أضف الفقرة الرئيسية مع النص العلوي إلى مربع النص
textFrame.getParagraphs().add(mainParagraph);
```
## الخطوة 5: إضافة نص سفلي
```java
// إنشاء فقرة أخرى للنص السفلي
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// إنشاء جزء للنص السفلي
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // تعيين الإفلات للمؤشر السفلي
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// أضف الفقرة السفلية إلى مربع النص
textFrame.getParagraphs().add(subscriptParagraph);
```
## الخطوة 6: حفظ العرض التقديمي
```java
// حفظ العرض التقديمي
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، استكشفنا كيفية تحسين عروض PowerPoint التقديمية بلغة جافا باستخدام النصوص العلوية والسفلية باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات، يمكنك إنشاء شرائح أكثر جاذبية بصريًا وغنية بالمعلومات، تُوصل محتواك بفعالية.

## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint ومعالجتها وتحويلها برمجيًا.
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
يمكن العثور على وثائق مفصلة [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### هل يمكنني تجربة Aspose.Slides لـJava مجانًا؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
للحصول على الدعم والمناقشات، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}