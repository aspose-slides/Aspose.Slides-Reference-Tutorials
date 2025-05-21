---
"description": "تعرّف على كيفية إضافة أعمدة في إطارات النصوص باستخدام Aspose.Slides لجافا لتحسين عروض PowerPoint التقديمية. يُبسّط دليلنا خطوة بخطوة العملية."
"linktitle": "إضافة أعمدة في إطار النص باستخدام Aspose.Slides لـ Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة أعمدة في إطار النص باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة أعمدة في إطار النص باستخدام Aspose.Slides لـ Java

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية التعامل مع إطارات النصوص لإضافة أعمدة باستخدام Aspose.Slides لجافا. Aspose.Slides هي مكتبة فعّالة تُمكّن مطوري جافا من إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها برمجيًا. تُحسّن إضافة الأعمدة إلى إطارات النصوص من المظهر المرئي وتنظيم النص داخل الشرائح، مما يجعل العروض التقديمية أكثر جاذبية وأسهل قراءة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على جهازك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- فهم أساسيات برمجة جافا.
- بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA.
- المعرفة بإدارة تبعيات المشروع باستخدام أدوات مثل Maven أو Gradle.

## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة من Aspose.Slides للعمل مع العروض التقديمية وإطارات النص:
```java
import com.aspose.slides.*;
```
## الخطوة 1: تهيئة العرض التقديمي
ابدأ بإنشاء كائن عرض تقديمي جديد في PowerPoint:
```java
String dataDir = "Your Document Directory";
String outPptxFileName = dataDir + "ColumnsTest.pptx";
// إنشاء كائن عرض تقديمي جديد
Presentation pres = new Presentation();
```
## الخطوة 2: إضافة شكل تلقائي مع إطار نص
أضف شكلًا تلقائيًا (على سبيل المثال، مستطيلًا) إلى الشريحة الأولى وقم بالوصول إلى إطار النص الخاص به:
```java
// إضافة شكل تلقائي إلى الشريحة الأولى
IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
// الوصول إلى إطار النص الخاص بالشكل التلقائي
TextFrameFormat format = (TextFrameFormat) shape1.getTextFrame().getTextFrameFormat();
```
## الخطوة 3: تعيين عدد الأعمدة والنص
تعيين عدد الأعمدة ومحتوى النص داخل إطار النص:
```java
// تعيين عدد الأعمدة
format.setColumnCount(2);
// ضبط محتوى النص
shape1.getTextFrame().setText("All these columns are limited to be within a single text container -- " +
    "you can add or delete text and the new or remaining text automatically adjusts " +
    "itself to flow within the container. You cannot have text flow from one container " +
    "to other though -- we told you PowerPoint's column options for text are limited!");
```
## الخطوة 4: حفظ العرض التقديمي
حفظ العرض التقديمي بعد إجراء التغييرات:
```java
// حفظ العرض التقديمي
pres.save(outPptxFileName, SaveFormat.Pptx);
```
## الخطوة 5: ضبط تباعد الأعمدة (اختياري)
إذا لزم الأمر، قم بتعديل المسافة بين الأعمدة:
```java
// تعيين تباعد الأعمدة
format.setColumnSpacing(20);
// حفظ العرض التقديمي مع تباعد الأعمدة المحدث
pres.save(outPptxFileName, SaveFormat.Pptx);
// يمكنك تغيير عدد الأعمدة والتباعد مرة أخرى إذا لزم الأمر
format.setColumnCount(3);
format.setColumnSpacing(15);
pres.save(outPptxFileName, SaveFormat.Pptx);
```

## خاتمة
في هذا البرنامج التعليمي، شرحنا كيفية استخدام Aspose.Slides لجافا لإضافة أعمدة داخل إطارات النص في عروض PowerPoint التقديمية برمجيًا. تُحسّن هذه الميزة العرض المرئي للمحتوى النصي، مما يُحسّن قابلية القراءة وهيكلية الشرائح.
## الأسئلة الشائعة
### هل يمكنني إضافة أكثر من ثلاثة أعمدة إلى إطار النص؟
نعم يمكنك التعديل `setColumnCount` طريقة لإضافة المزيد من الأعمدة حسب الحاجة.
### هل يدعم Aspose.Slides تعديل عرض العمود بشكل فردي؟
لا، يقوم Aspose.Slides بتعيين عرض متساوٍ للأعمدة داخل إطار النص تلقائيًا.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على مزيد من الوثائق حول Aspose.Slides لـ Java؟
الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides لـ Java؟
يمكنك طلب الدعم من المجتمع [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}