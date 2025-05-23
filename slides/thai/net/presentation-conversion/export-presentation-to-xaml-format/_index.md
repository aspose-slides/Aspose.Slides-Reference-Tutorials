---
"description": "เรียนรู้วิธีการส่งออกงานนำเสนอเป็นรูปแบบ XAML โดยใช้ Aspose.Slides สำหรับ .NET สร้างเนื้อหาเชิงโต้ตอบได้อย่างง่ายดาย!"
"linktitle": "ส่งออกงานนำเสนอเป็นรูปแบบ XAML"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "ส่งออกงานนำเสนอเป็นรูปแบบ XAML"
"url": "/th/net/presentation-conversion/export-presentation-to-xaml-format/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ส่งออกงานนำเสนอเป็นรูปแบบ XAML


ในโลกของการพัฒนาซอฟต์แวร์ การมีเครื่องมือที่ช่วยลดความซับซ้อนของงานถือเป็นสิ่งสำคัญ Aspose.Slides สำหรับ .NET เป็นหนึ่งในเครื่องมือที่ช่วยให้คุณสามารถทำงานกับการนำเสนอ PowerPoint ได้ด้วยโปรแกรม ในบทช่วยสอนทีละขั้นตอนนี้ เราจะมาดูวิธีการส่งออกการนำเสนอเป็นรูปแบบ XAML โดยใช้ Aspose.Slides สำหรับ .NET 

## บทนำสู่ Aspose.Slides สำหรับ .NET

ก่อนที่เราจะเจาะลึกในบทช่วยสอนนี้ เรามาทำความรู้จักกับ Aspose.Slides สำหรับ .NET กันก่อน Aspose.Slides สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถสร้าง แก้ไข แปลง และจัดการงานนำเสนอ PowerPoint ได้โดยไม่ต้องใช้ Microsoft PowerPoint เอง ด้วย Aspose.Slides สำหรับ .NET คุณสามารถทำให้การทำงานต่างๆ ที่เกี่ยวข้องกับงานนำเสนอ PowerPoint เป็นอัตโนมัติ ทำให้กระบวนการพัฒนาของคุณมีประสิทธิภาพมากขึ้น

## ข้อกำหนดเบื้องต้น

หากต้องการทำตามบทช่วยสอนนี้ คุณจะต้องมีสิ่งต่อไปนี้:

1. Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET และพร้อมใช้งานในโปรเจ็กต์ .NET ของคุณ

2. การนำเสนอต้นฉบับ: มีการนำเสนอ PowerPoint (PPTX) ที่คุณต้องการส่งออกเป็นรูปแบบ XAML ตรวจสอบให้แน่ใจว่าคุณทราบเส้นทางไปยังการนำเสนอนี้

3. ไดเร็กทอรีเอาต์พุต: เลือกไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ XAML ที่สร้างขึ้น

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ในขั้นตอนแรกนี้ เราจะตั้งค่าโครงการของเราและตรวจสอบให้แน่ใจว่าเรามีส่วนประกอบที่จำเป็นทั้งหมดพร้อมแล้ว ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มการอ้างอิงไปยังไลบรารี Aspose.Slides สำหรับ .NET ในโครงการของคุณแล้ว

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
// การนำเสนอเส้นทางสู่แหล่งที่มา
string presentationFileName = Path.Combine(dataDir, "XamlEtalon.pptx");
```

แทนที่ `"Your Document Directory"` พร้อมระบุเส้นทางไปยังไดเร็กทอรีที่มีไฟล์นำเสนอ PowerPoint ต้นฉบับของคุณ และระบุไดเร็กทอรีเอาต์พุตที่จะบันทึกไฟล์ XAML ที่สร้างขึ้นด้วย

## ขั้นตอนที่ 2: ส่งออกงานนำเสนอเป็น XAML

ตอนนี้เรามาดำเนินการส่งออกงานนำเสนอ PowerPoint เป็นรูปแบบ XAML กัน เราจะใช้ Aspose.Slides สำหรับ .NET เพื่อทำสิ่งนี้ 

```csharp
using (Presentation pres = new Presentation(presentationFileName))
{
    // สร้างตัวเลือกการแปลง
    XamlOptions xamlOptions = new XamlOptions();
    xamlOptions.ExportHiddenSlides = true;

    // กำหนดบริการการประหยัดผลลัพธ์ของคุณเอง
    NewXamlSaver newXamlSaver = new NewXamlSaver();
    xamlOptions.OutputSaver = newXamlSaver;

    // แปลงสไลด์
    pres.Save(xamlOptions);

    // บันทึกไฟล์ XAML ไปยังไดเร็กทอรีเอาท์พุต
    foreach (var pair in newXamlSaver.Results)
    {
        File.AppendAllText(Path.Combine(outPath, pair.Key), pair.Value);
    }
}
```

ในตัวอย่างโค้ดนี้ เราโหลดการนำเสนอแหล่งที่มา สร้างตัวเลือกการแปลง XAML และกำหนดบริการการบันทึกเอาต์พุตแบบกำหนดเองโดยใช้ `NewXamlSaver`จากนั้นเราบันทึกไฟล์ XAML ไปยังไดเร็กทอรีเอาต์พุตที่ระบุ

## ขั้นตอนที่ 3: คลาส XAML Saver ที่กำหนดเอง

ในการใช้โปรแกรมรักษา XAML แบบกำหนดเอง เราจะสร้างคลาสชื่อ `NewXamlSaver` ที่นำไปปฏิบัติ `IXamlOutputSaver` อินเทอร์เฟซ

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

ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการส่งออกงานนำเสนอ PowerPoint เป็นรูปแบบ XAML โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว ซึ่งถือเป็นทักษะที่มีค่าเมื่อทำงานในโครงการที่เกี่ยวข้องกับการจัดการงานนำเสนอ

อย่าลังเลที่จะสำรวจคุณลักษณะและความสามารถเพิ่มเติมของ Aspose.Slides สำหรับ .NET เพื่อเพิ่มประสิทธิภาพงานการทำงานอัตโนมัติของ PowerPoint ของคุณ

## คำถามที่พบบ่อย

1. ### Aspose.Slides สำหรับ .NET คืออะไร?
Aspose.Slides สำหรับ .NET เป็นไลบรารี .NET สำหรับการทำงานกับการนำเสนอ PowerPoint ด้วยโปรแกรม

2. ### ฉันสามารถรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จาก [ที่นี่](https://purchase-aspose.com/buy).

3. ### มีการทดลองใช้ฟรีหรือไม่?
ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ได้ฟรี [ที่นี่](https://releases-aspose.com/).

4. ### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).

5. ### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
คุณสามารถค้นหาการสนับสนุนและการสนทนาของชุมชนได้ [ที่นี่](https://forum-aspose.com/).

สำหรับบทช่วยสอนและทรัพยากรเพิ่มเติม โปรดไปที่ [เอกสารประกอบ API ของ Aspose.Slides](https://reference-aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}