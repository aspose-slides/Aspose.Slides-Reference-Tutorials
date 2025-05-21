---
"description": "تعرّف على كيفية إنشاء أشكال جماعية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. حسّن تنظيم العرض وجاذبيته البصرية بسهولة."
"linktitle": "إنشاء شكل المجموعة في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء شكل المجموعة في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-thumbnail-creation/create-group-shape-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء شكل المجموعة في PowerPoint

## مقدمة
في العروض التقديمية الحديثة، يُعدّ دمج عناصر جذابة بصريًا ومنظمة جيدًا أمرًا بالغ الأهمية لعرض المعلومات بفعالية. تتيح لك أشكال المجموعات في PowerPoint تنظيم أشكال متعددة في وحدة واحدة، مما يُسهّل التعامل معها وتنسيقها. يوفر Aspose.Slides لـ Java وظائف فعّالة لإنشاء أشكال المجموعات ومعالجتها برمجيًا، مما يوفر مرونة وتحكمًا في تصميم العرض التقديمي.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من إعداد المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
2. مكتبة Aspose.Slides لجافا: نزّل مكتبة Aspose.Slides لجافا وأضِفها إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر Java IDE حسب تفضيلاتك، مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
للبدء، قم باستيراد الحزم اللازمة لاستخدام وظائف Aspose.Slides لـ Java:
```java
import com.aspose.slides.*;

```
## الخطوة 1: إعداد البيئة الخاصة بك
تأكد من إعداد دليل لمشروعك حيث يمكنك إنشاء عروض PowerPoint التقديمية وحفظها. استبدل `"Your Document Directory"` مع المسار إلى الدليل المطلوب.
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء فئة العرض التقديمي
إنشاء مثيل لـ `Presentation` فئة لتهيئة عرض تقديمي جديد لبرنامج PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: الحصول على مجموعات الشرائح والأشكال
استرداد الشريحة الأولى من العرض التقديمي والوصول إلى مجموعة الأشكال الخاصة بها.
```java
ISlide sld = pres.getSlides().get_Item(0);
IShapeCollection slideShapes = sld.getShapes();
```
## الخطوة 4: إضافة شكل المجموعة
أضف شكل المجموعة إلى الشريحة باستخدام `addGroupShape()` طريقة.
```java
IGroupShape groupShape = slideShapes.addGroupShape();
```
## الخطوة 5: إضافة الأشكال داخل شكل المجموعة
قم بملء شكل المجموعة عن طريق إضافة أشكال فردية بداخلها.
```java
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```
## الخطوة 6: تخصيص إطار شكل المجموعة
اختياريًا، يمكنك تخصيص إطار شكل المجموعة وفقًا لتفضيلاتك.
```java
groupShape.setFrame(new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0));
```
## الخطوة 7: حفظ العرض التقديمي
احفظ عرض PowerPoint في الدليل المحدد.
```java
pres.save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يُتيح إنشاء أشكال المجموعات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java نهجًا مُبسّطًا لتنظيم المحتوى وهيكلته. باتباع الدليل التفصيلي الموضح أعلاه، يمكنك دمج أشكال المجموعات بفعالية في عروضك التقديمية، مما يُحسّن من جاذبيتها البصرية ويُوصل المعلومات بفعالية.

## الأسئلة الشائعة
### هل يمكنني تضمين أشكال المجموعة داخل أشكال المجموعة الأخرى؟
نعم، يسمح لك Aspose.Slides for Java بتداخل أشكال المجموعة داخل بعضها البعض لإنشاء هياكل هرمية معقدة.
### هل Aspose.Slides for Java متوافق مع الإصدارات المختلفة من PowerPoint؟
يقوم Aspose.Slides for Java بإنشاء عروض تقديمية PowerPoint متوافقة مع الإصدارات المختلفة، مما يضمن التوافق المتبادل.
### هل يدعم Aspose.Slides for Java إضافة الصور إلى أشكال المجموعة؟
بالتأكيد، يمكنك إضافة الصور مع الأشكال الأخرى لتجميع الأشكال باستخدام Aspose.Slides لـ Java.
### هل هناك أي قيود على عدد الأشكال داخل شكل المجموعة؟
لا يفرض Aspose.Slides for Java أي قيود صارمة على عدد الأشكال التي يمكن إضافتها إلى شكل المجموعة.
### هل يمكنني تطبيق الرسوم المتحركة على أشكال المجموعة باستخدام Aspose.Slides لـ Java؟
نعم، يوفر Aspose.Slides for Java دعمًا شاملاً لتطبيق الرسوم المتحركة على أشكال المجموعة، مما يتيح تقديم عروض تقديمية ديناميكية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}