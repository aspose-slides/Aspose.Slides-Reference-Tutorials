---
title: ضبط زوايا خط الرابط في PowerPoint باستخدام Aspose.Slides
linktitle: ضبط زوايا خط الموصل في شرائح العرض التقديمي باستخدام Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية ضبط زوايا خط الموصل في شرائح PowerPoint باستخدام Aspose.Slides for .NET. قم بتحسين عروضك التقديمية بدقة وسهولة.
type: docs
weight: 28
url: /ar/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---
## مقدمة
غالبًا ما يتضمن إنشاء شرائح عرض تقديمي جذابة بصريًا تعديلات دقيقة على خطوط الموصل. في هذا البرنامج التعليمي، سوف نستكشف كيفية ضبط زوايا خط الموصل في شرائح العرض التقديمي باستخدام Aspose.Slides for .NET. Aspose.Slides هي مكتبة قوية تتيح للمطورين العمل مع ملفات PowerPoint برمجيًا، مما يوفر إمكانات واسعة لإنشاء العروض التقديمية وتعديلها ومعالجتها.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، تأكد من أن لديك ما يلي:
- المعرفة الأساسية بلغة البرمجة C#.
- تم تثبيت Visual Studio أو أي بيئة تطوير C# أخرى.
-  Aspose.Slides لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).
- ملف عرض تقديمي لـ PowerPoint يحتوي على خطوط الموصل التي تريد ضبطها.
## استيراد مساحات الأسماء
للبدء، تأكد من تضمين مساحات الأسماء الضرورية في كود C# الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## الخطوة 1: قم بإعداد مشروعك
قم بإنشاء مشروع C# جديد في Visual Studio وقم بتثبيت حزمة Aspose.Slides NuGet. قم بإعداد هيكل المشروع مع الإشارة إلى مكتبة Aspose.Slides.
## الخطوة 2: قم بتحميل العرض التقديمي
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 قم بتحميل ملف عرض PowerPoint التقديمي الخاص بك إلى ملف`Presentation`هدف. استبدل "دليل المستندات الخاص بك" بالمسار الفعلي لملفك.
## الخطوة 3: الوصول إلى الشريحة والأشكال
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
قم بالوصول إلى الشريحة الأولى في العرض التقديمي وقم بتهيئة متغير لتمثيل الأشكال على الشريحة.
## الخطوة 4: التكرار من خلال الأشكال
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // رمز للتعامل مع خطوط الموصل
}
```
قم بالتمرير عبر كل شكل على الشريحة لتحديد خطوط الموصل ومعالجتها.
## الخطوة 5: ضبط زوايا خط الموصل
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // كود التعامل مع الأشكال التلقائية
}
else if (shape is Connector)
{
    // رمز التعامل مع الموصلات
}
Console.WriteLine(dir);
```
 حدد ما إذا كان الشكل هو شكل تلقائي أو موصل، واضبط زوايا خط الموصل باستخدام المتوفر`getDirection` طريقة.
##  الخطوة 6: تحديد`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // رمز لحساب الاتجاه
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 تنفيذ`getDirection` طريقة لحساب زاوية خط الموصل بناءً على أبعادها واتجاهها.
## خاتمة
باستخدام هذه الخطوات، يمكنك ضبط زوايا خط الموصل برمجيًا في عرض PowerPoint التقديمي الخاص بك باستخدام Aspose.Slides for .NET. يوفر هذا البرنامج التعليمي أساسًا لتحسين المظهر المرئي لشرائحك.
## الأسئلة الشائعة
### هل Aspose.Slides مناسب لكل من تطبيقات Windows والويب؟
نعم، يمكن استخدام Aspose.Slides في كل من تطبيقات Windows والويب.
### هل يمكنني تنزيل نسخة تجريبية مجانية من Aspose.Slides قبل الشراء؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق شاملة لـ Aspose.Slides لـ .NET؟
 الوثائق متاحة[هنا](https://reference.aspose.com/slides/net/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يمكنك الحصول على ترخيص مؤقت[هنا](https://purchase.aspose.com/temporary-license/).
### هل يوجد منتدى دعم لـ Aspose.Slides؟
 نعم، يمكنك زيارة منتدى الدعم[هنا](https://forum.aspose.com/c/slides/11).