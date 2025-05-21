---
"description": "تعلّم كيفية تنسيق النص داخل أعمدة الجدول في PowerPoint باستخدام Aspose.Slides لجافا من خلال هذا البرنامج التعليمي. حسّن عروضك التقديمية برمجيًا."
"linktitle": "تنسيق النص داخل عمود الجدول في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تنسيق النص داخل عمود الجدول في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-table-formatting-updates/format-text-inside-table-column-powerpoint-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تنسيق النص داخل عمود الجدول في PowerPoint باستخدام Java

## مقدمة
هل أنت مستعد للانطلاق في عالم عروض PowerPoint التقديمية مع لمسة جديدة؟ بدلاً من تنسيق الشرائح يدويًا، لنتخذ مسارًا أكثر فعالية باستخدام Aspose.Slides لجافا. سيرشدك هذا البرنامج التعليمي خلال عملية تنسيق النص داخل أعمدة الجدول في عروض PowerPoint التقديمية برمجيًا. استعد، فهذه ستكون تجربة ممتعة!
## المتطلبات الأساسية
قبل أن نبدأ، هناك بعض الأشياء التي ستحتاجها:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على جهازك. إذا لم يكن كذلك، يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل أحدث إصدار من [صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): ستعمل بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse على جعل رحلة الترميز الخاصة بك أكثر سلاسة.
4. عرض تقديمي على PowerPoint: لديك ملف PowerPoint يحتوي على جدول يمكنك استخدامه للاختبار. سنشير إليه باسم `SomePresentationWithTable.pptx`.

## استيراد الحزم
أولاً، لنُنشئ مشروعك ونستورد الحزم اللازمة. سيكون هذا أساسًا للبرنامج التعليمي.
```java
import com.aspose.slides.*;
```
## الخطوة 1: تحميل العرض التقديمي
الخطوة الأولى في رحلتنا هي تحميل عرض PowerPoint في برنامجنا.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
يؤدي هذا السطر من التعليمات البرمجية إلى إنشاء مثيل لـ `Presentation` الفئة التي تمثل ملف PowerPoint الخاص بنا.
## الخطوة 2: الوصول إلى الشريحة والجدول
بعد ذلك، علينا الوصول إلى الشريحة والجدول داخلها. للتبسيط، لنفترض أن الجدول هو الشكل الأول في الشريحة الأولى.
### الوصول إلى الشريحة الأولى
```java
ISlide slide = pres.getSlides().get_Item(0);
```
يسترجع هذا السطر الشريحة الأولى من العرض التقديمي.
### الوصول إلى الجدول
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
هنا، نقوم بالوصول إلى الشكل الأول على الشريحة الأولى، والذي نفترض أنه جدولنا.
## الخطوة 3: تعيين ارتفاع الخط للعمود الأول
الآن، دعنا نحدد ارتفاع الخط للنص في العمود الأول من الجدول.
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
في هذه السطور، نقوم بتعريف `PortionFormat` كائن لتعيين ارتفاع الخط إلى 25 نقطة للعمود الأول.
## الخطوة 4: محاذاة النص إلى اليمين
محاذاة النص تُحدث فرقًا كبيرًا في سهولة قراءة شرائحك. لنقم بمحاذاة النص إلى اليمين في العمود الأول.

```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
هنا نستخدم `ParagraphFormat` كائن لتعيين محاذاة النص إلى اليمين وإضافة هامش أيمن بمقدار 20.
## الخطوة 5: تعيين نوع النص العمودي
لإعطاء النص اتجاهًا فريدًا، يمكننا تعيين النوع الرأسي للنص.
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
يؤدي هذا المقطع إلى تعيين اتجاه النص إلى الوضع الرأسي للعمود الأول.
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، بعد إجراء كافة تغييرات التنسيق، نحتاج إلى حفظ العرض التقديمي المعدّل.
```java
pres.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
يحفظ هذا الأمر العرض التقديمي بالتنسيق الجديد المطبق على ملف يسمى `result.pptx`.

## خاتمة
هذا كل ما في الأمر! لقد قمتَ بتنسيق نص داخل عمود جدول في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. بأتمتة هذه المهام، يمكنك توفير الوقت وضمان التناسق في عروضك التقديمية. برمجة ممتعة!
## الأسئلة الشائعة
### هل يمكنني تنسيق أعمدة متعددة في وقت واحد؟
نعم، يمكنك تطبيق نفس التنسيق على أعمدة متعددة عن طريق تكرارها وتعيين التنسيقات المطلوبة.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides مجموعة واسعة من تنسيقات PowerPoint، مما يضمن التوافق مع معظم الإصدارات.
### هل يمكنني إضافة أنواع أخرى من التنسيق باستخدام Aspose.Slides؟
بالتأكيد! يتيح Aspose.Slides خيارات تنسيق شاملة، بما في ذلك أنماط الخطوط والألوان والمزيد.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides؟
يمكنك تنزيل نسخة تجريبية مجانية من [صفحة التجربة المجانية لـ Aspose](https://releases.aspose.com/).
### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟
تحقق من [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/) للحصول على أمثلة وإرشادات مفصلة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}