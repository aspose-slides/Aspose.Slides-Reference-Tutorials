---
"description": "تعلّم كيفية استنساخ الأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. بسّط سير عملك مع هذا البرنامج التعليمي السهل."
"linktitle": "استنساخ الأشكال في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "استنساخ الأشكال في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# استنساخ الأشكال في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية استنساخ الأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. يتيح لك استنساخ الأشكال تكرار الأشكال الموجودة في العرض التقديمي، وهو أمر مفيد بشكل خاص لإنشاء تخطيطات متسقة أو عناصر متكررة عبر الشرائح.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت مجموعة تطوير جافا على نظامك. يمكنك تنزيل أحدث إصدار وتثبيته من [موقع إلكتروني](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. مكتبة Aspose.Slides لجافا: نزّل مكتبة Aspose.Slides لجافا وأضِفها إلى مشروع جافا الخاص بك. تجد رابط التنزيل. [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
للبدء، ستحتاج إلى استيراد الحزم اللازمة إلى مشروع جافا. توفر هذه الحزم الوظائف اللازمة للعمل مع عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا.
```java
import com.aspose.slides.*;

```
## الخطوة 1: تحميل العرض التقديمي
أولاً، عليك تحميل عرض PowerPoint التقديمي الذي يحتوي على الأشكال التي تريد استنساخها. استخدم `Presentation` الفئة لتحميل العرض التقديمي المصدر.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## الخطوة 2: استنساخ الأشكال
بعد ذلك، ستستنسخ الأشكال من العرض التقديمي المصدر وتضيفها إلى شريحة جديدة في العرض التقديمي نفسه. يتضمن ذلك الوصول إلى الأشكال المصدر، وإنشاء شريحة جديدة، ثم إضافة الأشكال المستنسخة إلى الشريحة الجديدة.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## الخطوة 3: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل بالأشكال المستنسخة في ملف جديد.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## خاتمة
يُعدّ استنساخ الأشكال في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java عمليةً سهلةً تُسهّل سير عمل إنشاء العرض التقديمي. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة نسخ الأشكال الموجودة وتخصيصها حسب الحاجة.

## الأسئلة الشائعة
### هل يمكنني استنساخ الأشكال عبر شرائح مختلفة؟
نعم، يمكنك استنساخ الأشكال من أي شريحة في العرض التقديمي وإضافتها إلى شريحة أخرى باستخدام Aspose.Slides for Java.
### هل هناك أي قيود على استنساخ الأشكال؟
على الرغم من أن Aspose.Slides for Java يوفر إمكانيات استنساخ قوية، إلا أنه قد لا يتم تكرار الأشكال أو الرسوم المتحركة المعقدة بشكل مثالي.
### هل يمكنني تعديل الأشكال المستنسخة بعد إضافتها إلى الشريحة؟
بالتأكيد، بمجرد استنساخ الأشكال وإضافتها إلى شريحة، يمكنك تعديل خصائصها وأسلوبها ومحتواها حسب الحاجة.
### هل يدعم Aspose.Slides for Java استنساخ عناصر أخرى بالإضافة إلى الأشكال؟
نعم، يمكنك استنساخ الشرائح والنصوص والصور والعناصر الأخرى داخل عرض تقديمي في PowerPoint باستخدام Aspose.Slides for Java.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides for Java من [موقع إلكتروني](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}