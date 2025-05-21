---
"description": "تعلّم كيفية ضبط خصائص خط النص في PowerPoint باستخدام Aspose.Slides لجافا. دليل سهل وخطوة بخطوة لمطوري جافا. #تعلّم كيفية تعديل خصائص خط النص في PowerPoint باستخدام Aspose.Slides لجافا من خلال هذا البرنامج التعليمي خطوة بخطوة لمطوري جافا."
"linktitle": "تعيين خصائص خط النص في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين خصائص خط النص في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-text-font-customization/set-text-font-properties-powerpoint-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين خصائص خط النص في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية استخدام Aspose.Slides لجافا لتعيين خصائص خط النص المختلفة في عرض تقديمي لبرنامج PowerPoint برمجيًا. سنغطي ضبط نوع الخط، ونمطه (غامق، مائل)، والتسطير، وحجمه، ولونه للنص في الشرائح.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت JDK على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- المعرفة الأساسية ببرمجة جافا.
- تم إعداد بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
## استيراد الحزم
أولاً، تأكد من استيراد فئات Aspose.Slides الضرورية:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إعداد مشروع Java الخاص بك
قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف مكتبة Aspose.Slides إلى مسار بناء مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
إنشاء مثيل `Presentation` كائن للعمل مع ملفات PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وإضافة الشكل التلقائي
احصل على الشريحة الأولى وأضف إليها شكلًا تلقائيًا (مستطيلًا):
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## الخطوة 4: تعيين النص إلى الشكل التلقائي
تعيين محتوى النص إلى الشكل التلقائي:
```java
ITextFrame textFrame = shape.getTextFrame();
textFrame.setText("Aspose TextBox");
```
## الخطوة 5: تعيين خصائص الخط
الوصول إلى جزء من النص وتعيين خصائص الخط المختلفة:
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
// تعيين عائلة الخطوط
portion.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
// تعيين غامق
portion.getPortionFormat().setFontBold(NullableBool.True);
// تعيين مائل
portion.getPortionFormat().setFontItalic(NullableBool.True);
// تعيين التسطير
portion.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
// تعيين حجم الخط
portion.getPortionFormat().setFontHeight(25);
// تعيين لون الخط
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## الخطوة 6: حفظ العرض التقديمي
حفظ العرض التقديمي المعدل في ملف:
```java
presentation.save(dataDir + "SetTextFontProperties_out.pptx", SaveFormat.Pptx);
```
## الخطوة 7: تنظيف الموارد
التخلص من كائن العرض لتحرير الموارد:
```java
if (presentation != null) {
    presentation.dispose();
}
```

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية استخدام Aspose.Slides لجافا لتخصيص خصائص خطوط النصوص في شرائح PowerPoint ديناميكيًا. باتباع هذه الخطوات، يمكنك تنسيق النص بكفاءة لتلبية متطلبات التصميم المحددة برمجيًا.
## الأسئلة الشائعة
### هل يمكنني تطبيق تغييرات الخط هذه على نص موجود في شريحة PowerPoint؟
نعم، يمكنك تعديل النص الموجود عن طريق الوصول إليه `Portion` وتطبيق خصائص الخط المطلوبة.
### كيف يمكنني تغيير لون الخط إلى لون متدرج أو نمطي؟
بدلاً من `SolidFillColor`، يستخدم `GradientFillColأو` or `PatternedFillColor` وفقاً لذلك.
### هل Aspose.Slides متوافق مع قوالب PowerPoint (.potx)؟
نعم، يمكنك استخدام Aspose.Slides للعمل مع قوالب PowerPoint.
### هل يدعم Aspose.Slides التصدير إلى صيغة PDF؟
نعم، يسمح لك Aspose.Slides بتصدير العروض التقديمية إلى تنسيقات مختلفة بما في ذلك PDF.
### أين يمكنني العثور على مزيد من المساعدة والدعم لـ Aspose.Slides؟
يزور [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على الدعم والتوجيه المجتمعي.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}