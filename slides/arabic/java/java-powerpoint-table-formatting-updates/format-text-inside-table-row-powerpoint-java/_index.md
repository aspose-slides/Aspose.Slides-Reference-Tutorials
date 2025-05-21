---
"description": "تعلّم كيفية تنسيق النص داخل صفوف الجدول في PowerPoint باستخدام Aspose.Slides لجافا. حسّن عروضك التقديمية باتباع دليلنا المفصل."
"linktitle": "تنسيق النص داخل صف الجدول في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تنسيق النص داخل صف الجدول في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-table-formatting-updates/format-text-inside-table-row-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تنسيق النص داخل صف الجدول في PowerPoint باستخدام Java

## مقدمة
عند العمل على العروض التقديمية، يُعدّ إنشاء شرائح جذابة بصريًا أمرًا أساسيًا للحفاظ على تفاعل جمهورك. يُحسّن تنسيق النص داخل صفوف الجدول من سهولة القراءة وجمالية شرائحك بشكل ملحوظ. في هذا البرنامج التعليمي، سنستكشف كيفية تنسيق النص داخل صف جدول في PowerPoint باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل الخوض في جزء الترميز، دعنا نتأكد من أن لديك كل ما تحتاجه للبدء:
- مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Slides for Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java من [موقع إلكتروني](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE): استخدم بيئة التطوير المتكاملة مثل IntelliJ IDEA، أو Eclipse، أو NetBeans لكتابة وتشغيل كود Java الخاص بك.

## استيراد الحزم
قبل البدء بالبرمجة، علينا استيراد الحزم اللازمة. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;
```
دعونا نقسم العملية إلى خطوات متعددة لفهم أفضل.
## الخطوة 1: تحميل العرض التقديمي
أولاً، عليك تحميل عرض PowerPoint التقديمي. تأكد من إضافة جدول إلى ملف العرض التقديمي.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
## الخطوة 2: الوصول إلى الشريحة الأولى
الآن، لننتقل إلى الشريحة الأولى من العرض التقديمي. هناك سنجد جدولنا.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 3: تحديد موقع الجدول
بعد ذلك، علينا تحديد موقع الجدول داخل الشريحة. للتبسيط، لنفترض أن الجدول هو الشكل الأول في الشريحة.
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
## الخطوة 4: تعيين ارتفاع الخط لخلايا الصف الأول
لتعيين ارتفاع الخط لخلايا الصف الأول، قم بإنشاء مثيل لـ `PortionFormat` وضبط ارتفاع الخط المطلوب.
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25f);
someTable.getRows().get_Item(0).setTextFormat(portionFormat);
```
## الخطوة 5: ضبط محاذاة النص والهامش
لتعيين محاذاة النص والهامش الأيمن لخلايا الصف الأول، قم بإنشاء مثيل لـ `ParagraphFormat` وتكوين المحاذاة والهامش.
```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getRows().get_Item(0).setTextFormat(paragraphFormat);
```
## الخطوة 6: ضبط محاذاة النص الرأسية لخلايا الصف الثاني
لتعيين محاذاة النص الرأسية للخلايا الموجودة في الصف الثاني، قم بإنشاء مثيل لـ `TextFrameFormat` وضبط نوع النص العمودي.
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(textFrameFormat);
```
## الخطوة 7: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل في ملف جديد.
```java
presentation.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
## الخطوة 8: تنظيف الموارد
تخلص دائمًا من كائن العرض لتحرير الموارد.
```java
if (presentation != null) presentation.dispose();
```

## خاتمة
تنسيق النص داخل صفوف الجدول في PowerPoint باستخدام Aspose.Slides لجافا عملية سهلة وبسيطة. باتباع هذه الخطوات، يمكنك بسهولة تحسين مظهر عروضك التقديمية. سواء كنت تُعدّل أحجام الخطوط، أو تُحاذي النصوص، أو تُعيّن أنواع النصوص العمودية، يُوفّر Aspose.Slides واجهة برمجة تطبيقات فعّالة تُساعدك على إنشاء شرائح عرض احترافية.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مع لغات برمجة أخرى؟
يتوفر Aspose.Slides لعدة منصات، بما في ذلك .NET وC++. أما بالنسبة لجافا، فيتعين عليك استخدام مكتبة Aspose.Slides لجافا.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [موقع إلكتروني](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
يمكنك الحصول على الدعم من مجتمع Aspose من خلال زيارة موقعهم [منتدى الدعم](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص لـ Aspose.Slides لـ Java؟
نعم يمكنك شراء الترخيص من [صفحة الشراء](https://purchase.aspose.com/buy).
### ما هي تنسيقات الملفات التي يدعمها Aspose.Slides for Java؟
يدعم Aspose.Slides for Java مجموعة متنوعة من التنسيقات بما في ذلك PPT وPPTX وODP والمزيد.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}