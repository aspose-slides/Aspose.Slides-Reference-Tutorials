---
"description": "تعلّم كيفية إعادة تشكيل شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. اتبع هذا الدليل خطوة بخطوة لإعادة ترتيب الأشكال وتحسين المظهر."
"linktitle": "تغيير ترتيب الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إعادة تشكيل شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إعادة تشكيل شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET

## مقدمة
يُعد إنشاء شرائح عرض تقديمي جذابة بصريًا جانبًا أساسيًا للتواصل الفعال. يُمكّن Aspose.Slides for .NET المطورين من التعامل مع الشرائح برمجيًا، مُوفرًا مجموعة واسعة من الوظائف. في هذا البرنامج التعليمي، سنتعمق في عملية تغيير ترتيب الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Slides لـ .NET: تأكد من دمج مكتبة Aspose.Slides في مشروع .NET الخاص بك. إذا لم تكن كذلك، يمكنك تنزيلها من [صفحة الإصدارات](https://releases.aspose.com/slides/net/).
- بيئة التطوير: قم بإعداد بيئة تطوير عمل باستخدام Visual Studio أو أي أداة تطوير .NET أخرى.
- الفهم الأساسي للغة C#: تعرف على أساسيات لغة البرمجة C#.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم بتضمين مساحات الأسماء الضرورية للوصول إلى وظيفة Aspose.Slides:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: إعداد مشروعك
أنشئ مشروعًا جديدًا في Visual Studio أو بيئة تطوير .NET المفضلة لديك. تأكد من الإشارة إلى Aspose.Slides for .NET في مشروعك.
## الخطوة 2: تحميل العرض التقديمي
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## الخطوة 3: الوصول إلى الشريحة والأشكال
```csharp
ISlide slide = presentation.Slides[0];
```
## الخطوة 4: إضافة شكل جديد
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## الخطوة 5: تعديل النص في الشكل
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## الخطوة 6: إضافة شكل آخر
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## الخطوة 7: تغيير ترتيب الأشكال
```csharp
slide.Shapes.Reorder(2, shp3);
```
## الخطوة 8: حفظ العرض التقديمي المعدّل
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
هذا يكمل الدليل خطوة بخطوة لتغيير ترتيب الأشكال في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET.
## خاتمة
يُبسّط Aspose.Slides لـ .NET عملية معالجة شرائح العروض التقديمية برمجيًا. باتباع هذا البرنامج التعليمي، ستتعلم كيفية إعادة ترتيب الأشكال، مما يُحسّن المظهر المرئي لعروضك التقديمية.
## الأسئلة الشائعة
### س: هل يمكنني استخدام Aspose.Slides لـ .NET في بيئات Windows وLinux؟
ج: نعم، Aspose.Slides for .NET متوافق مع بيئات Windows وLinux.
### س: هل هناك أي اعتبارات ترخيصية لاستخدام Aspose.Slides في مشروع تجاري؟
ج: نعم، يمكنك العثور على تفاصيل الترخيص وخيارات الشراء على [صفحة شراء Aspose.Slides](https://purchase.aspose.com/buy).
### س: هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
ج: نعم، يمكنك استكشاف الميزات باستخدام [نسخة تجريبية مجانية](https://releases.aspose.com/) متاح على موقع Aspose.Slides.
### س: أين يمكنني العثور على الدعم أو طرح الأسئلة المتعلقة بـ Aspose.Slides لـ .NET؟
أ: قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على الدعم والتفاعل مع المجتمع.
### س: كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
أ: يمكنك الحصول على [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/) لأغراض التقييم.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}