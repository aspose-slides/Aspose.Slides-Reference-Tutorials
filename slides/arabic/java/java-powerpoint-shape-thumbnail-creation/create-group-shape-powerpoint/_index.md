---
title: إنشاء شكل المجموعة في PowerPoint
linktitle: إنشاء شكل المجموعة في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء أشكال جماعية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تحسين التنظيم والجاذبية البصرية دون عناء.
weight: 11
url: /ar/java/java-powerpoint-shape-thumbnail-creation/create-group-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شكل المجموعة في PowerPoint

## مقدمة
في العروض التقديمية الحديثة، يعد دمج العناصر الجذابة بصريًا والمنظمة بشكل جيد أمرًا ضروريًا لنقل المعلومات بشكل فعال. تسمح لك أشكال المجموعات في PowerPoint بتنظيم أشكال متعددة في وحدة واحدة، مما يسهل المعالجة والتنسيق. يوفر Aspose.Slides for Java وظائف قوية لإنشاء أشكال المجموعة ومعالجتها برمجيًا، مما يوفر المرونة والتحكم في تصميم العرض التقديمي الخاص بك.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2. Aspose.Slides for Java Library: قم بتنزيل مكتبة Aspose.Slides for Java وتضمينها في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر Java IDE الذي تفضله، مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
للبدء، قم باستيراد الحزم اللازمة لاستخدام Aspose.Slides لوظائف Java:
```java
import com.aspose.slides.*;

```
## الخطوة 1: إعداد بيئتك
 تأكد من إعداد دليل لمشروعك حيث يمكنك إنشاء عروض PowerPoint التقديمية وحفظها. يستبدل`"Your Document Directory"` مع المسار إلى الدليل المطلوب.
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي
 إنشاء مثيل لـ`Presentation` فئة لتهيئة عرض تقديمي جديد لـ PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: احصل على مجموعات الشرائح والأشكال
قم باسترجاع الشريحة الأولى من العرض التقديمي والوصول إلى مجموعة الأشكال الخاصة بها.
```java
ISlide sld = pres.getSlides().get_Item(0);
IShapeCollection slideShapes = sld.getShapes();
```
## الخطوة 4: إضافة شكل المجموعة
 أضف شكل مجموعة إلى الشريحة باستخدام`addGroupShape()` طريقة.
```java
IGroupShape groupShape = slideShapes.addGroupShape();
```
## الخطوة 5: إضافة الأشكال داخل شكل المجموعة
قم بتعبئة شكل المجموعة عن طريق إضافة أشكال فردية بداخله.
```java
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```
## الخطوة 6: تخصيص إطار شكل المجموعة
اختياريًا، قم بتخصيص إطار شكل المجموعة وفقًا لتفضيلاتك.
```java
groupShape.setFrame(new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0));
```
## الخطوة 7: احفظ العرض التقديمي
احفظ عرض PowerPoint التقديمي في الدليل المحدد.
```java
pres.save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يوفر إنشاء أشكال جماعية في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java أسلوبًا مبسطًا لتنظيم المحتوى وهيكلته. باتباع الدليل التفصيلي الموضح أعلاه، يمكنك دمج أشكال المجموعة بكفاءة في عروضك التقديمية، مما يعزز الجاذبية البصرية وينقل المعلومات بفعالية.

## الأسئلة الشائعة
### هل يمكنني دمج أشكال المجموعات داخل أشكال المجموعات الأخرى؟
نعم، يسمح Aspose.Slides for Java بتداخل أشكال المجموعات داخل بعضها البعض لإنشاء هياكل هرمية معقدة.
### هل Aspose.Slides for Java متوافق مع الإصدارات المختلفة من PowerPoint؟
يقوم Aspose.Slides for Java بإنشاء عروض PowerPoint التقديمية المتوافقة مع الإصدارات المختلفة، مما يضمن التوافق المتبادل.
### هل يدعم Aspose.Slides for Java إضافة الصور إلى أشكال المجموعة؟
بالتأكيد، يمكنك إضافة الصور إلى جانب الأشكال الأخرى لتجميع الأشكال باستخدام Aspose.Slides for Java.
### هل هناك أي قيود على عدد الأشكال داخل شكل المجموعة؟
لا يفرض Aspose.Slides for Java أي قيود صارمة على عدد الأشكال التي يمكن إضافتها إلى شكل المجموعة.
### هل يمكنني تطبيق الرسوم المتحركة على أشكال المجموعة باستخدام Aspose.Slides لـ Java؟
نعم، يوفر Aspose.Slides for Java دعمًا شاملاً لتطبيق الرسوم المتحركة على أشكال المجموعة، مما يتيح العروض التقديمية الديناميكية.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
