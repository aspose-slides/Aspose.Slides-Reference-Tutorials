---
"description": "เรียนรู้วิธีการเพิ่มเส้นแนวโน้มต่างๆ ลงในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET ในคู่มือทีละขั้นตอนนี้ พัฒนาทักษะการแสดงภาพข้อมูลของคุณได้อย่างง่ายดาย!"
"linktitle": "เส้นแนวโน้มของแผนภูมิ"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การสำรวจเส้นแนวโน้มของแผนภูมิใน Aspose.Slides สำหรับ .NET"
"url": "/th/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสำรวจเส้นแนวโน้มของแผนภูมิใน Aspose.Slides สำหรับ .NET


ในโลกแห่งการแสดงข้อมูลและการนำเสนอ การรวมแผนภูมิเข้าด้วยกันถือเป็นวิธีที่มีประสิทธิภาพในการถ่ายทอดข้อมูล Aspose.Slides สำหรับ .NET มอบชุดเครื่องมือที่อัดแน่นไปด้วยคุณสมบัติต่างๆ สำหรับการทำงานกับแผนภูมิ รวมถึงความสามารถในการเพิ่มเส้นแนวโน้มลงในแผนภูมิของคุณ ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเพิ่มเส้นแนวโน้มลงในแผนภูมิทีละขั้นตอนโดยใช้ Aspose.Slides สำหรับ .NET 

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มทำงานกับ Aspose.Slides สำหรับ .NET คุณจะต้องแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Aspose.Slides สำหรับ .NET: หากต้องการเข้าถึงและใช้งานไลบรารี คุณต้องติดตั้ง Aspose.Slides สำหรับ .NET คุณสามารถรับไลบรารีได้จาก [หน้าดาวน์โหลด](https://releases-aspose.com/slides/net/).

2. สภาพแวดล้อมการพัฒนา: คุณควรมีการตั้งค่าสภาพแวดล้อมการพัฒนา โดยควรใช้สภาพแวดล้อมการพัฒนาแบบบูรณาการ .NET เช่น Visual Studio

3. ความรู้พื้นฐานเกี่ยวกับ C#: ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C# จะเป็นประโยชน์เนื่องจากเราจะใช้ C# เพื่อทำงานกับ Aspose.Slides สำหรับ .NET

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว มาแยกขั้นตอนในการเพิ่มเส้นแนวโน้มลงในแผนภูมิทีละขั้นตอนกัน

## การนำเข้าเนมสเปซ

ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นไปยังโปรเจ็กต์ C# ของคุณแล้ว เนมสเปซเหล่านี้มีความจำเป็นสำหรับการทำงานกับ Aspose.Slides สำหรับ .NET

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ในขั้นตอนนี้ เราจะสร้างการนำเสนอเปล่าเพื่อใช้ในการทำงาน

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างไดเร็กทอรีหากยังไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// การสร้างการนำเสนอแบบว่างเปล่า
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์

ถัดไป เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์

```csharp
// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## ขั้นตอนที่ 3: เพิ่มเส้นแนวโน้มลงในแผนภูมิ

ตอนนี้ เรากำลังเพิ่มเส้นแนวโน้มประเภทต่างๆ ลงในชุดแผนภูมิ

### การเพิ่มเส้นแนวโน้มแบบเอ็กซ์โพเนนเชียล

```csharp
// การเพิ่มเส้นแนวโน้มเลขชี้กำลังให้กับชุดแผนภูมิที่ 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### การเพิ่มเส้นแนวโน้มเชิงเส้น

```csharp
// การเพิ่มเส้นแนวโน้มเชิงเส้นให้กับชุดแผนภูมิที่ 1
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
// การเพิ่มเส้นแนวโน้มค่าเฉลี่ยเคลื่อนที่สำหรับชุดแผนภูมิที่ 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### การเพิ่มเส้นแนวโน้มพหุนาม

```csharp
// การเพิ่มเส้นแนวโน้มพหุนามสำหรับชุดแผนภูมิที่ 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### การเพิ่มเส้นแนวโน้มพลัง

```csharp
// การเพิ่มเส้นแนวโน้มพลังให้กับแผนภูมิชุดที่ 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

หลังจากเพิ่มเส้นแนวโน้มลงในแผนภูมิแล้ว ให้บันทึกการนำเสนอ

```csharp
// บันทึกการนำเสนอ
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณเพิ่มเส้นแนวโน้มต่างๆ ลงในแผนภูมิได้สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ .NET

## บทสรุป

Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีความยืดหยุ่นซึ่งช่วยให้คุณสร้างและจัดการแผนภูมิได้อย่างง่ายดาย โดยทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถเพิ่มเส้นแนวโน้มประเภทต่างๆ ลงในแผนภูมิของคุณได้ ซึ่งจะช่วยปรับปรุงการแสดงภาพข้อมูลของคุณ

### คำถามที่พบบ่อย

### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
คุณสามารถเข้าถึงเอกสารได้ [ที่นี่](https://reference-aspose.com/slides/net/).

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร?
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จากหน้าดาวน์โหลด [ที่นี่](https://releases-aspose.com/slides/net/).

### มี Aspose.Slides สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรีโดยเข้าไปที่ [ลิงค์นี้](https://releases-aspose.com/).

### ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้จากที่ใด
หากต้องการซื้อ Aspose.Slides สำหรับ .NET โปรดไปที่หน้าการซื้อ [ที่นี่](https://purchase-aspose.com/buy).

### ฉันต้องมีใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET หรือไม่?
คุณสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้จาก [ลิงค์นี้](https://purchase-aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}