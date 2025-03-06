---
title: สำรวจเส้นแนวโน้มแผนภูมิใน Aspose.Slides สำหรับ .NET
linktitle: เส้นแนวโน้มแผนภูมิ
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มเส้นแนวโน้มต่างๆ ลงในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET ในคำแนะนำทีละขั้นตอนนี้ เสริมทักษะการแสดงภาพข้อมูลของคุณได้อย่างง่ายดาย!
weight: 12
url: /th/net/advanced-chart-customization/chart-trend-lines/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


ในโลกของการแสดงข้อมูลเป็นภาพและการนำเสนอ การรวมแผนภูมิเข้าด้วยกันอาจเป็นวิธีที่มีประสิทธิภาพในการถ่ายทอดข้อมูลอย่างมีประสิทธิภาพ Aspose.Slides สำหรับ .NET มีชุดเครื่องมือที่มีคุณสมบัติหลากหลายเพื่อทำงานกับแผนภูมิ รวมถึงความสามารถในการเพิ่มเส้นแนวโน้มลงในแผนภูมิของคุณ ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเพิ่มเส้นแนวโน้มลงในแผนภูมิทีละขั้นตอนโดยใช้ Aspose.Slides สำหรับ .NET 

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มทำงานกับ Aspose.Slides สำหรับ .NET คุณจะต้องแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Aspose.Slides สำหรับ .NET: หากต้องการเข้าถึงไลบรารีและใช้งาน คุณต้องติดตั้ง Aspose.Slides สำหรับ .NET คุณสามารถรับห้องสมุดได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/net/).

2. สภาพแวดล้อมการพัฒนา: คุณควรมีการตั้งค่าสภาพแวดล้อมการพัฒนา โดยควรใช้สภาพแวดล้อมการพัฒนาแบบรวม .NET เช่น Visual Studio

3. ความรู้พื้นฐานเกี่ยวกับ C#: ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C# มีประโยชน์ เนื่องจากเราจะใช้ C# เพื่อทำงานกับ Aspose.Slides สำหรับ .NET

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว เรามาแจกแจงขั้นตอนการเพิ่มเส้นแนวโน้มลงในแผนภูมิทีละขั้นตอนกัน

## การนำเข้าเนมสเปซ

ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ เนมสเปซเหล่านี้จำเป็นสำหรับการทำงานกับ Aspose.Slides สำหรับ .NET

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ในขั้นตอนนี้ เราจะสร้างงานนำเสนอเปล่าเพื่อใช้งาน

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างไดเร็กทอรีหากไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์

ต่อไป เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์

```csharp
// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ขั้นตอนที่ 3: เพิ่มเส้นแนวโน้มลงในแผนภูมิ

ตอนนี้ เราได้เพิ่มเส้นแนวโน้มประเภทต่างๆ ลงในชุดแผนภูมิ

### การเพิ่มเส้นแนวโน้มเอ็กซ์โปเนนเชียล

```csharp
// การเพิ่มเส้นแนวโน้มเอ็กซ์โพเนนเชียลสำหรับแผนภูมิชุดที่ 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### การเพิ่มเส้นแนวโน้มเชิงเส้น

```csharp
// การเพิ่มเส้นแนวโน้มเชิงเส้นสำหรับแผนภูมิชุดที่ 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### การเพิ่มเส้นแนวโน้มลอการิทึม

```csharp
// การเพิ่มเส้นแนวโน้มลอการิทึมสำหรับแผนภูมิชุดที่ 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่

```csharp
// การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่สำหรับแผนภูมิชุดที่ 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### การเพิ่มเส้นแนวโน้มพหุนาม

```csharp
// การเพิ่มเส้นแนวโน้มพหุนามสำหรับแผนภูมิชุดที่ 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### การเพิ่มเส้นแนวโน้มกำลัง

```csharp
// การเพิ่มเส้นแนวโน้มกำลังสำหรับแผนภูมิชุดที่ 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

หลังจากเพิ่มเส้นแนวโน้มลงในแผนภูมิแล้ว ให้บันทึกงานนำเสนอ

```csharp
// กำลังบันทึกการนำเสนอ
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้เพิ่มเส้นแนวโน้มต่างๆ ลงในแผนภูมิของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET

## บทสรุป

Aspose.Slides สำหรับ .NET เป็นไลบรารีอเนกประสงค์ที่ช่วยให้คุณสามารถสร้างและจัดการแผนภูมิได้อย่างง่ายดาย ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะสามารถเพิ่มเส้นแนวโน้มประเภทต่างๆ ลงในแผนภูมิได้ ซึ่งจะช่วยปรับปรุงการแสดงข้อมูลของคุณด้วยภาพ

### คำถามที่พบบ่อย

### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถเข้าถึงเอกสารประกอบ[ที่นี่](https://reference.aspose.com/slides/net/).

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จากหน้าดาวน์โหลด[ที่นี่](https://releases.aspose.com/slides/net/).

### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 ใช่ คุณสามารถลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรีโดยไปที่[ลิงค์นี้](https://releases.aspose.com/).

### ฉันจะซื้อ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 หากต้องการซื้อ Aspose.Slides สำหรับ .NET โปรดไปที่หน้าการซื้อ[ที่นี่](https://purchase.aspose.com/buy).

### ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
 คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้จาก[ลิงค์นี้](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
