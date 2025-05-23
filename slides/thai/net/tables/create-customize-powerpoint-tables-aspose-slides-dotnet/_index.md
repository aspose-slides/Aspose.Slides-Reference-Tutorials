---
"date": "2025-04-16"
"description": "เรียนรู้วิธีการสร้างและปรับแต่งตาราง PowerPoint แบบอัตโนมัติโดยใช้ Aspose.Slides สำหรับ .NET ช่วยประหยัดเวลาและรับรองการจัดรูปแบบที่สอดคล้องกัน"
"title": "สร้างและปรับแต่งตาราง PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET"
"url": "/th/net/tables/create-customize-powerpoint-tables-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างและปรับแต่งตาราง PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET

## การแนะนำ
การสร้างตารางที่น่าสนใจใน PowerPoint ถือเป็นสิ่งสำคัญสำหรับการนำเสนอข้อมูลอย่างมีประสิทธิภาพ การใช้ Aspose.Slides สำหรับ .NET เพื่อทำให้กระบวนการนี้เป็นอัตโนมัติจะช่วยประหยัดเวลาและรับประกันความสอดคล้องกันในงานนำเสนอต่างๆ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างและปรับแต่งตารางใน PowerPoint ด้วยโปรแกรม

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าสภาพแวดล้อมของคุณด้วย Aspose.Slides สำหรับ .NET
- การสร้างตาราง PowerPoint ด้วยโปรแกรม
- การปรับแต่งลักษณะที่ปรากฏของเส้นขอบเซลล์ตาราง
- บันทึกการนำเสนอของคุณในรูปแบบ PPTX

มาเริ่มต้นลงมือทำงานอัตโนมัติใน PowerPoint ของคุณโดยการตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการก่อน

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมี:

- **ห้องสมุดและสิ่งที่ต้องพึ่งพา:** Aspose.Slides สำหรับ .NET ได้รับการติดตั้งในโครงการของคุณแล้ว
- **การตั้งค่าสภาพแวดล้อม:** บทช่วยสอนนี้ถือว่าคุณใช้ Visual Studio หรือสภาพแวดล้อมการพัฒนา .NET ที่เข้ากันได้
- **ข้อกำหนดความรู้เบื้องต้น:** ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C# เป็นประโยชน์แต่ไม่ใช่สิ่งบังคับ

## การตั้งค่า Aspose.Slides สำหรับ .NET
หากต้องการรวม Aspose.Slides สำหรับ .NET ในโครงการของคุณ ให้ทำตามขั้นตอนการติดตั้งเหล่านี้:

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**ตัวจัดการแพ็กเกจ:**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet:**
- เปิดตัวจัดการแพ็คเกจ NuGet ใน IDE ของคุณ
- ค้นหา "Aspose.Slides" และติดตั้งเวอร์ชันล่าสุด

### การขอใบอนุญาต
หากต้องการใช้ Aspose.Slides ได้อย่างเต็มประสิทธิภาพ โปรดพิจารณาตัวเลือกเหล่านี้:
1. **ทดลองใช้งานฟรี:** ลองสำรวจคุณสมบัติก่อน
2. **ใบอนุญาตชั่วคราว:** รับหนึ่งจาก [อาโปเซ่](https://purchase-aspose.com/temporary-license/).
3. **ซื้อ:** หากต้องการเข้าถึงแบบเต็มรูปแบบ กรุณาซื้อการสมัครสมาชิก

### การเริ่มต้นขั้นพื้นฐาน
เมื่อติดตั้งแล้ว ให้เริ่มต้น Aspose.Slides ในโครงการของคุณ:
```csharp
using Aspose.Slides;
// สร้างอินสแตนซ์ของคลาสการนำเสนอที่แสดงไฟล์ PowerPoint
Presentation presentation = new Presentation();
```

## คู่มือการใช้งาน
มาแบ่งการใช้งานออกเป็นขั้นตอนที่ชัดเจนเพื่อสร้างและปรับแต่งตาราง

### การสร้างตารางใน PowerPoint
#### ภาพรวม
เราจะเริ่มต้นด้วยการสร้างตารางที่มีขนาดที่ระบุไว้ในสไลด์แรกโดยเน้นที่การกำหนดโครงสร้างของตารางและตำแหน่งเริ่มต้น

##### ขั้นตอนที่ 1: การเข้าถึงสไลด์
```csharp
// สร้างอินสแตนซ์ของคลาสการนำเสนอที่แสดงไฟล์ PPTX
using (Presentation pres = new Presentation()) {
    // เข้าถึงสไลด์แรกของการนำเสนอ
    ISlide sld = pres.Slides[0];
```

##### ขั้นตอนที่ 2: การกำหนดมิติตาราง
กำหนดคอลัมน์และแถวโดยมีความกว้างและความสูงเฉพาะเป็นจุด
```csharp
// กำหนดคอลัมน์ที่มีความกว้างและแถวที่มีความสูงเป็นจุด
double[] dblCols = { 70, 70, 70, 70 };
double[] dblRows = { 70, 70, 70, 70 };

// เพิ่มรูปร่างตารางลงในสไลด์ที่ตำแหน่ง (100, 50)
ITable tbl = sld.Shapes.AddTable(100, 50, dblCols, dblRows);
```

### การปรับแต่งขอบตาราง
#### ภาพรวม
ขั้นตอนต่อไปคือการปรับแต่งเส้นขอบของแต่ละเซลล์ในตารางที่คุณเพิ่งสร้างขึ้น ขั้นตอนนี้จะเพิ่มความน่าสนใจให้กับภาพด้วยการใช้เส้นขอบสีแดงทึบ

##### ขั้นตอนที่ 3: การตั้งค่าสไตล์ขอบ
ทำซ้ำผ่านแต่ละเซลล์เพื่อตั้งค่ารูปแบบเส้นขอบที่ต้องการ
```csharp
// ตั้งค่ารูปแบบเส้นขอบให้กับแต่ละเซลล์ในตาราง
foreach (IRow row in tbl.Rows) {
    foreach (ICell cell in row) {
        // ปรับแต่งขอบด้านบน ล่าง ซ้าย และขวาของเซลล์ด้วยสีแดงทึบ
cell.CellFormat.BorderTop.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderTop.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderTop.Width = 5;

cell.CellFormat.BorderBottom.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderBottom.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderBottom.Width = 5;

cell.CellFormat.BorderLeft.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderLeft.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderLeft.Width = 5;

cell.CellFormat.BorderRight.FillFormat.FillType = FillType.Solid;
cell.CellFormat.BorderRight.FillFormat.SolidFillColor.Color = Color.Red;
cell.CellFormat.BorderRight.Width = 5;
    }
}
```

### การบันทึกการนำเสนอ
#### ภาพรวม
สุดท้าย ให้บันทึกการนำเสนอของคุณลงในไฟล์บนดิสก์ ขั้นตอนนี้จะช่วยให้มั่นใจว่าการเปลี่ยนแปลงทั้งหมดจะยังคงอยู่

##### ขั้นตอนที่ 4: บันทึกงานของคุณ
```csharp
// บันทึกการนำเสนอด้วยชื่อไฟล์และรูปแบบที่ระบุ
pres.Save("StandardTables_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}