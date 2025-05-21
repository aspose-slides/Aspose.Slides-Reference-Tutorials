---
"description": "تعلّم كيفية إدارة عائلة الخطوط في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides لجافا. خصّص أنماط الخطوط وألوانها والمزيد بسهولة."
"linktitle": "إدارة عائلة الخطوط في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إدارة عائلة الخطوط في Java PowerPoint"
"url": "/ar/java/java-powerpoint-font-management/manage-font-family-java-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إدارة عائلة الخطوط في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إدارة عائلة الخطوط في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides. تلعب الخطوط دورًا أساسيًا في المظهر المرئي وسهولة قراءة شرائحك، لذا من الضروري معرفة كيفية التعامل معها بفعالية.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم أي بيئة تطوير متكاملة متوافقة مع Java مثل IntelliJ IDEA، أو Eclipse، أو NetBeans.

## استيراد الحزم
أولاً، دعنا نستورد الحزم اللازمة للعمل مع Aspose.Slides لـ Java:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## الخطوة 1: إنشاء كائن عرض تقديمي
إنشاء مثيل `Presentation` الصف لبدء العمل مع عرض تقديمي على PowerPoint:
```java
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة شريحة وشكل تلقائي
الآن، دعنا نضيف شريحة وشكلًا تلقائيًا (في هذه الحالة، مستطيلًا) إلى العرض التقديمي:
```java
ISlide sld = pres.getSlides().get_Item(0);
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## الخطوة 3: تعيين خصائص الخط
سنقوم بتعيين خصائص الخط المختلفة مثل نوع الخط والنمط والحجم واللون وما إلى ذلك للنص داخل الشكل التلقائي:
```java
ITextFrame tf = ashp.getTextFrame();
tf.setText("Aspose TextBox");
IPortion port = tf.getParagraphs().get_Item(0).getPortions().get_Item(0);
port.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
port.getPortionFormat().setFontBold(NullableBool.True);
port.getPortionFormat().setFontItalic(NullableBool.True);
port.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
port.getPortionFormat().setFontHeight(25);
port.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## الخطوة 4: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل على القرص:
```java
pres.save(dataDir + "pptxFont_out.pptx", SaveFormat.Pptx);
```

## خاتمة
إدارة عائلة الخطوط في عروض PowerPoint التقديمية بلغة جافا أصبحت أسهل مع Aspose.Slides لجافا. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك تخصيص خصائص الخطوط بفعالية لتحسين المظهر المرئي لشرائحك.
## الأسئلة الشائعة
### هل يمكنني تغيير لون الخط إلى قيمة RGB مخصصة؟
نعم، يمكنك تعيين لون الخط باستخدام قيم RGB عن طريق تحديد مكونات اللون الأحمر والأخضر والأزرق بشكل فردي.
### هل من الممكن تطبيق تغييرات الخط على أجزاء معينة من النص داخل الشكل؟
بالتأكيد، يمكنك استهداف أجزاء معينة من النص داخل شكل وتطبيق تغييرات الخط بشكل انتقائي.
### هل يدعم Aspose.Slides تضمين الخطوط المخصصة في العروض التقديمية؟
نعم، يسمح لك Aspose.Slides بتضمين خطوط مخصصة في العروض التقديمية الخاصة بك لضمان الاتساق عبر الأنظمة المختلفة.
### هل يمكنني إنشاء عروض تقديمية PowerPoint برمجيًا باستخدام Aspose.Slides؟
نعم، يوفر Aspose.Slides واجهات برمجة التطبيقات لإنشاء عروض PowerPoint وتعديلها والتلاعب بها بالكامل من خلال التعليمات البرمجية.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}