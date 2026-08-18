---
date: '2026-06-03'
description: Aprenda como exportar gráfico para Excel e criar gráficos Java usando
  Aspose.Slides for Java. Domine visualização de dados, slides de relatórios empresariais
  e geração de pastas de trabalho.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Exportar Gráfico para Excel e Criar Gráficos com Aspose.Slides
url: /pt/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportar Gráfico para Excel e Criar Gráficos com Aspose.Slides

**Domine Técnicas de Visualização de Dados com Aspose.Slides para Java**

No cenário atual orientado por dados, *export chart to excel* programaticamente é uma habilidade que pode transformar números brutos em histórias visuais envolventes. Seja construindo um conjunto de slides de relatório empresarial ou um painel de análise interativo, Aspose.Slides for Java lhe dá o poder de gerar, personalizar e exportar gráficos diretamente do seu código. Neste tutorial você aprenderá como criar objetos de gráfico, exportar dados do gráfico para Excel e vincular gráficos a pastas de trabalho externas para um gerenciamento de dados perfeito.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Slides for Java (v25.4+).  
- **Posso exportar dados do gráfico para Excel?** Sim – use `readWorkbookStream()` e escreva os bytes em um arquivo *.xlsx*.  
- **Qual versão do Java é necessária?** JDK 16 ou superior.  
- **Preciso de uma licença?** Um teste gratuito funciona para avaliação; uma licença permanente é necessária para produção.  
- **Qual tipo de gráfico é demonstrado?** Um gráfico de Pizza, mas a mesma abordagem funciona para Barras, Linhas e outros tipos de gráficos.

## O que é Aspose.Slides para Java?
Aspose.Slides for Java é uma API pura‑Java que permite aos desenvolvedores criar, editar e converter apresentações PowerPoint sem o Microsoft Office. Ela fornece um conjunto abrangente de classes para manipulação de slides, geração de gráficos e conversão de formatos, possibilitando soluções de relatórios automatizados. Suporta **50+ tipos de gráficos**, vinculação completa de dados e exportação direta para Excel, tornando-a ideal para projetos de **data visualization java**.

## Por que usar Aspose.Slides para criar gráfico e exportar gráfico para Excel?
Exportar gráfico para Excel de forma rápida e confiável. Aspose.Slides elimina a necessidade de instalações do Office, oferece **mais de 50 estilos de gráfico incorporados**, e processa apresentações **de até 300 MB em menos de 30 segundos** em hardware de servidor padrão. Você também obtém geração nativa de pastas de trabalho Excel, que permite que analistas posteriores trabalhem com números brutos sem copiar‑colar manualmente.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem o seguinte:

### Bibliotecas e Versões Necessárias
- **Aspose.Slides for Java** versão 25.4 ou posterior (suporta JDK 16+)

### Requisitos de Configuração do Ambiente
- Java Development Kit (JDK) 16 ou superior  
- Uma IDE como IntelliJ IDEA ou Eclipse (ou qualquer editor de texto de sua preferência)

### Pré‑requisitos de Conhecimento
- Habilidades básicas de programação Java  
- Familiaridade com as ferramentas de construção Maven ou Gradle

## Configurando Aspose.Slides para Java
Adicione a biblioteca ao seu projeto usando seu sistema de build favorito.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, você pode [baixar a versão mais recente diretamente](https://releases.aspose.com/slides/java/).

### Etapas de Aquisição de Licença
Aspose.Slides oferece uma licença de teste gratuita para explorar todos os seus recursos. Você também pode solicitar uma licença temporária ou comprar uma para uso prolongado. Siga estas etapas:

1. Visite a [página de Compra da Aspose](https://purchase.aspose.com/buy) para obter sua licença.  
2. Para um teste gratuito, baixe em [Releases](https://releases.aspose.com/slides/java/).  
3. Solicite uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

Depois de obter o arquivo de licença, inicialize-o em sua aplicação Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guia Passo a Passo

### Como criar gráfico – Carregar uma Apresentação
Carregue um arquivo PowerPoint existente antes de poder adicionar ou modificar gráficos.  
A classe `Presentation` representa um arquivo PowerPoint na memória, expondo slides, formas e objetos de gráfico.  
Carregue seu arquivo com `new Presentation("input.pptx")`, então trabalhe com o primeiro slide usando `presentation.getSlides().get_Item(0)`. Sempre chame `presentation.dispose()` em um bloco `finally` para liberar recursos nativos.

### Como criar gráfico – Adicionar um Gráfico de Pizza a um Slide
Insira um gráfico de Pizza, perfeito para mostrar dados proporcionais.  
A interface `IChart` é o ponto de entrada principal para manipulação de gráficos; `addChart` cria um novo gráfico no slide alvo. Forneça o tipo de gráfico (`ChartType.Pie`), coordenadas X/Y e largura/altura. Após a criação, você pode personalizar títulos, legenda e séries de dados através do objeto `ChartData`.

### Como exportar gráfico para Excel – Exportar Dados do Gráfico
Exportar dados do gráfico permite que analistas trabalhem com os números no Excel, possibilitando insights mais profundos.  
`readWorkbookStream()` devolve a pasta de trabalho Excel subjacente do gráfico como um array de bytes. Chame `chart.getChartData().readWorkbookStream()` para obter a pasta de trabalho e escreva esse array em um arquivo chamado `externalWorkbook1.xlsx` usando I/O padrão do Java. O arquivo Excel resultante contém os dados exatos usados pelo gráfico, pronto para análise adicional.

### Como criar gráfico – Definir Pasta de Trabalho Externa para Dados Dinâmicos
Vincule um gráfico a uma pasta de trabalho externa para permitir atualizações de dados em tempo real sem reconstruir o slide.  
`setExternalWorkbook()` associa o gráfico a um arquivo Excel externo para atualizações dinâmicas de dados. Use `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` para vincular o gráfico ao arquivo externo. Quando a pasta de trabalho Excel for editada, o gráfico refletirá automaticamente as alterações na próxima vez que a apresentação for aberta, suportando cenários de relatórios dinâmicos.

## Aplicações Práticas
Aspose.Slides oferece soluções versáteis para diversos cenários reais:

1. **Slides de Relatórios Empresariais:** Gere gráficos de desempenho trimestral automaticamente a partir de seus pipelines de dados.  
2. **Apresentações Acadêmicas:** Transforme dados de pesquisa em visualizações claras sem a necessidade de criar gráficos manualmente.  
3. **Análise Financeira:** Exporte dados do gráfico para Excel para que auditores verifiquem os números, reduzindo erros manuais.  
4. **Analytics de Marketing:** Visualize métricas de campanha e compartilhe pastas de trabalho editáveis com as partes interessadas para tomada de decisão colaborativa.  
5. **Geração Automatizada de Dashboards:** Combine a API de criação de gráficos com jobs agendados para produzir decks de slides atualizados todas as manhãs.

## Problemas Comuns & Solução de Problemas
- **`FileNotFoundException`** – Verifique se `dataDir` aponta para uma pasta válida e se o caminho de saída tem permissão de escrita.  
- **Vazamentos de memória** – Sempre chame `presentation.dispose()` em um bloco `finally` para liberar recursos nativos.  
- **Gráfico não aparece** – Certifique-se de que o índice do slide (`get_Item(0)`) corresponde a um slide existente, e que as dimensões do gráfico estejam dentro dos limites do slide.  
- **Exportação para Excel gera arquivo vazio** – Confirme que o gráfico realmente contém séries de dados antes de chamar `readWorkbookStream()`.

## Perguntas Frequentes

**Q: Posso usar um tipo de gráfico diferente (por exemplo, Barra, Linha) com o mesmo código?**  
A: Sim. Substitua `ChartType.Pie` por qualquer outro valor enum `ChartType`, como `ChartType.Bar` ou `ChartType.Line`.

**Q: É possível atualizar a pasta de trabalho externa após o gráfico ser criado?**  
A: Absolutamente. Modifique o arquivo Excel diretamente; o gráfico vinculado refletirá as alterações na próxima vez que a apresentação for aberta.

**Q: Preciso de uma licença separada para o recurso de exportação para Excel?**  
A: Não. A capacidade de exportação para Excel está incluída na licença padrão do Aspose.Slides para Java.

**Q: Quais versões do Java são suportadas?**  
A: Aspose.Slides para Java suporta JDK 16 e versões mais recentes; versões anteriores podem funcionar, mas não são testadas oficialmente.

**Q: Como posso incorporar a pasta de trabalho Excel gerada dentro do arquivo PPTX?**  
A: Use `chart.getChartData().setExternalWorkbook(null)` para incorporar a pasta de trabalho, ou mantenha o link externo para atualizações dinâmicas.

---

**Última Atualização:** 2026-06-03  
**Testado com:** Aspose.Slides for Java 25.4 (classificador JDK 16)  
**Autor:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar gráfico em Java com Aspose.Slides – Adicionar & Validar Gráficos](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recuperar Dados da Pasta de Trabalho de Gráficos PowerPoint Usando Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Como Atualizar o Intervalo de Dados de Gráficos PowerPoint Usando Aspose.Slides para Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}