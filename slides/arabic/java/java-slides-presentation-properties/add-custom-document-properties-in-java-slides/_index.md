---
title: أضف خصائص المستند المخصصة في شرائح Java
linktitle: أضف خصائص المستند المخصصة في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحسين عروض PowerPoint التقديمية باستخدام خصائص المستند المخصصة في Java Slides. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية باستخدام Aspose.Slides لـ Java.
weight: 13
url: /ar/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لإضافة خصائص مستند مخصصة في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة خصائص مستند مخصصة إلى عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. تسمح لك خصائص المستند المخصصة بتخزين معلومات إضافية حول العرض التقديمي كمرجع أو تصنيف.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك.

## الخطوة 1: استيراد الحزم المطلوبة

```java
import com.aspose.slides.*;
```

## الخطوة 2: إنشاء عرض تقديمي جديد

أولاً، تحتاج إلى إنشاء كائن عرض تقديمي جديد. يمكنك القيام بذلك على النحو التالي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 3: الحصول على خصائص المستند

بعد ذلك، ستقوم باسترداد خصائص مستند العرض التقديمي. تتضمن هذه الخصائص خصائص مضمنة مثل العنوان والمؤلف والخصائص المخصصة التي يمكنك إضافتها.

```java
// الحصول على خصائص الوثيقة
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## الخطوة 4: إضافة خصائص مخصصة

الآن، دعونا نضيف خصائص مخصصة إلى العرض التقديمي. تتكون الخصائص المخصصة من اسم وقيمة. يمكنك استخدامها لتخزين أي معلومات تريدها.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## الخطوة 5: الحصول على اسم الخاصية في فهرس معين

يمكنك أيضًا استرداد اسم الخاصية المخصصة في فهرس محدد. يمكن أن يكون هذا مفيدًا إذا كنت بحاجة إلى العمل مع خصائص معينة.

```java
// الحصول على اسم الخاصية في فهرس معين
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## الخطوة 6: إزالة الخاصية المحددة

إذا كنت تريد إزالة خاصية مخصصة، فيمكنك القيام بذلك عن طريق تحديد اسمها. هنا، نقوم بإزالة الخاصية التي حصلنا عليها في الخطوة 5.

```java
// إزالة الخاصية المحددة
documentProperties.removeCustomProperty(getPropertyName);
```

## الخطوة 7: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي بالخصائص المخصصة المضافة والمحذوفة في ملف.

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لإضافة خصائص المستند المخصصة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// الحصول على خصائص الوثيقة
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// إضافة خصائص مخصصة
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// الحصول على اسم الخاصية في فهرس معين
String getPropertyName = documentProperties.getCustomPropertyName(2);
// إزالة الخاصية المحددة
documentProperties.removeCustomProperty(getPropertyName);
// حفظ العرض التقديمي
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## خاتمة

لقد تعلمت كيفية إضافة خصائص مستند مخصصة إلى عرض تقديمي لـ PowerPoint في Java باستخدام Aspose.Slides. يمكن أن تكون الخصائص المخصصة ذات قيمة لتخزين المعلومات الإضافية المتعلقة بالعروض التقديمية الخاصة بك. يمكنك توسيع هذه المعرفة لتشمل المزيد من الخصائص المخصصة حسب الحاجة لحالة الاستخدام المحددة الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني استرداد قيمة خاصية مخصصة؟

 لاسترداد قيمة خاصية مخصصة، يمكنك استخدام`get_Item` الطريقة على`documentProperties` هدف. على سبيل المثال:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### هل يمكنني إضافة خصائص مخصصة لأنواع البيانات المختلفة؟

نعم، يمكنك إضافة خصائص مخصصة لأنواع البيانات المختلفة، بما في ذلك الأرقام والسلاسل والتواريخ والمزيد، كما هو موضح في المثال. يتعامل Aspose.Slides for Java مع أنواع البيانات المختلفة بسلاسة.

### هل هناك حد لعدد الخصائص المخصصة التي يمكنني إضافتها؟

لا يوجد حد صارم لعدد الخصائص المخصصة التي يمكنك إضافتها. ومع ذلك، ضع في اعتبارك أن إضافة عدد كبير جدًا من الخصائص قد يؤثر على أداء وحجم ملف العرض التقديمي الخاص بك.

### كيف يمكنني سرد كافة الخصائص المخصصة في العرض التقديمي؟

يمكنك تكرار كافة الخصائص المخصصة لإدراجها. فيما يلي مثال لكيفية القيام بذلك:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

سيعرض هذا الرمز أسماء وقيم جميع الخصائص المخصصة في العرض التقديمي.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
