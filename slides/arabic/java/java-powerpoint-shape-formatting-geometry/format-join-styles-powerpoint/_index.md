---
title: تنسيق أنماط الانضمام في PowerPoint
linktitle: تنسيق أنماط الانضمام في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحسين عروض PowerPoint التقديمية الخاصة بك عن طريق تعيين أنماط مختلفة لربط الأسطر للأشكال باستخدام Aspose.Slides لـ Java. اتبع دليلنا خطوة بخطوة.
weight: 15
url: /ar/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تنسيق أنماط الانضمام في PowerPoint

## مقدمة
يمكن أن يكون إنشاء عروض PowerPoint التقديمية الجذابة مهمة شاقة، خاصة عندما تريد أن تكون كل التفاصيل مثالية. هذا هو المكان الذي يكون فيه Aspose.Slides for Java مفيدًا. إنها واجهة برمجة تطبيقات قوية تتيح لك إنشاء العروض التقديمية ومعالجتها وإدارتها برمجيًا. إحدى الميزات التي يمكنك استخدامها هي تعيين أنماط ربط خطوط مختلفة للأشكال، والتي يمكن أن تعزز بشكل كبير جماليات الشرائح الخاصة بك. في هذا البرنامج التعليمي، سوف نتعمق في كيفية استخدام Aspose.Slides for Java لتعيين أنماط الانضمام للأشكال في عروض PowerPoint التقديمية. 
## المتطلبات الأساسية
قبل أن نبدأ، هناك بعض المتطلبات الأساسية التي يجب أن تتوفر لديك:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع أوراكل](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java Library: أنت بحاجة إلى تنزيل Aspose.Slides for Java وتضمينها في مشروعك. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse أو NetBeans لكتابة تعليمات Java البرمجية وتنفيذها.
4. المعرفة الأساسية لـ Java: سيساعدك الفهم الأساسي لبرمجة Java على متابعة البرنامج التعليمي.
## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة لـ Aspose.Slides. يعد هذا أمرًا ضروريًا للوصول إلى الفئات والأساليب المطلوبة لمعالجة العرض التقديمي لدينا.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## الخطوة 1: إعداد دليل المشروع
لنبدأ بإنشاء دليل لتخزين ملفات العرض التقديمي. وهذا يضمن أن جميع ملفاتنا منظمة ويمكن الوصول إليها بسهولة.
```java
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
في هذه الخطوة، نقوم بتحديد مسار الدليل والتحقق من وجوده. إذا لم يحدث ذلك، فإننا نقوم بإنشاء الدليل. هذه طريقة بسيطة لكنها فعالة للحفاظ على ملفاتك منظمة.
## الخطوة 2: تهيئة العرض التقديمي
 بعد ذلك، نقوم بإنشاء مثيل`Presentation` class، الذي يمثل ملف PowerPoint الخاص بنا. هذا هو الأساس الذي سنبني عليه شرائحنا وأشكالنا.
```java
Presentation pres = new Presentation();
```
يقوم هذا السطر من التعليمات البرمجية بإنشاء عرض تقديمي جديد. فكر في الأمر على أنه فتح ملف PowerPoint فارغ حيث ستضيف كل المحتوى الخاص بك.
## الخطوة 3: إضافة الأشكال إلى الشريحة
### احصل على الشريحة الأولى
قبل إضافة الأشكال، نحتاج إلى الحصول على مرجع للشريحة الأولى في عرضنا التقديمي. بشكل افتراضي، يحتوي العرض التقديمي الجديد على شريحة فارغة واحدة.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### إضافة الأشكال المستطيلة
الآن، دعونا نضيف ثلاثة أشكال مستطيلة إلى الشريحة لدينا. ستوضح هذه الأشكال أنماط ربط الخطوط المختلفة.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
في هذه الخطوة، نقوم بإضافة ثلاثة مستطيلات في مواضع محددة على الشريحة. سيتم لاحقًا تصميم كل مستطيل بشكل مختلف لعرض أنماط الانضمام المختلفة.
## الخطوة 4: تصميم الأشكال
### تعيين لون التعبئة
نريد أن تمتلئ مستطيلاتنا بلون خالص. هنا، نختار اللون الأسود للون التعبئة.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### ضبط عرض الخط واللون
بعد ذلك، نحدد عرض الخط واللون لكل مستطيل. يساعد هذا في التمييز بين أنماط الانضمام بشكل مرئي.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## الخطوة 5: تطبيق أنماط الانضمام
أهم ما يميز هذا البرنامج التعليمي هو تعيين أنماط ربط الخط. سوف نستخدم ثلاثة أنماط مختلفة: Mitre، Bevel، و Round.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
يمنح كل نمط ربط سطر الأشكال مظهرًا فريدًا في الزوايا التي تلتقي فيها الخطوط. يمكن أن يكون هذا مفيدًا بشكل خاص لإنشاء مخططات أو رسوم توضيحية مميزة بصريًا.
## الخطوة 6: إضافة نص إلى الأشكال
لتوضيح ما يمثله كل شكل، نضيف نصًا إلى كل مستطيل يصف نمط الربط المستخدم.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
تساعد إضافة النص في تحديد الأنماط المختلفة عند تقديم الشريحة أو مشاركتها.
## الخطوة 7: احفظ العرض التقديمي
وأخيرًا، نقوم بحفظ العرض التقديمي الخاص بنا في الدليل المحدد.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
يقوم هذا الأمر بكتابة العرض التقديمي في ملف PPTX، والذي يمكنك فتحه باستخدام Microsoft PowerPoint أو أي برنامج آخر متوافق.
## خاتمة
وهناك لديك! لقد قمت للتو بإنشاء شريحة PowerPoint بثلاثة مستطيلات، يعرض كل منها نمطًا مختلفًا لربط الأسطر باستخدام Aspose.Slides for Java. لا يساعدك هذا البرنامج التعليمي على فهم أساسيات Aspose.Slides فحسب، بل يوضح أيضًا كيفية تحسين عروضك التقديمية باستخدام أنماط فريدة. عرض سعيد!
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات قوية لإنشاء عروض PowerPoint التقديمية ومعالجتها وإدارتها برمجيًا.
### هل يمكنني استخدام Aspose.Slides لـ Java في أي بيئة تطوير متكاملة (IDE)؟
نعم، يمكنك استخدام Aspose.Slides لـ Java في أي IDE يدعم Java مثل IntelliJ IDEA أو Eclipse أو NetBeans.
### هل هناك نسخة تجريبية مجانية من Aspose.Slides لجافا؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### ما هي أنماط ربط الخط في PowerPoint؟
تشير أنماط ربط الخطوط إلى شكل الزوايا حيث يلتقي الخطان. تشمل الأنماط الشائعة Mitre وBevel وRound.
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
 يمكنك العثور على وثائق مفصلة[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
