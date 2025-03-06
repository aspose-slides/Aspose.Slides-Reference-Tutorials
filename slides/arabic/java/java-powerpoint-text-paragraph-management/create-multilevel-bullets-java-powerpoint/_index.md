---
title: إنشاء تعداد نقطي متعدد المستويات في Java PowerPoint
linktitle: إنشاء تعداد نقطي متعدد المستويات في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء تعداد نقطي متعدد المستويات في PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية والأسئلة الشائعة.
weight: 14
url: /ar/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية إنشاء رموز نقطية متعددة المستويات في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. تعد إضافة نقاط نقطية مطلبًا شائعًا لإنشاء محتوى منظم وجذاب بصريًا في العروض التقديمية. سنخوض العملية خطوة بخطوة، مما يضمن أنه بحلول نهاية هذا الدليل، ستكون جاهزًا لتحسين عروضك التقديمية بنقاط منظمة على مستويات متعددة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:
- بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من[هنا](https://releases.aspose.com/slides/java/).
- IDE: استخدم بيئة التطوير المتكاملة Java (IDE) المفضلة لديك مثل IntelliJ IDEA أو Eclipse أو غيرها.
- المعرفة الأساسية: الإلمام ببرمجة Java ومفاهيم PowerPoint الأساسية سيكون مفيدًا.

## حزم الاستيراد
قبل الغوص في البرنامج التعليمي، فلنستورد الحزم الضرورية من Aspose.Slides for Java والتي سنستخدمها خلال البرنامج التعليمي.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## الخطوة 1: قم بإعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف Aspose.Slides for Java إلى تبعيات مشروعك. تأكد من تضمين ملف Aspose.Slides JAR الضروري في مسار بناء مشروعك.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
```
## الخطوة 2: تهيئة كائن العرض التقديمي
ابدأ بإنشاء مثيل عرض تقديمي جديد. سيكون هذا بمثابة مستند PowerPoint الخاص بك حيث ستضيف الشرائح والمحتوى.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة
بعد ذلك، قم بالوصول إلى الشريحة التي تريد إضافة الرموز النقطية متعددة المستويات إليها. في هذا المثال، سنعمل مع الشريحة الأولى (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل تلقائي بإطار نص
أضف شكلاً تلقائيًا إلى الشريحة حيث ستضع النص الخاص بك باستخدام تعداد نقطي متعدد المستويات.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## الخطوة 5: الوصول إلى إطار النص
قم بالوصول إلى إطار النص داخل الشكل التلقائي حيث ستضيف فقرات ذات نقاط نقطية.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //مسح الفقرات الافتراضية
```
## الخطوة 6: إضافة فقرات ذات تعداد نقطي
أضف فقرات بمستويات مختلفة من التعداد النقطي. إليك كيفية إضافة تعداد نقطي متعدد المستويات:
```java
// مستوى اول
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
## الخطوة 7: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي كملف PPTX في الدليل المطلوب.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، تناولنا كيفية إنشاء رموز نقطية متعددة المستويات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. باتباع هذه الخطوات، يمكنك تنظيم المحتوى الخاص بك بشكل فعال من خلال نقاط نقطية منظمة على مستويات مختلفة، مما يعزز الوضوح والجاذبية البصرية لعروضك التقديمية.
## الأسئلة الشائعة
### هل يمكنني تخصيص الرموز النقطية بشكل أكبر؟
نعم، يمكنك تخصيص الرموز النقطية عن طريق ضبط أحرف Unicode أو استخدام أشكال مختلفة.
### هل يدعم Aspose.Slides أنواع التعداد النقطي الأخرى؟
نعم، يدعم Aspose.Slides مجموعة متنوعة من أنواع التعداد النقطي بما في ذلك الرموز والأرقام والصور المخصصة.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يقوم Aspose.Slides بإنشاء عروض تقديمية متوافقة مع Microsoft PowerPoint 2007 والإصدارات الأحدث.
### هل يمكنني أتمتة إنشاء الشرائح باستخدام Aspose.Slides؟
نعم، يوفر Aspose.Slides واجهات برمجة التطبيقات لأتمتة إنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من مجتمع Aspose.Slides والخبراء على[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
