---
"description": "تعلّم كيفية ضبط مرساة إطار النص في PowerPoint باستخدام Java مع Aspose.Slides. حسّن عروضك التقديمية."
"linktitle": "تعيين مرساة إطار النص في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين مرساة إطار النص في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-text-font-customization/set-anchor-text-frame-powerpoint-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين مرساة إطار النص في PowerPoint باستخدام Java

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية ضبط مرساة إطار نص في عروض PowerPoint التقديمية باستخدام Java بمساعدة Aspose.Slides. يتيح لك تثبيت إطارات النص التحكم بدقة في موضع النص وسلوكه داخل الشكل، مما يضمن أن تكون شرائحك جذابة بصريًا ومنظمة بشكل فعال.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- مجموعة تطوير Java (JDK) مثبتة على نظامك
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/)
- فهم أساسي للغة برمجة جافا ومفاهيم البرمجة الكائنية التوجه
## استيراد الحزم
للبدء، قم بتضمين مكتبة Aspose.Slides الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## الخطوة 1: إعداد مشروعك
تأكد من إعداد مشروع جافا في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من إضافة ملف Aspose.Slides JAR إلى مسار بناء مشروعك.
## الخطوة 2: إنشاء كائن عرض تقديمي
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
يؤدي هذا إلى تهيئة كائن عرض تقديمي جديد في PowerPoint.
## الخطوة 3: الوصول إلى الشريحة وإضافة شكل
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
هنا، تتم إضافة شكل مستطيل إلى الشريحة عند إحداثيات وأبعاد محددة.
## الخطوة 4: إضافة إطار نص إلى الشكل
```java
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAnchoringType(TextAnchorType.Bottom);
```
تمت إضافة إطار نص إلى شكل المستطيل، وتم تعيين نوع رسوخه على `Bottom`، مع التأكد من تثبيت النص في أسفل الشكل.
## الخطوة 5: إدراج النص في إطار النص
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
يؤدي هذا إلى إضافة محتوى نصي إلى إطار النص وتطبيق التنسيق، مثل تعيين لون النص إلى الأسود.
## الخطوة 6: حفظ العرض التقديمي
```java
presentation.save(dataDir + "AnchorText_out.pptx", SaveFormat.Pptx);
```
وأخيرًا، احفظ العرض التقديمي المعدّل في موقع محدد على القرص لديك.

## خاتمة
يُعدّ ضبط موضع إطار النص في PowerPoint باستخدام Java أمرًا أساسيًا لإنشاء عروض تقديمية منظمة. باتباع هذه الخطوات والاستفادة من Aspose.Slides for Java، يمكنك إدارة موضع النص بكفاءة داخل الأشكال، مما يعزز المظهر المرئي ووضوح شرائحك.

## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية تسمح لمطوري Java بإنشاء عروض PowerPoint وقراءتها ومعالجتها وتحويلها.
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
يمكنك الوصول إلى الوثائق [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### هل يمكنني تجربة Aspose.Slides لـJava مجانًا؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك زيارة منتدى الدعم [هنا](https://forum.aspose.com/c/slides/11) لأي استفسارات أو مساعدة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}