---
date: '2026-07-27'
description: Aprenda como criar doughnut chart java usando Aspose.Slides – um guia
  rápido para configurar a biblioteca, adicionar um doughnut chart personalizável,
  ajustar o tamanho do furo e salvar a apresentação.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Aprenda como criar doughnut chart java usando Aspose.Slides – um guia
  rápido para configurar a biblioteca, adicionar um doughnut chart personalizável,
  ajustar o tamanho do furo e salvar a apresentação.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Criar Doughnut Chart Java – Passo a Passo com Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Criar Doughnut Chart Java – Passo a Passo com Aspose.Slides
url: /pt/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Criar Gráficos de Rosca em Java Usando Aspose.Slides para Apresentações

## Introdução
Criar apresentações visualmente atraentes é essencial para transmitir informações de forma eficaz. **Create doughnut chart java** é uma necessidade comum quando você precisa ilustrar dados proporcionais com um visual moderno. Neste tutorial, você aprenderá como configurar o Aspose.Slides para Java, criar um gráfico de rosca, personalizar o tamanho do buraco e as cores, e finalmente salvar o arquivo de apresentação. Ao final, você terá um padrão reutilizável que pode ser inserido em qualquer projeto Java que gera decks PowerPoint automaticamente.

**O que você aprenderá:**
- Configurar o Aspose.Slides para Java
- Criar e configurar gráficos de rosca em apresentações
- Ajustar a estética do gráfico, como o tamanho do buraco
- Salvar a apresentação com seu novo gráfico

Vamos começar configurando nosso ambiente!

## Respostas Rápidas
- **Qual biblioteca cria doughnut chart java?** Aspose.Slides for Java.
- **Quantas linhas de código são necessárias para um gráfico de rosca básico?** Cerca de 8–10 linhas após a apresentação ser instanciada.
- **Posso mudar o tamanho do buraco?** Sim, o método `setHoleSize(double)` aceita valores de 0 % a 100 %.
- **Quais formatos de saída são suportados?** PPTX, PDF, XPS, PNG, JPEG e vários outros (mais de 50 no total).
- **Preciso de licença para produção?** Uma licença comercial é necessária para uso ilimitado; um teste gratuito funciona para avaliação.

## O que é Aspose.Slides para Java?
**Aspose.Slides for Java** é uma API totalmente gerenciada que permite aos desenvolvedores criar, modificar, converter e renderizar arquivos PowerPoint sem o Microsoft Office. Ela suporta mais de 50 formatos de arquivo e pode lidar com apresentações com milhares de slides mantendo o uso de memória baixo.

## Por que usar gráficos de rosca em apresentações?
Gráficos de rosca exibem relações parte‑todo enquanto liberam espaço no centro para rótulos ou imagens. Aspose.Slides pode renderizar gráficos de rosca até **500 slides por minuto** em um servidor típico de 2,5 GHz, e processa **apresentações com centenas de páginas** sem carregar o arquivo inteiro na memória, tornando‑a ideal para soluções de relatórios em grande escala.

## Pré‑requisitos
Antes de começar, certifique-se de que cobriu estes pré‑requisitos:

### Bibliotecas e Versões Necessárias
Para trabalhar com Aspose.Slides para Java, inclua-o em seu projeto via Maven ou Gradle, ou faça o download diretamente.

#### Requisitos de Configuração do Ambiente
- Um Java Development Kit (JDK) funcional, de preferência a versão 8 ou superior.
- Um Ambiente de Desenvolvimento Integrado (IDE) como IntelliJ IDEA ou Eclipse.

### Pré‑requisitos de Conhecimento
Familiaridade com Java e conceitos básicos de programação é benéfica. Conhecimento básico de Maven ou Gradle ajudará a simplificar o processo de configuração.

## Configurando Aspose.Slides para Java
Incorporar Aspose.Slides ao seu projeto pode ser feito de várias maneiras:

**Maven:**  
Adicione esta dependência ao seu arquivo `pom.xml`:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Inclua isto no seu arquivo `build.gradle`:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
- **Teste Gratuito:** Comece baixando uma versão de avaliação para explorar os recursos do Aspose.Slides.  
- **Licença Temporária:** Obtenha uma licença temporária para funcionalidade estendida sem limitações.  
- **Compra:** Para uso contínuo, é necessário adquirir uma licença.

Depois de configurar a biblioteca e seu ambiente, vamos avançar para implementar nosso gráfico de rosca.

## Como criar um gráfico de rosca em Java?
Carregue um novo objeto `Presentation`, adicione um gráfico de rosca a um slide, defina o tamanho do buraco e salve o arquivo – tudo em algumas chamadas de API simples. Essa abordagem lhe dá controle total sobre os dados do gráfico, aparência e formato de exportação, e funciona sem precisar do Microsoft PowerPoint instalado no servidor.

### Inicializar Objeto Presentation
A classe `Presentation` é o objeto de nível superior do Aspose.Slides que representa um arquivo PowerPoint na memória.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Esta etapa cria uma apresentação vazia onde você pode adicionar slides, formas e gráficos.

### Adicionar Gráfico de Rosca ao Slide
`ISlide` é a interface para um único slide; você pode recuperar o primeiro slide ou adicionar um novo.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
O método `addChart` cria um gráfico de rosca; os parâmetros definem sua posição (X, Y) e tamanho (largura, altura) no slide.

### Configurar Tamanho do Buraco da Rosca
`Chart` expõe `setHoleSize(double)` para controlar o raio interno como porcentagem do raio do gráfico.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Definir o tamanho do buraco para 90 % faz o gráfico parecer quase um círculo completo, o que é útil quando você deseja enfatizar os segmentos externos.

### Salvar Apresentação
`presentation.save(String, SaveFormat)` grava o arquivo no disco no formato escolhido.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
O exemplo salva o resultado como `DoughnutHoleSize_out.pptx`, mas você também pode escolher PDF, PNG ou qualquer um dos mais de 50 formatos suportados.

### Limpar Recursos
Chamar `presentation.dispose()` libera recursos nativos e previne vazamentos de memória, especialmente importante em aplicações de servidor de longa duração.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Aplicações Práticas
Gráficos de rosca são versáteis. Aqui estão alguns cenários onde eles se destacam:
1. **Alocação de Orçamento:** Exibir como um orçamento é distribuído entre departamentos.  
2. **Resultados de Pesquisa:** Visualizar respostas a perguntas com opções múltiplas.  
3. **Fontes de Tráfego do Site:** Mostrar a porcentagem de tráfego proveniente de diferentes canais (orgânico, pago, referência, etc.).

## Considerações de Desempenho
Ao trabalhar com Aspose.Slides, considere estas dicas para desempenho ideal:
- Descarte objetos `Presentation` assim que terminar para liberar memória nativa.  
- Use streams (`FileInputStream`, `ByteArrayOutputStream`) para grandes conjuntos de dados, evitando carregar arquivos inteiros na RAM.  
- Reutilize objetos de gráfico ao gerar muitos slides em um loop para reduzir a sobrecarga de criação de objetos.

## Problemas Comuns e Soluções
- **Erro ao salvar:** Verifique se o diretório de saída existe e se a aplicação tem permissões de gravação.  
- **Dados do gráfico ausentes:** Certifique-se de preencher a coleção `ChartData` do gráfico antes de chamar `setHoleSize`.  
- **Picos de memória:** Para apresentações com milhares de slides, habilite `Presentation.setSlideSize` para um tamanho menor e descarte slides intermediários prontamente.

## Perguntas Frequentes

**Q: Posso ajustar as cores dos segmentos do meu gráfico de rosca?**  
A: Sim. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` e então especifique a cor RGB desejada.

**Q: Como adiciono rótulos de dados ao meu gráfico?**  
A: Chame `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` para exibir o valor dentro de cada segmento.

**Q: É possível salvar gráficos em formatos diferentes de PPTX?**  
A: Absolutamente. Aspose.Slides suporta PDF, XPS, PNG, JPEG, TIFF e muitos outros formatos — mais de 50 no total.

**Q: O que devo fazer se encontrar uma exceção ao carregar uma apresentação grande?**  
A: Use o construtor `Presentation` que aceita um stream e habilite `loadOptions.setLoadFormat(LoadFormat.Pptx)` para transmitir o arquivo e reduzir o consumo de memória.

**Q: Posso automatizar atualizações de gráficos com fontes de dados ao vivo?**  
A: Sim. Recupere dados de um banco de dados ou API REST, atualize a coleção `ChartData` e chame `chart.refresh()` antes de salvar a apresentação.

## Recursos
- **Documentação:** Explore referências detalhadas da API em [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Download:** Obtenha a versão mais recente da biblioteca em [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Compra:** Para acesso completo, adquira uma licença em [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Teste Gratuito:** Experimente o Aspose.Slides com um teste gratuito disponível na página de download.  
- **Licença Temporária:** Obtenha uma licença temporária para testes estendidos sem limitações.  
- **Suporte:** Tem dúvidas? Visite o [Aspose Forum](https://forum.aspose.com/c/slides/11) para assistência.

---

**Última Atualização:** 2026-07-27  
**Testado com:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Adicionar Gráficos ao PowerPoint Usando Aspose.Slides para Java: Um Guia Passo a Passo](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Como Criar Gráfico em Java com Aspose.Slides: Um Guia Abrangente](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}