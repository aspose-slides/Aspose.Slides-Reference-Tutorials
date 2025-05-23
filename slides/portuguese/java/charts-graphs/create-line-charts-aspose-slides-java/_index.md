---
"date": "2025-04-17"
"description": "Aprenda a criar gráficos de linhas com marcadores em Java usando o Aspose.Slides. Este tutorial aborda a criação de gráficos, a adição de séries e o salvamento eficaz de apresentações."
"title": "Crie gráficos de linhas com marcadores padrão usando Aspose.Slides para Java"
"url": "/pt/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crie gráficos de linhas com marcadores padrão usando Aspose.Slides para Java
## Introdução
Criar gráficos visualmente atraentes e informativos é essencial para apresentações, relatórios e painéis. Automatizar esse processo no desenvolvimento de software economiza tempo e garante consistência em todos os documentos. Este tutorial demonstra como criar gráficos de linhas com marcadores usando o Aspose.Slides para Java.
**Aspose.Slides para Java** é uma biblioteca poderosa que permite aos desenvolvedores manipular apresentações do PowerPoint programaticamente, sem a necessidade de instalar o Microsoft Office. Ela simplifica tarefas como criar, editar e exportar slides, tornando-se uma ferramenta essencial para a geração automatizada de documentos.
**O que você aprenderá:**
- Como inicializar o Aspose.Slides para Java
- Etapas para criar um gráfico de linhas com marcadores
- Adicionar séries e categorias aos gráficos
- Configurando legendas de gráficos
- Salvando a apresentação
Pronto para começar? Vamos garantir que você tenha tudo pronto primeiro!
## Pré-requisitos
Antes de começar, certifique-se de que seu ambiente de desenvolvimento esteja pronto:
1. **Bibliotecas e Dependências:**
   - Biblioteca Aspose.Slides para Java (versão 25.4 recomendada)
   - Java Development Kit (JDK) versão 16 ou superior
2. **Configuração do ambiente:**
   - Seu IDE deve suportar ferramentas de construção Maven ou Gradle.
   - Certifique-se de ter um arquivo de licença válido, se necessário.
3. **Pré-requisitos de conhecimento:**
   - Noções básicas de programação Java
   - Familiaridade com projetos de construção usando Maven ou Gradle
Com isso pronto, vamos configurar o Aspose.Slides para seu projeto!
## Configurando o Aspose.Slides para Java
Para usar o Aspose.Slides para Java, você precisa incluí-lo como uma dependência no seu projeto. A configuração pode variar um pouco, dependendo se você estiver usando Maven ou Gradle.
### Especialista
Adicione a seguinte dependência ao seu `pom.xml` arquivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Inclua isso em seu `build.gradle` arquivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Download direto
Alternativamente, você pode baixar a versão mais recente em [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).
**Etapas de aquisição de licença:**
- Para um teste gratuito, visite o [página de teste gratuito](https://releases.aspose.com/slides/java/).
- Para obter uma licença temporária, navegue até o [página de licença temporária](https://purchase.aspose.com/temporary-license/).
- Compre uma licença completa através de seu [portal de compras](https://purchase.aspose.com/buy).
**Inicialização básica:**
Veja como você pode inicializar o Aspose.Slides em seu aplicativo Java:
```java
import com.aspose.slides.Presentation;
// Inicializar um novo objeto de apresentação
Presentation pres = new Presentation();
```
Agora, vamos começar a criar gráficos!
## Guia de Implementação
### Recurso 1: Criação de gráficos com marcadores padrão
Esta seção demonstra como criar um gráfico de linhas equipado com marcadores. Este recurso é essencial para visualizar tendências de dados de forma eficaz.
#### Adicionando um gráfico de linhas
Para adicionar um gráfico de linhas com marcadores:
```java
import com.aspose.slides.*;
// Acesse o primeiro slide
ISlide slide = pres.getSlides().get_Item(0);
// Adicione um gráfico de linhas com marcadores ao slide na posição (10, 10) com tamanho (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### Séries e categorias de compensação
Para começar do zero:
```java
// Limpe as séries e categorias existentes para garantir uma tela limpa
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtenha a pasta de trabalho de dados do gráfico para manipulação posterior
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### Recurso 2: Adicionando séries e categorias
Adicionar séries e categorias é crucial para preencher seus gráficos com dados significativos.
#### Criando uma nova série
Para adicionar uma nova série chamada "Série 1":
```java
// Adicionar uma nova série ao gráfico
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Acesse a primeira série para preenchimento de dados
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### Preenchendo categorias e pontos de dados
Para adicionar categorias e pontos de dados correspondentes:
```java
// Adicionar nomes de categorias e seus respectivos pontos de dados
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Manipulando pontos de dados nulos com elegância
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### Recurso 3: Adicionando a segunda série e preenchendo pontos de dados
Adicionar séries adicionais proporciona mais profundidade aos seus gráficos.
#### Criando e preenchendo uma segunda série
Para adicionar "Série 2":
```java
// Adicione outra série chamada 'Série 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Acesse a segunda série para preenchimento de dados
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Adicionar pontos de dados para 'Série 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### Recurso 4: Configurando a legenda do gráfico
Configurar a legenda melhora a legibilidade do gráfico.
#### Ajustando as configurações de legenda
Para configurar:
```java
// Habilite a legenda e configure-a para não sobrepor pontos de dados
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### Recurso 5: Salvando a apresentação
Quando seu gráfico estiver pronto, salve a apresentação em um arquivo.
```java
try {
    // Salvar a apresentação modificada em um diretório especificado
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## Aplicações práticas
1. **Relatórios de negócios:**
   - Use gráficos em relatórios financeiros para descrever tendências ao longo do tempo.
2. **Análise de dados:**
   - Visualize padrões de dados e correlações durante as fases de análise.
3. **Materiais Educacionais:**
   - Crie slides informativos para palestras ou apresentações acadêmicas.
4. **Gerenciamento de projetos:**
   - Melhore os cronogramas do projeto com elementos gráficos visuais.
5. **Apresentações de marketing:**
   - Apresente tendências de vendas e resultados de campanhas de forma eficaz usando gráficos.
## Conclusão
Você aprendeu a criar gráficos de linhas com marcadores em Java usando Aspose.Slides, adicionando séries e categorias, configurando legendas e salvando apresentações. Essas habilidades são valiosas para a criação de conteúdo visual dinâmico em diversos aplicativos profissionais.
Para explorar mais sobre os recursos do Aspose.Slides ou buscar suporte da comunidade, visite seu [documentação oficial](https://docs.aspose.com/slides/java/) ou participe de fóruns como o Stack Overflow.
Boa codificação!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}