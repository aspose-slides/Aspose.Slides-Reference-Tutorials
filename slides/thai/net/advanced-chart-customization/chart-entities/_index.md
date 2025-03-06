---
title: การสร้างแผนภูมิที่สวยงามด้วย Aspose.Slides สำหรับ .NET
linktitle: เอนทิตีแผนภูมิและการจัดรูปแบบ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิที่น่าทึ่งด้วย Aspose.Slides สำหรับ .NET ยกระดับเกมการแสดงภาพข้อมูลของคุณด้วยคำแนะนำทีละขั้นตอนของเรา
weight: 13
url: /th/net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


ในโลกที่ขับเคลื่อนด้วยข้อมูลในปัจจุบัน การแสดงภาพข้อมูลที่มีประสิทธิภาพเป็นกุญแจสำคัญในการถ่ายทอดข้อมูลไปยังผู้ชมของคุณ Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสามารถสร้างงานนำเสนอและสไลด์ที่น่าทึ่ง รวมถึงแผนภูมิที่สะดุดตา ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างแผนภูมิที่สวยงามโดยใช้ Aspose.Slides สำหรับ .NET เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนเพื่อช่วยให้คุณเข้าใจและใช้งานเอนทิตีแผนภูมิและการจัดรูปแบบ เอาล่ะ มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกในการสร้างแผนภูมิที่สวยงามด้วย Aspose.Slides สำหรับ .NET คุณจะต้องแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/slides/net/).

2. สภาพแวดล้อมการพัฒนา: คุณควรมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้กับ Visual Studio หรือ IDE อื่น ๆ ที่รองรับการพัฒนา .NET

3. ความรู้พื้นฐาน C#: ความคุ้นเคยกับการเขียนโปรแกรม C# เป็นสิ่งจำเป็นสำหรับบทช่วยสอนนี้

ตอนนี้เราได้เรียงลำดับข้อกำหนดเบื้องต้นแล้ว เรามาสร้างแผนภูมิที่สวยงามด้วย Aspose.Slides สำหรับ .NET กันดีกว่า

## นำเข้าเนมสเปซ

ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides สำหรับ .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

เราเริ่มต้นด้วยการสร้างงานนำเสนอใหม่เพื่อใช้งาน การนำเสนอนี้จะทำหน้าที่เป็นผืนผ้าใบสำหรับแผนภูมิของเรา

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

## ขั้นตอนที่ 2: เข้าถึงสไลด์แรก

เรามาเข้าสู่สไลด์แรกในการนำเสนอซึ่งเราจะวางแผนภูมิของเรากัน

```csharp
// การเข้าถึงสไลด์แรก
ISlide slide = pres.Slides[0];
```

## ขั้นตอนที่ 3: เพิ่มแผนภูมิตัวอย่าง

ตอนนี้ เราจะเพิ่มแผนภูมิตัวอย่างลงในสไลด์ของเรา ในตัวอย่างนี้ เราจะสร้างแผนภูมิเส้นพร้อมเครื่องหมาย

```csharp
// การเพิ่มแผนภูมิตัวอย่าง
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## ขั้นตอนที่ 4: ตั้งชื่อแผนภูมิ

เราจะตั้งชื่อแผนภูมิของเรา เพื่อให้มีข้อมูลมากขึ้นและดึงดูดสายตา

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

## ขั้นตอนที่ 5: ปรับแต่งเส้นตารางแกนตั้ง

ในขั้นตอนนี้ เราจะปรับแต่งเส้นตารางของแกนแนวตั้งเพื่อทำให้แผนภูมิของเราดูน่าดึงดูดยิ่งขึ้น

```csharp
// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนค่า
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// การตั้งค่ารูปแบบเส้นกริดรองสำหรับแกนค่า
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// การตั้งค่ารูปแบบตัวเลขแกนค่า
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## ขั้นตอนที่ 6: กำหนดช่วงแกนตั้ง

ในขั้นตอนนี้ เราจะตั้งค่าสูงสุด ต่ำสุด และหน่วยสำหรับแกนตั้ง

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

## ขั้นตอนที่ 7: ปรับแต่งข้อความแกนตั้ง

ตอนนี้เราจะปรับแต่งลักษณะที่ปรากฏของข้อความบนแกนตั้ง

```csharp
// การตั้งค่าคุณสมบัติข้อความแกนค่า
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

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

## ขั้นตอนที่ 8: ปรับแต่งเส้นตารางแกนนอน

ตอนนี้ เรามาปรับแต่งเส้นกริดสำหรับแกนนอนกัน

```csharp
// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนหมวดหมู่
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// การตั้งค่ารูปแบบเส้นตารางรองสำหรับแกนประเภท
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// การตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## ขั้นตอนที่ 9: ปรับแต่งป้ายกำกับแกนนอน

ในขั้นตอนนี้ เราจะปรับตำแหน่งและการหมุนของป้ายกำกับแกนนอน

```csharp
// การตั้งค่าตำแหน่งป้ายกำกับแกนหมวดหมู่
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// การตั้งค่ามุมการหมุนฉลากแกนหมวดหมู่
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## ขั้นตอนที่ 10: ปรับแต่งตำนาน

มาปรับปรุงคำอธิบายแผนภูมิในแผนภูมิของเราเพื่อให้อ่านง่ายขึ้น

```csharp
// การตั้งค่าคุณสมบัติข้อความตำนาน
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// ตั้งค่าคำอธิบายแผนภูมิการแสดงโดยไม่ทับซ้อนกัน
chart.Legend.Overlay = true;
```

## ขั้นตอนที่ 11: ปรับแต่งพื้นหลังแผนภูมิ

เราจะปรับแต่งสีพื้นหลังของแผนภูมิ ผนังด้านหลัง และพื้น

```csharp
// การตั้งค่าแผนภูมิสีผนังด้านหลัง
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//การตั้งค่าสีพื้นที่พล็อต
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## ขั้นตอนที่ 12: บันทึกการนำเสนอ

สุดท้ายนี้ มาบันทึกงานนำเสนอของเราด้วยแผนภูมิที่จัดรูปแบบแล้ว

```csharp
// บันทึกการนำเสนอ
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

การสร้างแผนภูมิที่สวยงามและให้ข้อมูลในงานนำเสนอของคุณง่ายกว่าที่เคยด้วย Aspose.Slides สำหรับ .NET ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญในการปรับแต่งแง่มุมต่างๆ ของแผนภูมิ ทำให้ดูน่าสนใจและให้ข้อมูล ด้วยเทคนิคเหล่านี้ คุณสามารถสร้างแผนภูมิที่น่าทึ่งซึ่งถ่ายทอดข้อมูลของคุณไปยังผู้ชมได้อย่างมีประสิทธิภาพ

เริ่มการทดลองกับ Aspose.Slides สำหรับ .NET และยกระดับการแสดงภาพข้อมูลของคุณไปอีกระดับ!

## คำถามที่พบบ่อย

### 1. Aspose.Slides สำหรับ .NET คืออะไร

Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนา .NET สามารถสร้าง จัดการ และแปลงงานนำเสนอ Microsoft PowerPoint โดยมีคุณสมบัติที่หลากหลายสำหรับการทำงานกับสไลด์ รูปร่าง แผนภูมิ และอื่นๆ

### 2. ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้ที่ไหน

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จากเว็บไซต์[ที่นี่](https://releases.aspose.com/slides/net/).

### 3. Aspose.Slides สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่

 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### 4. ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร

 หากคุณต้องการใบอนุญาตชั่วคราว คุณสามารถขอรับได้จาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).

### 5. มีชุมชนหรือฟอรัมสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET หรือไม่

 ใช่ คุณสามารถค้นหาชุมชน Aspose.Slides และฟอรัมสนับสนุนได้[ที่นี่](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
