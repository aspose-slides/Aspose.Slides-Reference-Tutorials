---
"description": "حسّن عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تعلّم كيفية ضبط الخصائص، وتعطيل التشفير، وإضافة حماية كلمة المرور، وحفظ العروض بسهولة."
"linktitle": "حفظ الخصائص في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "حفظ الخصائص في شرائح Java"
"url": "/ar/java/saving-options/save-properties-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# حفظ الخصائص في شرائح Java


## مقدمة لحفظ الخصائص في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية حفظ خصائص عرض تقديمي في PowerPoint باستخدام Aspose.Slides لجافا. ستتعلم كيفية ضبط خصائص المستند، وتعطيل تشفيرها، وتعيين كلمة مرور لحماية عرضك التقديمي، وحفظه في ملف. سنقدم لك تعليمات خطوة بخطوة وأمثلة على الكود المصدري.

## المتطلبات الأساسية

قبل البدء، تأكد من دمج مكتبة Aspose.Slides لجافا في مشروع جافا. يمكنك تنزيل المكتبة من موقع Aspose الإلكتروني. [هنا](https://downloads.aspose.com/slides/java).

## الخطوة 1: استيراد المكتبات المطلوبة

للبدء، قم باستيراد الفئات والمكتبات الضرورية:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## الخطوة 2: إنشاء كائن عرض تقديمي

أنشئ كائن عرض تقديمي لتمثيل عرض PowerPoint التقديمي. يمكنك إنشاء عرض تقديمي جديد أو تحميل عرض تقديمي موجود. في هذا المثال، سننشئ عرضًا تقديميًا جديدًا.

```java
// المسار إلى الدليل الذي تريد حفظ العرض التقديمي فيه
String dataDir = "Your Document Directory";

// إنشاء كائن عرض تقديمي
Presentation presentation = new Presentation();
```

## الخطوة 3: تعيين خصائص المستند

يمكنك تعيين خصائص متنوعة للمستند، مثل العنوان والمؤلف والكلمات المفتاحية وغيرها. سنحدد هنا بعض الخصائص الشائعة:

```java
// تعيين عنوان العرض التقديمي
presentation.getDocumentProperties().setTitle("My Presentation");

// تعيين مؤلف العرض التقديمي
presentation.getDocumentProperties().setAuthor("John Doe");

// تعيين الكلمات الرئيسية للعرض التقديمي
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## الخطوة 4: تعطيل التشفير لخصائص المستند

افتراضيًا، يُشفّر Aspose.Slides خصائص المستند. لتعطيل تشفير خصائص المستند، استخدم الكود التالي:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## الخطوة 5: تعيين كلمة مرور لحماية العرض التقديمي

يمكنك حماية عرضك التقديمي بكلمة مرور لتقييد الوصول. استخدم `encrypt` طريقة تعيين كلمة المرور:

```java
// تعيين كلمة مرور لحماية العرض التقديمي
presentation.getProtectionManager().encrypt("your_password");
```

يستبدل `"your_password"` مع كلمة المرور المطلوبة.

## الخطوة 6: حفظ العرض التقديمي

أخيرًا، احفظ العرض التقديمي في ملف. في هذا المثال، سنحفظه كملف PPTX:

```java
// حفظ العرض التقديمي في ملف
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

يستبدل `"Password_Protected_Presentation_out.pptx"` مع اسم الملف والمسار المطلوب.

## كود المصدر الكامل لخصائص الحفظ في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء كائن عرض تقديمي يمثل ملف PPT
Presentation presentation = new Presentation();
try
{
	//....قم ببعض العمل هنا.....
	// إعداد الوصول إلى خصائص المستند في وضع الحماية بكلمة مرور
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// تعيين كلمة المرور
	presentation.getProtectionManager().encrypt("pass");
	// احفظ عرضك التقديمي في ملف
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية حفظ خصائص المستند في عرض تقديمي لبرنامج PowerPoint باستخدام Aspose.Slides لجافا. يمكنك تعيين خصائص متنوعة، وتعطيل تشفير خصائص المستند، وتعيين كلمة مرور للحماية، وحفظ العرض التقديمي بالتنسيق الذي تريده.

## الأسئلة الشائعة

### كيف يمكنني تعيين خصائص المستند في Aspose.Slides لـ Java؟

لتعيين خصائص المستند في Aspose.Slides لـ Java، يمكنك استخدام `DocumentProperties` الصف. إليك مثال لكيفية تعيين خصائص مثل العنوان والمؤلف والكلمات الرئيسية:

```java
// تعيين عنوان العرض التقديمي
presentation.getDocumentProperties().setTitle("My Presentation");

// تعيين مؤلف العرض التقديمي
presentation.getDocumentProperties().setAuthor("John Doe");

// تعيين الكلمات الرئيسية للعرض التقديمي
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### ما هو الغرض من تعطيل التشفير لخصائص المستند؟

يتيح لك تعطيل تشفير خصائص المستند تخزين بياناته الوصفية دون تشفير. قد يكون هذا مفيدًا عندما تريد أن تكون خصائص المستند (مثل العنوان والمؤلف، إلخ) مرئية وسهلة الوصول دون الحاجة إلى إدخال كلمة مرور.

يمكنك تعطيل التشفير باستخدام الكود التالي:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### كيف يمكنني حماية عرض PowerPoint الخاص بي بكلمة مرور باستخدام Aspose.Slides لـ Java؟

لحماية عرض PowerPoint الخاص بك بكلمة مرور، يمكنك استخدام `encrypt` الطريقة التي تقدمها `ProtectionManager` الصف. إليك كيفية تعيين كلمة مرور:

```java
// تعيين كلمة مرور لحماية العرض التقديمي
presentation.getProtectionManager().encrypt("your_password");
```

يستبدل `"your_password"` مع كلمة المرور المطلوبة.

### هل يمكنني حفظ العرض التقديمي بتنسيق مختلف عن PPTX؟

نعم، يمكنك حفظ العرض التقديمي بتنسيقات متنوعة يدعمها Aspose.Slides لجافا، مثل PPT وPDF وغيرها. لحفظه بتنسيق مختلف، غيّر `SaveFormat` المعلمة في `presentation.save` الطريقة. على سبيل المثال، لحفظ ملف PDF:

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### هل من الضروري التخلص من كائن العرض التقديمي بعد الحفظ؟

من الجيد التخلص من كائن العرض لتحرير موارد النظام. يمكنك استخدام `finally` كتلة لضمان التخلص منها بشكل صحيح، كما هو موضح في مثال الكود:

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

يساعد هذا على منع تسرب الذاكرة في تطبيقك.

### كيف يمكنني معرفة المزيد عن Aspose.Slides لـ Java وميزاته؟

يمكنك استكشاف وثائق Aspose.Slides لـ Java على [هنا](https://docs.aspose.com/slides/java/) للحصول على معلومات مفصلة، ودروس تعليمية، وأمثلة حول استخدام المكتبة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}