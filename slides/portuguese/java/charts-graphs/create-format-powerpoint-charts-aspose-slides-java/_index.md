---
date: '2026-03-15'
description: Aprenda como adicionar um gráfico de colunas agrupadas a um slide do
  PowerPoint usando Aspose.Slides for Java, abordando as etapas para inserir o gráfico
  no slide e criar slides do PowerPoint em Java de forma eficiente.
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: Adicionar Gráfico de Colunas Agrupadas ao PPT usando Aspose.Slides Java
url: /pt/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Adicionar Gráfico de Colunas Agrupadas ao PPT usando Aspose.Slides Java

## Introdução
Neste guia você **adicionará um gráfico de colunas agrupadas** a uma apresentação PowerPoint programaticamente com Aspose.Slides para Java. Seja criando relatórios empresariais, decks educacionais ou apresentações de marketing, automatizar a criação de gráficos economiza tempo e garante consistência. Vamos percorrer a configuração da biblioteca, a criação de um slide, a adição do gráfico, a aplicação de estilos de linha e cantos arredondados e, finalmente, a gravação do arquivo. Ao final, você estará confortável com todo o fluxo de trabalho para **adicionar gráfico ao slide** e até mesmo **criar slide PowerPoint Java**‑baseado em soluções.

### Respostas Rápidas
- **Qual é a classe principal para iniciar?** `Presentation`
- **Qual tipo de gráfico é usado?** `ChartType.ClusteredColumn`
- **Como habilitar cantos arredondados?** `chart.setRoundedCorners(true);`
- **Qual formato é recomendado para salvar?** `SaveFormat.Pptx`
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença comprada é necessária para produção.

## O que é um gráfico de colunas agrupadas?
Um gráfico de colunas agrupadas agrupa várias séries de dados lado a lado para cada categoria, tornando‑o ideal para comparar valores entre diferentes grupos. Aspose.Slides permite gerar esse tipo de gráfico totalmente por código, sem abrir o PowerPoint.

## Por que usar Aspose.Slides para Java para adicionar gráfico de colunas agrupadas?
- **Automação completa** – Nenhuma interação manual de UI necessária.  
- **Multiplataforma** – Funciona em qualquer SO que suporte Java.  
- **Formatação rica** – Controle de estilos de linha, preenchimentos, cantos arredondados e mais.  
- **Sem dependências COM** – Ao contrário do Office Interop, roda em servidores com segurança.

## Pré‑requisitos
- **Aspose.Slides para Java** (v25.4 ou mais recente)  
- **JDK 16** (ou superior)  
- Uma IDE como IntelliJ IDEA, Eclipse ou NetBeans  

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

### Download Direto
Baixe a versão mais recente em [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Etapas para Aquisição de Licença
- **Teste Gratuito** – Teste todos os recursos sem limite de tempo.  
- **Licença Temporária** – Solicite uma no portal Aspose para avaliação completa de recursos.  
- **Compra** – Obtenha uma licença permanente para uso em produção.

## Guia de Implementação

### Criando uma Apresentação e Adicionando um Slide
#### Visão Geral
Primeiro, criamos um novo objeto `Presentation` e obtém‑se o slide padrão que vem com um arquivo recém‑criado.

#### Passo a Passo
**1. Inicializar o Objeto Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Acessar o Primeiro Slide**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Liberar Recursos**  
```java
if (presentation != null) presentation.dispose();
```

### Adicionando um Gráfico a um Slide
#### Visão Geral
Agora incorporamos um **gráfico de colunas agrupadas** ao slide que preparamos.

#### Passo a Passo
**1. Inicializar o Objeto Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Acessar o Primeiro Slide**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Adicionar um Gráfico de Colunas Agrupadas**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Liberar Recursos**  
```java
if (presentation != null) presentation.dispose();
```

### Formatando o Estilo da Linha do Gráfico e Definindo Cantos Arredondados
#### Visão Geral
Aprimore a aparência visual aplicando um preenchimento de linha sólido, um único estilo de linha e cantos arredondados.

#### Passo a Passo
**1. Inicializar o Objeto Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Acessar o Primeiro Slide**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Adicionar um Gráfico de Colunas Agrupadas**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Definir Formato da Linha como Tipo de Preenchimento Sólido**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. Aplicar Estilo de Linha Única**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. Habilitar Cantos Arredondados para a Área do Gráfico**  
```java
chart.setRoundedCorners(true);
```

**7. Liberar Recursos**  
```java
if (presentation != null) presentation.dispose();
```

### Salvando uma Apresentação
#### Visão Geral
Por fim, gravamos a apresentação no disco no formato PPTX.

#### Passo a Passo
**1. Inicializar o Objeto Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Definir Diretório de Saída e Nome do Arquivo**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. Salvar a Apresentação no Formato PPTX**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. Liberar Recursos**  
```java
if (presentation != null) presentation.dispose();
```

## Aplicações Práticas
- **Relatórios Empresariais** – Automatize decks financeiros trimestrais com gráficos dinâmicos.  
- **Conteúdo Educacional** – Gere slides de aula que extraem dados de um banco de dados.  
- **Apresentações de Marketing** – Visualize tendências de produtos com gráficos refinados.

## Considerações de Desempenho
- **Gerenciamento de Recursos** – Sempre chame `dispose()` ou use try‑with‑resources.  
- **Otimização de Memória** – Processar grandes conjuntos de dados em lotes menores.  
- **Melhores Práticas** – Prefira estruturas de dados imutáveis para séries de gráficos quando possível.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| **`NullPointerException` em `getSlides()`** | Garanta que o objeto `Presentation` foi instanciado com sucesso antes de acessar os slides. |
| **Gráfico não aparece** | Verifique se as dimensões do gráfico (x, y, largura, altura) estão dentro dos limites do slide. |
| **Licença não aplicada** | Carregue seu arquivo de licença antes de criar o objeto `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Perguntas Frequentes

**P: Como adiciono diferentes tipos de gráficos usando Aspose.Slides?**  
R: Substitua `ChartType.ClusteredColumn` por qualquer outro valor enum, como `ChartType.Pie`, `ChartType.Line` ou `ChartType.Bar`.

**P: O que devo fazer se encontrar erros de compilação?**  
R: Verifique se está usando JDK 16 ou superior e se a dependência Maven/Gradle corresponde à versão mostrada acima.

**P: Posso popular o gráfico com dados de um banco de dados?**  
R: Sim. Acesse a coleção `getChartData()` do gráfico, crie séries e categorias e preencha‑as com valores obtidos em tempo de execução.

**P: Como melhorar o desempenho para apresentações muito grandes?**  
R: Divida o trabalho em múltiplas instâncias de `Presentation`, reutilize modelos de gráficos e sempre libere os objetos prontamente.

## Conclusão
Agora você tem uma receita completa, de ponta a ponta, para **adicionar um gráfico de colunas agrupadas** a um slide PowerPoint com Aspose.Slides para Java. Experimente outros tipos de gráficos, vincule fontes de dados ao vivo e integre essa lógica em pipelines de relatórios maiores para automatizar seu fluxo de trabalho de apresentações.

---

**Última atualização:** 2026-03-15  
**Testado com:** Aspose.Slides 25.4 para Java (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}