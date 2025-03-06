---
title: إنشاء مستطيل منسق في PowerPoint
linktitle: إنشاء مستطيل منسق في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مستطيل وتنسيقه في PowerPoint باستخدام Aspose.Slides لـ Java باستخدام هذا الدليل التفصيلي خطوة بخطوة.
weight: 18
url: /ar/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مستطيل منسق في شريحة PowerPoint باستخدام Aspose.Slides for Java. سنقوم بتفصيل كل خطوة، مما يضمن أنه يمكنك متابعة وتنفيذ ذلك في مشاريعك الخاصة.
## المتطلبات الأساسية
قبل أن نتعمق في التعليمات البرمجية، دعونا نغطي المتطلبات الأساسية. ستحتاج إلى ما يلي:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2. Aspose.Slides for Java Library: قم بتنزيل مكتبة Aspose.Slides for Java وتضمينها في مشروعك.
3. بيئة التطوير المتكاملة (IDE): بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse ستجعل تجربة البرمجة الخاصة بك أكثر سلاسة.
4. المعرفة الأساسية بجافا: الإلمام ببرمجة جافا سيساعدك على متابعة هذا البرنامج التعليمي.
## حزم الاستيراد
للبدء، ستحتاج إلى استيراد الحزم الضرورية من مكتبة Aspose.Slides. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
تعتبر هذه الواردات حاسمة لأنها توفر الفئات المطلوبة لإنشاء الأشكال وتنسيقها في عرض PowerPoint التقديمي.
## الخطوة 1: إعداد دليل المشروع
أولاً، تحتاج إلى إنشاء دليل لمشروعك. سيقوم هذا الدليل بتخزين ملفات PowerPoint الخاصة بك.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
يتحقق هذا الرمز من وجود الدليل ويقوم بإنشائه إذا لم يكن موجودًا. إنها ممارسة جيدة للحفاظ على ملفات مشروعك منظمة.
## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي
 بعد ذلك، سوف تقوم بإنشاء مثيل`Presentation` class الذي يمثل ملف PowerPoint الخاص بك.
```java
Presentation pres = new Presentation();
```
يقوم سطر التعليمات البرمجية هذا بإنشاء عرض تقديمي جديد وفارغ يمكنك البدء في إضافة المحتوى إليه.
## الخطوة 3: إضافة شريحة إلى العرض التقديمي
الآن، دعونا نضيف شريحة إلى العرض التقديمي الخاص بك. افتراضيًا، يحتوي العرض التقديمي الجديد على شريحة واحدة، لذلك سنتعامل معها.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
يحصل مقتطف الكود هذا على الشريحة الأولى من العرض التقديمي.
## الخطوة 4: إضافة شكل مستطيل
سنقوم الآن بإضافة مستطيل إلى الشريحة.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
نقوم هنا بإضافة مستطيل بأبعاد محددة (العرض والارتفاع) والموضع (x، y) إلى الشريحة.
## الخطوة 5: تنسيق المستطيل
دعونا نطبق بعض التنسيق لجعل المستطيل جذابًا بصريًا.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
يقوم هذا الرمز بتعيين نوع التعبئة إلى صلب ولون التعبئة إلى الشوكولاتة.
## تنسيق حدود المستطيل
بعد ذلك، سنقوم بتنسيق حدود المستطيل.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
يقوم هذا الرمز بتعيين لون الحدود إلى اللون الأسود وعرض الحدود إلى 5.
## الخطوة 6: احفظ العرض التقديمي
أخيرًا، دعنا نحفظ العرض التقديمي في دليل مشروعك.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
يحفظ سطر التعليمات البرمجية هذا العرض التقديمي كملف PPTX في الدليل المحدد لديك.
## الخطوة 7: تنظيف الموارد
 إنها ممارسة جيدة للتخلص من`Presentation` كائن لتحرير الموارد.
```java
if (pres != null) pres.dispose();
```
وهذا يضمن تحرير جميع الموارد بشكل صحيح.
## خاتمة
يعد إنشاء الأشكال وتنسيقها في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java عملية مباشرة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك أتمتة إنشاء شرائح جذابة بصريًا بسهولة. سواء كنت تقوم بتطوير تطبيقات لتقارير الأعمال أو المحتوى التعليمي أو العروض التقديمية الديناميكية، فإن Aspose.Slides for Java يوفر الأدوات التي تحتاجها لتحقيق النجاح.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجياً.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي بيئة تطوير متكاملة (IDE)؟
نعم، يمكنك استخدام Aspose.Slides لـ Java مع أي IDE متوافق مع Java مثل IntelliJ IDEA أو Eclipse أو NetBeans.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
 يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/).
###  هل من الضروري التخلص من`Presentation` object?
 نعم التخلص من`Presentation` يساعد الكائن على تحرير الموارد وتجنب تسرب الذاكرة.
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
 الوثائق متاحة[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
