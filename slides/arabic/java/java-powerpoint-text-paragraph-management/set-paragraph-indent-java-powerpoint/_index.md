---
"description": "تعلّم كيفية ضبط المسافات البادئة للفقرات في شرائح PowerPoint برمجيًا باستخدام Aspose.Slides لجافا. حسّن تنسيق عرضك التقديمي بسهولة."
"linktitle": "تعيين مسافة بادئة للفقرة في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين مسافة بادئة للفقرة في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-paragraph-management/set-paragraph-indent-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين مسافة بادئة للفقرة في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية التعامل مع عروض PowerPoint التقديمية برمجيًا باستخدام Aspose.Slides لجافا. سنركز تحديدًا على ضبط المسافات البادئة للفقرات داخل الشرائح. يوفر Aspose.Slides لجافا مجموعة قوية من واجهات برمجة التطبيقات (APIs) التي تتيح للمطورين إنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها وإدارتها دون الاعتماد على أتمتة Microsoft Office.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من إعداد ما يلي:
- تم تثبيت Java Development Kit (JDK) على جهازك.
- تم تنزيل مكتبة Aspose.Slides لجافا. يمكنك الحصول عليها من [هنا](https://releases.aspose.com/slides/java/).
- فهم أساسي للغة البرمجة جافا.
## استيراد الحزم
أولاً، قم باستيراد الحزم اللازمة للوصول إلى وظيفة Aspose.Slides:
```java
import com.aspose.slides.*;
import java.io.File;
```
دعنا نتعمق في عملية تعيين المسافات البادئة للفقرات في شريحة PowerPoint خطوة بخطوة باستخدام Aspose.Slides لـ Java.
## الخطوة 1: إنشاء كائن عرض تقديمي
إنشاء مثيل `Presentation` الصف لبدء العمل على عرض تقديمي جديد في PowerPoint.
```java
// إنشاء فئة عرض تقديمي
Presentation pres = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة
استرجع الشريحة الأولى من العرض التقديمي. يمكنك تعديل الشرائح المختلفة حسب الفهرس حسب الحاجة.
```java
// احصل على الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل مستطيل
أضف شكل مستطيل إلى الشريحة، والذي سيحتوي على النص مع فقرات مسننة.
```java
// إضافة شكل مستطيل
IAutoShape rect = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 500, 150);
```
## الخطوة 4: إضافة نص إلى المستطيل
قم بإنشاء إطار نص داخل شكل المستطيل وتعيين محتوى النص.
```java
// إضافة إطار نصي إلى المستطيل
ITextFrame textFrame = rect.addTextFrame("This is first line \rThis is second line \rThis is third line");
```
## الخطوة 5: ضبط ملاءمة النص تلقائيًا
قم بتعيين ملاءمة النص تلقائيًا لتتناسب مع حدود الشكل.
```java
// ضبط النص ليناسب الشكل
textFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## الخطوة 6: ضبط المسافات البادئة للفقرات
قم بالوصول إلى كل فقرة داخل إطار النص وتعيين المسافة البادئة الخاصة بها.
```java
// احصل على الفقرة الأولى في إطار النص واضبط المسافة البادئة الخاصة بها
IParagraph para1 = textFrame.getParagraphs().get_Item(0);
para1.getParagraphFormat().setIndent(30);
// احصل على الفقرة الثانية في إطار النص واضبط المسافة البادئة الخاصة بها
IParagraph para2 = textFrame.getParagraphs().get_Item(1);
para2.getParagraphFormat().setIndent(40);
// احصل على الفقرة الثالثة في إطار النص واضبط المسافة البادئة الخاصة بها
IParagraph para3 = textFrame.getParagraphs().get_Item(2);
para3.getParagraphFormat().setIndent(50);
```
## الخطوة 7: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدّل على القرص.
```java
// كتابة العرض التقديمي على القرص
String dataDir = "Your_Document_Directory_Path/";
pres.save(dataDir + "IndentedPresentation.pptx", SaveFormat.Pptx);
```
## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة ضبط المسافات البادئة للفقرات في شريحة PowerPoint باستخدام Aspose.Slides لجافا. تتيح لك هذه الميزة التحكم الدقيق في تنسيق وعرض النص داخل الشرائح برمجيًا.

## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java عبارة عن مكتبة قوية للعمل مع عروض PowerPoint برمجيًا.
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
يمكنك العثور على الوثائق [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني تنزيل Aspose.Slides لـ Java؟
يمكنك تنزيله من [هنا](https://releases.aspose.com/slides/java/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم من منتدى المجتمع [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}