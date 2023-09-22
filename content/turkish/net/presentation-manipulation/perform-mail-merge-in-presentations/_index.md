---
title: Sunumlarda Adres Mektup Birleştirme Gerçekleştirme
linktitle: Sunumlarda Adres Mektup Birleştirme Gerçekleştirme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Bu kapsamlı adım adım kılavuzdan Aspose.Slides for .NET kullanarak sunumlarda adres-mektup birleştirmenin nasıl gerçekleştirileceğini öğrenin. Kolaylıkla kişiselleştirilmiş ve dinamik sunumlar oluşturun.
type: docs
weight: 21
url: /tr/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

Yazılım geliştirme alanında dinamik ve kişiselleştirilmiş sunumlar oluşturmak ortak bir gerekliliktir. İşletmelerin sıklıkla belirli verilere göre uyarlanmış sunumlar oluşturması gerekir ve adres-mektup birleştirme işlevi burada devreye girer. Bu eğitimde, Aspose.Slides for .NET kullanarak sunumlarda adres-mektup birleştirme gerçekleştirme sürecinde size rehberlik edeceğiz.

## giriiş

Adres mektup birleştirme, sunum şablonlarını veritabanları veya XML dosyaları gibi çeşitli kaynaklardan alınan verilerle doldurmanıza olanak tanıyan güçlü bir tekniktir. Bu eğitimde, sunumlarda adım adım adres-mektup birleştirme gerçekleştirmek için Aspose.Slides for .NET'i kullanmaya odaklanacağız.

## Ortamınızı Kurma

Adres-posta birleştirme sürecine dalmadan önce geliştirme ortamınızı ayarlamanız gerekir. Aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya başka herhangi bir C# geliştirme ortamı.
-  Aspose.Slides for .NET kütüphanesi kuruldu. İndirebilirsin[Burada](https://releases.aspose.com/slides/net/).

## Veri Kaynağını Anlamak

Adres-mektup birleştirme için bir veri kaynağına ihtiyacınız olacak. Bu eğitimde veri kaynağımız olarak bir XML dosyası kullanacağız. Aşağıda veri kaynağınızın nasıl görünebileceğine dair bir örnek verilmiştir:

```xml
<!-- TestData.xml -->
<?xml version="1.0" encoding="UTF-8"?>
<MailMerge>
    <TestTable>
        <Id>1</Id>
        <Code>105</Code>
        <Name>Samuel Ellington</Name>
        <Department>Legal Department</Department> <Img></Img>
    </TestTable>
    <StaffList>
        <Id>18</Id>
        <UserId>1</UserId>
        <Name>Amelia Walker</Name>
    </StaffList>
    <Plan_Fact>
        <Id>1</Id>
        <UserId>1</UserId>
        <OnDate>2020/01</OnDate>
        <PlanData>2,0</PlanData>
        <FactData>2,8</FactData>
    </Plan_Fact>
</MailMerge>
```

## Sunum Şablonunun Oluşturulması

Adres-mektup birleştirmeyi gerçekleştirmek için son sunumlarınızın düzenini tanımlayan bir sunum şablonuna (PPTX dosyası) ihtiyacınız olacaktır. Bu şablonu Microsoft PowerPoint'i veya seçtiğiniz başka bir aracı kullanarak oluşturabilirsiniz.

## Adres Mektup Birleştirme İşlemi

Şimdi Aspose.Slides for .NET'i kullanarak gerçek adres-mektup birleştirme sürecine dalalım. Bunu adımlara ayıracağız:

1. Sunum şablonunu yükleyin.
2. Metin kutularını veri kaynağındaki verilerle doldurun.
3. Sunuma görseller ekleyin.
4. Metin çerçevelerini hazırlayın ve doldurun.
5. Bireysel sunumları kaydedin.

Aşağıda bu adımları gerçekleştiren bir C# kodu pasajı verilmiştir:

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // Verilere giden yol.
    // XML verileri, olası MailMerge veri kaynaklarının (RDBMS ve diğer veri kaynağı türleri arasında) örneklerinden biridir.
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // Sonuç yolunun mevcut olup olmadığını kontrol edin
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // XML verilerini kullanarak DataSet oluşturma
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // Ana tablodaki tüm kayıtlar için ayrı bir sunum oluşturacağız
        foreach (DataRow userRow in usersTable.Rows)
        {
            // sonuç (bireysel) sunum adı oluştur
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //Sunum şablonunu yükle
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // Metin kutularını veri tabanı ana tablosundaki verilerle doldurun
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // Veri tabanından resim alın
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // sunumun resim çerçevesine resim ekleme
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // Verilerle doldurmak için abd'nin metin çerçevesini hazırlamasını sağlayın
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                // personel verilerini doldur
                FillStaffList(textFrame, userRow, staffListTable);

                // plan gerçek verilerini doldur
                FillPlanFact(pres, userRow, planFactTable);

                pres.Save(presPath, SaveFormat.Pptx);
            }
        }
    }

static void FillStaffList(ITextFrame textFrame, DataRow userRow, DataTable staffListTable)
{
    foreach (DataRow listRow in staffListTable.Rows)
    {
        if (listRow["UserId"].ToString() == userRow["Id"].ToString())
        {
            Paragraph para = new Paragraph();
            para.ParagraphFormat.Bullet.Type = BulletType.Symbol;
            para.ParagraphFormat.Bullet.Char = Convert.ToChar(8226);
            para.Text = listRow["Name"].ToString();
            para.ParagraphFormat.Bullet.Color.ColorType = ColorType.RGB;
            para.ParagraphFormat.Bullet.Color.Color = Color.Black;
            para.ParagraphFormat.Bullet.IsBulletHardColor = NullableBool.True;
            para.ParagraphFormat.Bullet.Height = 100;
            textFrame.Paragraphs.Add(para);
        }
    }
}

// Veri grafiğini ikincil planFact tablosundan doldurur
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";

    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();

    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 1,
            double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2,
            double.Parse(selRows[0]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1,
            double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2,
            double.Parse(selRows[1]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[2]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[3]["FactData"].ToString())));

    chart.ChartData.SetRange(range);
}		
```

## Sonucun Kaydedilmesi

Veri kaynağınızdaki tüm kayıtlar için adres-mektup birleştirme işlemini tamamladıktan sonra, bireysel sunumlarınız hazır olacaktır. Bunları istediğiniz konuma kaydedebilirsiniz.

## Çözüm

Aspose.Slides for .NET'i kullanarak sunumlarda adres-mektup birleştirme gerçekleştirmek, özelleştirilmiş ve veri odaklı sunumlar oluşturmak için bir fırsatlar dünyasının kapılarını açar. Bu eğitim, bunu sorunsuz bir şekilde başarmanız için gerekli adımlar konusunda size rehberlik etmiştir.

## SSS

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
Cevap1: Aspose.Slides for .NET güçlü bir seçim olsa da diğer kütüphaneler ve araçlar da benzer işlevsellik sunuyor. Sonuçta özel gereksinimlerinize ve tercihlerinize bağlıdır.

**Q2: Can I use different data sources apart from XML files?**
C2: Evet, Aspose.Slides for .NET, veritabanları ve özel veri yapıları da dahil olmak üzere çeşitli veri kaynaklarını destekler.

**Q3: How can I format the merged presentations further?**
Cevap3: Aspose.Slides'ın zengin özellik setini kullanarak birleştirilmiş sunumlara ek formatlama, stiller ve animasyonlar uygulayabilirsiniz.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 Cevap4: Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü edinebilirsiniz[Burada](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 A5: Teknik destek ve tartışmalar için şu adresi ziyaret edebilirsiniz:[Aspose.Slides forumu](https://forum.aspose.com/).

Artık Aspose.Slides for .NET ile sunumlarda adres-mektup birleştirmeyi nasıl gerçekleştireceğinizi öğrendiğinize göre, projeleriniz için dinamik ve veri açısından zengin sunumlar oluşturmaya başlayabilirsiniz. Mutlu kodlama!
