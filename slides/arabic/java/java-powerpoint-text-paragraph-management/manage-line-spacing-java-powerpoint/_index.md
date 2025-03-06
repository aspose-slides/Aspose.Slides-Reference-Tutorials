---
title: إدارة تباعد الأسطر في Java PowerPoint
linktitle: إدارة تباعد الأسطر في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إدارة تباعد الأسطر في عروض Java PowerPoint التقديمية دون عناء باستخدام Aspose.Slides for Java. تعزيز الشرائح الخاصة بك.
weight: 12
url: /ar/java/java-powerpoint-text-paragraph-management/manage-line-spacing-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في برمجة Java، تعد إدارة تباعد الأسطر داخل عروض PowerPoint التقديمية أمرًا بالغ الأهمية لإنشاء شرائح جذابة بصريًا تنقل المعلومات بشكل فعال. سواء كنت تقوم بضبط المسافة بين الفقرات أو التحكم في التباعد قبل كل فقرة وبعدها، فإن Aspose.Slides for Java يوفر أدوات شاملة لتحقيق هذه المهام بسلاسة.
## المتطلبات الأساسية
قبل الغوص في إدارة تباعد الأسطر في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على جهازك.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
-  تم تثبيت Aspose.Slides لمكتبة Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
أولاً، تأكد من استيراد الحزم اللازمة في مشروع Java الخاص بك لاستخدام Aspose.Slides:
```java
import com.aspose.slides.*;
```
## الخطوة 1: قم بتحميل العرض التقديمي
ابدأ بتحميل ملف عرض PowerPoint التقديمي (.pptx):
```java
String dataDir = "Your Document Directory/";
Presentation presentation = new Presentation(dataDir + "Fonts.pptx");
```
## الخطوة 2: الوصول إلى الشريحة وإطار النص
للتعامل مع النص في شريحة معينة، قم بالوصول إليه من خلال فهرسه ثم قم بالوصول إلى TextFrame الذي يحتوي على النص:
```java
ISlide slide = presentation.getSlides().get_Item(0); // احصل على الشريحة الأولى
ITextFrame textFrame = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
```
## الخطوة 3: الوصول إلى خصائص الفقرة وتعديلها
بعد ذلك، قم بالوصول إلى فقرة معينة داخل TextFrame وقم بتعديل خصائص تنسيق الفقرة الخاصة بها:
```java
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // الحصول على الفقرة الأولى
// تعيين مسافة داخل الفقرة
paragraph.getParagraphFormat().setSpaceWithin(80);
// تعيين المسافة قبل وبعد الفقرة
paragraph.getParagraphFormat().setSpaceBefore(40);
paragraph.getParagraphFormat().setSpaceAfter(40);
```
## الخطوة 4: احفظ العرض التقديمي المعدل
بعد إجراء التعديلات اللازمة، احفظ العرض التقديمي المعدل مرة أخرى في ملف:
```java
presentation.save(dataDir + "LineSpacing_out.pptx", SaveFormat.Pptx);
```

## خاتمة
إن إتقان إدارة تباعد الأسطر في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides for Java يمكّن المطورين من إنشاء شرائح جذابة بصريًا ومصممة خصيصًا لمتطلبات التصميم المحددة. من خلال الاستفادة من مرونة وقوة Aspose.Slides، يمكن لمطوري Java التحكم بكفاءة في تباعد الفقرات لتحسين تخطيط العرض التقديمي العام.
## الأسئلة الشائعة
### هل يستطيع Aspose.Slides التعامل مع مهام التنسيق الأخرى إلى جانب تباعد الأسطر؟
نعم، يدعم Aspose.Slides مجموعة واسعة من خيارات التنسيق بما في ذلك أنماط الخطوط والألوان والمحاذاة والمزيد.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides التنسيقات القديمة (.ppt) والأحدث (.pptx) لعروض PowerPoint التقديمية.
### أين يمكنني العثور على وثائق شاملة لـ Aspose.Slides؟
يمكنك استكشاف الوثائق التفصيلية[هنا](https://reference.aspose.com/slides/java/).
### هل يقدم Aspose.Slides نسخة تجريبية مجانية؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides؟
 للحصول على المساعدة الفنية، قم بزيارة Aspose.Slides[منتدى الدعم](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
