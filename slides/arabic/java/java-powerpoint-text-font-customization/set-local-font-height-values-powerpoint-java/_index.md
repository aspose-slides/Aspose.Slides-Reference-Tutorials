---
"description": "تعلّم كيفية ضبط ارتفاع الخطوط في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. حسّن تنسيق النص في شرائحك بسهولة."
"linktitle": "تعيين قيم ارتفاع الخط المحلي في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين قيم ارتفاع الخط المحلي في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين قيم ارتفاع الخط المحلي في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية التحكم في ارتفاعات الخطوط على مستويات مختلفة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. يُعد التحكم في أحجام الخطوط أمرًا بالغ الأهمية لإنشاء عروض تقديمية جذابة بصريًا ومنظمة. سنستعرض أمثلة خطوة بخطوة لتوضيح كيفية ضبط ارتفاعات الخطوط لعناصر نصية مختلفة.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- مجموعة تطوير Java (JDK) مثبتة على نظامك
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها [هنا](https://releases.aspose.com/slides/java/).
- فهم أساسي لبرمجة Java وعروض PowerPoint
## استيراد الحزم
تأكد من تضمين حزم Aspose.Slides الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تهيئة كائن العرض التقديمي
أولاً، قم بإنشاء كائن عرض تقديمي جديد في PowerPoint:
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة إطار الشكل والنص
أضف شكلًا تلقائيًا مع إطار نص إلى الشريحة الأولى:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## الخطوة 3: إنشاء أجزاء النص
تحديد أجزاء النص بارتفاعات خطوط مختلفة:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## الخطوة 4: تعيين ارتفاعات الخطوط
تعيين ارتفاعات الخطوط على مستويات مختلفة:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## الخطوة 5: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل في ملف:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## خاتمة
يوضح هذا البرنامج التعليمي كيفية ضبط ارتفاعات الخطوط في شرائح PowerPoint برمجيًا باستخدام Aspose.Slides لجافا. من خلال تعديل أحجام الخطوط على مستويات مختلفة (على مستوى العرض التقديمي، والفقرات، والأجزاء)، يمكنك التحكم بدقة في تنسيق النص في عروضك التقديمية.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية للتعامل مع عروض PowerPoint برمجيًا.
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـJava قبل الشراء؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
للحصول على الدعم، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### أين يمكنني شراء ترخيص لـ Aspose.Slides لـ Java؟
يمكنك شراء ترخيص [هنا](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}