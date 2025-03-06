---
title: إضافة نص مرتفع ومنخفض في Java PowerPoint
linktitle: إضافة نص مرتفع ومنخفض في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة نص مرتفع ومنخفض في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. مثالية لتعزيز الشرائح الخاصة بك.
weight: 13
url: /ar/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
غالبًا ما يتطلب إنشاء عروض PowerPoint التقديمية الجذابة والغنية بالمعلومات استخدام ميزات التنسيق مثل النص المرتفع والنص المنخفض. سيرشدك هذا البرنامج التعليمي خلال عملية دمج النص المرتفع والمنخفض في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse تم إعدادها لتطوير Java.
- الإلمام الأساسي ببرمجة Java وعروض PowerPoint التقديمية.

## حزم الاستيراد
أولاً، قم باستيراد الحزم الضرورية من Aspose.Slides لـ Java:
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
// قم بإنشاء شكل تلقائي ليكون بمثابة مربع نص
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## الخطوة 4: إضافة نص مرتفع
```java
// إنشاء فقرة للنص الرئيسي
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// قم بإنشاء جزء للنص المرتفع
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // تعيين الهروب للخط المرتفع
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//أضف الفقرة الرئيسية بخط مرتفع إلى مربع النص
textFrame.getParagraphs().add(mainParagraph);
```
## الخطوة 5: إضافة نص منخفض
```java
// قم بإنشاء فقرة أخرى للنص المنخفض
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// قم بإنشاء جزء للنص المنخفض
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // تعيين الهروب للمنخفض
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// أضف الفقرة المنخفضة إلى مربع النص
textFrame.getParagraphs().add(subscriptParagraph);
```
## الخطوة 6: احفظ العرض التقديمي
```java
// احفظ العرض التقديمي
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية تحسين عروض Java PowerPoint التقديمية باستخدام نص مرتفع ومنخفض باستخدام Aspose.Slides لـ Java. باتباع هذه الخطوات، يمكنك إنشاء شرائح أكثر جاذبية وغنية بالمعلومات والتي تنقل المحتوى الخاص بك بشكل فعال.

## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها برمجياً.
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
 يمكن العثور على وثائق مفصلة[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل يمكنني تجربة Aspose.Slides لـ Java مجانًا؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 للحصول على الدعم والمناقشات، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
