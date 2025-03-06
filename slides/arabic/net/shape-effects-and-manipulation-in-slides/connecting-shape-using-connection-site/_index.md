---
title: إتقان اتصال الأشكال باستخدام Aspose.Slides لـ .NET
linktitle: ربط الشكل باستخدام موقع الاتصال في العرض التقديمي
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: يمكنك إنشاء عروض تقديمية جذابة باستخدام Aspose.Slides for .NET، وربط الأشكال بسلاسة. اتبع دليلنا للحصول على تجربة سلسة وجذابة.
weight: 30
url: /ar/net/shape-effects-and-manipulation-in-slides/connecting-shape-using-connection-site/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
في عالم العروض التقديمية الديناميكي، يعد إنشاء شرائح جذابة بصريًا بأشكال مترابطة أمرًا بالغ الأهمية للتواصل الفعال. يوفر Aspose.Slides for .NET حلاً قويًا لتحقيق ذلك من خلال السماح لك بربط الأشكال باستخدام مواقع الاتصال. سيرشدك هذا البرنامج التعليمي خلال عملية ربط الأشكال خطوة بخطوة، مما يضمن تميز عروضك التقديمية من خلال انتقالات مرئية سلسة.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:
- فهم أساسي لبرمجة C# و.NET.
-  تم تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- بيئة تطوير متكاملة (IDE) مثل إعداد Visual Studio.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية في كود C# الخاص بك:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
تأكد من أن لديك دليلًا مخصصًا للمستند الخاص بك. إذا لم يكن موجودًا، قم بإنشاء واحد:
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## الخطوة 2: إنشاء عرض تقديمي
قم بإنشاء مثيل لفئة العرض التقديمي لتمثيل ملف PPTX الخاص بك:
```csharp
using (Presentation presentation = new Presentation())
{
    // رمز العرض التقديمي الخاص بك موجود هنا
}
```
## الخطوة 3: الوصول إلى الأشكال وإضافتها
قم بالوصول إلى مجموعة الأشكال للشريحة المحددة وأضف الأشكال الضرورية:
```csharp
IShapeCollection shapes = presentation.Slides[0].Shapes;
IConnector connector = shapes.AddConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## الخطوة 4: انضم إلى الأشكال باستخدام الموصلات
قم بتوصيل الأشكال باستخدام الموصل:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## الخطوة 5: قم بتعيين موقع الاتصال المطلوب
حدد فهرس موقع الاتصال المطلوب للموصل:
```csharp
uint wantedIndex = 6;
if (ellipse.ConnectionSiteCount > wantedIndex)
{
    connector.StartShapeConnectionSiteIndex = wantedIndex;
}
```
## الخطوة 6: احفظ العرض التقديمي الخاص بك
احفظ العرض التقديمي الخاص بك بالأشكال المتصلة:
```csharp
presentation.Save(dataDir + "Connecting_Shape_on_desired_connection_site_out.pptx", SaveFormat.Pptx);
```
لقد نجحت الآن في توصيل الأشكال باستخدام مواقع الاتصال في العرض التقديمي الخاص بك.
## خاتمة
يعمل Aspose.Slides for .NET على تبسيط عملية ربط الأشكال، مما يسمح لك بإنشاء عروض تقديمية جذابة بصريًا دون عناء. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك تحسين المظهر المرئي لشرائحك ونقل رسالتك بشكل فعال.
## أسئلة مكررة
### هل Aspose.Slides متوافق مع Visual Studio 2019؟
نعم، Aspose.Slides متوافق مع Visual Studio 2019. تأكد من تثبيت الإصدار المناسب.
### هل يمكنني ربط أكثر من شكلين في موصل واحد؟
يتيح لك Aspose.Slides توصيل شكلين بموصل واحد. لتوصيل المزيد من الأشكال، ستحتاج إلى موصلات إضافية.
### كيف أتعامل مع الاستثناءات أثناء استخدام Aspose.Slides؟
يمكنك استخدام كتل محاولة الالتقاط للتعامل مع الاستثناءات. الرجوع إلى[توثيق](https://reference.aspose.com/slides/net/) لاستثناءات محددة ومعالجة الأخطاء.
### هل هناك نسخة تجريبية متاحة من Aspose.Slides؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
 قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) لدعم المجتمع والمناقشات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
