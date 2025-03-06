---
title: قم بتعيين خصائص خط النص في PowerPoint باستخدام Java
linktitle: قم بتعيين خصائص خط النص في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين خصائص خط النص في PowerPoint باستخدام Aspose.Slides لـ Java. دليل سهل خطوة بخطوة لمطوري Java. #تعرف على كيفية التعامل مع خصائص خط نص PowerPoint باستخدام Aspose.Slides لـ Java باستخدام هذا البرنامج التعليمي خطوة بخطوة لمطوري Java.
type: docs
weight: 18
url: /ar/java/java-powerpoint-text-font-customization/set-text-font-properties-powerpoint-java/
---
## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية استخدام Aspose.Slides لـ Java لتعيين خصائص خطوط النص المتنوعة في عرض PowerPoint التقديمي برمجيًا. سنغطي إعداد نوع الخط والنمط (غامق ومائل) والتسطير والحجم واللون للنص في الشرائح.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت JDK على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- المعرفة الأساسية ببرمجة جافا.
- إعداد بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
## حزم الاستيراد
أولاً، تأكد من استيراد فئات Aspose.Slides الضرورية:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: قم بإعداد مشروع Java الخاص بك
قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف مكتبة Aspose.Slides إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
 إنشاء مثيل أ`Presentation` كائن للعمل مع ملفات PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وإضافة الشكل التلقائي
احصل على الشريحة الأولى وأضف شكلاً تلقائيًا (مستطيلًا) إليها:
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## الخطوة 4: اضبط النص على الشكل التلقائي
تعيين محتوى النص إلى الشكل التلقائي:
```java
ITextFrame textFrame = shape.getTextFrame();
textFrame.setText("Aspose TextBox");
```
## الخطوة 5: تعيين خصائص الخط
الوصول إلى جزء النص وتعيين خصائص الخط المختلفة:
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
// تعيين عائلة الخطوط
portion.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
// تعيين جريئة
portion.getPortionFormat().setFontBold(NullableBool.True);
// تعيين مائل
portion.getPortionFormat().setFontItalic(NullableBool.True);
// تعيين التسطير
portion.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
// ضبط حجم الخط
portion.getPortionFormat().setFontHeight(25);
// ضبط لون الخط
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدل في ملف:
```java
presentation.save(dataDir + "SetTextFontProperties_out.pptx", SaveFormat.Pptx);
```
## الخطوة 7: تنظيف الموارد
تخلص من كائن العرض التقديمي لتحرير الموارد:
```java
if (presentation != null) {
    presentation.dispose();
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية استخدام Aspose.Slides لـ Java لتخصيص خصائص خط النص في شرائح PowerPoint ديناميكيًا. باتباع هذه الخطوات، يمكنك تنسيق النص بكفاءة لتلبية متطلبات التصميم المحددة برمجيًا.
## الأسئلة الشائعة
### هل يمكنني تطبيق تغييرات الخط هذه على النص الموجود في شريحة PowerPoint؟
 نعم، يمكنك تعديل النص الموجود عن طريق الوصول إليه`Portion` وتطبيق خصائص الخط المطلوب.
### كيف يمكنني تغيير لون الخط إلى تعبئة متدرجة أو نمطية؟
 بدلاً من`SolidFillColor` ، يستخدم`GradientFillColor` أو`PatternedFillColor` وفقاً لذلك.
### هل Aspose.Slides متوافق مع قوالب PowerPoint (.potx)؟
نعم، يمكنك استخدام Aspose.Slides للعمل مع قوالب PowerPoint.
### هل يدعم Aspose.Slides التصدير إلى تنسيق PDF؟
نعم، يسمح Aspose.Slides بتصدير العروض التقديمية إلى تنسيقات مختلفة بما في ذلك PDF.
### أين يمكنني العثور على مزيد من المساعدة والدعم لـ Aspose.Slides؟
 يزور[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع وتوجيهه.