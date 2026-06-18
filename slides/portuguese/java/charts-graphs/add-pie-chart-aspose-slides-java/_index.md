---
date: '2026-05-29'
description: Aprenda como criar gráfico de pizza usando Aspose.Slides Maven, adicionar
  gráfico de pizza Java a um slide e personalizar os dados do gráfico. Guia passo
  a passo com configuração do Maven e exemplos do mundo real.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Criar Gráfico de Pizza Aspose – Adicionar um Gráfico a uma Apresentação com
  Maven
url: /pt/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como Adicionar um Gráfico de Pizza a uma Apresentação Usando Aspose.Slides Java

## Introdução
Neste guia você **create pie chart aspose** com Aspose.Slides Maven e verá como incorporá‑lo em um slide do PowerPoint. Criar apresentações visualmente atraentes é crucial para transmitir informações de forma eficaz, especialmente quando a visualização de dados desempenha um papel fundamental. Se você deseja automatizar esse processo com **aspose slides maven**, está no lugar certo. Vamos percorrer a adição de um gráfico a um slide — especificamente um gráfico de pizza — e personalizá‑lo para cenários do mundo real.

### O que você aprenderá
- Como inicializar um objeto de apresentação em Java.  
- Etapas para **add a pie chart java** no primeiro slide de uma apresentação.  
- Acessar as pastas de trabalho de dados do gráfico e listar as planilhas dentro delas.  

Vamos mergulhar em como você pode aproveitar o Aspose.Slides Java para aprimorar suas apresentações com gráficos dinâmicos!

## Respostas Rápidas
- **Qual biblioteca adiciona gráficos via Maven?** aspose slides maven  
- **Qual tipo de gráfico é demonstrado?** Gráfico de pizza (add chart to slide)  
- **Versão mínima do Java necessária?** JDK 16 ou posterior  
- **Preciso de licença para testes?** Um teste gratuito funciona; produção requer licença  
- **Onde posso encontrar a dependência Maven?** Na seção de configuração abaixo  

## O que é Aspose Slides Maven?
Aspose.Slides for Java é uma API poderosa que permite que desenvolvedores criem, modifiquem e renderizem arquivos PowerPoint programaticamente. O pacote Maven (`aspose-slides`) simplifica o gerenciamento de dependências, permitindo que você se concentre em construir e personalizar slides—como adicionar um gráfico de pizza—sem lidar com manipulação de arquivos de baixo nível.

## Por que usar Aspose.Slides Maven para adicionar um gráfico a um slide?
Usar Aspose.Slides Maven permite gerar gráficos diretamente a partir do código Java sem edição manual no PowerPoint. Ele fornece controle programático total sobre tipos de gráficos, fontes de dados e estilos, garantindo consistência de marca e precisão. O artefato Maven também cuida de todas as dependências necessárias, simplificando builds e permitindo integração fluida em pipelines CI/CD.

## Pré-requisitos
- **Aspose.Slides for Java** versão 25.4 ou posterior (Maven/Gradle).  
- JDK 16+ instalado.  
- Uma IDE (IntelliJ IDEA, Eclipse, etc.).  
- Conhecimento básico de Java e familiaridade com Maven ou Gradle.

## Configurando Aspose.Slides para Java
Primeiro, inclua Aspose.Slides em seu projeto via Maven ou Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, você pode [download the latest release](https://releases.aspose.com/slides/java/) diretamente do site da Aspose.

### Aquisição de Licença
Aspose.Slides for Java oferece um teste gratuito com uma licença temporária para testes. Para uso de produção sem restrições, adquira uma licença através da [purchase page](https://purchase.aspose.com/buy).

## Guia de Implementação
A seguir, dividimos a solução em duas funcionalidades: adicionar um gráfico de pizza e acessar sua pasta de trabalho de dados.

### Recurso 1: Criando uma Apresentação e Adicionando um Gráfico
#### Visão geral
Esta parte mostra como criar uma nova apresentação e **add a pie chart** ao primeiro slide.

#### Como criar gráfico de pizza aspose?
Carregue a classe `Presentation`, adicione um gráfico do tipo `ChartType.Pie` e salve o arquivo. Toda a operação requer apenas três chamadas de API e é concluída em menos de um segundo para um deck típico de 10 slides, tornando‑a ideal para geração automática de relatórios.

#### Passo a passo

**Step 1: Initialize a New Presentation Object**  
A classe `Presentation` é o objeto de nível superior do Aspose.Slides que representa um arquivo PowerPoint na memória.  
```java
Presentation pres = new Presentation();
```
*Cria a instância `Presentation` que conterá todos os slides.*

**Step 2: Add a Pie Chart**  
`ChartType.Pie` indica ao Aspose que deve renderizar um gráfico de pizza.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Posiciona um gráfico de pizza nas coordenadas (50, 50) com largura de 400 e altura de 500.*

**Step 3: Dispose of Resources**  
Chamar `dispose()` libera recursos nativos e evita vazamentos de memória.  
```java
if (pres != null) pres.dispose();
```
*Libera recursos nativos; sempre chame `dispose()` quando terminar.*

### Recurso 2: Acessando a Pasta de Trabalho de Dados do Gráfico e as Planilhas
#### Visão geral
Aprenda como acessar a pasta de trabalho subjacente que armazena os dados do gráfico e iterar pelas suas planilhas.

#### Como acessar a pasta de trabalho de dados do gráfico?
Recupere o `IChartDataWorkbook` do gráfico e, em seguida, percorra sua coleção `Worksheets`. Essa pasta de trabalho imita um arquivo Excel, permitindo ler, modificar ou adicionar séries de dados programaticamente, o que o gráfico refletirá instantaneamente quando atualizado em tempo de execução sem reinicialização.

#### Passo a passo

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Mesmo do Recurso 1, Etapa 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*Mesmo do Recurso 1, Etapa 2.*

**Step 3: Get the Chart Data Workbook**  
`IChartDataWorkbook` é a interface que fornece acesso de leitura/gravação à pasta de trabalho interna do gráfico.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Recupera o `IChartDataWorkbook` vinculado ao gráfico.*

**Step 4: Iterate Through Worksheets**  
Objetos `Worksheet` representam planilhas individuais dentro da pasta de trabalho.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Imprime o nome de cada planilha, permitindo que você verifique a estrutura de dados.*

**Step 5: Dispose of Resources**  
*Mesmo do Recurso 1, Etapa 3.*

## Aplicações Práticas
- **Relatórios de Dados:** Geração automática de decks de slides com métricas atualizadas para business intelligence.  
- **Apresentações Acadêmicas:** Visualizar resultados de pesquisa sem criação manual de gráficos.  
- **Material de Marketing:** Exibir desempenho de produtos ou resultados de pesquisas instantaneamente.

## Considerações de Desempenho
- Aspose.Slides pode lidar com **mais de 50 formatos de entrada e saída** e processar apresentações de centenas de páginas sem carregar todo o arquivo na memória.  
- Mantenha o número de slides e gráficos razoável; cada gráfico consome memória nativa.  
- Sempre chame `dispose()` para liberar recursos prontamente.  
- Otimize o manuseio de dados da pasta de trabalho—evite carregar conjuntos de dados massivos em um único gráfico.

## Conclusão
Cobremos como **aspose slides maven** permite **add chart to slide** programaticamente e como trabalhar com a pasta de trabalho de dados do gráfico. Com esses blocos de construção, você pode automatizar qualquer fluxo de trabalho de relatório que exija uma saída PowerPoint polida.

### Próximos passos
- Explore opções de estilo de gráfico (cores, legendas, rótulos de dados).  
- Conecte a fontes de dados externas (CSV, bancos de dados) para popular gráficos dinamicamente.  
- Combine múltiplos tipos de gráficos em uma única apresentação para contar histórias mais ricas.

## Perguntas Frequentes

**Q: Como instalo Aspose.Slides para Java?**  
A: Use a dependência Maven ou Gradle mostrada acima, ou faça o download da biblioteca na página de releases.

**Q: Quais são os requisitos de sistema para Aspose.Slides?**  
A: JDK 16 ou posterior; a biblioteca funciona em qualquer plataforma que suporte Java.

**Q: Posso adicionar outros tipos de gráficos além de gráficos de pizza?**  
A: Sim, Aspose.Slides suporta barras, linhas, dispersão, radar e mais de 20 tipos de gráficos.

**Q: Como devo lidar com apresentações grandes de forma eficiente?**  
A: Libere objetos prontamente, limite imagens de alta resolução e reutilize modelos de gráficos para manter o uso de memória baixo.

**Q: Onde posso encontrar mais detalhes sobre os recursos do Aspose.Slides?**  
A: Visite a [Aspose documentation](https://reference.aspose.com/slides/java/) para uma referência completa da API.

**Q: É necessária uma licença para uso comercial?**  
A: Uma licença válida é necessária para produção; um teste gratuito está disponível para avaliação.

**Q: O pacote Maven inclui todas as capacidades de gráficos?**  
A: Sim, o artefato Maven `aspose-slides` contém o motor completo de gráficos.

## Recursos
- Documentação: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Compra e Teste: [Purchase Page](https://purchase.aspose.com/buy)
- Teste gratuito: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Licença Temporária: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Fórum de Suporte: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Última atualização:** 2026-05-29  
**Testado com:** Aspose.Slides 25.4 for Java (jdk16)  
**Autor:** Aspose

## Tutoriais Relacionados

- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Create a Pie of Pie Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}