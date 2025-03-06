---
title: تغيير نمط لون شكل SmartArt باستخدام Java
linktitle: تغيير نمط لون شكل SmartArt باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعلم كيفية تغيير ألوان أشكال SmartArt ديناميكيًا في PowerPoint باستخدام Java وAspose.Slides. تعزيز الجاذبية البصرية دون عناء.
weight: 20
url: /ar/java/java-powerpoint-smartart-manipulation/change-smartart-shape-color-style-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في هذا البرنامج التعليمي، سنتعرف على عملية تغيير أنماط ألوان أشكال SmartArt باستخدام Java مع Aspose.Slides. SmartArt هي ميزة قوية في عروض PowerPoint التقديمية تسمح بإنشاء رسومات جذابة بصريًا. من خلال تغيير نمط الألوان لأشكال SmartArt، يمكنك تحسين التصميم العام والتأثير المرئي لعروضك التقديمية. سنقوم بتقسيم العملية إلى خطوات سهلة المتابعة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2.  Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من[موقع إلكتروني](https://releases.aspose.com/slides/java/).
3. المعرفة الأساسية بجافا: الإلمام بمفاهيم لغة برمجة جافا سيكون مفيدًا.
## حزم الاستيراد
قبل الغوص في الكود، فلنستورد الحزم الضرورية:
```java
import com.aspose.slides.*;
```
الآن، دعونا نقسم مثال الكود إلى تعليمات خطوة بخطوة:
## الخطوة 1: قم بتحميل العرض التقديمي
أولاً، نحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على شكل SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## الخطوة 2: اجتياز الأشكال
بعد ذلك، سنتنقل خلال كل شكل داخل الشريحة الأولى لتحديد أشكال SmartArt:
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## الخطوة 3: التحقق من نوع SmartArt
بالنسبة لكل شكل، سوف نتحقق مما إذا كان شكل SmartArt:
```java
if (shape instanceof ISmartArt)
```
## الخطوة 4: تغيير نمط اللون
إذا كان الشكل عبارة عن شكل SmartArt، فسنقوم بتغيير نمط لونه:
```java
ISmartArt smart = (ISmartArt) shape;
if (smart.getColorStyle() == SmartArtColorType.ColoredFillAccent1)
{
    smart.setColorStyle(SmartArtColorType.ColorfulAccentColors);
}
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، سنقوم بحفظ العرض التقديمي المعدل:
```java
presentation.save(dataDir + "ChangeSmartArtColorStyle_out.pptx", SaveFormat.Pptx);
```
## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة تغيير أنماط ألوان أشكال SmartArt في عروض PowerPoint التقديمية باستخدام Java مع Aspose.Slides. قم بتجربة أنماط الألوان المختلفة لتعزيز المظهر المرئي لعروضك التقديمية.
## الأسئلة الشائعة
### هل يمكنني تغيير نمط الألوان لأشكال SmartArt معينة فقط؟
نعم، يمكنك تعديل التعليمات البرمجية لاستهداف أشكال SmartArt معينة بناءً على متطلباتك.
### هل يدعم Aspose.Slides خيارات المعالجة الأخرى لـ SmartArt؟
نعم، يوفر Aspose.Slides واجهات برمجة التطبيقات المتنوعة للتعامل مع أشكال SmartArt، بما في ذلك تغيير الحجم وتغيير الموضع وإضافة النص.
### هل يمكنني أتمتة هذه العملية لعروض تقديمية متعددة؟
بالتأكيد، يمكنك دمج هذا الرمز في البرامج النصية لمعالجة الدفعات للتعامل مع العروض التقديمية المتعددة بكفاءة.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يدعم Aspose.Slides مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق مع معظم ملفات العروض التقديمية.
### أين يمكنني الحصول على الدعم للاستفسارات المتعلقة بـ Aspose.Slides؟
 يمكنك زيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة من المجتمع وموظفي الدعم Aspose.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
