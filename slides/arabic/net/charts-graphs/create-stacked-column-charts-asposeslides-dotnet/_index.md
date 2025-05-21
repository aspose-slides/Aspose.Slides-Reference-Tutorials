---
"date": "2025-04-15"
"description": "تعرّف على كيفية إنشاء مخططات بيانية عمودية مكدسة، مبنية على النسب المئوية، جذابة بصريًا باستخدام Aspose.Slides لـ .NET. اتبع هذا الدليل خطوة بخطوة لعرض البيانات بوضوح."
"title": "كيفية إنشاء مخططات عمودية مكدسة تعتمد على النسبة المئوية في .NET باستخدام Aspose.Slides"
"url": "/ar/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط عمودي مكدس قائم على النسبة المئوية باستخدام Aspose.Slides لـ .NET

## مقدمة

في مجال تصور البيانات، يُعد عرض المعلومات بوضوح وفعالية أمرًا بالغ الأهمية لاتخاذ قرارات مؤثرة. لعرض مجموعات البيانات المعقدة بسهولة، تُعد المخططات العمودية المكدسة القائمة على النسب المئوية مثالية. سيرشدك هذا الدليل إلى كيفية إنشاء هذه المخططات باستخدام Aspose.Slides for .NET، وهي مكتبة قوية مصممة للتعامل مع ملفات العروض التقديمية.

من خلال اتباع هذا البرنامج التعليمي، سوف تتعلم:
- إعداد بيانات الرسم البياني وتكوين تنسيقات الأرقام.
- إضافة المسلسلات وتخصيص مظهرها.
- تنسيق العلامات لتحسين قابلية القراءة.

هل أنت مستعد للبدء؟ لنبدأ بالمتطلبات الأساسية التي تحتاجها!

## المتطلبات الأساسية

قبل إنشاء مخططاتك العمودية المكدسة القائمة على النسب المئوية، تأكد من إعداد بيئتك بشكل صحيح. ستحتاج إلى:

### المكتبات والإصدارات والتبعيات المطلوبة
- **Aspose.Slides لـ .NET**:تأكد من تثبيت هذه المكتبة.

### متطلبات إعداد البيئة
- بيئة تطوير مع تثبيت .NET SDK.
- Visual Studio أو أي IDE متوافق لتشغيل كود C#.

### متطلبات المعرفة
- فهم أساسي لبرمجة C#.
- المعرفة بإعداد مشروع .NET وإدارة الحزم.

## إعداد Aspose.Slides لـ .NET

لبدء إنشاء المخططات البيانية باستخدام Aspose.Slides، قم أولاً بتثبيت المكتبة باستخدام إحدى الطرق التالية:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
- ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص

ابدأ بفترة تجريبية مجانية عن طريق تنزيل ترخيص مؤقت من [موقع Aspose](https://purchase.aspose.com/temporary-license/)للاستمرار في الاستخدام، فكر في شراء ترخيص كامل. 

بمجرد الإعداد، قم بتشغيل Aspose.Slides في مشروعك:
```csharp
using Aspose.Slides;
```

## دليل التنفيذ

بعد أن أصبحت البيئة جاهزة، دعنا نقسم عملية إنشاء مخطط عمودي مكدس يعتمد على النسبة المئوية إلى خطوات.

### إنشاء الرسم البياني وتكوينه

#### ملخص
إنشاء مثيل لـ `Presentation` فئة أساسية للتعامل مع الشرائح. ثم أضف مخططًا عموديًا مكدسًا وقم بتكوينه على الشريحة.

#### إضافة مخطط عمودي مكدس
```csharp
// إنشاء مثيل لفئة العرض التقديمي
document = new Presentation();

// احصل على مرجع للشريحة الأولى
slide = document.Slides[0];

// أضف مخطط PercentsStackedColumn في الموضع (20، 20) بحجم (500 × 400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### تكوين تنسيق الأرقام
تأكد من عرض بياناتك كنسب مئوية:
```csharp
// تكوين تنسيق الأرقام للمحور الرأسي
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // تعيين تنسيق الرقم إلى النسبة المئوية
```

#### إضافة سلسلة البيانات والنقاط
مسح بيانات السلسلة الحالية وإضافة بيانات جديدة:
```csharp
// مسح أي بيانات سلسلة موجودة
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// مصنف بيانات مخطط الوصول
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// أضف سلسلة بيانات جديدة "Reds"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// تعيين لون التعبئة للسلسلة إلى اللون الأحمر
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// تكوين خصائص تنسيق الملصق لسلسلة "Reds"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // تعيين تنسيق النسبة المئوية
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// أضف سلسلة أخرى "بلوز"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// تعيين لون التعبئة للسلسلة إلى اللون الأزرق
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // تعيين تنسيق النسبة المئوية
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### حفظ العرض التقديمي
احفظ عرضك التقديمي في ملف:
```csharp
// حفظ العرض التقديمي بتنسيق PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من استيراد كافة المساحات الأساسية بشكل صحيح.
- التحقق من وجود أخطاء مطبعية في أسماء الخصائص واستدعاءات الطريقة.
- تأكد من أن مساراتك لحفظ الملفات موجودة ولديها الأذونات الصحيحة.

## التطبيقات العملية

فيما يلي بعض السيناريوهات حيث يمكن أن تكون المخططات العمودية المكدسة القائمة على النسبة المئوية مفيدة:
1. **تحليل المبيعات**:تصور أداء المنتج عبر مناطق مختلفة كنسبة من إجمالي المبيعات.
2. **تخصيص الميزانية**:أظهر كيف تقوم الأقسام بتخصيص ميزانيتها فيما يتعلق بالإنفاق الإجمالي للشركة.
3. **أبحاث السوق**:مقارنة تفضيلات المستهلكين لفئات المنتجات المختلفة على مر الزمن.
4. **البيانات التعليمية**:عرض توزيع درجات الطلاب في المواد المختلفة.
5. **إحصائيات الرعاية الصحية**:تمثيل التركيبة السكانية للمرضى عبر ظروف صحية متعددة.

## اعتبارات الأداء

للحصول على الأداء الأمثل، ضع في اعتبارك ما يلي:
- الحد من عدد نقاط البيانات إلى ما هو ضروري.
- تحميل البيانات مسبقًا لتقليل معالجة وقت التشغيل.
- استخدام ممارسات إدارة الذاكرة الفعالة مع Aspose.Slides لـ .NET.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية إنشاء مخطط بياني عمودي مكدس قائم على النسب المئوية باستخدام Aspose.Slides لـ .NET. تُحسّن هذه الأداة العروض التقديمية بجعل البيانات المعقدة أكثر وضوحًا وجاذبية بصريًا.

ما هي الخطوات التالية؟ استكشف أنواع المخططات الأخرى المتوفرة في Aspose.Slides أو ادمج هذه الميزة في تطبيقات أكبر. برمجة ممتعة!

## قسم الأسئلة الشائعة

**س1: هل يمكنني استخدام Aspose.Slides مجانًا؟**
ج1: نعم، يمكنك البدء بإصدار تجريبي مجاني لاختبار ميزات Aspose.Slides.

**س2: ما هي أنواع المخططات التي يدعمها Aspose.Slides لـ .NET؟**
ج2: يدعم العديد من المخططات البيانية مثل الدائرية والشريطية والعمودية والخطية والمزيد.

**س3: كيف يمكنني البدء باستخدام Aspose.Slides لـ .NET؟**
ج٣: ثبّت المكتبة باستخدام NuGet أو .NET CLI كما هو موضح أعلاه. اتبع وثائقنا لإنشاء مخططك الأول.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}