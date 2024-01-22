---
title: ส่งออกการนำเสนอเป็นรูปแบบ XAML
linktitle: ส่งออกการนำเสนอเป็นรูปแบบ XAML
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีส่งออกงานนำเสนอเป็นรูปแบบ XAML โดยใช้ Aspose.Slides สำหรับ .NET สร้างเนื้อหาเชิงโต้ตอบได้อย่างง่ายดาย!
type: docs
weight: 27
url: /th/net/presentation-conversion/export-presentation-to-xaml-format/
---

ในโลกของการพัฒนาซอฟต์แวร์ จำเป็นต้องมีเครื่องมือที่ช่วยลดความซับซ้อนของงานได้ Aspose.Slides สำหรับ .NET เป็นหนึ่งในเครื่องมือที่ช่วยให้คุณสามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรมได้ ในบทช่วยสอนทีละขั้นตอนนี้ เราจะสำรวจวิธีการส่งออกงานนำเสนอเป็นรูปแบบ XAML โดยใช้ Aspose.Slides สำหรับ .NET 

## ข้อมูลเบื้องต้นเกี่ยวกับ Aspose.Slides สำหรับ .NET

ก่อนที่เราจะเจาะลึกบทช่วยสอน เรามาแนะนำ Aspose.Slides สำหรับ .NET กันก่อน เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข แปลง และจัดการงานนำเสนอ PowerPoint โดยไม่ต้องใช้ Microsoft PowerPoint เอง ด้วย Aspose.Slides สำหรับ .NET คุณสามารถทำงานต่างๆ ที่เกี่ยวข้องกับการนำเสนอ PowerPoint ได้โดยอัตโนมัติ ทำให้กระบวนการพัฒนาของคุณมีประสิทธิภาพมากขึ้น

## ข้อกำหนดเบื้องต้น

หากต้องการปฏิบัติตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

1. Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET และพร้อมใช้งานในโปรเจ็กต์ .NET ของคุณ

2. การนำเสนอแหล่งที่มา: มีงานนำเสนอ PowerPoint (PPTX) ที่คุณต้องการส่งออกเป็นรูปแบบ XAML ตรวจสอบให้แน่ใจว่าคุณทราบเส้นทางสู่การนำเสนอนี้

3. ไดเร็กทอรีเอาท์พุต: เลือกไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ XAML ที่สร้างขึ้น

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ในขั้นตอนแรกนี้ เราจะจัดเตรียมโปรเจ็กต์ของเราและตรวจสอบให้แน่ใจว่ามีส่วนประกอบที่จำเป็นทั้งหมดพร้อมแล้ว ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Slides สำหรับ .NET ในโปรเจ็กต์ของคุณ

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// เส้นทางสู่การนำเสนอแหล่งที่มา
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีงานนำเสนอ PowerPoint ต้นทางของคุณ นอกจากนี้ ให้ระบุไดเร็กทอรีเอาต์พุตที่จะบันทึกไฟล์ XAML ที่สร้างขึ้น

## ขั้นตอนที่ 2: ส่งออกงานนำเสนอเป็น XAML

ตอนนี้เรามาดำเนินการส่งออกงานนำเสนอ PowerPoint เป็นรูปแบบ XAML กัน เราจะใช้ Aspose.Slides สำหรับ .NET เพื่อให้บรรลุเป้าหมายนี้ 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // สร้างตัวเลือกการแปลง
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // กำหนดบริการประหยัดผลผลิตของคุณเอง
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // แปลงสไลด์
    pres.Save(xamlOptions);

    // บันทึกไฟล์ XAML ไปยังไดเร็กทอรีเอาต์พุต
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

 ในโค้ดขนาดสั้นนี้ เราจะโหลดการนำเสนอต้นฉบับ สร้างตัวเลือกการแปลง XAML และกำหนดบริการประหยัดเอาต์พุตแบบกำหนดเองโดยใช้`NewXamlSaver`. จากนั้นเราจะบันทึกไฟล์ XAML ไปยังไดเร็กทอรีเอาต์พุตที่ระบุ

## ขั้นตอนที่ 3: คลาส XAML Saver แบบกำหนดเอง

 หากต้องการใช้โปรแกรมรักษา XAML แบบกำหนดเอง เราจะสร้างคลาสชื่อ`NewXamlSaver` ที่ใช้`IXamlOutputSaver` อินเตอร์เฟซ.

```csharp
class NewXamlSaver : IXamlOutputSaver
{
    private Dictionary<string, string> m_result = new Dictionary<string, string>();

    public Dictionary<string, string> Results
    {
        get { return m_result; }
    }

    public void Save(string path, byte[] data)
    {
        string name = Path.GetFileName(path);
        Results[name] = Encoding.UTF8.GetString(data);
    }
}
```

คลาสนี้จะจัดการการบันทึกไฟล์ XAML ไปยังไดเร็กทอรีเอาต์พุต

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีส่งออกงานนำเสนอ PowerPoint เป็นรูปแบบ XAML เรียบร้อยแล้วโดยใช้ Aspose.Slides สำหรับ .NET นี่อาจเป็นทักษะที่มีคุณค่าเมื่อทำงานในโครงการที่เกี่ยวข้องกับการบิดเบือนการนำเสนอ

สำรวจฟีเจอร์และความสามารถเพิ่มเติมของ Aspose.Slides สำหรับ .NET ได้อย่างอิสระ เพื่อปรับปรุงงานอัตโนมัติของ PowerPoint ของคุณ

## คำถามที่พบบ่อย

1. ### Aspose.Slides สำหรับ .NET คืออะไร
Aspose.Slides สำหรับ .NET เป็นไลบรารี .NET สำหรับการทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม

2. ### ฉันจะหา Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จาก[ที่นี่](https://purchase.aspose.com/buy).

3. ### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรี[ที่นี่](https://releases.aspose.com/).

4. ### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).

5. ### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนและการสนทนาในชุมชนได้[ที่นี่](https://forum.aspose.com/).

 สำหรับบทช่วยสอนและทรัพยากรเพิ่มเติม โปรดไปที่[เอกสารประกอบ API ของ Aspose.Slides](https://reference.aspose.com/slides/net/).