---
"description": "تعرّف على كيفية تحسين عروض PowerPoint التقديمية باستخدام خصائص المستندات المخصصة في Java Slides. دليل خطوة بخطوة مع أمثلة برمجية باستخدام Aspose.Slides لـ Java."
"linktitle": "إضافة خصائص مستند مخصصة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة خصائص مستند مخصصة في شرائح Java"
"url": "/ar/java/presentation-properties/add-custom-document-properties-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خصائص مستند مخصصة في شرائح Java


## مقدمة حول إضافة خصائص مستند مخصصة في شرائح Java

في هذا البرنامج التعليمي، سنشرح لك عملية إضافة خصائص مستند مخصصة إلى عرض تقديمي في PowerPoint باستخدام Aspose.Slides لجافا. تتيح لك خصائص المستند المخصصة تخزين معلومات إضافية حول العرض التقديمي للرجوع إليها أو تصنيفها.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك.

## الخطوة 1: استيراد الحزم المطلوبة

```java
import com.aspose.slides.*;
```

## الخطوة 2: إنشاء عرض تقديمي جديد

أولاً، عليك إنشاء كائن عرض تقديمي جديد. يمكنك القيام بذلك كما يلي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 3: الحصول على خصائص المستند

بعد ذلك، ستسترد خصائص مستند العرض التقديمي. تتضمن هذه الخصائص خصائص مدمجة مثل العنوان والمؤلف وخصائص مخصصة يمكنك إضافتها.

```java
// الحصول على خصائص المستند
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## الخطوة 4: إضافة خصائص مخصصة

الآن، لنُضِف خصائص مُخصَّصة إلى العرض التقديمي. تتكوَّن هذه الخصائص من اسم وقيمة. يُمكنك استخدامها لتخزين أي معلومات تُريدها.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## الخطوة 5: الحصول على اسم خاصية في فهرس معين

يمكنك أيضًا استرجاع اسم خاصية مخصصة عند فهرس محدد. قد يكون هذا مفيدًا إذا كنت بحاجة إلى العمل مع خصائص محددة.

```java
// الحصول على اسم الخاصية في فهرس معين
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## الخطوة 6: إزالة خاصية محددة

إذا كنت ترغب في إزالة خاصية مخصصة، يمكنك ذلك بتحديد اسمها. هنا، نقوم بإزالة الخاصية التي حصلنا عليها في الخطوة 5.

```java
// إزالة الخاصية المحددة
documentProperties.removeCustomProperty(getPropertyName);
```

## الخطوة 7: حفظ العرض التقديمي

أخيرًا، احفظ العرض التقديمي مع الخصائص المخصصة المضافة والمحذوفة إلى ملف.

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لإضافة خصائص مستند مخصصة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// الحصول على خصائص المستند
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// إضافة خصائص مخصصة
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// الحصول على اسم الخاصية في مؤشر معين
String getPropertyName = documentProperties.getCustomPropertyName(2);
// إزالة الخاصية المحددة
documentProperties.removeCustomProperty(getPropertyName);
// حفظ العرض التقديمي
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## خاتمة

لقد تعلمتَ كيفية إضافة خصائص مستند مخصصة إلى عرض تقديمي في PowerPoint بلغة Java باستخدام Aspose.Slides. تُعدّ الخصائص المخصصة قيّمة لتخزين معلومات إضافية متعلقة بعروضك التقديمية. يمكنك توسيع هذه المعرفة لتشمل المزيد من الخصائص المخصصة حسب الحاجة لحالة استخدامك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني استرداد قيمة الخاصية المخصصة؟

لاسترداد قيمة خاصية مخصصة، يمكنك استخدام `get_Item` الطريقة على `documentProperties` كائن. على سبيل المثال:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### هل يمكنني إضافة خصائص مخصصة لأنواع البيانات المختلفة؟

نعم، يمكنك إضافة خصائص مخصصة لأنواع بيانات مختلفة، بما في ذلك الأرقام والسلاسل والتواريخ وغيرها، كما هو موضح في المثال. يتعامل Aspose.Slides for Java مع أنواع البيانات المختلفة بسلاسة.

### هل هناك حد لعدد الخصائص المخصصة التي يمكنني إضافتها؟

لا يوجد حد أقصى لعدد الخصائص المخصصة التي يمكنك إضافتها. مع ذلك، تذكّر أن إضافة عدد كبير منها قد يؤثر على أداء ملف العرض التقديمي وحجمه.

### كيف يمكنني إدراج جميع الخصائص المخصصة في العرض التقديمي؟

يمكنك تكرار جميع الخصائص المخصصة لعرضها. إليك مثال لكيفية القيام بذلك:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

سيعرض هذا الكود أسماء وقيم جميع الخصائص المخصصة في العرض التقديمي.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}