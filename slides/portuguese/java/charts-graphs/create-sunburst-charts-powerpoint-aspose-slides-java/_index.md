---
date: '2026-07-17'
description: Aprenda a adicionar gráficos Sunburst no PowerPoint usando Aspose Slides
  for Java. Guia passo a passo cobre configuração, criação de gráficos, personalização
  e casos de uso reais.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Como adicionar gráficos Sunburst no PowerPoint usando Aspose Slides
  for Java. Siga este tutorial para configurar a biblioteca, criar um gráfico, personalizar
  pontos de dados e aplicá-lo em projetos reais.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Como adicionar gráficos Sunburst no PowerPoint com Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Como adicionar gráficos Sunburst no PowerPoint com Aspose (Java)
url: /pt/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Adicionar Gráficos Sunburst no PowerPoint com Aspose (Java)

## Introdução

Adicionar um gráfico sunburst a um deck de PowerPoint pode transformar instantaneamente uma tabela de dados plana em uma hierarquia visual envolvente. Neste tutorial você aprenderá **como adicionar gráficos sunburst** no PowerPoint usando Aspose.Slides para Java, desde a configuração do ambiente até o ajuste fino de cores e rótulos. Seja construindo um painel de vendas, uma decomposição de tarefas de projeto ou um conjunto de slides educacionais, os passos abaixo fornecerão uma solução pronta para produção.

**O que Você Vai Aprender**
- Como configurar Aspose.Slides em um projeto Maven ou Gradle  
- Como criar uma nova apresentação e inserir um gráfico sunburst  
- Como personalizar pontos de dados, rótulos e cores de preenchimento  
- Cenários do mundo real onde gráficos sunburst se destacam  

Vamos começar e ver como é fácil transformar dados hierárquicos brutos em um visual de PowerPoint refinado.

## Respostas Rápidas
- **Biblioteca principal?** Aspose.Slides para Java  
- **Tipo de gráfico suportado?** Sunburst (hierárquico radial)  
- **Versão mínima do Java?** JDK 16  
- **Tempo típico de implementação?** 10‑15 minutos para um gráfico básico  
- **Licença necessária para produção?** Sim, uma licença Aspose válida  

## O que é um Gráfico Sunburst?
Um gráfico sunburst é um diagrama radial que visualiza dados hierárquicos aninhando anéis a partir de um ponto central. É perfeito para mostrar relações de múltiplos níveis, como estruturas organizacionais, categorias de produtos ou árvores de sistemas de arquivos. Cada anel concêntrico representa um nível da hierarquia, e o tamanho de cada segmento reflete seu valor quantitativo, permitindo que os espectadores compreendam rapidamente tanto a estrutura quanto a magnitude.

## Por que Usar Aspose.Slides para Java?
Aspose.Slides suporta **mais de 50 tipos de gráfico** e pode manipular apresentações com **até 10.000 slides** sem carregar todo o arquivo na memória, oferecendo alto desempenho para relatórios em escala empresarial. Funciona em múltiplas plataformas, oferece ampla cobertura de API e inclui opções robustas de licenciamento que removem limites de avaliação, tornando‑o ideal para ambientes de produção.

## Pré-requisitos
- **Java Development Kit (JDK)** 16 ou superior  
- **IDE** – IntelliJ IDEA, Eclipse ou qualquer editor compatível com Java  
- Familiaridade básica com sintaxe Java e ferramentas de build Maven/Gradle  

## Configurando Aspose.Slides para Java

### Dependência Maven
Adicione o artefato Aspose.Slides Maven ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dependência Gradle
Se preferir Gradle, inclua a linha a seguir em `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download Direto
Você também pode baixar o JAR mais recente diretamente da página oficial de lançamentos: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
Para executar sem limites de avaliação, obtenha uma licença:
- **Teste gratuito** – licença temporária para avaliação rápida.  
- **Licença temporária** – solicite uma no [site da Aspose](https://purchase.aspose.com/temporary-license).  
- **Compra completa** – adquira uma assinatura para uso ilimitado em produção.

### Inicialização Básica
A classe `Presentation` é o ponto de entrada para criar ou abrir arquivos PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Guia de Implementação

### Como adicionar um gráfico sunburst a uma apresentação PowerPoint usando Aspose.Slides para Java?

Carregue uma nova `Presentation`, adicione um slide, insira um `IChart` do tipo `ChartType.Sunburst` e chame `save`. Este padrão conciso de três etapas cria um gráfico sunburst totalmente funcional pronto para personalização adicional.

#### Etapa 1: Inicializar a Apresentação
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Etapa 2: Adicionar Gráfico Sunburst
A interface `IChart` define um objeto de gráfico que pode ser colocado em qualquer slide. Aqui adicionamos um gráfico sunburst nas coordenadas (100, 100) com tamanho de 450 × 400 pontos.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Etapa 3: Salvar a Apresentação
Sempre persista suas alterações chamando `save`. Você pode escolher PPTX, PDF ou qualquer um dos mais de 50 formatos de saída suportados.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modificar Pontos de Dados no Gráfico

#### Visão Geral
Você pode personalizar cada fatia do sunburst — rótulos, cores e visibilidade — através da coleção de pontos de dados do gráfico.

#### Etapa 1: Acessar a Coleção de Pontos de Dados
A primeira série do gráfico contém uma coleção de objetos `IChartDataPoint` que representam cada fatia.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Etapa 2: Exibir Valor para um Ponto de Dados Específico
Defina `IsValueShown` como `true` no ponto de dados desejado para exibir seu valor numérico diretamente na fatia.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Etapa 3: Modificar Formatos de Rótulo
Ajuste a visibilidade do rótulo, cor da fonte e fundo para melhorar a legibilidade.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Etapa 4: Definir Cor de Preenchimento para Pontos de Dados
Personalize a cor de preenchimento de fatias individuais para combinar com a paleta da sua marca ou destacar segmentos chave.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Etapa 5: Salvar a Apresentação Modificada
Persistir o gráfico personalizado salvando a apresentação novamente.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Aplicações Práticas

1. **Business Analytics** – Visualizar vendas por região → linha de produto → SKU em uma única visualização radial.  
2. **Project Management** – Mostrar estruturas de decomposição de trabalho, detalhando de fases para tarefas e subtarefas.  
3. **Education** – Mapear hierarquias curriculares, como departamentos → cursos → módulos.  

## Considerações de Desempenho

- **Eficiência de Memória:** Aspose.Slides transmite dados, de modo que até um deck de 500 páginas com múltiplos gráficos permanece abaixo de 200 MB de RAM.  
- **Coleta de Lixo:** Libere objetos de slide (`slide.dispose()`) quando não forem mais necessários para evitar vazamentos de memória.  

## Perguntas Frequentes

**Q: O que é um gráfico sunburst?**  
A: Um gráfico sunburst visualiza dados hierárquicos em anéis concêntricos, com cada anel representando um nível da hierarquia.

**Q: Como instalar Aspose.Slides para Java usando Maven?**  
A: Adicione a dependência Maven mostrada na seção “Dependência Maven” ao seu `pom.xml` e execute `mvn clean install`.

**Q: Posso personalizar outros tipos de gráfico com Aspose.Slides?**  
A: Sim, a biblioteca suporta mais de 50 tipos de gráfico, incluindo colunas, linhas, pizza e radar.

**Q: Minha apresentação não está salvando—o que devo verificar?**  
A: Verifique se o caminho do arquivo está correto, se o diretório existe e se você tem permissões de escrita. Também assegure que o método `Presentation.save()` foi chamado.

**Q: Onde posso obter mais ajuda ou exemplos?**  
A: Visite o [Aspose forum](https://forum.aspose.com/c/slides/11) ou consulte a referência oficial do [Aspose.Slides](https://reference.aspose.com/slides/java/).

## Recursos
- **Documentação:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Referência (minúsculas):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Fórum da Comunidade:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Downloads:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Última atualização:** 2026-07-17  
**Testado com:** Aspose.Slides para Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Adicionar Gráficos ao PowerPoint Usando Aspose.Slides para Java: Um Guia Passo a Passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animar Gráficos no PowerPoint Usando Aspose.Slides para Java – Um Guia Passo a Passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Criar gráfico em Java com Aspose.Slides – Adicionar & Validar Gráficos](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}