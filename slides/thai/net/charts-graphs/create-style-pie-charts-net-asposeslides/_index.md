---
"date": "2025-04-15"
"description": "เรียนรู้วิธีการสร้างแผนภูมิวงกลมแบบอัตโนมัติในงานนำเสนอ .NET ด้วย Aspose.Slides เพื่อปรับปรุงการแสดงภาพข้อมูลได้อย่างง่ายดาย"
"title": "วิธีการสร้างและปรับแต่งแผนภูมิวงกลมในงานนำเสนอ .NET โดยใช้ Aspose.Slides"
"url": "/th/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีการสร้างและปรับแต่งแผนภูมิวงกลมในงานนำเสนอ .NET โดยใช้ Aspose.Slides

## การแนะนำ
การสร้างงานนำเสนอที่น่าสนใจและให้ข้อมูลถือเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ ไม่ว่าคุณจะนำเสนอข้อมูลที่ทำงานหรือแสดงผลการค้นพบล่าสุดในโครงการของคุณ วิธีที่มีประสิทธิภาพวิธีหนึ่งในการสร้างภาพข้อมูลคือการใช้แผนภูมิวงกลม ซึ่งสามารถแสดงส่วนต่างๆ ของข้อมูลทั้งหมดได้อย่างชัดเจน อย่างไรก็ตาม การสร้างแผนภูมิเหล่านี้ด้วยตนเองในซอฟต์แวร์นำเสนอ เช่น PowerPoint อาจใช้เวลานานและอาจขาดความยืดหยุ่นที่จำเป็นสำหรับการอัปเดตแบบไดนามิก

นั่นคือจุดที่ Aspose.Slides สำหรับ .NET เข้ามามีบทบาท ไลบรารีที่ครอบคลุมนี้ช่วยให้คุณสร้าง แก้ไข และกำหนดรูปแบบการนำเสนอตามโปรแกรม ทำให้เป็นเครื่องมืออันล้ำค่าสำหรับนักพัฒนาที่ต้องการทำให้เวิร์กโฟลว์เป็นอัตโนมัติและรับรองความสอดคล้องกันในงานนำเสนอต่างๆ

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการใช้ Aspose.Slides สำหรับ .NET เพื่อสร้างและปรับแต่งแผนภูมิวงกลมในงานนำเสนอของคุณ คุณจะได้เรียนรู้วิธีการดังต่อไปนี้:
- **สร้างการนำเสนอและเข้าถึงสไลด์**
- **เพิ่มและกำหนดค่าแผนภูมิวงกลม**
- **ปรับแต่งข้อมูลแผนภูมิและชุดข้อมูล**
- **รูปแบบแผนภูมิวงกลมภาคส่วน**
- **เพิ่มป้ายกำกับที่กำหนดเอง**
- **กำหนดค่าคุณสมบัติการแสดงผลและบันทึกการนำเสนอ**

พร้อมที่จะดำดิ่งสู่การสร้างแผนภูมิวงกลมอันน่าทึ่งได้อย่างง่ายดายหรือยัง มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีการตั้งค่าต่อไปนี้:

### ห้องสมุดที่จำเป็น
- Aspose.Slides สำหรับ .NET (แนะนำเวอร์ชัน 21.11 ขึ้นไป)

### การตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาที่รัน .NET Framework หรือ .NET Core/5+/6+
- โปรแกรมแก้ไขโค้ด เช่น Visual Studio

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
- ความคุ้นเคยกับแนวคิดเชิงวัตถุ

## การตั้งค่า Aspose.Slides สำหรับ .NET
ในการเริ่มต้น คุณจะต้องติดตั้งไลบรารี Aspose.Slides คุณสามารถทำได้โดยใช้หนึ่งในวิธีต่อไปนี้:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**คอนโซลตัวจัดการแพ็คเกจ**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet**
- เปิดโปรเจ็กต์ของคุณใน Visual Studio
- ไปที่ "เครื่องมือ" > "ตัวจัดการแพ็กเกจ NuGet" > "จัดการแพ็กเกจ NuGet สำหรับโซลูชัน"
- ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### ขั้นตอนการรับใบอนุญาต
หากต้องการใช้ Aspose.Slides คุณสามารถเริ่มทดลองใช้งานฟรีได้โดยดาวน์โหลดใบอนุญาตชั่วคราว เยี่ยมชม [เว็บไซต์ของ Aspose](https://purchase.aspose.com/temporary-license/) เพื่อรับสิทธิ์ใช้งาน หากต้องการใช้งานอย่างต่อเนื่อง โปรดพิจารณาซื้อสิทธิ์ใช้งานแบบเต็ม

### การเริ่มต้นและการตั้งค่าเบื้องต้น
เมื่อติดตั้งแล้ว ให้เริ่มต้นคลาสการนำเสนอซึ่งแสดงไฟล์ PPTX ของคุณ:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## คู่มือการใช้งาน
เราจะแบ่งกระบวนการสร้างแผนภูมิวงกลมออกเป็นหลายส่วนเพื่อให้จัดการได้ แต่ละส่วนได้รับการออกแบบให้เน้นที่ฟีเจอร์เฉพาะ ช่วยให้คุณเพิ่มพูนความรู้ได้ทีละส่วน

### สร้างการนำเสนอและเข้าถึงสไลด์
**ภาพรวม:** เริ่มต้นด้วยการสร้างงานนำเสนอใหม่และเข้าถึงสไลด์แรก การทำเช่นนี้จะเป็นการเตรียมการสำหรับการเพิ่มแผนภูมิและองค์ประกอบอื่นๆ

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
    Presentation presentation = new Presentation();
    
    // เข้าถึงสไลด์แรก
    ISlide slides = presentation.Slides[0];
}
```

### เพิ่มและกำหนดค่าแผนภูมิวงกลม
**ภาพรวม:** เรียนรู้วิธีการเพิ่มแผนภูมิวงกลมลงในสไลด์ของคุณและตั้งชื่อเพื่อให้เข้ากับบริบท

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
    Presentation presentation = new Presentation();
    
    // เข้าถึงสไลด์แรก
    ISlide slides = presentation.Slides[0];
    
    // เพิ่มแผนภูมิพร้อมข้อมูลเริ่มต้นลงในสไลด์
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // ตั้งค่าแผนภูมิชื่อ
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### ปรับแต่งข้อมูลแผนภูมิและชุดข้อมูล
**ภาพรวม:** ปรับแต่งหมวดหมู่และชุดข้อมูลเพื่อให้เหมาะกับความต้องการเฉพาะของคุณ

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
    Presentation presentation = new Presentation();
    
    // เข้าถึงสไลด์แรก
    ISlide slides = presentation.Slides[0];
    
    // เพิ่มแผนภูมิพร้อมข้อมูลเริ่มต้นลงในสไลด์
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // ตั้งค่าซีรีส์แรกให้แสดงค่า
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
    int defaultWorksheetIndex = 0;
    
    // การรับแผ่นงานข้อมูลแผนภูมิ
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // การเพิ่มหมวดหมู่ใหม่
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // เพิ่มซีรีย์ใหม่
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### ปรับแต่งสไตล์ภาคส่วนของแผนภูมิวงกลม
**ภาพรวม:** ออกแบบแต่ละส่วนของแผนภูมิวงกลมของคุณเพื่อเพิ่มความน่าสนใจและเน้นจุดข้อมูลที่สำคัญ

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
    Presentation presentation = new Presentation();
    
    // เข้าถึงสไลด์แรก
    ISlide slides = presentation.Slides[0];
    
    // เพิ่มแผนภูมิพร้อมข้อมูลเริ่มต้นลงในสไลด์
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // รับซีรีส์จากชาร์ต
    IChartSeries series = chart.ChartData.Series[0];
    
    // การปรับแต่งรูปแบบภาคส่วนสำหรับแต่ละจุดข้อมูลในซีรีส์
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // การตั้งค่าขอบเขตภาค
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // การตั้งค่าขอบเขตภาค
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // การตั้งค่าขอบเขตภาค
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### เพิ่มป้ายกำกับที่กำหนดเองลงในแผนภูมิวงกลม
**ภาพรวม:** ปรับปรุงแผนภูมิวงกลมของคุณด้วยการเพิ่มป้ายที่กำหนดเองเพื่อให้แสดงข้อมูลได้ชัดเจนยิ่งขึ้น

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // ปรับตำแหน่งฉลากตามต้องการ
    }
}
```

### บทสรุป
ตอนนี้คุณได้เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิวงกลมในงานนำเสนอ .NET โดยใช้ Aspose.Slides แล้ว การทำงานอัตโนมัตินี้จะช่วยเพิ่มประสิทธิภาพในการแสดงภาพข้อมูลของคุณได้อย่างมาก ช่วยประหยัดเวลาและรับรองความสอดคล้องกันในงานนำเสนอต่างๆ

หากต้องการสำรวจความสามารถของ Aspose.Slides สำหรับ .NET เพิ่มเติม โปรดพิจารณาเจาะลึกคุณลักษณะเพิ่มเติม เช่น การสร้างประเภทแผนภูมิอื่น หรือการรวมองค์ประกอบการออกแบบที่ซับซ้อนมากขึ้นลงในสไลด์ของคุณ

สนุกกับการเขียนโค้ด!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}