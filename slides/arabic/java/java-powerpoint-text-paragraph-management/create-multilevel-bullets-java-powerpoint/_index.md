---
"description": "تعلّم كيفية إنشاء نقاط متعددة المستويات في PowerPoint باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع أمثلة برمجية وأسئلة شائعة."
"linktitle": "إنشاء نقاط متعددة المستويات في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء نقاط متعددة المستويات في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء نقاط متعددة المستويات في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء نقاط متعددة المستويات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تُعد إضافة النقاط شرطًا أساسيًا لإنشاء محتوى منظم وجذاب في العروض التقديمية. سنشرح العملية خطوة بخطوة، لضمان أن تكون جاهزًا بنهاية هذا الدليل لتحسين عروضك التقديمية باستخدام نقاط منظمة على مستويات متعددة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من إعداد ما يلي:
- بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
- Aspose.Slides لمكتبة Java: قم بتنزيل Aspose.Slides لمكتبة Java وتثبيتها من [هنا](https://releases.aspose.com/slides/java/).
- IDE: استخدم بيئة التطوير المتكاملة Java (IDE) المفضلة لديك مثل IntelliJ IDEA أو Eclipse أو غيرها.
- المعرفة الأساسية: ستكون المعرفة ببرمجة Java ومفاهيم PowerPoint الأساسية مفيدة.

## استيراد الحزم
قبل الغوص في البرنامج التعليمي، دعنا نستورد الحزم الضرورية من Aspose.Slides لـ Java والتي سنستخدمها طوال البرنامج التعليمي.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## الخطوة 1: إعداد مشروعك
أولاً، أنشئ مشروع جافا جديدًا في بيئة التطوير المتكاملة لديك، وأضف Aspose.Slides for Java إلى تبعيات مشروعك. تأكد من تضمين ملف Aspose.Slides JAR المطلوب في مسار بناء مشروعك.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
```
## الخطوة 2: تهيئة كائن العرض التقديمي
ابدأ بإنشاء نموذج عرض تقديمي جديد. سيُستخدم هذا النموذج كمستند PowerPoint الخاص بك، حيث ستضيف الشرائح والمحتوى.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة
بعد ذلك، انتقل إلى الشريحة التي تريد إضافة النقاط متعددة المستويات إليها. في هذا المثال، سنعمل مع الشريحة الأولى (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة الشكل التلقائي مع إطار النص
أضف شكلاً تلقائياً إلى الشريحة حيث ستضع نصك مع نقاط متعددة المستويات.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## الخطوة 5: الوصول إلى إطار النص
قم بالوصول إلى إطار النص داخل الشكل التلقائي حيث ستضيف فقرات تحتوي على نقاط نقطية.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); // مسح الفقرات الافتراضية
```
## الخطوة 6: إضافة فقرات مع نقاط
أضف فقرات بمستويات مختلفة من النقاط. إليك كيفية إضافة نقاط متعددة المستويات:
```java
// المستوى الأول
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// المستوى الثاني
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// المستوى الثالث
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// المستوى الرابع
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## الخطوة 7: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي كملف PPTX في الدليل المطلوب.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية إنشاء نقاط متعددة المستويات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. باتباع هذه الخطوات، يمكنك تنظيم محتواك بفعالية باستخدام نقاط منظمة على مستويات مختلفة، مما يعزز وضوح عروضك التقديمية وجاذبيتها البصرية.
## الأسئلة الشائعة
### هل يمكنني تخصيص رموز الرصاصة بشكل أكبر؟
نعم، يمكنك تخصيص رموز النقاط عن طريق ضبط أحرف Unicode أو استخدام أشكال مختلفة.
### هل يدعم Aspose.Slides أنواع أخرى من النقاط؟
نعم، يدعم Aspose.Slides مجموعة متنوعة من أنواع النقاط بما في ذلك الرموز والأرقام والصور المخصصة.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يُنشئ Aspose.Slides عروض تقديمية متوافقة مع Microsoft PowerPoint 2007 والإصدارات الأحدث.
### هل يمكنني أتمتة عملية إنشاء الشرائح باستخدام Aspose.Slides؟
نعم، يوفر Aspose.Slides واجهات برمجة التطبيقات لأتمتة إنشاء عروض PowerPoint وتعديلها ومعالجتها.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم من مجتمع Aspose.Slides والخبراء في [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}