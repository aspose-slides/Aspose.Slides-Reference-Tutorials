---
date: '2026-08-27'
description: Aprenda a criar um gráfico de colunas agrupadas em Java usando Aspose.Slides,
  adicionar o gráfico, definir cores automáticas das séries e salvar a apresentação
  como PPTX.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: Aprenda a criar um gráfico de colunas agrupadas em Java usando Aspose.Slides,
  adicionar o gráfico, definir cores automáticas das séries e salvar a apresentação
  como PPTX — tudo com instruções claras passo a passo.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: Criar gráfico de colunas agrupadas em Java com Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: Como criar gráfico de colunas agrupadas em Java com Aspose.Slides
url: /pt/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar um gráfico de colunas agrupadas em Java com Aspose.Slides

## Introdução
Criar um gráfico de colunas agrupadas programaticamente economiza horas de formatação manual e garante consistência em várias apresentações. Neste tutorial você aprenderá **como criar um gráfico de colunas agrupadas** em Java com Aspose.Slides, **como adicionar o gráfico**, **como definir cores** e **como salvar a apresentação como PPTX**. Cobriremos tudo, desde a instalação da biblioteca até a personalização das cores de preenchimento das séries e a persistência do arquivo, para que você possa incorporar visualizações de dados avançadas em qualquer deck do PowerPoint.

## Respostas rápidas
- **Qual é a classe principal para trabalhar com apresentações?** `Presentation` do pacote `com.aspose.slides`.  
- **Como adiciono um gráfico de colunas agrupadas?** Chame `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **As cores das séries podem ser definidas automaticamente?** Sim—habilite `setAutomaticSeriesColor(true)` em cada série.  
- **Qual formato devo usar para salvar o arquivo?** `SaveFormat.Pptx` produz um arquivo PowerPoint padrão.  
- **É necessária uma licença para produção?** Um trial funciona para desenvolvimento; uma licença completa é necessária para uso comercial.

## O que é um gráfico de colunas agrupadas?
Um gráfico de colunas agrupadas exibe várias séries de dados lado a lado para cada categoria, facilitando a comparação de valores entre grupos. O Aspose.Slides oferece suporte a esse tipo de gráfico nativamente e permite controlar todos os aspectos visuais programaticamente.

## Por que criar um gráfico de colunas agrupadas com Aspose.Slides?
O Aspose.Slides pode lidar com **mais de 50 formatos de entrada e saída** e processar apresentações com **centenas de slides** sem carregar o arquivo inteiro na memória. Essa eficiência permite gerar decks extensos em um ambiente server‑side com consumo mínimo de recursos.

## Pré-requisitos
- **Java Development Kit** 16 ou mais recente.  
- **Maven** ou **Gradle** para gerenciamento de dependências.  
- Familiaridade básica com a sintaxe Java e conceitos de programação orientada a objetos.  

### Bibliotecas e dependências necessárias
É necessário a biblioteca Aspose.Slides for Java (versão 25.4 ou posterior). A biblioteca é totalmente compatível com JDK 16 e oferece uma API rica para manipulação de gráficos.

### Requisitos de configuração do ambiente
Seu IDE (IntelliJ IDEA, Eclipse, VS Code) deve estar configurado para compilar código Java 16 e resolver dependências Maven/Gradle.

### Pré-requisitos de conhecimento
Entender a estrutura de slides do PowerPoint e a terminologia básica de gráficos (séries, categorias, pontos de dados) ajudará a seguir os exemplos mais rapidamente.

## Configurando Aspose.Slides para Java
Integre a biblioteca ao seu projeto usando um dos métodos a seguir.

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

**Download direto** – obtenha o JAR na página oficial de lançamentos: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Etapas de aquisição de licença
- **Trial gratuito** – registre‑se no site da Aspose para receber um arquivo de licença temporário.  
- **Licença temporária** – solicite uma licença de 30 dias para suítes de teste maiores.  
- **Licença completa** – adquira para uso ilimitado em produção.

**Inicialização e configuração básicas**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## Como adicionar um gráfico de colunas agrupadas?
`Presentation` representa um arquivo PowerPoint na memória.  

**Resposta direta:**  
Crie um objeto `Presentation`, recupere o primeiro slide e chame `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`. Essa única chamada insere um gráfico de colunas agrupadas totalmente funcional, pronto para receber dados, e o posiciona nas coordenadas especificadas no slide.

### Recurso 1: criar gráfico de colunas agrupadas
A classe `Presentation` representa um arquivo PowerPoint na memória e fornece acesso a slides, formas e objetos de gráfico.

**Etapa 1: inicializar a apresentação**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**Etapa 2: adicionar gráfico de colunas agrupadas**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**Etapa 3: liberar recursos**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Como definir cores para o gráfico?
`Series` representa uma coleção de pontos de dados dentro de um gráfico.  

**Resposta direta:**  
Após criar o gráfico, obtenha seus dados via `chart.getChartData()` e itere sobre cada objeto `Series`. Para cada série, chame `setAutomaticSeriesColor(true)` na série pai. O Aspose.Slides então atribui automaticamente uma cor distinta e contrastante da sua paleta a cada série, garantindo clareza visual sem necessidade de seleção manual de cores.

### Recurso 2: definir preenchimento automático de série
`IChart` é a interface que representa uma forma de gráfico; ela expõe `getChartData()` para manipulação de séries.

**Etapa 1: acessar o gráfico e iterar as séries**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**Etapa 2: gerenciamento de recursos**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Como salvar a apresentação como PPTX?
`save` grava a apresentação em um arquivo no formato escolhido.  

**Resposta direta:**  
Defina um caminho de saída, por exemplo `"output/ClusteredColumnChart.pptx"`, e invoque `presentation.save(outputPath, SaveFormat.Pptx)`. O método `save` serializa todo o deck de slides, incluindo todas as formas, gráficos e recursos, em um arquivo PPTX padrão que pode ser aberto pelo PowerPoint 2010 ou posterior, bem como por diversos visualizadores online.

### Recurso 3: salvar a apresentação no disco
Salvar com `SaveFormat.Pptx` produz um arquivo compatível com PowerPoint 2010 e versões posteriores, além da maioria dos visualizadores online.

**Etapa 1: definir o caminho de saída**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**Etapa 2: salvar a apresentação**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## Aplicações práticas
- **Relatórios financeiros** – comparar a receita trimestral entre linhas de produto.  
- **Análises de marketing** – visualizar o desempenho de campanhas por região.  
- **Gerenciamento de projetos** – exibir a velocidade de sprint ou alocação de recursos entre equipes.  

## Considerações de desempenho
- Libere os objetos `Presentation` prontamente para liberar recursos nativos.  
- Use `presentation.getSlides().removeUnusedResources()` antes de salvar para reduzir o tamanho do arquivo.  
- Popule as séries do gráfico com coleções leves (por exemplo, `ArrayList<Double>`) para manter o uso de memória baixo.

## Conclusão
Agora você sabe **como criar um gráfico de colunas agrupadas**, definir **cores automaticamente** e **salvar a apresentação como PPTX** usando Aspose.Slides para Java. Essas etapas permitem gerar slides orientados a dados programaticamente, eliminando trabalho manual repetitivo e assegurando consistência visual em toda a sua organização.

**Próximos passos:**  
Explore personalizações avançadas como rótulos de dados, formatação de eixos e vinculação dinâmica de dados a partir de bancos de dados ou arquivos CSV para enriquecer ainda mais suas apresentações.

## Perguntas frequentes
**Q: Posso usar este código em uma aplicação web?**  
**A:** Sim—Aspose.Slides é independente de plataforma e funciona em qualquer ambiente servidor baseado em Java, incluindo Spring Boot e Jakarta EE.

**Q: A biblioteca suporta outros tipos de gráfico?**  
**A:** Absolutamente. O enum `ChartType` inclui Pie, Bar, Line, Area, Radar e muitos outros.

**Q: E se a pasta de saída não existir?**  
**A:** Certifique‑se de criar o diretório previamente ou use `Files.createDirectories(Paths.get(folder))` para evitar `FileNotFoundException`.

**Q: Como lidar com conjuntos de dados grandes (milhares de pontos)?**  
**A:** Popule as séries usando APIs de streaming ou inserções em lote e considere desativar animações do gráfico para melhorar a velocidade de renderização.

**Q: Onde posso encontrar mais exemplos de código?**  
**A:** Visite a documentação oficial e o repositório de exemplos: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## Recursos
- **Documentação:** [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Referência:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download:** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Comprar licença:** [Buy a License](https://purchase.aspose.com/buy)  
- **Iniciar teste gratuito:** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Licença temporária:** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Fórum Aspose:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-27  
**Tested With:** Aspose.Slides 25.4 (JDK 16)  
**Author:** Aspose

## Tutoriais Relacionados

- [Criar Gráfico PowerPoint Java – Salvar Apresentações com Gráficos Usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Dependência Maven do Aspose Slides: Adicionar e Configurar Gráficos em Apresentações Usando Aspose.Slides para Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Adicionar animação a gráfico PowerPoint usando Aspose.Slides para Java – Guia passo a passo](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}