---
date: '2026-09-02'
description: Aprenda como adicionar um gráfico de colunas agrupadas a um slide do
  PowerPoint usando Aspose.Slides para Java, abordando a criação do gráfico, formatação
  e salvamento como PPTX.
keywords:
- add clustered column chart
- save powerpoint as pptx
- powerpoint chart formatting
- add chart to slide
- java create chart slide
lastmod: '2026-09-02'
og_description: Aprenda como adicionar um gráfico de colunas agrupadas a um slide
  do PowerPoint usando Aspose.Slides para Java, abordando a criação do gráfico, formatação
  e salvamento como PPTX.
og_image_alt: Guide showing how to add a clustered column chart to a PowerPoint slide
  with Aspose.Slides for Java
og_title: Adicionar gráfico de colunas agrupadas ao PPT usando Aspose.Slides Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to add clustered column chart to a PowerPoint slide using
    Aspose.Slides for Java, covering chart creation, formatting, and saving as PPTX.
  headline: Add clustered column chart to PPT using Aspose.Slides Java
  type: TechArticle
- questions:
  - answer: Replace `ChartType.ClusteredColumn` with any other enum value such as
      `ChartType.Pie`, `ChartType.Line`, or `ChartType.Bar`.
    question: How do I add different types of charts using Aspose.Slides?
  - answer: Double‑check that you’re using JDK 16 or newer and that the Maven/Gradle
      dependency version matches the library you downloaded.
    question: What should I do if I encounter compilation errors?
  - answer: Yes. Access the chart’s `getChartData()` collection, create series and
      categories, and fill them with values retrieved at runtime.
    question: Can I populate the chart with data from a database?
  - answer: Split the work into multiple `Presentation` instances, reuse chart templates,
      and always dispose of objects promptly.
    question: How can I improve performance for very large presentations?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java PowerPoint automation
- chart formatting
- PPTX
title: Adicionar gráfico de colunas agrupadas ao PPT usando Aspose.Slides Java
url: /pt/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar gráfico de colunas agrupadas ao PPT usando Aspose.Slides Java

## Introdução
Neste guia você **adicionará um gráfico de colunas agrupadas** a uma apresentação PowerPoint programaticamente com Aspose.Slides para Java. Seja construindo relatórios de negócios, decks educacionais ou apresentações de marketing, automatizar a criação de gráficos economiza tempo e garante consistência. Percorreremos a configuração da biblioteca, a criação de um slide, a adição do gráfico, a aplicação de estilos de linha e cantos arredondados, e finalmente a gravação do arquivo como PPTX. Ao final, você estará confortável com todo o fluxo de trabalho para **adicionar gráfico ao slide** e até **criar slides PowerPoint baseados em Java**.

### Respostas rápidas
- **Qual é a classe principal para iniciar?** `Presentation`
- **Qual tipo de gráfico é usado?** `ChartType.ClusteredColumn`
- **Como habilitar cantos arredondados?** `chart.setRoundedCorners(true);`
- **Qual formato é recomendado para salvar?** `SaveFormat.Pptx`
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença comprada é necessária para produção.

## O que é um gráfico de colunas agrupadas?
Um gráfico de colunas agrupadas agrupa várias séries de dados lado a lado para cada categoria, tornando‑o ideal para comparar valores entre diferentes grupos. Aspose.Slides permite gerar esse tipo de gráfico totalmente por código sem abrir o PowerPoint, e você pode personalizar cores, marcadores e opções de eixo para combinar com sua marca.

## Por que usar Aspose.Slides para Java para adicionar gráfico de colunas agrupadas?
Você pode automatizar todo o pipeline de criação de gráficos sem interação de UI, essencial para geração de relatórios no lado do servidor. Aspose.Slides funciona em qualquer sistema operacional compatível com Java, manipula apresentações com até 500 slides sem carregá‑las completamente e oferece mais de 50 estilos de gráficos incorporados. Isso elimina dependências COM e permite incorporar visuais de alta qualidade diretamente do Java.

## Pré‑requisitos
- **Aspose.Slides for Java** (v25.4 ou mais recente) – suporta mais de 50 tipos de gráficos e mais de 30 formatos de imagem.  
- **JDK 16** (ou superior) – necessário para os recursos de linguagem mais recentes.  
- Uma IDE como IntelliJ IDEA, Eclipse ou NetBeans.

## Configurando Aspose.Slides para Java
Você pode adicionar a biblioteca via Maven, Gradle ou download direto.

### Usando Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Usando Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Download direto
Baixe a versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Etapas de aquisição de licença
- **Teste gratuito** – teste todos os recursos sem limite de tempo.  
- **Licença temporária** – solicite uma no portal da Aspose para avaliação completa de recursos.  
- **Compra** – obtenha uma licença permanente para uso em produção.

## Guia de implementação

### Criando uma apresentação e adicionando um slide
`Presentation` é o objeto central do Aspose.Slides que representa um arquivo PowerPoint na memória. Depois de instanciá‑lo, você pode acessar, modificar ou adicionar slides.

#### Visão geral
Primeiro, criamos um novo objeto `Presentation` e pegamos o slide padrão que vem com um arquivo novo.

#### Passo a passo
**1. inicializar o objeto Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. acessar o primeiro slide**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. liberar recursos**  
```java
if (presentation != null) presentation.dispose();
```  

### Adicionando um gráfico a um slide
`IChart` é a interface que representa qualquer gráfico adicionado a um slide. Ao especificar `ChartType.ClusteredColumn` você indica ao Aspose.Slides para renderizar um gráfico de colunas agrupadas.

#### Visão geral
Agora incorporamos um **gráfico de colunas agrupadas** ao slide que acabamos de preparar.

#### Passo a passo
**1. inicializar o objeto Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. acessar o primeiro slide**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. adicionar um gráfico de colunas agrupadas**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. liberar recursos**  
```java
if (presentation != null) presentation.dispose();
```  

### Formatando o estilo de linha do gráfico e definindo cantos arredondados
`Chart` fornece um método `getChartFormat()` que retorna um objeto `ChartFormat`, que você pode usar para ajustar preenchimentos de linha, estilos de traço e arredondamento de cantos.

`Chart` é a classe concreta que implementa `IChart` e representa um objeto de gráfico em um slide.

#### Visão geral
Aprimore o apelo visual aplicando um preenchimento de linha sólido, um estilo de linha único e cantos arredondados.

#### Passo a passo
**1. inicializar o objeto Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. acessar o primeiro slide**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. adicionar um gráfico de colunas agrupadas**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. definir o formato da linha como tipo de preenchimento sólido**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```  

**5. aplicar estilo de linha único**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```  

**6. habilitar cantos arredondados para a área do gráfico**  
```java
chart.setRoundedCorners(true);
```  

**7. liberar recursos**  
```java
if (presentation != null) presentation.dispose();
```  

### Salvando uma apresentação
`SaveFormat.Pptx` é o formato recomendado para arquivos PowerPoint modernos, preservando toda a formatação do gráfico e permitindo edição posterior.

#### Visão geral
Finalmente, gravamos a apresentação no disco no formato PPTX, que é o padrão para operações de **salvar PowerPoint como PPTX**.

#### Passo a passo
**1. inicializar o objeto Presentation**  
```java
Presentation presentation = new Presentation();
```  

**2. definir diretório de saída e nome do arquivo**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```  

**3. salvar a apresentação no formato PPTX**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```  

**4. liberar recursos**  
```java
if (presentation != null) presentation.dispose();
```  

## Aplicações práticas
- **Relatórios de negócios** – automatize decks financeiros trimestrais com gráficos dinâmicos.  
- **Conteúdo educacional** – gere slides de aula que extraem dados de um banco de dados.  
- **Apresentações de marketing** – visualize tendências de produtos com gráficos polidos e com a marca.  

## Considerações de desempenho
- **Gerenciamento de recursos** – sempre chame `dispose()` ou use try‑with‑resources para liberar memória nativa.  
- **Otimização de memória** – processe grandes conjuntos de dados em lotes menores; Aspose.Slides pode lidar com apresentações de até 500 MB sem carregamento completo.  
- **Melhores práticas** – prefira estruturas de dados imutáveis para séries de gráficos quando possível; isso reduz a pressão de GC e melhora o rendimento.  

## Problemas comuns e soluções

| Problema | Solução |
|----------|---------|
| **`NullPointerException` on `getSlides()`** | Garanta que o objeto `Presentation` seja instanciado com sucesso antes de acessar os slides. |
| **Chart not appearing** | Verifique se as dimensões do gráfico (x, y, largura, altura) estão dentro dos limites do slide e se `ChartType.ClusteredColumn` está sendo usado. |
| **License not applied** | Carregue seu arquivo de licença antes de criar o objeto `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Perguntas frequentes

**Q: Como adiciono diferentes tipos de gráficos usando Aspose.Slides?**  
A: Substitua `ChartType.ClusteredColumn` por qualquer outro valor enum, como `ChartType.Pie`, `ChartType.Line` ou `ChartType.Bar`.

**Q: O que devo fazer se encontrar erros de compilação?**  
A: Verifique novamente se está usando JDK 16 ou superior e se a versão da dependência Maven/Gradle corresponde à biblioteca que você baixou.

**Q: Posso preencher o gráfico com dados de um banco de dados?**  
A: Sim. Acesse a coleção `getChartData()` do gráfico, crie séries e categorias, e preencha-as com valores obtidos em tempo de execução.

**Q: Como posso melhorar o desempenho para apresentações muito grandes?**  
A: Divida o trabalho em múltiplas instâncias de `Presentation`, reutilize modelos de gráficos e sempre libere os objetos prontamente.

## Conclusão
Agora você tem uma receita completa, de ponta a ponta, para **adicionar um gráfico de colunas agrupadas** a um slide PowerPoint com Aspose.Slides para Java. Experimente outros tipos de gráficos, vincule fontes de dados ao vivo e integre essa lógica em pipelines de relatórios maiores para automatizar seu fluxo de trabalho de apresentações.

---

**Última atualização:** 2026-09-02  
**Testado com:** Aspose.Slides 25.4 para Java (JDK 16)  
**Autor:** Aspose

## Tutoriais relacionados

- [Como adicionar gráfico ao PowerPoint usando Aspose.Slides para Java: um guia passo a passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Criar gráfico PowerPoint Java – Salvar apresentações com gráficos usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Adicionar animação a gráfico PowerPoint usando Aspose.Slides para Java – um guia passo a passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}