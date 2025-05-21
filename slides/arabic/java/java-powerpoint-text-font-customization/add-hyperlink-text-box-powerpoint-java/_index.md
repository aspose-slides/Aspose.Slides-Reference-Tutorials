---
"description": "تعرّف على كيفية إضافة روابط تشعبية إلى مربعات نص PowerPoint باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع أمثلة لمطوري جافا."
"linktitle": "إضافة ارتباط تشعبي إلى مربع النص في PowerPoint باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة ارتباط تشعبي إلى مربع النص في PowerPoint باستخدام Java"
"url": "/ar/java/java-powerpoint-text-font-customization/add-hyperlink-text-box-powerpoint-java/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة ارتباط تشعبي إلى مربع النص في PowerPoint باستخدام Java

## مقدمة
في عصرنا الرقمي، يُعدّ إنشاء عروض تقديمية ديناميكية تفاعلية وغنية بالمعلومات أمرًا بالغ الأهمية للتواصل الفعال. يلجأ مطورو جافا، الذين يسعون إلى تحسين تطبيقاتهم بميزات تفاعلية، غالبًا إلى Aspose.Slides for Java، وهي مكتبة فعّالة تُمكّن من التعامل مع عروض PowerPoint التقديمية برمجيًا. يتعمق هذا البرنامج التعليمي في إحدى هذه الميزات: إضافة روابط تشعبية إلى مربعات النص في عروض PowerPoint التقديمية باستخدام جافا. بنهاية هذا الدليل، ستفهم بوضوح كيفية تطبيق هذه الوظيفة بسلاسة في تطبيقات جافا.
## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك المتطلبات الأساسية التالية:
- المعرفة الأساسية بلغة البرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على نظامك.
- تم تنزيل وإعداد مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse مثبتة.

## استيراد الحزم
قبل الغوص في المثال، تأكد من استيراد الحزم الضرورية:
```java
import com.aspose.slides.*;
import java.io.File;
```
## الخطوة 1: إنشاء كائن عرض تقديمي
أولاً، قم بإنشاء كائن عرض تقديمي يمثل عرض تقديمي في PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation pptxPresentation = new Presentation();
```
## الخطوة 2: الوصول إلى الشريحة وتعديلها
احصل على الشريحة الأولى من العرض التقديمي للتلاعب بها.
```java
ISlide slide = pptxPresentation.getSlides().get_Item(0);
```
## الخطوة 3: إضافة شكل تلقائي (مربع نص)
أضف شكلًا تلقائيًا من نوع المستطيل إلى الشريحة عند الإحداثيات المحددة.
```java
IShape pptxShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 150, 50);
```
## الخطوة 4: الوصول إلى إطار النص
قم بتحويل الشكل إلى الشكل التلقائي والوصول إلى إطار النص الخاص به.
```java
IAutoShape pptxAutoShape = (IAutoShape) pptxShape;
pptxAutoShape.addTextFrame("");
ITextFrame textFrame = pptxAutoShape.getTextFrame();
```
## الخطوة 5: إضافة نص إلى إطار النص
أضف محتوى النص المطلوب إلى إطار النص.
```java
textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0).setText("Aspose.Slides");
```
## الخطوة 6: تعيين ارتباط تشعبي للنص
قم بتعيين ارتباط تشعبي لجزء النص المضاف في الخطوة السابقة.
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
IHyperlinkManager hyperlinkManager = portion.getPortionFormat().getHyperlinkManager();
hyperlinkManager.setExternalHyperlinkClick("http://www.aspose.com");
```
## الخطوة 7: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل في الموقع المحدد.
```java
pptxPresentation.save(dataDir + "hLinkPPTX_out.pptx", SaveFormat.Pptx);
```

## خاتمة
باتباع هذه الخطوات، تكون قد تعلمت بنجاح كيفية إضافة روابط تشعبية إلى مربعات النص في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تتيح لك هذه الميزة إنشاء محتوى ديناميكي وتفاعلي ضمن تطبيقات جافا، مما يعزز تفاعل المستخدمين وتفاعلهم.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لـ Java مجانًا؟
نعم، يمكنك البدء بالتجربة المجانية المتاحة [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم إذا واجهت مشاكل؟
يمكنك الحصول على الدعم من مجتمع Aspose [هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ Java؟
نعم، التراخيص المؤقتة متاحة للشراء [هنا](https://purchase.aspose.com/temporary-license/).
### هل Aspose.Slides متوافق مع مكتبات Java الأخرى؟
يتكامل Aspose.Slides بشكل جيد مع مكتبات Java المختلفة للتعامل الشامل مع PowerPoint.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}