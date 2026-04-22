---
date: '2026-02-09'
description: Aprenda a criar gráficos e exportar gráficos para o Excel usando Aspose.Slides
  for Java. Domine a visualização de dados, slides de relatórios empresariais e a
  geração de pastas de trabalho.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Como criar gráfico com Aspose.Slides Java
url: /pt/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Criar Gráfico Usando Aspose.Slides para Java

**Domine Técnicas de Visualização de Dados com Aspose.Slides para Java**

No cenário atual orientado por dados, *como criar gráfico* programaticamente é uma habilidade que pode transformar números brutos em histórias visuais envolventes. Seja construindo um deck de slides de relatório empresarial ou um painel de análise interativo, o Aspose.Slides para Java oferece o poder de gerar, personalizar e exportar gráficos diretamente do seu código. Neste tutorial você aprenderá a criar objetos de gráfico, exportar dados do gráfico para Excel e vincular gráficos a pastas de trabalho externas para um gerenciamento de dados fluido.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Slides para Java (v25.4+).  
- **Posso exportar dados do gráfico para Excel?** Sim – use `readWorkbookStream()` e grave os bytes em um arquivo *.xlsx*.  
- **Qual versão do Java é exigida?** JDK 16 ou superior.  
- **Preciso de licença?** Uma licença de avaliação funciona para testes; uma licença permanente é necessária para produção.  
- **Qual tipo de gráfico é demonstrado?** Um gráfico de Pizza, mas a mesma abordagem funciona para Barras, Linhas e outros tipos de gráfico.

## O que é Aspose.Slides para Java?
Aspose.Slides para Java é uma API pura‑Java que permite a desenvolvedores criar, editar e converter apresentações PowerPoint sem o Microsoft Office. Ela suporta toda a gama de tipos de gráfico, vinculação de dados e recursos de exportação, tornando‑a ideal para projetos de **data visualization java**.

## Por que usar Aspose.Slides para criar gráfico e exportar gráfico para Excel?
- **Sem necessidade de instalação do Office** – funciona em qualquer servidor ou ambiente de nuvem.  
- **Biblioteca rica de gráficos** – dezenas de tipos de gráfico e controle total de estilo.  
- **Exportação direta para Excel** – gera uma pasta de trabalho externa para análise posterior.  
- **Orientado a desempenho** – baixo consumo de memória e processamento rápido para decks grandes.

## Pré‑requisitos
Antes de mergulharmos, certifique‑se de que você possui o seguinte:

### Bibliotecas Necessárias e Versões
- **Aspose.Slides para Java** versão 25.4 ou posterior

### Requisitos de Configuração do Ambiente
- Java Development Kit (JDK) 16 ou superior  
- Uma IDE como IntelliJ IDEA ou Eclipse (ou qualquer editor de texto de sua preferência)

### Pré‑requisitos de Conhecimento
- Habilidades básicas de programação em Java  
- Familiaridade com ferramentas de build Maven ou Gradle

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

### Etapas para Aquisição de Licença
Aspose.Slides oferece uma licença de avaliação gratuita para explorar todos os recursos. Você também pode solicitar uma licença temporária ou adquirir uma licença para uso prolongado. Siga estas etapas:

1. Visite a [página de Compra da Aspose](https://purchase.aspose.com/buy) para obter sua licença.  
2. Para uma avaliação gratuita, faça o download em [Releases](https://releases.aspose.com/slides/java/).  
3. Solicite uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

Depois de obter o arquivo de licença, inicialize‑o em sua aplicação Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guia Passo a Passo

### Como criar gráfico – Carregar uma Apresentação
Carregar um arquivo PowerPoint existente é o primeiro passo antes de adicionar ou modificar gráficos.

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

**Explicação:**  
- `Presentation` representa o arquivo PowerPoint.  
- Sempre chame `dispose()` para liberar recursos nativos.

### Como criar gráfico – Adicionar um Gráfico de Pizza a um Slide
Agora inseriremos um gráfico de Pizza, que é perfeito para mostrar dados proporcionais.

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

**Explicação:**  
- `addChart` insere o gráfico no primeiro slide.  
- Os parâmetros definem o tipo de gráfico, posição X/Y e tamanho.

### Como exportar gráfico para Excel – Exportar Dados do Gráfico
Exportar os dados do gráfico permite que analistas trabalhem com os números no Excel, possibilitando insights mais profundos.

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

**Explicação:**  
- `readWorkbookStream()` extrai a pasta de trabalho Excel subjacente ao gráfico como um array de bytes.  
- O array de bytes é gravado em `externalWorkbook1.xlsx`, fornecendo um arquivo Excel pronto para uso.

### Como criar gráfico – Definir Pasta de Trabalho Externa para Dados Dinâmicos
Vincular um gráfico a uma pasta de trabalho externa permite atualizar o gráfico simplesmente editando o arquivo Excel.

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

**Explicação:**  
- `setExternalWorkbook` associa o gráfico ao arquivo Excel especificado, permitindo atualizações de dados em tempo real sem reconstruir o slide.

## Aplicações Práticas
Aspose.Slides oferece soluções versáteis para diversos cenários reais:

1. **Slides de Relatórios Empresariais:** Gere gráficos de desempenho trimestral automaticamente a partir de seus pipelines de dados.  
2. **Apresentações Acadêmicas:** Transforme dados de pesquisa em visualizações claras sem a necessidade de criar gráficos manualmente.  
3. **Análise Financeira:** Exporte dados do gráfico para Excel para que auditores verifiquem os números.  
4. **Analytics de Marketing:** Visualize métricas de campanhas e compartilhe pastas de trabalho editáveis com as partes interessadas.

## Problemas Comuns & Solução de Problemas
- **`FileNotFoundException`** – Verifique se `dataDir` aponta para uma pasta válida e se o caminho de saída tem permissão de gravação.  
- **Vazamentos de memória** – Sempre chame `pres.dispose()` em um bloco `finally` para liberar recursos nativos.  
- **Gráfico não aparece** – Certifique‑se de que o índice do slide (`get_Item(0)`) corresponde a um slide que realmente existe.

## Perguntas Frequentes

**P: Posso usar um tipo de gráfico diferente (ex.: Barra, Linha) com o mesmo código?**  
R: Sim. Substitua `ChartType.Pie` por qualquer outro valor do enum `ChartType`, como `ChartType.Bar` ou `ChartType.Line`.

**P: É possível atualizar a pasta de trabalho externa depois que o gráfico foi criado?**  
R: Absolutamente. Modifique o arquivo Excel diretamente; o gráfico vinculado refletirá as alterações na próxima vez que a apresentação for aberta.

**P: Preciso de uma licença separada para o recurso de exportação para Excel?**  
R: Não. A capacidade de exportação para Excel está incluída na licença padrão do Aspose.Slides para Java.

**P: Quais versões do Java são suportadas?**  
R: Aspose.Slides para Java suporta JDK 16 e versões mais recentes; versões anteriores podem funcionar, mas não são testadas oficialmente.

**P: Como posso incorporar a pasta de trabalho Excel gerada dentro do arquivo PPTX?**  
R: Use `chart.getChartData().setExternalWorkbook(null)` para incorporar a pasta de trabalho, ou mantenha o link externo para atualizações dinâmicas.

---

**Última Atualização:** 2026-02-09  
**Testado Com:** Aspose.Slides para Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}