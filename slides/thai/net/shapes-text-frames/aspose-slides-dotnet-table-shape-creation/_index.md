---
"date": "2025-04-16"
"description": "เรียนรู้วิธีการสร้างตารางและรูปทรงแบบไดนามิกในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อเพิ่มความน่าสนใจทางภาพ"
"title": "การสร้างตารางและรูปร่างใน PowerPoint ด้วย Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอน"
"url": "/th/net/shapes-text-frames/aspose-slides-dotnet-table-shape-creation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การสร้างตารางและรูปทรงใน PowerPoint ด้วย Aspose.Slides สำหรับ .NET: คำแนะนำทีละขั้นตอน

## การแนะนำ

เพิ่มประสิทธิภาพการนำเสนอ PowerPoint ของคุณด้วยการสร้างตารางแบบไดนามิกหรือวาดรูปร่างรอบข้อความโดยใช้ C# กับ Aspose.Slides สำหรับ .NET คู่มือนี้จะแนะนำคุณเกี่ยวกับกระบวนการสร้างตารางและวาดรูปร่าง ซึ่งจะทำให้สไลด์ของคุณมีข้อมูลและน่าสนใจมากขึ้น

ในบทช่วยสอนนี้เราจะครอบคลุม:
- การสร้างตารางในงานนำเสนอ PowerPoint
- การเพิ่มย่อหน้าพร้อมส่วนข้อความลงในเซลล์ตาราง
- การฝังกรอบข้อความภายในรูปทรง
- การวาดสี่เหลี่ยมรอบองค์ประกอบข้อความเฉพาะ

เมื่ออ่านคู่มือนี้จบ คุณจะพร้อมที่จะปรับปรุงสไลด์การนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ .NET แล้ว มาเจาะลึกข้อกำหนดเบื้องต้นกันก่อน

### ข้อกำหนดเบื้องต้น

หากต้องการทำตามบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมี:
- **สภาพแวดล้อมการพัฒนา**:Visual Studio ติดตั้งอยู่บนเครื่องของคุณแล้ว
- **Aspose.Slides สำหรับไลบรารี .NET**:เราจะใช้เวอร์ชัน 22.x หรือใหม่กว่า
- **ความรู้พื้นฐานเกี่ยวกับ C#**: ต้องมีความคุ้นเคยกับโครงสร้างและแนวคิดของ C#

## การตั้งค่า Aspose.Slides สำหรับ .NET

ก่อนที่เราจะเริ่มเขียนโค้ด เรามาตั้งค่าไลบรารี Aspose.Slides ในโปรเจ็กต์ของคุณกันก่อน มีหลายวิธีในการติดตั้ง:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**คอนโซลตัวจัดการแพ็คเกจ**
```powershell
Install-Package Aspose.Slides
```

**UI ตัวจัดการแพ็กเกจ NuGet**: ค้นหา "Aspose.Slides" และคลิกปุ่มติดตั้ง

### การขอใบอนุญาต

คุณสามารถเริ่มต้นด้วยใบอนุญาตทดลองใช้งานฟรีเพื่อสำรวจฟีเจอร์ทั้งหมด สำหรับการใช้งานแบบขยายเวลา คุณสามารถเลือกใบอนุญาตชั่วคราวหรือซื้อจาก [เว็บไซต์อาโพส](https://purchase-aspose.com/buy).

เมื่อติดตั้งแล้ว ให้เริ่มต้น Aspose.Slides ในโปรเจ็กต์ของคุณโดยเพิ่ม:

```csharp
using Aspose.Slides;
```

## คู่มือการใช้งาน

### การสร้างตารางบนสไลด์

**ภาพรวม:**
การสร้างตารางถือเป็นพื้นฐานเมื่อคุณต้องนำเสนอข้อมูลอย่างชัดเจน ด้วย Aspose.Slides คุณสามารถกำหนดขนาดและตำแหน่งของตารางได้อย่างง่ายดาย

#### ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ
เริ่มต้นด้วยการสร้างอินสแตนซ์ของ `Presentation` ระดับ:

```csharp
Presentation pres = new Presentation();
```

#### ขั้นตอนที่ 2: เพิ่มตาราง
ใช้ `AddTable` วิธีการเพิ่มตารางลงในสไลด์ของคุณ ระบุตำแหน่งและขนาดของแถวและคอลัมน์:

```csharp
ITable tbl = pres.Slides[0].Shapes.AddTable(50, 50, new double[] { 50, 70 }, new double[] { 50, 50, 50 });
```

**คำอธิบายพารามิเตอร์:**
- `50, 50`:พิกัด X และ Y สำหรับมุมบนซ้าย
- อาร์เรย์ระบุความกว้างของคอลัมน์และความสูงของแถว

#### ขั้นตอนที่ 3: บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอของคุณ:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY/CreateTable_Out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}