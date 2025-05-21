---
"description": "تعرّف على كيفية الوصول إلى الخصائص المضمنة في PowerPoint باستخدام Aspose.Slides لجافا. يرشدك هذا البرنامج التعليمي إلى كيفية استرجاع اسم المؤلف وتاريخ الإنشاء والمزيد."
"linktitle": "الوصول إلى الخصائص المضمنة في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الوصول إلى الخصائص المضمنة في PowerPoint"
"url": "/ar/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الوصول إلى الخصائص المضمنة في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية الوصول إلى الخصائص المضمنة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. Aspose.Slides هي مكتبة فعّالة تُمكّن مطوري جافا من العمل مع عروض PowerPoint التقديمية برمجيًا، مما يُمكّنهم من قراءة الخصائص وتعديلها بسلاسة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من [هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [هذا الرابط](https://releases.aspose.com/slides/java/).

## استيراد الحزم
أولاً، عليك استيراد الحزم اللازمة لمشروع جافا. أضف عبارة الاستيراد التالية في بداية ملف جافا:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## الخطوة 1: إعداد كائن العرض التقديمي
ابدأ بإعداد كائن العرض التقديمي ليمثل عرض PowerPoint الذي ترغب بالعمل عليه. إليك كيفية القيام بذلك:
```java
// المسار إلى الدليل الذي يحتوي على ملف العرض التقديمي
String dataDir = "path_to_your_presentation_directory/";
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## الخطوة 2: الوصول إلى خصائص المستند
بعد إعداد كائن العرض التقديمي، يمكنك الوصول إلى خصائصه المضمنة باستخدام واجهة IDocumentProperties. إليك كيفية استرداد مختلف الخصائص:
### فئة
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### الحالة الحالية
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### تاريخ الإنشاء
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### مؤلف
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### وصف
```java
System.out.println("Description : " + documentProperties.getComments());
```
### الكلمات الرئيسية
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### تم التعديل الأخير بواسطة
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### مشرف
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### تاريخ التعديل
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### تنسيق العرض التقديمي
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### تاريخ آخر طباعة
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### مشتركة بين المنتجين
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### موضوع
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### عنوان
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية الوصول إلى الخصائص المضمنة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. باتباع الخطوات الموضحة أعلاه، يمكنك بسهولة استرجاع خصائص متنوعة، مثل المؤلف وتاريخ الإنشاء والعنوان، برمجيًا.
## الأسئلة الشائعة
### هل يمكنني تعديل هذه الخصائص المضمنة باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تعديل هذه الخصائص باستخدام Aspose.Slides. ما عليك سوى استخدام طرق الضبط المناسبة التي توفرها واجهة IDocumentProperties.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
يدعم Aspose.Slides مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق عبر منصات مختلفة.
### هل يمكنني استرجاع الخصائص المخصصة أيضًا؟
نعم، بالإضافة إلى الخصائص المضمنة، يمكنك أيضًا استرداد الخصائص المخصصة وتعديلها باستخدام Aspose.Slides لـ Java.
### هل يوفر Aspose.Slides التوثيق والدعم؟
نعم، يمكنك العثور على وثائق شاملة والوصول إلى منتديات الدعم على [موقع Aspose](https://reference.aspose.com/slides/java/).
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}