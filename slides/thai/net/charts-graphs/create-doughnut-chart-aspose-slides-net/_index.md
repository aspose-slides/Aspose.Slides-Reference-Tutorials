---
"date": "2025-04-15"
"description": "เรียนรู้วิธีสร้างแผนภูมิโดนัทแบบไดนามิกโดยใช้ Aspose.Slides สำหรับ .NET ทำตามคำแนะนำนี้เพื่อดูคำแนะนำทีละขั้นตอน รวมถึงการตั้งค่าและคุณลักษณะขั้นสูง"
"title": "คู่มือทีละขั้นตอนในการสร้างแผนภูมิโดนัทด้วย Aspose.Slides .NET | แผนภูมิและกราฟ"
"url": "/th/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# คู่มือทีละขั้นตอน: สร้างแผนภูมิโดนัทด้วย Aspose.Slides .NET

## การแนะนำ

ลองนึกภาพว่าคุณได้รับมอบหมายให้นำเสนอผลการวิเคราะห์ข้อมูลต่อทีมหรือลูกค้า และคุณต้องการวิธีที่น่าสนใจในการแสดงข้อมูลดังกล่าว ลองใช้แผนภูมิโดนัท ซึ่งเป็นเครื่องมืออเนกประสงค์ที่สามารถเปลี่ยนตัวเลขดิบให้กลายเป็นข้อมูลเชิงลึกที่เข้าใจง่าย ด้วย Aspose.Slides สำหรับ .NET การสร้างแผนภูมิโดนัทแบบกำหนดเองในสไลด์การนำเสนอของคุณนั้นเป็นเรื่องง่ายและมีประสิทธิภาพ คู่มือนี้จะแนะนำคุณเกี่ยวกับการใช้ Aspose.Slides เพื่อสร้างแผนภูมิโดนัทที่ดึงดูดสายตาพร้อมการกำหนดค่าชุดข้อมูลที่ปรับแต่งได้

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Aspose.Slides สำหรับ .NET
- การสร้างและปรับแต่งแผนภูมิโดนัทในงานนำเสนอ
- การนำคุณสมบัติขั้นสูงเช่นชื่อหมวดหมู่และเส้นผู้นำมาใช้
- การเพิ่มประสิทธิภาพการทำงานสำหรับชุดข้อมูลขนาดใหญ่

มาเจาะลึกข้อกำหนดเบื้องต้นที่คุณต้องมีเพื่อเริ่มต้นกันเลย

## ข้อกำหนดเบื้องต้น

ก่อนที่จะนำฟีเจอร์นี้ไปใช้ โปรดตรวจสอบว่าสภาพแวดล้อมการพัฒนาของคุณได้รับการตั้งค่าอย่างถูกต้อง บทช่วยสอนนี้ถือว่ามีความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม .NET และมีความคุ้นเคยกับ Visual Studio หรือ IDE ที่คล้ายกัน

### ไลบรารีและเวอร์ชันที่จำเป็น
- **Aspose.Slides สำหรับ .NET**:ตรวจสอบความเข้ากันได้กับเวอร์ชั่นล่าสุด [เอกสารอย่างเป็นทางการ](https://reference-aspose.com/slides/net/).

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการทำงานของ .NET
- การเข้าถึงโปรแกรมแก้ไขโค้ด เช่น Visual Studio

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานเกี่ยวกับ C# และ .NET framework
- ความคุ้นเคยกับแนวคิดของซอฟต์แวร์การนำเสนอ (เป็นทางเลือกแต่ก็มีประโยชน์)

## การตั้งค่า Aspose.Slides สำหรับ .NET

หากต้องการเริ่มใช้ Aspose.Slides ในโปรเจ็กต์ของคุณ คุณจะต้องติดตั้งผ่าน NuGet โดยมีวิธีการต่างๆ ให้เลือกดังนี้:

**การใช้ .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**การใช้ตัวจัดการแพ็คเกจ:**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet:**
ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### ขั้นตอนการรับใบอนุญาต

1. **ทดลองใช้งานฟรี**: เริ่มต้นด้วย [ทดลองใช้งานฟรี](https://releases.aspose.com/slides/net/) เพื่อสำรวจฟังก์ชันพื้นฐาน
2. **ใบอนุญาตชั่วคราว**:รับใบอนุญาตชั่วคราวหากคุณต้องการเข้าถึงคุณสมบัติทั้งหมดเพื่อวัตถุประสงค์ในการประเมินผลโดยไปที่ [ที่นี่](https://purchase-aspose.com/temporary-license/).
3. **ซื้อ**: สำหรับการใช้งานเชิงพาณิชย์ กรุณาซื้อใบอนุญาตจาก [เว็บไซต์อาโพส](https://purchase-aspose.com/buy).

เมื่อติดตั้งและได้รับอนุญาตแล้ว ให้เริ่มต้น Aspose.Slides ในโปรเจ็กต์ของคุณ:
```csharp
using Aspose.Slides;

// เริ่มต้น Aspose.Slides สำหรับ .NET
var presentation = new Presentation();
```

## คู่มือการใช้งาน

### การสร้างงานนำเสนอใหม่และการเพิ่มแผนภูมิโดนัท

#### ภาพรวม
เราจะเริ่มต้นด้วยการสร้างงานนำเสนอใหม่และเพิ่มแผนภูมิโดนัทลงในสไลด์แรก หัวข้อนี้จะครอบคลุมถึงการโหลดงานนำเสนอที่มีอยู่ การเข้าถึงสไลด์ และการแทรกแผนภูมิ

**ขั้นตอนที่ 1: โหลดหรือสร้างงานนำเสนอ**
ขั้นแรก ให้ระบุไดเรกทอรีเอกสารของคุณและโหลดการนำเสนอที่มีอยู่:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
หากคุณไม่มีไฟล์อยู่แล้ว ให้สร้างไฟล์ใหม่ด้วย `new Presentation()`-

**ขั้นตอนที่ 2: เข้าถึงสไลด์แรก**
เข้าถึงสไลด์แรกที่เราจะเพิ่มแผนภูมิของเรา:
```csharp
ISlide slide = pres.Slides[0];
```

**ขั้นตอนที่ 3: เพิ่มแผนภูมิโดนัท**
เพิ่มแผนภูมิโดนัทตามพิกัดและมิติที่ระบุ:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### การกำหนดค่าสมุดงานข้อมูล

#### ภาพรวม
หัวข้อนี้จะอธิบายวิธีการกำหนดค่าเวิร์กบุ๊กข้อมูลที่เชื่อมโยงกับแผนภูมิโดนัทของคุณ

**ขั้นตอนที่ 4: เข้าถึงและล้างข้อมูลที่มีอยู่**
เข้าถึงสมุดงานข้อมูลของแผนภูมิ จากนั้นล้างชุดข้อมูลหรือหมวดหมู่ที่มีอยู่:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**ขั้นตอนที่ 5: ปิดใช้งานตำนานและเพิ่มซีรีส์**
ปิดใช้งานคำอธิบายเพื่อรักษาแผนภูมิให้สะอาด จากนั้นเพิ่มชุดข้อมูลได้สูงสุดถึง 15 ชุดด้วยการกำหนดค่าแบบกำหนดเอง:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### การเพิ่มหมวดหมู่และจุดข้อมูล

#### ภาพรวม
ต่อไป เรามาเพิ่มหมวดหมู่และจุดข้อมูลสำหรับแต่ละชุดลงในแผนภูมิกัน

**ขั้นตอนที่ 6: เพิ่มหมวดหมู่**
วนซ้ำเพื่อเพิ่ม 15 หมวดหมู่:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**ขั้นตอนที่ 7: เติมจุดข้อมูล**
เพิ่มจุดข้อมูลสำหรับแต่ละชุดภายในหมวดหมู่ปัจจุบัน:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // ปรับแต่งรูปลักษณ์
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // กำหนดค่ารูปแบบฉลากสำหรับซีรีย์สุดท้าย
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // กำหนดค่าการแสดงฉลาก
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### การบันทึกการนำเสนอ

**ขั้นตอนที่ 8: บันทึกไฟล์**
สุดท้าย ให้บันทึกการนำเสนอของคุณไปยังไดเร็กทอรีที่ระบุ:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}