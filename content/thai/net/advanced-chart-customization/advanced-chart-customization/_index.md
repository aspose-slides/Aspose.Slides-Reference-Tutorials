---
title: การปรับแต่งแผนภูมิขั้นสูงใน Aspose.Slides
linktitle: การปรับแต่งแผนภูมิขั้นสูงใน Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้การปรับแต่งแผนภูมิขั้นสูงใน Aspose.Slides สำหรับ .NET สร้างแผนภูมิที่ดึงดูดสายตาพร้อมคำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/advanced-chart-customization/advanced-chart-customization/
---

การสร้างแผนภูมิที่ดึงดูดสายตาและให้ข้อมูลเป็นส่วนสำคัญของการนำเสนอข้อมูลในหลายแอปพลิเคชัน Aspose.Slides สำหรับ .NET มีเครื่องมือที่มีประสิทธิภาพสำหรับการปรับแต่งแผนภูมิ ซึ่งช่วยให้คุณปรับแต่งทุกแง่มุมของแผนภูมิได้ ในบทช่วยสอนนี้ เราจะสำรวจเทคนิคการปรับแต่งแผนภูมิขั้นสูงโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการปรับแต่งแผนภูมิขั้นสูงด้วย Aspose.Slides สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Aspose.Slides สำหรับ .NET Library: คุณต้องติดตั้งไลบรารี Aspose.Slides และกำหนดค่าอย่างเหมาะสมในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/net/).

2. สภาพแวดล้อมการพัฒนา .NET: คุณควรตั้งค่าสภาพแวดล้อมการพัฒนา .NET รวมถึง Visual Studio หรือ IDE อื่นๆ ที่คุณเลือก

3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ เนื่องจากเราจะเขียนโค้ด C# เพื่อทำงานกับ Aspose.Slides

ตอนนี้ เราจะแบ่งการปรับแต่งแผนภูมิขั้นสูงออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการ

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก สร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างไดเร็กทอรีหากไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// การนำเสนอทันที
Presentation pres = new Presentation();
```

ในขั้นตอนนี้ เราเริ่มต้นการนำเสนอใหม่ที่จะยึดแผนภูมิของเรา

## ขั้นตอนที่ 2: เข้าถึงสไลด์แรก

จากนั้น ให้เข้าถึงสไลด์แรกในงานนำเสนอที่คุณต้องการเพิ่มแผนภูมิ

```csharp
// การเข้าถึงสไลด์แรก
ISlide slide = pres.Slides[0];
```

ข้อมูลโค้ดนี้ช่วยให้คุณสามารถทำงานกับสไลด์แรกในงานนำเสนอได้

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิตัวอย่าง

ตอนนี้ เรามาเพิ่มแผนภูมิตัวอย่างลงในสไลด์ ในตัวอย่างนี้ เราจะสร้างแผนภูมิเส้นพร้อมเครื่องหมาย

```csharp
// การเพิ่มแผนภูมิตัวอย่าง
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

ที่นี่ เราระบุประเภทของแผนภูมิ (LineWithMarkers) รวมถึงตำแหน่งและขนาดบนสไลด์

## ขั้นตอนที่ 4: การตั้งชื่อแผนภูมิ

มาตั้งชื่อแผนภูมิเพื่อให้บริบทกันดีกว่า

```csharp
// การตั้งชื่อแผนภูมิ
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

รหัสนี้ตั้งชื่อให้กับแผนภูมิ โดยระบุข้อความ ลักษณะ และรูปแบบแบบอักษร

## ขั้นตอนที่ 5: ปรับแต่งเส้นกริดหลัก

ตอนนี้ เรามาปรับแต่งเส้นกริดหลักสำหรับแกนค่ากัน

```csharp
// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนค่า
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

ขั้นตอนนี้จะกำหนดค่าลักษณะที่ปรากฏของเส้นกริดหลักบนแกนค่า

## ขั้นตอนที่ 6: ปรับแต่งเส้นกริดรอง

ในทำนองเดียวกัน เราสามารถปรับแต่งเส้นกริดรองสำหรับแกนค่าได้

```csharp
// การตั้งค่ารูปแบบเส้นกริดรองสำหรับแกนค่า
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

รหัสนี้จะปรับลักษณะของเส้นกริดรองบนแกนค่า

## ขั้นตอนที่ 7: กำหนดรูปแบบตัวเลขแกนค่า

ปรับแต่งรูปแบบตัวเลขสำหรับแกนค่า

```csharp
// การตั้งค่ารูปแบบตัวเลขแกนค่า
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

ขั้นตอนนี้ช่วยให้คุณสามารถจัดรูปแบบตัวเลขที่แสดงบนแกนค่าได้

## ขั้นตอนที่ 8: ตั้งค่าแผนภูมิสูงสุดและต่ำสุด

กำหนดค่าสูงสุดและต่ำสุดสำหรับแผนภูมิ

```csharp
// การตั้งค่ากราฟสูงสุดและค่าต่ำสุด
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

ที่นี่ คุณจะระบุช่วงของค่าที่แกนแผนภูมิควรแสดง

## ขั้นตอนที่ 9: ปรับแต่งคุณสมบัติข้อความแกนค่า

คุณยังสามารถปรับแต่งคุณสมบัติข้อความของแกนค่าได้อีกด้วย

```csharp
// การตั้งค่าคุณสมบัติข้อความแกนค่า
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

รหัสนี้ช่วยให้คุณสามารถปรับลักษณะแบบอักษรและรูปลักษณ์ของป้ายกำกับแกนค่าได้

## ขั้นตอนที่ 10: เพิ่มชื่อแกนค่า

หากแผนภูมิของคุณต้องการชื่อสำหรับแกนค่า คุณสามารถเพิ่มได้ด้วยขั้นตอนนี้

```csharp
// การตั้งค่าชื่อแกนค่า
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

ในขั้นตอนนี้ คุณสามารถตั้งชื่อให้กับแกนค่าได้

## ขั้นตอนที่ 11: ปรับแต่งเส้นกริดหลักสำหรับแกนหมวดหมู่

ตอนนี้ เรามาเน้นที่เส้นตารางหลักสำหรับแกนหมวดหมู่กัน

```csharp
// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนหมวดหมู่
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

รหัสนี้กำหนดค่าลักษณะที่ปรากฏของเส้นตารางหลักบนแกนหมวดหมู่

## ขั้นตอนที่ 12: ปรับแต่งเส้นกริดรองสำหรับแกนหมวดหมู่

เช่นเดียวกับแกนค่า คุณสามารถปรับแต่งเส้นตารางรองสำหรับแกนประเภทได้

```csharp
// การตั้งค่ารูปแบบเส้นตารางรองสำหรับแกนประเภท
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

ที่นี่ คุณจะปรับลักษณะของเส้นกริดรองบนแกนหมวดหมู่ได้

## ขั้นตอนที่ 13: ปรับแต่งคุณสมบัติข้อความแกนหมวดหมู่

ปรับแต่งคุณสมบัติข้อความสำหรับป้ายกำกับแกนหมวดหมู่

```csharp
// การตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

รหัสนี้ช่วยให้คุณปรับลักษณะแบบอักษรและรูปลักษณ์ของป้ายกำกับแกนหมวดหมู่ได้

## ขั้นตอนที่ 14: เพิ่มชื่อแกนหมวดหมู่

คุณยังสามารถเพิ่มชื่อเรื่องลงในแกนหมวดหมู่ได้หากจำเป็น

```csharp
// การตั้งค่าหัวข้อหมวดหมู่
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

ในขั้นตอนนี้ คุณสามารถตั้งชื่อให้กับแกนประเภทได้

## ขั้นตอนที่ 15: การปรับแต่งเพิ่มเติม

คุณสามารถสำรวจการปรับแต่งเพิ่มเติมได้ เช่น คำอธิบายแผนภูมิ ผนังด้านหลัง พื้น และสีพื้นที่พล็อต การปรับแต่งเหล่านี้ทำให้คุณสามารถเพิ่มความสวยงามให้กับแผนภูมิของคุณได้

```csharp
// การปรับแต่งเพิ่มเติม (ไม่บังคับ)

// การตั้งค่าคุณสมบัติข้อความตำนาน
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// ตั้งค่าคำอธิบายแผนภูมิการแสดงโดยไม่ทับซ้อนกัน
chart.Legend.Overlay = true;

// การพล็อตอนุกรมแรกบนแกนค่าทุติยภูมิ (หากจำเป็น)
// Chart.ChartData.Series[0].PlotOnSecondAxis = จริง;

// การตั้งค่าแผนภูมิสีผนังด้านหลัง
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// การตั้งค่าสีพื้นแผนภูมิ
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//การตั้งค่าสีพื้นที่พล็อต
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// บันทึกการนำเสนอ
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

การปรับแต่งเพิ่มเติมเหล่านี้เป็นทางเลือกและสามารถนำมาใช้ได้ตามความต้องการในการออกแบบแผนภูมิเฉพาะของคุณ

## บทสรุป

ในคำแนะนำทีละขั้นตอนนี้ เราได้สำรวจการปรับแต่งแผนภูมิขั้นสูงโดยใช้ Aspose.Slides สำหรับ .NET คุณได้เรียนรู้วิธีสร้างงานนำเสนอ เพิ่มแผนภูมิ และปรับแต่งรูปลักษณ์ รวมถึงเส้นตาราง ป้ายชื่อแกน และองค์ประกอบภาพอื่นๆ ด้วยตัวเลือกการปรับแต่งอันทรงพลังจาก Aspose.Slides คุณสามารถสร้างแผนภูมิที่ถ่ายทอดข้อมูลของคุณได้อย่างมีประสิทธิภาพและดึงดูดผู้ชมของคุณ

 หากคุณมีคำถามหรือเผชิญกับความท้าทายใดๆ ในขณะที่ทำงานกับ Aspose.Slides สำหรับ .NET โปรดอ่านเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/net/) หรือขอความช่วยเหลือใน Aspose.Slides[ฟอรั่ม](https://forum.aspose.com/).

## คำถามที่พบบ่อย

### Aspose.Slides สำหรับ .NET รองรับ .NET เวอร์ชันใดบ้าง
Aspose.Slides สำหรับ .NET รองรับ .NET เวอร์ชันต่างๆ รวมถึง .NET Framework และ .NET Core คุณสามารถดูเอกสารประกอบเพื่อดูรายการเวอร์ชันที่รองรับทั้งหมด

### ฉันสามารถสร้างแผนภูมิจากแหล่งข้อมูล เช่น ไฟล์ Excel โดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET ช่วยให้คุณสร้างแผนภูมิจากแหล่งข้อมูลภายนอก เช่น สเปรดชีต Excel คุณสามารถสำรวจเอกสารประกอบเพื่อดูตัวอย่างโดยละเอียด

### ฉันจะเพิ่มป้ายกำกับข้อมูลที่กำหนดเองลงในชุดแผนภูมิของฉันได้อย่างไร
 หากต้องการเพิ่มป้ายกำกับข้อมูลที่กำหนดเองให้กับชุดแผนภูมิของคุณ คุณสามารถเข้าถึง`DataLabels` คุณสมบัติของซีรีส์และปรับแต่งป้ายกำกับได้ตามต้องการ โปรดดูเอกสารประกอบสำหรับตัวอย่างโค้ดและตัวอย่าง

### เป็นไปได้ไหมที่จะส่งออกแผนภูมิเป็นรูปแบบไฟล์ต่างๆ เช่น PDF หรือรูปแบบรูปภาพ
ใช่ Aspose.Slides สำหรับ .NET มีตัวเลือกในการส่งออกงานนำเสนอของคุณด้วยแผนภูมิเป็นรูปแบบต่างๆ รวมถึง PDF และรูปแบบรูปภาพ คุณสามารถใช้ไลบรารีเพื่อบันทึกงานของคุณในรูปแบบเอาต์พุตที่ต้องการได้

### ฉันจะหาบทช่วยสอนและตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณจะพบบทช่วยสอน ตัวอย่างโค้ด และเอกสารประกอบมากมายได้ใน Aspose.Slides[เว็บไซต์](https://reference.aspose.com/slides/net/).