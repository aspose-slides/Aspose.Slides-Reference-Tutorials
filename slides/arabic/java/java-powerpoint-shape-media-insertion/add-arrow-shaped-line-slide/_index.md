---
"description": "تعرّف على كيفية إضافة خطوط على شكل أسهم إلى شرائح PowerPoint باستخدام Aspose.Slides لجافا. خصّص الأنماط والألوان والمواضع بسهولة."
"linktitle": "إضافة خط على شكل سهم إلى الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة خط على شكل سهم إلى الشريحة"
"url": "/ar/java/java-powerpoint-shape-media-insertion/add-arrow-shaped-line-slide/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خط على شكل سهم إلى الشريحة

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إضافة خط سهمي إلى شريحة باستخدام Aspose.Slides لجافا. Aspose.Slides هي واجهة برمجة تطبيقات Java فعّالة تُمكّن المطورين من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. إضافة خطوط سهمية إلى الشرائح تُحسّن من جاذبية عروضك التقديمية ووضوحها.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- تم تنزيل مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا الخاص بك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- المعرفة الأساسية بلغة البرمجة جافا.

## استيراد الحزم
أولاً، قم باستيراد الحزم الضرورية إلى فئة Java الخاصة بك:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## الخطوة 1: إعداد البيئة
تأكد من إعداد المجلدات اللازمة. إذا لم يكن المجلد موجودًا، فأنشئه.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: إنشاء كائن العرض التقديمي
إنشاء مثيل لـ `Presentation` الفئة لتمثيل ملف PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: الحصول على الشريحة وإضافة شكل تلقائي
استرداد الشريحة الأولى وإضافة شكل تلقائي من نوع الخط إليها.
```java
ISlide sld = pres.getSlides().get_Item(0);
IAutoShape shp = sld.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## الخطوة 4: تنسيق الخط
قم بتطبيق التنسيق على الخط، مثل النمط، والعرض، ونمط الشرطة، ونمط رأس السهم.
```java
shp.getLineFormat().setStyle(LineStyle.ThickBetweenThin);
shp.getLineFormat().setWidth(10);
shp.getLineFormat().setDashStyle(LineDashStyle.DashDot);
shp.getLineFormat().setBeginArrowheadStyle(LineArrowheadStyle.Oval);
shp.getLineFormat().setBeginArrowheadLength(LineArrowheadLength.Short);
shp.getLineFormat().setEndArrowheadStyle(LineArrowheadStyle.Triangle);
shp.getLineFormat().setEndArrowheadLength(LineArrowheadLength.Long);
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Maroon));
```
## الخطوة 5: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل على القرص.
```java
pres.save(dataDir + "LineShape2_out.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إضافة خط على شكل سهم إلى شريحة باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات، يمكنك إنشاء عروض تقديمية جذابة بصريًا بأشكال وأنماط مخصصة.
## الأسئلة الشائعة
### هل يمكنني تخصيص لون خط السهم؟
نعم، يمكنك تحديد أي لون باستخدام `setColor` الطريقة مع `SolidFillColor`.
### كيف يمكنني تغيير موضع وحجم خط السهم؟
ضبط المعلمات المرسلة إلى `addAutoShape` طريقة لتغيير الموضع والأبعاد.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides تنسيقات PowerPoint المختلفة، مما يضمن التوافق بين الإصدارات المختلفة.
### هل يمكنني إضافة نص إلى خط السهم؟
نعم، يمكنك إضافة نص إلى السطر عن طريق إنشاء TextFrame وتعيين خصائصه وفقًا لذلك.
### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Slides؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على الدعم واستكشاف [التوثيق](https://reference.aspose.com/slides/java/) لمزيد من المعلومات التفصيلية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}