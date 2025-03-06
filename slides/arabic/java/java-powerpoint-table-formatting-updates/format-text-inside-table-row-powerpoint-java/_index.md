---
title: تنسيق النص داخل صف الجدول في PowerPoint باستخدام Java
linktitle: تنسيق النص داخل صف الجدول في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تنسيق النص داخل صفوف الجدول في PowerPoint باستخدام Aspose.Slides لـ Java. قم بتعزيز العروض التقديمية الخاصة بك من خلال دليلنا خطوة بخطوة.
weight: 12
url: /ar/java/java-powerpoint-table-formatting-updates/format-text-inside-table-row-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
عند العمل مع العروض التقديمية، يعد إنشاء شرائح جذابة بصريًا أمرًا ضروريًا للحفاظ على تفاعل جمهورك. يمكن أن يؤدي تنسيق النص داخل صفوف الجدول إلى تحسين قابلية القراءة وجماليات الشرائح بشكل كبير. في هذا البرنامج التعليمي، سنستكشف كيفية تنسيق النص داخل صف جدول في PowerPoint باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل الغوص في جزء البرمجة، دعونا نتأكد من أن لديك كل ما تحتاجه للبدء:
-  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides for Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java من[موقع إلكتروني](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans لكتابة تعليمات Java البرمجية وتشغيلها.

## حزم الاستيراد
قبل أن نبدأ بالبرمجة، نحتاج إلى استيراد الحزم الضرورية. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;
```
دعونا نقسم العملية إلى خطوات متعددة لفهم أفضل.
## الخطوة 1: قم بتحميل العرض التقديمي
أولاً، تحتاج إلى تحميل عرض PowerPoint التقديمي الخاص بك. تأكد من أن لديك ملف عرض تقديمي يحتوي على جدول مضاف بالفعل.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
## الخطوة 2: الوصول إلى الشريحة الأولى
الآن، دعنا نصل إلى الشريحة الأولى من العرض التقديمي. هذا هو المكان الذي سنجد فيه طاولتنا.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: تحديد موقع الجدول
بعد ذلك، نحتاج إلى تحديد موقع الجدول داخل الشريحة. للتبسيط، لنفترض أن الجدول هو الشكل الأول على الشريحة.
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
## الخطوة 4: ضبط ارتفاع الخط لخلايا الصف الأول
 لتعيين ارتفاع الخط لخلايا الصف الأول، قم بإنشاء مثيل لـ`PortionFormat` وضبط ارتفاع الخط المطلوب.
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25f);
someTable.getRows().get_Item(0).setTextFormat(portionFormat);
```
## الخطوة 5: تعيين محاذاة النص والهامش
 لتعيين محاذاة النص والهامش الأيمن لخلايا الصف الأول، قم بإنشاء مثيل لـ`ParagraphFormat` وتكوين المحاذاة والهامش.
```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getRows().get_Item(0).setTextFormat(paragraphFormat);
```
## الخطوة 6: ضبط محاذاة النص العمودي لخلايا الصف الثاني
 لتعيين محاذاة النص الرأسي للخلايا الموجودة في الصف الثاني، قم بإنشاء مثيل لـ`TextFrameFormat` وقم بتعيين نوع النص العمودي.
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(textFrameFormat);
```
## الخطوة 7: احفظ العرض التقديمي
وأخيراً، احفظ العرض التقديمي المعدل في ملف جديد.
```java
presentation.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
## الخطوة 8: تنظيف الموارد
تخلص دائمًا من كائن العرض التقديمي لتحرير الموارد.
```java
if (presentation != null) presentation.dispose();
```

## خاتمة
يعد تنسيق النص داخل صفوف الجدول في PowerPoint باستخدام Aspose.Slides لـ Java عملية مباشرة. باتباع هذه الخطوات، يمكنك بسهولة تحسين مظهر عروضك التقديمية. سواء كنت تقوم بضبط أحجام الخطوط، أو محاذاة النص، أو تعيين أنواع النص الرأسي، فإن Aspose.Slides يوفر واجهة برمجة تطبيقات قوية لمساعدتك في إنشاء شرائح ذات مظهر احترافي.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع لغات البرمجة الأخرى؟
يتوفر Aspose.Slides للعديد من الأنظمة الأساسية، بما في ذلك .NET وC++. ومع ذلك، بالنسبة لـ Java، تحتاج إلى استخدام مكتبة Aspose.Slides for Java.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[موقع إلكتروني](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
 يمكنك الحصول على الدعم من مجتمع Aspose من خلال زيارة موقعهم[منتدى الدعم](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص Aspose.Slides لـ Java؟
 نعم، يمكنك شراء ترخيص من[صفحة الشراء](https://purchase.aspose.com/buy).
### ما تنسيقات الملفات التي يدعمها Aspose.Slides لـ Java؟
يدعم Aspose.Slides for Java مجموعة متنوعة من التنسيقات بما في ذلك PPT وPPTX وODP والمزيد.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
