---
"date": "2025-04-15"
"description": "เรียนรู้การกำหนดค่าชื่อแผนภูมิ แกน และคำอธิบายแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET คู่มือนี้ครอบคลุมทุกอย่างตั้งแต่การตั้งค่าพื้นฐานจนถึงการปรับแต่งขั้นสูง"
"title": "การกำหนดค่าแผนภูมิหลักใน .NET ด้วย Aspose.Slides และคู่มือฉบับสมบูรณ์"
"url": "/th/net/charts-graphs/master-chart-configuration-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การเรียนรู้การกำหนดค่าแผนภูมิใน .NET ด้วย Aspose.Slides

## การแนะนำ
การสร้างแผนภูมิที่ดึงดูดสายตาและให้ข้อมูลเป็นสิ่งสำคัญสำหรับการนำเสนอข้อมูลอย่างมีประสิทธิภาพ ไม่ว่าคุณจะกำลังเตรียมรายงานทางธุรกิจหรือการนำเสนอทางเทคนิค การกำหนดค่าชื่อและแกนของแผนภูมิสามารถปรับปรุงการอ่านและผลกระทบได้อย่างมาก คู่มือที่ครอบคลุมนี้จะแนะนำคุณเกี่ยวกับการใช้ Aspose.Slides สำหรับ .NET เพื่อกำหนดค่าองค์ประกอบแผนภูมิอย่างเชี่ยวชาญ เช่น ชื่อ คุณสมบัติแกน และคำอธิบายแผนภูมิ คุณจะได้เรียนรู้วิธีใช้ประโยชน์จากไลบรารีอันทรงพลังนี้เพื่อสร้างการนำเสนอระดับมืออาชีพได้อย่างง่ายดาย

**สิ่งที่คุณจะได้เรียนรู้:**
- สร้างและจัดรูปแบบชื่อแผนภูมิ
- กำหนดค่าเส้นกริดหลักและรองสำหรับแกนค่า
- ตั้งค่าคุณสมบัติข้อความสำหรับแกนค่าและหมวดหมู่
- ปรับแต่งการจัดรูปแบบตำนาน
- ปรับสีผนังแผนภูมิ

พร้อมที่จะเปลี่ยนแผนภูมิของคุณให้กลายเป็นภาพข้อมูลที่น่าสนใจหรือยัง มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- **Aspose.Slides สำหรับ .NET**ไลบรารีนี้จำเป็นสำหรับการจัดการไฟล์ PowerPoint โปรดตรวจสอบให้แน่ใจว่ามีการติดตั้งและกำหนดค่าแล้ว
- **สภาพแวดล้อมการพัฒนา**:สภาพแวดล้อมการพัฒนา AC# เช่น Visual Studio
- **ความรู้พื้นฐาน**: มีความคุ้นเคยกับการเขียนโปรแกรม C# และเข้าใจแนวคิดการนำเสนอ

## การตั้งค่า Aspose.Slides สำหรับ .NET
### คำแนะนำในการติดตั้ง
หากต้องการใช้ Aspose.Slides ในโครงการของคุณ ให้ปฏิบัติตามขั้นตอนการติดตั้งต่อไปนี้:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**คอนโซลตัวจัดการแพ็คเกจ**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet**
ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### การออกใบอนุญาต
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว**: การขอใบอนุญาตชั่วคราวเพื่อการทดสอบขยายเวลา
- **ซื้อ**:หากต้องการใช้ในระยะยาว ให้ซื้อใบอนุญาต เยี่ยมชม [การซื้อ Aspose](https://purchase.aspose.com/buy) สำหรับรายละเอียดเพิ่มเติม

เริ่มต้นโครงการของคุณโดยเพิ่มคำสั่งการใช้ที่จำเป็นและตั้งค่าอินสแตนซ์การนำเสนอพื้นฐาน:
```csharp
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Charts;

// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation pres = new Presentation();
```

## คู่มือการใช้งาน
คู่มือนี้แบ่งออกเป็นหลายส่วน โดยแต่ละส่วนมุ่งเน้นที่ด้านการกำหนดค่าแผนภูมิโดยเฉพาะโดยใช้ Aspose.Slides สำหรับ .NET

### สร้างและกำหนดค่าชื่อแผนภูมิ
**ภาพรวม**
การเพิ่มชื่อที่บรรยายลักษณะลงในแผนภูมิจะช่วยให้แผนภูมิมีความชัดเจนยิ่งขึ้น ในส่วนนี้จะแนะนำคุณเกี่ยวกับการสร้างแผนภูมิและปรับแต่งชื่อแผนภูมิด้วยตัวเลือกการจัดรูปแบบเฉพาะ

#### การดำเนินการแบบทีละขั้นตอน
1. **เพิ่มแผนภูมิลงในสไลด์**
   เข้าถึงสไลด์แรกในการนำเสนอของคุณและแทรกแผนภูมิเส้น:
   ```csharp
   ISlide slide = pres.Slides[0];
   IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
   ```
2. **ตั้งชื่อแผนภูมิพร้อมการจัดรูปแบบ**
   ปรับแต่งข้อความชื่อเรื่องและใช้การจัดรูปแบบ:
   ```csharp
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

### กำหนดค่าเส้นตารางแกนค่าและคุณสมบัติ
**ภาพรวม**
เส้นกริดที่จัดรูปแบบอย่างถูกต้องบนแกนค่าจะช่วยให้ข้อมูลอ่านได้ง่ายขึ้น มาตั้งค่าเส้นกริดหลักและรองด้วยรูปแบบเฉพาะกัน

#### การดำเนินการแบบทีละขั้นตอน
1. **เข้าถึงแกนแนวตั้งของแผนภูมิ**
   ดึงข้อมูลแกนตั้งของแผนภูมิของคุณ:
   ```csharp
   IVerticalAxis verticalAxis = chart.Axes.VerticalAxis;
   ```
2. **รูปแบบเส้นตารางหลักและรอง**
   ใช้สี ความกว้าง และรูปแบบกับเส้นกริดหลักและรอง:
   ```csharp
   // เส้นกริดหลัก
   verticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   verticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
   verticalAxis.MajorGridLinesFormat.Line.Width = 5;
   verticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

   // เส้นกริดย่อย
   verticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   verticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
   verticalAxis.MinorGridLinesFormat.Line.Width = 3;
   ```
3. **ตั้งค่ารูปแบบตัวเลขและคุณสมบัติแกน**
   กำหนดค่ารูปแบบตัวเลขและคุณสมบัติแกนสำหรับการแสดงข้อมูลที่แม่นยำ:
   ```csharp
   verticalAxis.IsNumberFormatLinkedToSource = false;
   verticalAxis.DisplayUnit = DisplayUnitType.Thousands;
   verticalAxis.NumberFormat = "0.0%";
   verticalAxis.IsAutomaticMajorUnit = false;
   verticalAxis.IsAutomaticMaxValue = false;
   verticalAxis.IsAutomaticMinorUnit = false;
   verticalAxis.IsAutomaticMinValue = false;

   verticalAxis.MaxValue = 15f;
   verticalAxis.MinValue = -2f;
   verticalAxis.MinorUnit = 0.5f;
   verticalAxis.MajorUnit = 2.0f;
   ```

### กำหนดค่าคุณสมบัติข้อความแกนค่า
**ภาพรวม**
ปรับปรุงแกนค่าด้วยคุณสมบัติข้อความที่กำหนดเองเพื่อให้อ่านได้ง่ายขึ้น

#### การดำเนินการแบบทีละขั้นตอน
1. **ตั้งค่าการจัดรูปแบบข้อความสำหรับแกนแนวตั้ง**
   ใช้รูปแบบตัวหนา ตัวเอียง และสีให้กับข้อความ:
   ```csharp
   IChartPortionFormat txtVal = verticalAxis.TextFormat.PortionFormat;
   txtVal.FontBold = NullableBool.True;
   txtVal.FontHeight = 16;
   txtVal.FontItalic = NullableBool.True;
   txtVal.FillFormat.FillType = FillType.Solid;
   txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
   txtVal.LatinFont = new FontData("Times New Roman");
   ```

### กำหนดค่าเส้นตารางแกนหมวดหมู่และคุณสมบัติข้อความ
**ภาพรวม**
การปรับแต่งเส้นตารางแกนหมวดหมู่และคุณสมบัติข้อความจะช่วยให้แผนภูมิของคุณทั้งให้ข้อมูลและดึงดูดสายตา

#### การดำเนินการแบบทีละขั้นตอน
1. **การเข้าถึงและจัดรูปแบบเส้นตารางหลัก/รองสำหรับแกนหมวดหมู่**
   ดึงข้อมูลและกำหนดรูปแบบแกนแนวนอน:
   ```csharp
   IHorizontalAxis horizontalAxis = chart.Axes.HorizontalAxis;

   // เส้นกริดหลัก
   horizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   horizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
   horizontalAxis.MajorGridLinesFormat.Line.Width = 5;

   // เส้นกริดย่อย
   horizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
   horizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
   horizontalAxis.MinorGridLinesFormat.Line.Width = 3;
   ```
2. **ตั้งค่าคุณสมบัติข้อความสำหรับแกนหมวดหมู่**
   ปรับแต่งลักษณะข้อความบนแกนหมวดหมู่:
   ```csharp
   IChartPortionFormat txtCat = horizontalAxis.TextFormat.PortionFormat;
   txtCat.FontBold = NullableBool.True;
   txtCat.FontHeight = 16;
   txtCat.FontItalic = NullableBool.True;
   txtCat.FillFormat.FillType = FillType.Solid;
   txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
   txtCat.LatinFont = new FontData("Arial");
   ```

### กำหนดค่าชื่อแกนหมวดหมู่และป้ายกำกับ
**ภาพรวม**
ชื่อแกนหมวดหมู่ที่อธิบายรายละเอียดจะช่วยให้เข้าใจแผนภูมิได้ดีขึ้น มากำหนดค่าคุณสมบัติชื่อและป้ายกำกับกัน

#### การดำเนินการแบบทีละขั้นตอน
1. **ตั้งค่าชื่อแกนหมวดหมู่พร้อมการจัดรูปแบบ**
   เพิ่มชื่อเรื่องให้กับแกนแนวนอน:
   ```csharp
   horizontalAxis.HasTitle = true;
   horizontalAxis.Title.AddTextFrameForOverriding("");
   IPortion chartLabel = horizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
   chartLabel.Text = "Sample Axis";
   chartLabel.PortionFormat.FillFormat.FillType = FillType.Solid;
   chartLabel.PortionFormat.FillFormat.SolidFillColor.Color = Color.DarkBlue;
   chartLabel.PortionFormat.FontHeight = 18;
   chartLabel.PortionFormat.FontBold = NullableBool.True;
   ```

## บทสรุป
ด้วยขั้นตอนเหล่านี้ คุณจะได้เรียนรู้วิธีการกำหนดค่าแผนภูมิอย่างมีประสิทธิภาพโดยใช้ Aspose.Slides สำหรับ .NET ทดลองใช้สไตล์และรูปแบบต่างๆ เพื่อให้การนำเสนอของคุณโดดเด่น

**คำแนะนำคีย์เวิร์ด:**
- "Aspose.Slides สำหรับ .NET"
- "การกำหนดค่าแผนภูมิใน .NET"
- "การปรับแต่งแผนภูมิ Aspose.Slides"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}