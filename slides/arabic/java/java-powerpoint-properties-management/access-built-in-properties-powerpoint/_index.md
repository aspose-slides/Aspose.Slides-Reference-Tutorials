---
title: الوصول إلى الخصائص المضمنة في PowerPoint
linktitle: الوصول إلى الخصائص المضمنة في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية الوصول إلى الخصائص المضمنة في PowerPoint باستخدام Aspose.Slides لـ Java. يرشدك هذا البرنامج التعليمي إلى كيفية استرداد المؤلف وتاريخ الإنشاء والمزيد.
weight: 10
url: /ar/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية الوصول إلى الخصائص المضمنة في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. Aspose.Slides هي مكتبة قوية تسمح لمطوري Java بالعمل مع عروض PowerPoint التقديمية برمجياً، مما يتيح مهام مثل القراءة وتعديل الخصائص بسلاسة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك. يمكنك تنزيله من[هنا](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من[هذا الرابط](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة لمشروع Java الخاص بك. أضف عبارة الاستيراد التالية في بداية ملف Java الخاص بك:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## الخطوة 1: إعداد كائن العرض التقديمي
ابدأ بإعداد كائن العرض التقديمي ليمثل عرض PowerPoint التقديمي الذي تريد العمل معه. وإليك كيف يمكنك القيام بذلك:
```java
// المسار إلى الدليل الذي يحتوي على ملف العرض التقديمي
String dataDir = "path_to_your_presentation_directory/";
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## الخطوة 2: الوصول إلى خصائص المستند
بعد إعداد كائن العرض التقديمي، يمكنك الوصول إلى الخصائص المضمنة للعرض التقديمي باستخدام واجهة IDocumentProperties. وإليك كيفية استرداد الخصائص المختلفة:
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
### الكلمات الدالة
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### التعديل الأخير من قبل
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### مشرف
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### تاريخ معدل
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### تنسيق العرض
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### تاريخ الطباعة الأخير
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### المشتركة بين المنتجين
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
في هذا البرنامج التعليمي، تعلمنا كيفية الوصول إلى الخصائص المضمنة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. باتباع الخطوات الموضحة أعلاه، يمكنك بسهولة استرداد خصائص متنوعة مثل المؤلف وتاريخ الإنشاء والعنوان برمجيًا.
## الأسئلة الشائعة
### هل يمكنني تعديل هذه الخصائص المضمنة باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تعديل هذه الخصائص باستخدام Aspose.Slides. ما عليك سوى استخدام أساليب الضبط المناسبة التي توفرها واجهة IDocumentProperties.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
يدعم Aspose.Slides مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق عبر الأنظمة الأساسية المختلفة.
### هل يمكنني استرداد الخصائص المخصصة أيضًا؟
نعم، إلى جانب الخصائص المضمنة، يمكنك أيضًا استرداد الخصائص المخصصة وتعديلها باستخدام Aspose.Slides لـ Java.
### هل يقدم Aspose.Slides الوثائق والدعم؟
 نعم، يمكنك العثور على وثائق شاملة والوصول إلى منتديات الدعم على الموقع[موقع أسبوز](https://reference.aspose.com/slides/java/).
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
