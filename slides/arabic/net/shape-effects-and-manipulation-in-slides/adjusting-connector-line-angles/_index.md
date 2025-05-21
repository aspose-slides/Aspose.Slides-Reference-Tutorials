---
"description": "تعرّف على كيفية ضبط زوايا خطوط التوصيل في شرائح PowerPoint باستخدام Aspose.Slides لـ .NET. حسّن عروضك التقديمية بدقة وسهولة."
"linktitle": "ضبط زوايا خطوط الموصل في شرائح العرض التقديمي باستخدام Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "ضبط زوايا خطوط الموصل في PowerPoint باستخدام Aspose.Slides"
"url": "/ar/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ضبط زوايا خطوط الموصل في PowerPoint باستخدام Aspose.Slides

## مقدمة
غالبًا ما يتطلب إنشاء شرائح عرض تقديمي جذابة بصريًا تعديلات دقيقة لخطوط التوصيل. في هذا البرنامج التعليمي، سنستكشف كيفية تعديل زوايا خطوط التوصيل في شرائح العرض التقديمي باستخدام Aspose.Slides لـ .NET. Aspose.Slides هي مكتبة فعّالة تتيح للمطورين العمل مع ملفات PowerPoint برمجيًا، مما يوفر إمكانيات واسعة لإنشاء العروض التقديمية وتعديلها ومعالجتها.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio أو أي بيئة تطوير C# أخرى.
- مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها [هنا](https://releases.aspose.com/slides/net/).
- ملف عرض تقديمي PowerPoint يحتوي على خطوط الاتصال التي تريد تعديلها.
## استيراد مساحات الأسماء
للبدء، تأكد من تضمين المساحات الأساسية اللازمة في كود C# الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## الخطوة 1: إعداد مشروعك
أنشئ مشروع C# جديدًا في Visual Studio وثبّت حزمة Aspose.Slides NuGet. جهّز هيكل المشروع بالرجوع إلى مكتبة Aspose.Slides.
## الخطوة 2: تحميل العرض التقديمي
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
قم بتحميل ملف عرض PowerPoint الخاص بك إلى `Presentation` الكائن. استبدل "دليل مستنداتك" بالمسار الفعلي لملفك.
## الخطوة 3: الوصول إلى الشريحة والأشكال
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
قم بالوصول إلى الشريحة الأولى في العرض التقديمي وقم بإنشاء متغير لتمثيل الأشكال الموجودة على الشريحة.
## الخطوة 4: التكرار عبر الأشكال
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // كود التعامل مع خطوط الموصل
}
```
قم بالمرور على كل شكل على الشريحة لتحديد خطوط الموصل ومعالجتها.
## الخطوة 5: ضبط زوايا خطوط الموصل
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // كود التعامل مع الأشكال التلقائية
}
else if (shape is Connector)
{
    // كود التعامل مع الموصلات
}
Console.WriteLine(dir);
```
حدد ما إذا كان الشكل عبارة عن شكل تلقائي أو موصل، واضبط زوايا خط الموصل باستخدام الأداة المقدمة `getDirection` طريقة.
## الخطوة 6: تحديد `getDirection` طريقة
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // كود حساب الاتجاه
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
تنفيذ `getDirection` طريقة لحساب زاوية خط الموصل بناءً على أبعاده واتجاهه.
## خاتمة
باتباع هذه الخطوات، يمكنك تعديل زوايا خطوط التوصيل برمجيًا في عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ .NET. يوفر هذا البرنامج التعليمي أساسًا لتحسين المظهر المرئي لشرائحك.
## الأسئلة الشائعة
### هل Aspose.Slides مناسب لكل من تطبيقات Windows والويب؟
نعم، يمكن استخدام Aspose.Slides في كل من تطبيقات Windows والويب.
### هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Slides قبل الشراء؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق شاملة لـ Aspose.Slides لـ .NET؟
الوثائق متاحة [هنا](https://reference.aspose.com/slides/net/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يمكنك الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
### هل يوجد منتدى دعم لـ Aspose.Slides؟
نعم يمكنك زيارة منتدى الدعم [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}