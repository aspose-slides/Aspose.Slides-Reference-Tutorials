---
title: قم بتعيين قيم ارتفاع الخط المحلي في PowerPoint باستخدام Java
linktitle: قم بتعيين قيم ارتفاع الخط المحلي في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية ضبط ارتفاعات الخطوط في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. تحسين تنسيق النص في الشرائح الخاصة بك دون عناء.
weight: 17
url: /ar/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# قم بتعيين قيم ارتفاع الخط المحلي في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية التعامل مع ارتفاعات الخطوط على مستويات مختلفة داخل عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. يعد التحكم في أحجام الخطوط أمرًا بالغ الأهمية لإنشاء عروض تقديمية جذابة ومنظمة. سنتعرف على الأمثلة خطوة بخطوة لتوضيح كيفية تعيين ارتفاعات الخطوط لعناصر النص المختلفة.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/java/).
- الفهم الأساسي لبرمجة Java وعروض PowerPoint التقديمية
## حزم الاستيراد
تأكد من تضمين حزم Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تهيئة كائن العرض التقديمي
أولاً، قم بإنشاء كائن عرض تقديمي جديد لـ PowerPoint:
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة شكل وإطار نص
أضف شكلاً تلقائيًا بإطار نص إلى الشريحة الأولى:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## الخطوة 3: إنشاء أجزاء النص
تحديد أجزاء النص بارتفاعات خط مختلفة:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## الخطوة 4: تعيين ارتفاعات الخط
ضبط ارتفاعات الخط على مستويات مختلفة:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## الخطوة 5: احفظ العرض التقديمي
احفظ العرض التقديمي المعدل في ملف:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## خاتمة
يوضح هذا البرنامج التعليمي كيفية ضبط ارتفاعات الخطوط داخل شرائح PowerPoint برمجياً باستخدام Aspose.Slides لـ Java. من خلال معالجة أحجام الخطوط على مستويات مختلفة (على مستوى العرض التقديمي والفقرة والجزء)، يمكنك تحقيق تحكم دقيق في تنسيق النص في عروضك التقديمية.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لمعالجة عروض PowerPoint التقديمية برمجياً.
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـ Java قبل الشراء؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 للحصول على الدعم، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### أين يمكنني شراء ترخيص Aspose.Slides لـ Java؟
 يمكنك شراء ترخيص[هنا](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
