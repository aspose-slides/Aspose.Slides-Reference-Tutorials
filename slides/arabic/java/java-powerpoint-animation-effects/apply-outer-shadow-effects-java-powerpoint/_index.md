---
title: تطبيق تأثيرات الظل الخارجي في Java PowerPoint
linktitle: تطبيق تأثيرات الظل الخارجي في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تطبيق تأثيرات الظل الخارجي بسهولة في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides من خلال دليلنا التفصيلي خطوة بخطوة.
weight: 11
url: /ar/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
يتطلب إنشاء عروض تقديمية جذابة في كثير من الأحيان إضافة تأثيرات متنوعة لتحسين المظهر المرئي لشرائحك. أحد هذه التأثيرات هو الظل الخارجي، الذي يمكن أن يجعل عناصرك بارزة ويضيف عمقًا إلى المحتوى الخاص بك. في هذا البرنامج التعليمي، سنتعرف على عملية تطبيق تأثيرات الظل الخارجي على الأشكال في عرض PowerPoint التقديمي باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل أن نتعمق في الدليل التفصيلي، دعنا نتأكد من أن لديك كل ما تحتاجه:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides لمكتبة Java: قم بتنزيل أحدث إصدار من[Aspose.Slides لجافا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse لكتابة كود Java الخاص بك وتنفيذه.
4.  ترخيص اطرح صالح: يمكنك شراء ترخيص من[Aspose](https://purchase.aspose.com/buy) أو الحصول على[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) للتقييم.
## حزم الاستيراد
أولاً، ستحتاج إلى استيراد الحزم اللازمة لـ Aspose.Slides. وهذا يمهد الطريق للاستفادة من الوظائف القوية التي توفرها المكتبة.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
دعونا نقسم عملية تطبيق تأثيرات الظل الخارجي إلى خطوات يمكن التحكم فيها:
## الخطوة 1: إعداد دليل المشروع
قبل البدء في كتابة التعليمات البرمجية الخاصة بك، تحتاج إلى إعداد دليل المشروع حيث سيتم تخزين ملفات PowerPoint الخاصة بك والوصول إليها.
تأكد من وجود دليل المشروع الخاص بك. إذا لم يحدث ذلك، قم بإنشائه باستخدام الكود التالي:
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: تهيئة العرض التقديمي
الآن، نحتاج إلى تهيئة العرض التقديمي حيث سنضيف الأشكال والتأثيرات.

 إنشاء مثيل جديد لـ`Presentation` الفصل لبدء العمل مع ملف PowerPoint جديد.
```java
// إنشاء مثيل لفئة PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة شريحة وشكل
بعد ذلك، أضف شريحة إلى العرض التقديمي الخاص بك، ثم أضف الشكل الذي ستطبق عليه تأثير الظل.
### الحصول على إشارة إلى الشريحة
استرداد إشارة إلى الشريحة الأولى في العرض التقديمي.
```java
// الحصول على مرجع الشريحة
ISlide sld = pres.getSlides().get_Item(0);
```
### إضافة شكل تلقائي
قم بإضافة شكل تلقائي مستطيل إلى الشريحة عند الإحداثيات المحددة.
```java
// إضافة شكل تلقائي لنوع المستطيل
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## الخطوة 4: تخصيص الشكل
أضف نصًا إلى الشكل الخاص بك واضبط إعدادات التعبئة الخاصة به لجعل تأثير الظل أكثر وضوحًا.
### إضافة TextFrame إلى الشكل
أدخل النص في شكل المستطيل.
```java
// أضف TextFrame إلى المستطيل
aShp.addTextFrame("Aspose TextBox");
```
### تعطيل تعبئة الشكل
قم بتعطيل تعبئة الشكل للتأكيد على ظل النص.
```java
// قم بتعطيل تعبئة الشكل في حال أردنا الحصول على ظل النص
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## الخطوة 5: تطبيق تأثير الظل الخارجي
حان الوقت الآن لتطبيق تأثير الظل الخارجي على الشكل.
### تمكين تأثير الظل الخارجي
تمكين تأثير الظل الخارجي للشكل.
```java
// أضف الظل الخارجي وقم بتعيين كافة المعلمات الضرورية
aShp.getEffectFormat().enableOuterShadowEffect();
```
### تكوين معلمات الظل
قم بتعيين خصائص مختلفة للظل مثل نصف قطر التمويه والاتجاه والمسافة والمحاذاة واللون.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## الخطوة 6: احفظ العرض التقديمي
وأخيرا، احفظ العرض التقديمي على القرص.
```java
//اكتب العرض التقديمي على القرص
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## الخطوة 7: التخلص من الموارد
تأكد من تحرير الموارد عن طريق التخلص من كائن العرض التقديمي.
```java
// تنظيف الموارد
if (pres != null) pres.dispose();
```
## خاتمة
وهناك لديك! لقد نجحت في تطبيق تأثير الظل الخارجي على شكل في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكن أن يؤدي هذا التأثير إلى تحسين المظهر المرئي لشرائحك بشكل كبير، مما يجعل المحتوى الخاص بك مميزًا.
 إذا واجهت أية مشكلات أو كنت بحاجة إلى مزيد من المساعدة، فلا تتردد في الاطلاع على[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/) أو زيارة[منتدى الدعم](https://forum.aspose.com/c/slides/11). ترميز سعيد!
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح لك بإنشاء عروض PowerPoint التقديمية ومعالجتها وتحويلها في تطبيقات Java.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
 يمكنك تنزيل نسخة تجريبية مجانية من[موقع أسبوز](https://releases.aspose.com/).
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي بيئة تطوير متكاملة (IDE)؟
نعم، يمكنك استخدام Aspose.Slides لـ Java مع أي Java IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يمكنك الحصول على ترخيص مؤقت من[موقع أسبوز](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides؟
 يمكنك العثور على المزيد من الأمثلة والوثائق التفصيلية على[صفحة وثائق Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
