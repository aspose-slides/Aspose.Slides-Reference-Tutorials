---
"description": "تعلّم كيفية إدارة مسافات الأسطر في عروض PowerPoint التقديمية بلغة Java بسهولة باستخدام Aspose.Slides لـ Java. حسّن عروضك التقديمية."
"linktitle": "إدارة تباعد الأسطر في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إدارة تباعد الأسطر في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-paragraph-management/manage-line-spacing-java-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إدارة تباعد الأسطر في Java PowerPoint

## مقدمة
في برمجة جافا، تُعدّ إدارة مسافات الأسطر في عروض PowerPoint التقديمية أمرًا بالغ الأهمية لإنشاء شرائح جذابة بصريًا تُقدّم المعلومات بفعالية. سواءً كنت تُعدّل المسافة بين الفقرات أو تتحكم في التباعد قبل كل فقرة وبعدها، يُوفّر Aspose.Slides for Java أدوات شاملة لإنجاز هذه المهام بسلاسة.
## المتطلبات الأساسية
قبل الغوص في إدارة المسافة بين الأسطر في عروض PowerPoint باستخدام Aspose.Slides لـ Java، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Java Development Kit (JDK) على جهازك.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
- تم تثبيت مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
أولاً، تأكد من استيراد الحزم الضرورية في مشروع Java الخاص بك لاستخدام Aspose.Slides:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تحميل العرض التقديمي
ابدأ بتحميل ملف العرض التقديمي PowerPoint (.pptx):
```java
String dataDir = "Your Document Directory/";
Presentation presentation = new Presentation(dataDir + "Fonts.pptx");
```
## الخطوة 2: الوصول إلى الشريحة وإطار النص
للتعامل مع النص على شريحة معينة، قم بالوصول إليه من خلال فهرسه ثم قم بالوصول إلى TextFrame الذي يحتوي على النص:
```java
ISlide slide = presentation.getSlides().get_Item(0); // احصل على الشريحة الأولى
ITextFrame textFrame = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
```
## الخطوة 3: الوصول إلى خصائص الفقرة وتعديلها
بعد ذلك، قم بالوصول إلى فقرة محددة داخل TextFrame وتعديل خصائص تنسيق الفقرة الخاصة بها:
```java
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // احصل على الفقرة الأولى
// تعيين مسافة داخل الفقرة
paragraph.getParagraphFormat().setSpaceWithin(80);
// تعيين مسافة قبل وبعد الفقرة
paragraph.getParagraphFormat().setSpaceBefore(40);
paragraph.getParagraphFormat().setSpaceAfter(40);
```
## الخطوة 4: حفظ العرض التقديمي المعدّل
بعد إجراء التعديلات اللازمة، احفظ العرض التقديمي المعدل في ملف مرة أخرى:
```java
presentation.save(dataDir + "LineSpacing_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يُمكّن إتقان إدارة مسافات السطور في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides للمطورين من إنشاء شرائح جذابة بصريًا ومُصممة خصيصًا لتلبية متطلبات التصميم المحددة. بالاستفادة من مرونة Aspose.Slides وقوته، يُمكن لمطوري جافا التحكم بكفاءة في مسافات الفقرات لتحسين تصميم العرض التقديمي بشكل عام.
## الأسئلة الشائعة
### هل يمكن لـ Aspose.Slides التعامل مع مهام التنسيق الأخرى بالإضافة إلى تباعد الأسطر؟
نعم، يدعم Aspose.Slides مجموعة واسعة من خيارات التنسيق بما في ذلك أنماط الخطوط والألوان والمحاذاة والمزيد.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides التنسيقات القديمة (.ppt) والجديدة (.pptx) لعروض PowerPoint التقديمية.
### أين يمكنني العثور على وثائق شاملة لـ Aspose.Slides؟
يمكنك استكشاف الوثائق التفصيلية [هنا](https://reference.aspose.com/slides/java/).
### هل يقدم Aspose.Slides نسخة تجريبية مجانية؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides؟
للحصول على المساعدة الفنية، قم بزيارة Aspose.Slides [منتدى الدعم](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}