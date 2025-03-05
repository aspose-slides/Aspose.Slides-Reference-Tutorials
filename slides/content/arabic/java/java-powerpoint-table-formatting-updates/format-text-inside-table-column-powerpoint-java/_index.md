---
title: تنسيق النص داخل عمود الجدول في PowerPoint باستخدام Java
linktitle: تنسيق النص داخل عمود الجدول في PowerPoint باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تنسيق النص داخل أعمدة الجدول في PowerPoint باستخدام Aspose.Slides لـ Java باستخدام هذا البرنامج التعليمي. تعزيز العروض التقديمية الخاصة بك برمجيا.
type: docs
weight: 11
url: /ar/java/java-powerpoint-table-formatting-updates/format-text-inside-table-column-powerpoint-java/
---
## مقدمة
هل أنت مستعد للغوص في عالم عروض PowerPoint التقديمية ولكن مع لمسة جديدة؟ بدلاً من تنسيق الشرائح يدويًا، دعنا نتبع طريقًا أكثر كفاءة باستخدام Aspose.Slides for Java. سيرشدك هذا البرنامج التعليمي خلال عملية تنسيق النص داخل أعمدة الجدول في عروض PowerPoint التقديمية برمجياً. اربطوا حزام الأمان، لأن هذه ستكون رحلة ممتعة!
## المتطلبات الأساسية
قبل أن نبدأ، هناك بعض الأشياء التي ستحتاج إليها:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. إذا لم يكن الأمر كذلك، يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من[صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse ستجعل رحلة البرمجة الخاصة بك أكثر سلاسة.
4.  عرض PowerPoint التقديمي: احصل على ملف PowerPoint يحتوي على جدول يمكنك استخدامه للاختبار. سوف نشير إليها باسم`SomePresentationWithTable.pptx`.

## حزم الاستيراد
أولاً، لنقم بإعداد مشروعك واستيراد الحزم الضرورية. سيكون هذا هو أساسنا للبرنامج التعليمي.
```java
import com.aspose.slides.*;
```
## الخطوة 1: قم بتحميل العرض التقديمي
الخطوة الأولى في رحلتنا هي تحميل عرض PowerPoint التقديمي في برنامجنا.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
 يقوم سطر التعليمات البرمجية هذا بإنشاء مثيل لـ`Presentation` class، الذي يمثل ملف PowerPoint الخاص بنا.
## الخطوة 2: الوصول إلى الشريحة والجدول
بعد ذلك، نحتاج إلى الوصول إلى الشريحة والجدول الموجود داخل تلك الشريحة. للتبسيط، لنفترض أن الجدول هو الشكل الأول في الشريحة الأولى.
### الوصول إلى الشريحة الأولى
```java
ISlide slide = pres.getSlides().get_Item(0);
```
يسترد هذا السطر الشريحة الأولى من العرض التقديمي.
### الوصول إلى الجدول
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
نحن هنا نصل إلى الشكل الأول في الشريحة الأولى، والذي نفترض أنه جدولنا.
## الخطوة 3: ضبط ارتفاع الخط للعمود الأول
الآن، لنقم بتعيين ارتفاع الخط للنص في العمود الأول من الجدول.
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 في هذه السطور نحدد أ`PortionFormat` كائن لتعيين ارتفاع الخط إلى 25 نقطة للعمود الأول.
## الخطوة 4: محاذاة النص إلى اليمين
يمكن أن تُحدث محاذاة النص فرقًا كبيرًا في سهولة قراءة الشرائح. لنقم بمحاذاة النص إلى اليمين في العمود الأول.

```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 وهنا نستخدم أ`ParagraphFormat` كائن لتعيين محاذاة النص إلى اليمين وإضافة هامش أيمن قدره 20.
## الخطوة 5: تعيين نوع النص العمودي
لإعطاء النص اتجاهًا فريدًا، يمكننا ضبط النوع الرأسي للنص.
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
يقوم هذا المقتطف بتعيين اتجاه النص إلى الوضع الرأسي للعمود الأول.
## الخطوة 6: احفظ العرض التقديمي
أخيرًا، بعد إجراء جميع تغييرات التنسيق، نحتاج إلى حفظ العرض التقديمي المعدل.
```java
pres.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
 يحفظ هذا الأمر العرض التقديمي بالتنسيق الجديد المطبق على ملف مسمى`result.pptx`.

## خاتمة
ها هو ذا! لقد قمت للتو بتنسيق النص داخل عمود جدول في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. من خلال أتمتة هذه المهام، يمكنك توفير الوقت وضمان الاتساق عبر العروض التقديمية الخاصة بك. ترميز سعيد!
## الأسئلة الشائعة
### هل يمكنني تنسيق أعمدة متعددة في وقت واحد؟
نعم، يمكنك تطبيق نفس التنسيق على أعمدة متعددة من خلال التكرار خلالها وتعيين التنسيقات المطلوبة.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides مجموعة واسعة من تنسيقات PowerPoint، مما يضمن التوافق مع معظم الإصدارات.
### هل يمكنني إضافة أنواع أخرى من التنسيق باستخدام Aspose.Slides؟
قطعاً! يتيح Aspose.Slides خيارات تنسيق واسعة النطاق، بما في ذلك أنماط الخطوط والألوان والمزيد.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides؟
 يمكنك تنزيل نسخة تجريبية مجانية من[Aspose صفحة تجريبية مجانية](https://releases.aspose.com/).
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
 تفحص ال[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/) للحصول على أمثلة وأدلة مفصلة.