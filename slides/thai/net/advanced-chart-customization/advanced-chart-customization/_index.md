---
"description": "เรียนรู้การปรับแต่งแผนภูมิขั้นสูงใน Aspose.Slides สำหรับ .NET สร้างแผนภูมิที่ดึงดูดสายตาด้วยคำแนะนำทีละขั้นตอน"
"linktitle": "การปรับแต่งแผนภูมิขั้นสูงใน Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การปรับแต่งแผนภูมิขั้นสูงใน Aspose.Slides"
"url": "/th/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การปรับแต่งแผนภูมิขั้นสูงใน Aspose.Slides


การสร้างแผนภูมิที่ดึงดูดสายตาและให้ข้อมูลถือเป็นส่วนสำคัญของการนำเสนอข้อมูลในแอปพลิเคชันต่างๆ Aspose.Slides สำหรับ .NET มอบเครื่องมือที่มีประสิทธิภาพสำหรับการปรับแต่งแผนภูมิ ช่วยให้คุณปรับแต่งทุกแง่มุมของแผนภูมิของคุณได้อย่างละเอียด ในบทช่วยสอนนี้ เราจะมาสำรวจเทคนิคการปรับแต่งแผนภูมิขั้นสูงโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำเนินการปรับแต่งแผนภูมิขั้นสูงด้วย Aspose.Slides สำหรับ .NET โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Aspose.Slides สำหรับไลบรารี .NET: คุณต้องติดตั้งไลบรารี Aspose.Slides และกำหนดค่าอย่างถูกต้องในโปรเจ็กต์ .NET ของคุณ คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).

2. สภาพแวดล้อมการพัฒนา .NET: คุณควรมีการตั้งค่าสภาพแวดล้อมการพัฒนา .NET ไว้ รวมถึง Visual Studio หรือ IDE อื่นๆ ที่คุณเลือก

3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ เนื่องจากเราจะเขียนโค้ด C# เพื่อใช้กับ Aspose.Slides

ตอนนี้ มาแบ่งการปรับแต่งแผนภูมิขั้นสูงออกเป็นหลายขั้นตอนเพื่อเป็นแนวทางให้คุณตลอดกระบวนการ

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก ให้สร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างไดเร็กทอรีหากยังไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// การสร้างตัวอย่างการนำเสนอ
Presentation pres = new Presentation();
```

ในขั้นตอนนี้ เราจะเริ่มต้นการนำเสนอใหม่ซึ่งจะมีแผนภูมิของเรา

## ขั้นตอนที่ 2: เข้าถึงสไลด์แรก

ขั้นตอนต่อไปคือเข้าถึงสไลด์แรกในงานนำเสนอที่คุณต้องการเพิ่มแผนภูมิ

```csharp
// การเข้าถึงสไลด์แรก
ISlide slide = pres.Slides[0];
```

โค้ดชิ้นนี้ทำให้คุณสามารถทำงานกับสไลด์แรกของการนำเสนอได้

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิตัวอย่าง

ตอนนี้เรามาเพิ่มแผนภูมิตัวอย่างลงในสไลด์กัน ในตัวอย่างนี้ เราจะสร้างแผนภูมิเส้นพร้อมเครื่องหมาย

```csharp
// การเพิ่มแผนภูมิตัวอย่าง
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

ที่นี่ เราจะระบุประเภทของแผนภูมิ (LineWithMarkers) และตำแหน่งและมิติบนสไลด์

## ขั้นตอนที่ 4: ตั้งชื่อแผนภูมิ

เรามาตั้งชื่อแผนภูมิกันเพื่อให้เข้าใจบริบท

```csharp
// ตั้งค่าชื่อแผนภูมิ
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

โค้ดนี้จะตั้งชื่อให้กับแผนภูมิ โดยระบุข้อความ ลักษณะที่ปรากฏ และรูปแบบอักษร

## ขั้นตอนที่ 5: ปรับแต่งเส้นกริดหลัก

ตอนนี้ มาปรับแต่งเส้นกริดหลักของแกนค่ากัน

```csharp
// การตั้งค่ารูปแบบเส้นกริดหลักสำหรับแกนค่า
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

ขั้นตอนนี้จะกำหนดค่าลักษณะที่ปรากฏของเส้นกริดหลักบนแกนค่า

## ขั้นตอนที่ 6: ปรับแต่งเส้นกริดย่อย

ในทำนองเดียวกัน เราสามารถปรับแต่งเส้นกริดรองสำหรับแกนค่าได้

```csharp
// การตั้งค่ารูปแบบเส้นกริดย่อยสำหรับแกนค่า
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

โค้ดนี้จะปรับลักษณะที่ปรากฏของเส้นกริดรองบนแกนค่า

## ขั้นตอนที่ 7: กำหนดรูปแบบตัวเลขแกนค่า

ปรับแต่งรูปแบบตัวเลขสำหรับแกนค่า

```csharp
// ตั้งค่ารูปแบบหมายเลขแกนค่า
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

ขั้นตอนนี้ช่วยให้คุณจัดรูปแบบตัวเลขที่แสดงบนแกนค่าได้

## ขั้นตอนที่ 8: ตั้งค่าสูงสุดและต่ำสุดของแผนภูมิ

กำหนดค่าสูงสุดและต่ำสุดสำหรับแผนภูมิ

```csharp
// แผนภูมิการตั้งค่าค่าสูงสุดและต่ำสุด
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

ที่นี่คุณระบุช่วงค่าที่แกนแผนภูมิควรจะแสดง

## ขั้นตอนที่ 9: ปรับแต่งคุณสมบัติข้อความแกนค่า

คุณยังสามารถปรับแต่งคุณสมบัติข้อความของแกนค่าได้

```csharp
// ตั้งค่าคุณสมบัติข้อความแกนค่า
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

โค้ดนี้ช่วยให้คุณปรับเปลี่ยนรูปแบบอักษรและลักษณะของป้ายแกนค่าได้

## ขั้นตอนที่ 10: เพิ่มชื่อแกนค่า

หากแผนภูมิของคุณต้องการชื่อสำหรับแกนค่า คุณสามารถเพิ่มได้ด้วยขั้นตอนนี้

```csharp
// ตั้งค่าชื่อแกนค่า
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

ตอนนี้ เรามาดูเส้นกริดหลักของแกนหมวดหมู่กัน

```csharp
// การตั้งค่ารูปแบบเส้นกริดหลักสำหรับแกนหมวดหมู่
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

โค้ดนี้จะกำหนดค่าลักษณะที่ปรากฏของเส้นกริดหลักบนแกนหมวดหมู่

## ขั้นตอนที่ 12: ปรับแต่งเส้นกริดย่อยสำหรับแกนหมวดหมู่

คล้ายกับแกนค่า คุณสามารถปรับแต่งเส้นกริดรองสำหรับแกนหมวดหมู่ได้

```csharp
// การตั้งค่ารูปแบบเส้นกริดย่อยสำหรับแกนหมวดหมู่
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

ที่นี่คุณปรับแต่งลักษณะของเส้นกริดรองบนแกนหมวดหมู่

## ขั้นตอนที่ 13: ปรับแต่งคุณสมบัติข้อความแกนหมวดหมู่

ปรับแต่งคุณสมบัติข้อความสำหรับป้ายแกนหมวดหมู่

```csharp
// ตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

โค้ดนี้ช่วยให้คุณปรับแต่งรูปแบบแบบอักษรและลักษณะของป้ายแกนหมวดหมู่ได้

## ขั้นตอนที่ 14: เพิ่มชื่อแกนหมวดหมู่

คุณสามารถเพิ่มชื่อให้กับแกนหมวดหมู่ได้หากจำเป็น

```csharp
// การตั้งค่าหมวดหมู่ชื่อเรื่อง
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

ในขั้นตอนนี้ คุณสามารถตั้งชื่อให้กับแกนหมวดหมู่ได้

## ขั้นตอนที่ 15: การปรับแต่งเพิ่มเติม

คุณสามารถสำรวจการปรับแต่งเพิ่มเติมได้ เช่น คำอธิบาย สีของผนังด้านหลังแผนภูมิ พื้น และบริเวณแปลง การปรับแต่งเหล่านี้ช่วยให้คุณปรับปรุงความสวยงามของแผนภูมิได้

```csharp
// การปรับแต่งเพิ่มเติม (ทางเลือก)

// การตั้งค่าคุณสมบัติข้อความตำนาน
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// ตั้งค่าคำอธิบายแผนภูมิการแสดงโดยไม่ให้แผนภูมิทับซ้อนกัน
chart.Legend.Overlay = true;

// การวางแผนชุดแรกบนแกนค่ารอง (ถ้าจำเป็น)
// แผนภูมิ.ChartData.Series[0].PlotOnSecondAxis = true;

// แผนภูมิการตั้งค่าสีผนังด้านหลัง
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// แผนภูมิการตั้งค่าสีพื้น
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// การตั้งค่าสีพื้นที่พล็อต
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// บันทึกการนำเสนอ
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

การปรับแต่งเพิ่มเติมเหล่านี้เป็นทางเลือกและสามารถนำไปใช้ตามความต้องการในการออกแบบแผนภูมิเฉพาะของคุณได้

## บทสรุป

ในคู่มือทีละขั้นตอนนี้ เราได้สำรวจการปรับแต่งแผนภูมิขั้นสูงโดยใช้ Aspose.Slides สำหรับ .NET คุณได้เรียนรู้วิธีการสร้างงานนำเสนอ เพิ่มแผนภูมิ และปรับแต่งรูปลักษณ์ของแผนภูมิ รวมถึงเส้นตาราง ป้ายแกน และองค์ประกอบภาพอื่นๆ ด้วยตัวเลือกการปรับแต่งอันทรงพลังที่ Aspose.Slides จัดเตรียมไว้ คุณสามารถสร้างแผนภูมิที่ถ่ายทอดข้อมูลของคุณได้อย่างมีประสิทธิภาพและดึงดูดผู้ชมของคุณ

หากคุณมีคำถามหรือพบความท้าทายใดๆ ระหว่างใช้งาน Aspose.Slides สำหรับ .NET โปรดอ่านเอกสารประกอบ [ที่นี่](https://reference.aspose.com/slides/net/) หรือขอความช่วยเหลือได้ที่ Aspose.Slides [ฟอรั่ม](https://forum-aspose.com/).

## คำถามที่พบบ่อย

### Aspose.Slides รองรับ .NET เวอร์ชันใดบ้างสำหรับ .NET?
Aspose.Slides สำหรับ .NET รองรับ .NET เวอร์ชันต่างๆ รวมถึง .NET Framework และ .NET Core คุณสามารถดูรายการเวอร์ชันที่รองรับทั้งหมดได้ในเอกสารประกอบ

### ฉันสามารถสร้างแผนภูมิจากแหล่งข้อมูล เช่น ไฟล์ Excel โดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET ช่วยให้คุณสร้างแผนภูมิจากแหล่งข้อมูลภายนอก เช่น สเปรดชีต Excel คุณสามารถศึกษาเอกสารประกอบเพื่อดูตัวอย่างโดยละเอียดได้

### ฉันจะเพิ่มป้ายข้อมูลแบบกำหนดเองลงในชุดแผนภูมิของฉันได้อย่างไร
หากต้องการเพิ่มป้ายข้อมูลที่กำหนดเองลงในชุดแผนภูมิของคุณ คุณสามารถเข้าถึง `DataLabels` คุณสมบัติของซีรีส์และปรับแต่งป้ายกำกับตามต้องการ ดูตัวอย่างโค้ดและตัวอย่างอื่นๆ ในเอกสารประกอบ

### สามารถส่งออกแผนภูมิไปยังรูปแบบไฟล์อื่น เช่น PDF หรือรูปแบบรูปภาพได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET มีตัวเลือกในการส่งออกงานนำเสนอของคุณพร้อมแผนภูมิไปยังรูปแบบต่างๆ รวมถึง PDF และรูปแบบรูปภาพ คุณสามารถใช้ไลบรารีเพื่อบันทึกงานของคุณในรูปแบบเอาต์พุตที่ต้องการได้

### ฉันสามารถหาบทช่วยสอนและตัวอย่างเพิ่มเติมสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
คุณสามารถค้นหาบทช่วยสอน ตัวอย่างโค้ด และเอกสารประกอบมากมายได้ที่ Aspose.Slides [เว็บไซต์](https://reference-aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}