---
"description": "تعرف على كيفية إنشاء مستطيل وتنسيقه في PowerPoint باستخدام Aspose.Slides for Java من خلال هذا الدليل خطوة بخطوة."
"linktitle": "إنشاء مستطيل منسق في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء مستطيل منسق في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مستطيل منسق في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مستطيل منسق في شريحة PowerPoint باستخدام Aspose.Slides لجافا. سنشرح كل خطوة بالتفصيل، لضمان قدرتك على متابعتها وتطبيقها في مشاريعك الخاصة.
## المتطلبات الأساسية
قبل أن نتعمق في الكود، دعونا نتناول المتطلبات الأساسية. ستحتاج إلى ما يلي:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
2. مكتبة Aspose.Slides لـ Java: قم بتنزيل مكتبة Aspose.Slides لـ Java وقم بإضافتها إلى مشروعك.
3. بيئة التطوير المتكاملة (IDE): ستعمل بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse على جعل تجربة الترميز الخاصة بك أكثر سلاسة.
4. المعرفة الأساسية بلغة جافا: ستساعدك المعرفة ببرمجة جافا على متابعة هذا البرنامج التعليمي.
## استيراد الحزم
للبدء، ستحتاج إلى استيراد الحزم اللازمة من مكتبة Aspose.Slides. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
تُعد هذه الواردات بالغة الأهمية لأنها توفر الفئات المطلوبة لإنشاء الأشكال وتنسيقها في عرض PowerPoint التقديمي.
## الخطوة 1: إعداد دليل المشروع
أولاً، عليك إنشاء مجلد لمشروعك. سيُخزّن هذا المجلد ملفات PowerPoint الخاصة بك.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
يتحقق هذا الكود من وجود الدليل، ويُنشئه إن لم يكن موجودًا. يُنصح بتنظيم ملفات مشروعك.
## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي
بعد ذلك، سوف تقوم بإنشاء مثيل `Presentation` الفئة التي تمثل ملف PowerPoint الخاص بك.
```java
Presentation pres = new Presentation();
```
يؤدي هذا السطر من التعليمات البرمجية إلى إنشاء عرض تقديمي جديد فارغ يمكنك البدء في إضافة المحتوى إليه.
## الخطوة 3: إضافة شريحة إلى العرض التقديمي
الآن، لنُضِف شريحةً إلى عرضك التقديمي. افتراضيًا، يحتوي العرض التقديمي الجديد على شريحة واحدة، لذا سنعمل على ذلك.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
يعتبر مقتطف التعليمات البرمجية هذا بمثابة الشريحة الأولى من العرض التقديمي.
## الخطوة 4: إضافة شكل مستطيل
سنقوم الآن بإضافة مستطيل إلى الشريحة.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
هنا، نضيف مستطيلًا بأبعاد محددة (العرض والارتفاع) وموضع (x، y) إلى الشريحة.
## الخطوة 5: تنسيق المستطيل
دعونا نطبق بعض التنسيق لجعل المستطيل جذابًا بصريًا.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
يقوم هذا الكود بتعيين نوع التعبئة إلى صلب ولون التعبئة إلى الشوكولاتة.
## تنسيق حدود المستطيل
بعد ذلك، سنقوم بتنسيق حدود المستطيل.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
يقوم هذا الكود بتعيين لون الحدود إلى اللون الأسود وعرض الحدود إلى 5.
## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، دعنا نحفظ العرض التقديمي في دليل المشروع الخاص بك.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
يحفظ هذا السطر من التعليمات البرمجية العرض التقديمي كملف PPTX في الدليل المحدد.
## الخطوة 7: تنظيف الموارد
من الجيد التخلص من `Presentation` هدف لتحرير الموارد.
```java
if (pres != null) pres.dispose();
```
ويضمن هذا تحرير كافة الموارد بشكل صحيح.
## خاتمة
إنشاء الأشكال وتنسيقها في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا عملية سهلة وبسيطة. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك أتمتة إنشاء شرائح جذابة بصريًا بسهولة. سواء كنت تُطوّر تطبيقات لتقارير الأعمال، أو محتوى تعليميًا، أو عروضًا تقديمية ديناميكية، فإن Aspose.Slides لجافا يوفر لك الأدوات اللازمة للنجاح.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة تسمح للمطورين بإنشاء عروض PowerPoint وتعديلها وتحويلها برمجيًا.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي IDE؟
نعم، يمكنك استخدام Aspose.Slides for Java مع أي IDE متوافق مع Java مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/).
### هل من الضروري التخلص من `Presentation` هدف؟
نعم التخلص منها `Presentation` يساعد الكائن على تحرير الموارد وتجنب تسرب الذاكرة.
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
الوثائق متاحة [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}