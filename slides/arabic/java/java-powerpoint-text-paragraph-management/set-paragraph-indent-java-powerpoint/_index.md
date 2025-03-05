---
title: تعيين المسافة البادئة للفقرة في Java PowerPoint
linktitle: تعيين المسافة البادئة للفقرة في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين المسافات البادئة للفقرة في شرائح PowerPoint برمجياً باستخدام Aspose.Slides لـ Java. قم بتحسين تنسيق العرض التقديمي الخاص بك دون عناء.
type: docs
weight: 16
url: /ar/java/java-powerpoint-text-paragraph-management/set-paragraph-indent-java-powerpoint/
---
## مقدمة
في هذا البرنامج التعليمي، ستتعلم كيفية التعامل مع عروض PowerPoint التقديمية برمجياً باستخدام Aspose.Slides لـ Java. على وجه التحديد، سوف نركز على تعيين المسافات البادئة للفقرة داخل الشرائح. يوفر Aspose.Slides for Java مجموعة قوية من واجهات برمجة التطبيقات التي تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها وتحويلها وإدارتها دون الاعتماد على Microsoft Office Automation.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك الإعداد التالي:
- تم تثبيت Java Development Kit (JDK) على جهازك.
-  تم تنزيل Aspose.Slides لمكتبة Java. يمكنك الحصول عليه من[هنا](https://releases.aspose.com/slides/java/).
- الفهم الأساسي للغة البرمجة جافا.
## حزم الاستيراد
أولاً، قم باستيراد الحزم اللازمة للوصول إلى وظيفة Aspose.Slides:
```java
import com.aspose.slides.*;
import java.io.File;
```
دعنا نتعمق في العملية خطوة بخطوة لإعداد المسافات البادئة للفقرة في شريحة PowerPoint باستخدام Aspose.Slides for Java.
## الخطوة 1: إنشاء كائن العرض التقديمي
 إنشاء مثيل`Presentation` الفصل الدراسي لبدء العمل باستخدام عرض PowerPoint التقديمي الجديد.
```java
// إنشاء فئة العرض التقديمي
Presentation pres = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة
استرداد الشريحة الأولى من العرض التقديمي. يمكنك التعامل مع شرائح مختلفة حسب الفهرس حسب الحاجة.
```java
// احصل على الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل مستطيل
أضف شكلًا مستطيلًا إلى الشريحة، والذي سيحتوي على النص مع فقرات ذات مسافة بادئة.
```java
// إضافة شكل مستطيل
IAutoShape rect = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 500, 150);
```
## الخطوة 4: إضافة نص إلى المستطيل
قم بإنشاء إطار نص داخل الشكل المستطيل وقم بتعيين محتوى النص.
```java
// أضف TextFrame إلى المستطيل
ITextFrame textFrame = rect.addTextFrame("This is first line \rThis is second line \rThis is third line");
```
## الخطوة 5: ضبط الاحتواء التلقائي للنص
قم بتعيين الاحتواء التلقائي للنص ليتناسب مع حدود الشكل.
```java
// اضبط النص ليناسب الشكل
textFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## الخطوة 6: ضبط المسافات البادئة للفقرة
قم بالوصول إلى كل فقرة داخل إطار النص وقم بتعيين المسافة البادئة الخاصة بها.
```java
// احصل على الفقرة الأولى في TextFrame وقم بتعيين المسافة البادئة الخاصة بها
IParagraph para1 = textFrame.getParagraphs().get_Item(0);
para1.getParagraphFormat().setIndent(30);
// احصل على الفقرة الثانية في TextFrame وقم بتعيين المسافة البادئة الخاصة بها
IParagraph para2 = textFrame.getParagraphs().get_Item(1);
para2.getParagraphFormat().setIndent(40);
//احصل على الفقرة الثالثة في TextFrame وقم بتعيين المسافة البادئة الخاصة بها
IParagraph para3 = textFrame.getParagraphs().get_Item(2);
para3.getParagraphFormat().setIndent(50);
```
## الخطوة 7: احفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي المعدل على القرص.
```java
// كتابة العرض التقديمي على القرص
String dataDir = "Your_Document_Directory_Path/";
pres.save(dataDir + "IndentedPresentation.pptx", SaveFormat.Pptx);
```
## خاتمة
باتباع هذه الخطوات، يمكنك بسهولة تعيين المسافات البادئة للفقرة في شريحة PowerPoint باستخدام Aspose.Slides for Java. تسمح هذه الإمكانية بالتحكم الدقيق في تنسيق النص وعرضه داخل شرائحك برمجيًا.

## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية للعمل مع عروض PowerPoint التقديمية برمجياً.
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 يمكنك العثور على الوثائق[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني تنزيل Aspose.Slides لجافا؟
 يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على الدعم من منتدى المجتمع[هنا](https://forum.aspose.com/c/slides/11).