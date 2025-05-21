---
"description": "تعلّم كيفية تغيير ترتيب الأشكال في PowerPoint باستخدام Aspose.Slides لجافا من خلال هذا البرنامج التعليمي خطوة بخطوة. طوّر مهاراتك في العروض التقديمية بسهولة."
"linktitle": "تغيير ترتيب الشكل في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تغيير ترتيب الشكل في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تغيير ترتيب الشكل في PowerPoint

## مقدمة
إنشاء عروض تقديمية جذابة بصريًا ومنظمة جيدًا قد يكون مهمة شاقة. مع ذلك، باستخدام الأدوات والتقنيات المناسبة، يمكنك تسهيل الأمر بشكل كبير. Aspose.Slides for Java هي مكتبة فعّالة تساعدك على إدارة عروض PowerPoint التقديمية برمجيًا. في هذا البرنامج التعليمي، سنشرح لك خطوات تغيير ترتيب الأشكال في شريحة PowerPoint باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من [موقع أوراكل](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides لمكتبة Java: قم بتنزيل الإصدار الأحدث من [صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse للترميز.
4. ملف العرض التقديمي: قم بإعداد ملف PowerPoint الذي تريد التعامل معه.
## استيراد الحزم
للبدء، عليك استيراد الحزم اللازمة من مكتبة Aspose.Slides. ستتيح لك هذه الاستيرادات العمل مع العروض التقديمية والشرائح والأشكال.
```java
import com.aspose.slides.*;

```
في هذا الدليل، سنقوم بتقسيم عملية تغيير ترتيب الشكل إلى عدة خطوات لتحسين الفهم وسهولة التنفيذ.
## الخطوة 1: تحميل العرض التقديمي
أولاً، عليك تحميل ملف عرض PowerPoint الذي ترغب بالعمل عليه. تتضمن هذه الخطوة تهيئة `Presentation` الفئة التي تحتوي على المسار إلى ملف PowerPoint الخاص بك.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## الخطوة 2: الوصول إلى الشريحة المطلوبة
بعد تحميل العرض التقديمي، انتقل إلى الشريحة التي تريد إعادة ترتيب الأشكال فيها. تبدأ فهرسة الشرائح من 0، لذا للوصول إلى الشريحة الأولى، استخدم الفهرس 0.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## الخطوة 3: إضافة الأشكال إلى الشريحة
بعد ذلك، أضف الأشكال إلى الشريحة. للتوضيح، سنضيف شكلي مستطيل ومثلث إلى الشريحة.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## الخطوة 4: إعادة ترتيب الأشكال
الآن، قم بإعادة ترتيب الأشكال على الشريحة. `reorder` تتيح لك الطريقة تحديد الموضع الجديد للشكل ضمن مجموعة الأشكال الخاصة بالشريحة.
```java
slide.getShapes().reorder(2, shp3);
```
## الخطوة 5: حفظ العرض التقديمي المعدّل
بعد إعادة ترتيب الأشكال، احفظ العرض التقديمي المُعدَّل في ملف جديد. هذا يضمن بقاء ملفك الأصلي دون تغيير.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## الخطوة 6: تنظيف الموارد
أخيرًا، تخلص من كائن العرض لتحرير الموارد.
```java
if (presentation1 != null) presentation1.dispose();
```
## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة تغيير ترتيب الأشكال في شريحة PowerPoint باستخدام Aspose.Slides for Java. تُبسّط هذه المكتبة الفعّالة العديد من المهام المرتبطة بعروض PowerPoint التقديمية، مما يُمكّنك من إنشاء الشرائح وتعديلها برمجيًا. سواء كنت تُؤتمت إنشاء العروض التقديمية أو تحتاج فقط إلى إجراء تغييرات شاملة، فإن Aspose.Slides for Java أداة قيّمة للغاية.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن واجهة برمجة تطبيقات Java لإنشاء عروض PowerPoint والتلاعب بها دون استخدام Microsoft PowerPoint.
### هل يمكنني استخدام Aspose.Slides لـ Java مع بيئات التطوير المتكاملة Java IDE الأخرى؟
نعم، يمكنك استخدامه مع أي Java IDE مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.
### هل Aspose.Slides for Java متوافق مع كافة تنسيقات PowerPoint؟
نعم، يدعم Aspose.Slides for Java تنسيقات PPT وPPTX وتنسيقات PowerPoint الأخرى.
### كيف يمكنني الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ Java؟
يمكنك تنزيل نسخة تجريبية مجانية من [صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
يمكنك العثور على وثائق مفصلة على [صفحة توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}