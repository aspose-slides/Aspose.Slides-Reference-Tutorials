---
title: ضبط لغة العرض وشكل النص في Java
linktitle: ضبط لغة العرض وشكل النص في Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية أتمتة عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. يمكنك إنشاء الشرائح وتعديلها وتحسينها برمجيًا بسهولة.
weight: 19
url: /ar/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
يمكن أن يؤدي إنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا في Java إلى تبسيط أتمتة سير العمل وتحسين الإنتاجية. يوفر Aspose.Slides for Java مجموعة قوية من الأدوات لتحقيق هذه المهام بكفاءة. يرشدك هذا البرنامج التعليمي خلال الخطوات الأساسية لتعيين لغة العرض التقديمي وشكل النص باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت مجموعة أدوات تطوير Java (JDK).
-  Aspose.Slides لمكتبة Java، والتي يمكنك التنزيل منها[هنا](https://releases.aspose.com/slides/java/)
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse التي تم إعدادها على نظامك
- المعرفة الأساسية بلغة البرمجة جافا
## حزم الاستيراد
للبدء، قم باستيراد حزم Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## الخطوة 1: إنشاء كائن العرض التقديمي
 ابدأ بتهيئة أ`Presentation` هدف:
```java
Presentation pres = new Presentation();
```
يؤدي هذا إلى إنشاء عرض تقديمي جديد لـ PowerPoint.
## الخطوة 2: إضافة شكل تلقائي وتكوينه
بعد ذلك، قم بإضافة شكل تلقائي إلى الشريحة الأولى وقم بتكوين خصائصه:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
هنا نقوم بإضافة شكل تلقائي مستطيل عند الإحداثيات (50، 50) بأبعاد 200x50 بكسل.
## الخطوة 3: تعيين النص واللغة
قم بتعيين محتوى النص وحدد لغة التدقيق الإملائي:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 يستبدل`"Text to apply spellcheck language"` بالنص الذي تريده معرف اللغة`"en-EN"`تحدد اللغة الإنجليزية (الولايات المتحدة).
## الخطوة 4: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل في دليل الإخراج المحدد:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 تأكد من الاستبدال`"Your Output Directory"` باستخدام مسار الدليل الفعلي الذي تريد حفظ الملف فيه.
## الخطوة 5: التخلص من الموارد
 التخلص بشكل صحيح من`Presentation` كائن لتحرير الموارد:
```java
pres.dispose();
```
هذه الخطوة ضرورية لتجنب تسرب الذاكرة.

## خاتمة
في الختام، Aspose.Slides for Java يبسط عملية إنشاء عروض PowerPoint التقديمية ومعالجتها برمجياً. باتباع هذه الخطوات، يمكنك ضبط لغة العرض التقديمي بكفاءة وتكوين خصائص النص وفقًا لمتطلباتك.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java لإنشاء عروض PowerPoint التقديمية من البداية؟
نعم، يوفر Aspose.Slides واجهات برمجة تطبيقات شاملة لإنشاء العروض التقديمية برمجيًا بالكامل.
### كيف يمكنني تطبيق خطوط مختلفة على النص في شرائح PowerPoint باستخدام Aspose.Slides لـ Java؟
 يمكنك ضبط خصائص الخط من خلال`IPortionFormat` الكائنات المرتبطة بأجزاء النص.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 الوثائق التفصيلية متاحة[هنا](https://reference.aspose.com/slides/java/).
### ما خيارات الدعم المتوفرة لـ Aspose.Slides لـ Java؟
 يمكنك زيارة منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11) لدعم المجتمع.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
