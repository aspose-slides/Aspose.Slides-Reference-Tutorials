---
"date": "2025-04-15"
"description": "تعلّم كيفية إنشاء وتخصيص مخططات PieOfPie الديناميكية بسهولة في PowerPoint باستخدام Aspose.Slides لـ .NET. حسّن عروضك التقديمية مع هذا الدليل المفصل."
"title": "كيفية إنشاء مخططات PieOfPie ديناميكية في PowerPoint باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/charts-graphs/dynamic-pieofpie-charts-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخططات PieOfPie ديناميكية في PowerPoint باستخدام Aspose.Slides لـ .NET

## مقدمة

حسّن عروضك التقديمية بمخططات PieOfPie ديناميكية وجذابة بصريًا باستخدام Aspose.Slides لـ .NET. تُبسّط هذه المكتبة إنشاء مخططات بيانية معقدة دون الحاجة إلى معرفة برمجية واسعة، مما يتيح لك جذب انتباه جمهورك من خلال عرض دقيق للبيانات.

في هذا الدليل، ستتعلم كيفية إضافة مخطط PieOfPie بسلاسة وتخصيص خصائصه، مثل تسميات البيانات وإعدادات مجموعات السلاسل. لنبدأ بالتأكد من تهيئة بيئتك بشكل صحيح!

## المتطلبات الأساسية

قبل البدء، تأكد من أن إعدادك يلبي المتطلبات التالية:

1. **المكتبات المطلوبة**:قم بتثبيت Aspose.Slides لـ .NET.
2. **بيئة التطوير**:استخدم Visual Studio أو أي IDE يدعم تطوير .NET.
3. **قاعدة المعرفة**:يوصى بالإلمام بلغة C# ومفاهيم البرمجة الأساسية.

## إعداد Aspose.Slides لـ .NET

### تعليمات التثبيت

قم بتثبيت Aspose.Slides باستخدام طريقتك المفضلة:

- **استخدام .NET CLI:**
  ```bash
  dotnet add package Aspose.Slides
  ```

- **استخدام وحدة تحكم إدارة الحزم:**
  ```powershell
  Install-Package Aspose.Slides
  ```

- **واجهة مستخدم مدير الحزم NuGet**:ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص

- **نسخة تجريبية مجانية**:ابدأ بإصدار تجريبي مجاني لاستكشاف الميزات.
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت [هنا](https://purchase.aspose.com/temporary-license/).
- **شراء**:للاستخدام طويل الأمد، فكر في شراء ترخيص كامل من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

### التهيئة الأساسية

تهيئة `Presentation` الفصل للبدء:

```csharp
using Aspose.Slides;

// تهيئة عرض تقديمي جديد
class Program
{
    static void Main()
    {
        Presentation presentation = new Presentation();
    }
}
```

## دليل التنفيذ

### إضافة مخطط PieOfPie إلى العرض التقديمي الخاص بك

#### ملخص

يوضح هذا القسم كيفية إنشاء مخطط PieOfPie وإضافته إلى شريحة PowerPoint الخاصة بك باستخدام Aspose.Slides.

#### تعليمات خطوة بخطوة

**1. تهيئة العرض التقديمي**

إنشاء مثيل لـ `Presentation` فصل:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

**2. أضف مخطط PieOfPie**

أدخل الرسم البياني في الموضع والأبعاد المطلوبة على الشريحة الأولى:

```csharp
using Aspose.Slides.Charts;

IChart chart = presentation.Slides[0].Shapes.AddChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

**3. احفظ عرضك التقديمي**

احفظ ملفك بتنسيق PPTX بعد إضافة الرسم البياني:

```csharp
using Aspose.Slides.Export;

presentation.Save("YOUR_OUTPUT_DIRECTORY/SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

### تكوين تسميات بيانات الرسم البياني وخصائص مجموعة السلاسل

#### ملخص

قم بتعزيز الرسم البياني الخاص بك عن طريق تكوين تسميات البيانات وخصائص مجموعة السلسلة لتحسين التصور.

**1. تعيين تنسيق تسمية البيانات**

عرض القيم في السلسلة الأولى:

```csharp
chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
```

**2. اضبط حجم الفطيرة الثانية**

تعيين الحجم المناسب للوضوح:

```csharp
chart.ChartData.Series[0].ParentSeriesGroup.SecondPieSize = 149;
```

**3. تخصيص التقسيم حسب النسبة المئوية والموضع**

ضبط تقسيم البيانات داخل الرسم البياني:

```csharp
chart.ChartData.Series[0].ParentSeriesGroup.PieSplitBy = PieSplitType.ByPercentage;
chart.ChartData.Series[0].ParentSeriesGroup.PieSplitPosition = 53;
```

### نصائح استكشاف الأخطاء وإصلاحها

- تأكد من تثبيت Aspose.Slides بشكل صحيح والإشارة إليه في مشروعك.
- تحقق من المسار عند حفظ العرض التقديمي لتجنب أخطاء عدم العثور على الملف.

## التطبيقات العملية

1. **التقارير المالية**:قم بتقسيم مصادر الإيرادات باستخدام مخططات PieOfPie للحصول على تحليل مفصل.
2. **إدارة المشاريع**:تصور توزيعات المهام ضمن مرحلة المشروع، مع إظهار المهام الرئيسية والمهام الفرعية.
3. **تحليل التسويق**:قم بتحليل التركيبة السكانية للعملاء عن طريق تقسيمهم إلى فئات ذات أقسام فرعية أخرى.

## اعتبارات الأداء

- **تحسين استخدام الموارد**:قم بتحميل البيانات الضرورية فقط لتقليل استخدام الذاكرة.
- **أفضل ممارسات إدارة الذاكرة**:التخلص من الأشياء بطريقة مناسبة باستخدام `using` بيانات أو طرق التخلص الصريحة.

من خلال اتباع هذه النصائح، يمكنك ضمان أداء سلس حتى عند التعامل مع مجموعات بيانات كبيرة في العروض التقديمية الخاصة بك.

## خاتمة

لقد أتقنتَ إضافة مخطط PieOfPie باستخدام Aspose.Slides لـ .NET. تُساعدك هذه المهارة على إنشاء عروض تقديمية شيقة وغنية بالمعلومات، مما يُحسّن تبادل البيانات في مشاريعك.

**الخطوات التالية:**
- استكشف أنواع المخططات الأخرى التي يدعمها Aspose.Slides.
- قم بتجربة خصائص إضافية لتخصيص المخططات بشكل أكبر.

هل أنت مستعد لتطوير مهاراتك في العرض التقديمي؟ طبّق هذه الحلول اليوم!

## قسم الأسئلة الشائعة

1. **هل يمكنني استخدام Aspose.Slides مجانًا؟** 
   نعم، ابدأ بفترة تجريبية مجانية ثم قم بالتقدم بطلب للحصول على ترخيص مؤقت أو كامل حسب الحاجة.
2. **كيف أقوم بتخصيص مخطط الألوان الخاص بمخطط PieOfPie الخاص بي؟**
   تخصيص الألوان من خلال `FillFormat` الخصائص على نقاط البيانات المتسلسلة.
3. **هل من الممكن إضافة عدة مخططات في عرض تقديمي واحد؟**
   بالتأكيد! أضف مخططات متعددة بتكرار الشرائح باستخدام نفس الطرق الموضحة أعلاه.
4. **هل يمكنني تصدير العروض التقديمية إلى تنسيقات أخرى غير PPTX؟**
   نعم، يدعم Aspose.Slides تنسيقات مختلفة بما في ذلك PDF وPNG وJPEG وما إلى ذلك.
5. **ما هي متطلبات النظام لتشغيل Aspose.Slides؟**
   يتطلب بيئة .NET Framework أو .NET Core وبيئة تطوير متكاملة متوافقة مثل Visual Studio.

## موارد

- [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/)
- [التنزيلات](https://releases.aspose.com/slides/net/)
- [شراء الترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/slides/net/)
- [رخصة مؤقتة](https://purchase.aspose.com/temporary-license/)
- [منتدى الدعم](https://forum.aspose.com/c/slides/11)

استكشف هذه الموارد لتعميق فهمك وتوسيع قدراتك مع Aspose.Slides. برمجة ممتعة!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}