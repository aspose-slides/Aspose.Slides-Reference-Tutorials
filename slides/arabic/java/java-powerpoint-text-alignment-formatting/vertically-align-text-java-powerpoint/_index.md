---
"description": "تعرف على كيفية محاذاة النص عموديًا في عروض PowerPoint التقديمية باستخدام Aspose.Slides لتنسيق الشرائح بشكل سلس."
"linktitle": "محاذاة النص عموديًا في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "محاذاة النص عموديًا في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# محاذاة النص عموديًا في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية محاذاة النص عموديًا داخل خلايا الجدول في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُعد محاذاة النص عموديًا جانبًا أساسيًا في تصميم الشرائح، مما يضمن عرض محتواك بشكل أنيق واحترافي. يوفر Aspose.Slides ميزات فعّالة لإدارة العروض التقديمية وتنسيقها برمجيًا، مما يمنحك تحكمًا كاملاً في جميع جوانب شرائحك.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على جهازك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- تم تثبيت IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
قبل متابعة البرنامج التعليمي، تأكد من استيراد حزم Aspose.Slides الضرورية إلى ملف Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إعداد مشروع Java الخاص بك
تأكد من إعداد مشروع Java جديد في بيئة التطوير المتكاملة المفضلة لديك وإضافة مكتبة Aspose.Slides إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
إنشاء مثيل لـ `Presentation` الفصل لبدء العمل على عرض تقديمي جديد في PowerPoint:
```java
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة الأولى
احصل على الشريحة الأولى من العرض التقديمي لإضافة المحتوى إليها:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## الخطوة 4: تحديد أبعاد الجدول وإضافة جدول
قم بتحديد عرض الأعمدة وارتفاع الصفوف للجدول الخاص بك، ثم أضف شكل الجدول إلى الشريحة:
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## الخطوة 5: تعيين محتوى النص في خلايا الجدول
تعيين محتوى النص لصفوف محددة في الجدول:
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## الخطوة 6: الوصول إلى إطار النص وتنسيق النص
الوصول إلى إطار النص وتنسيق النص داخل خلية محددة:
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## الخطوة 7: محاذاة النص عموديًا
تعيين المحاذاة الرأسية للنص داخل الخلية:
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## الخطوة 8: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل في موقع محدد على القرص الخاص بك:
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## الخطوة 9: تنظيف الموارد
التخلص من `Presentation` هدف تحرير الموارد:
```java
if (presentation != null) presentation.dispose();
```

## خاتمة
باتباع هذه الخطوات، يمكنك محاذاة النص عموديًا بفعالية داخل خلايا الجدول في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides. تُحسّن هذه الميزة من جاذبية العرض ووضوحه، مما يضمن عرض محتواك باحترافية.

## الأسئلة الشائعة
### هل يمكنني محاذاة النص عموديا في أشكال أخرى غير الجداول؟
نعم، يوفر Aspose.Slides طرقًا لمحاذاة النص عموديًا في أشكال مختلفة، بما في ذلك مربعات النص وعناصر النائبة.
### هل يدعم Aspose.Slides محاذاة النص أفقيًا أيضًا؟
نعم، يمكنك محاذاة النص أفقيًا باستخدام خيارات المحاذاة المختلفة التي يوفرها Aspose.Slides.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides إنشاء عروض تقديمية متوافقة مع كافة الإصدارات الرئيسية من Microsoft PowerPoint.
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides؟
قم بزيارة [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/) للحصول على أدلة شاملة ومراجع API وعينات التعليمات البرمجية.
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟
للحصول على المساعدة الفنية ودعم المجتمع، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}