---
"date": "2025-04-17"
"description": "Aprenda a criar e personalizar gráficos de rosca em apresentações Java com o Aspose.Slides, incluindo a configuração do seu ambiente e o ajuste da estética do gráfico."
"title": "Como criar gráficos de rosca em Java usando Aspose.Slides para apresentações"
"url": "/pt/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como criar gráficos de rosca em Java usando Aspose.Slides para apresentações

## Introdução
Criar apresentações visualmente atraentes é essencial para transmitir informações de forma eficaz. Os gráficos são elementos cruciais que aprimoram a compreensão das distribuições de dados. Este tutorial orienta você na criação de gráficos de rosca personalizáveis usando o Aspose.Slides para Java, permitindo a geração fácil de gráficos com amplas opções de personalização, como tamanho e posicionamento dos furos.

**O que você aprenderá:**
- Configurando o Aspose.Slides para Java
- Criação e configuração de gráficos de rosca em apresentações
- Ajustando a estética do gráfico, como o tamanho do furo
- Salvando a apresentação com seu novo gráfico

Vamos começar configurando nosso ambiente!

## Pré-requisitos
Antes de começar, certifique-se de ter atendido a estes pré-requisitos:

### Bibliotecas e versões necessárias
Para trabalhar com o Aspose.Slides para Java, inclua-o no seu projeto via Maven ou Gradle, ou baixe-o diretamente.

#### Requisitos de configuração do ambiente
- Um Java Development Kit (JDK) funcional, de preferência versão 8 ou superior.
- Um Ambiente de Desenvolvimento Integrado (IDE) como IntelliJ IDEA ou Eclipse.

### Pré-requisitos de conhecimento
Familiaridade com Java e conceitos básicos de programação é benéfica. Conhecimentos básicos de Maven ou Gradle ajudarão a agilizar o processo de configuração.

## Configurando o Aspose.Slides para Java
A incorporação do Aspose.Slides ao seu projeto pode ser feita de várias maneiras:

**Especialista:**
Adicione esta dependência ao seu `pom.xml` arquivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Inclua isso em seu `build.gradle` arquivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Download direto:**
Alternativamente, baixe a versão mais recente em [Lançamentos do Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Aquisição de Licença
- **Teste grátis**: Comece baixando uma versão de teste para explorar os recursos do Aspose.Slides.
- **Licença Temporária**: Obtenha uma licença temporária para funcionalidade estendida sem limitações.
- **Comprar**:Para uso contínuo, é necessário adquirir uma licença.

Depois que você tiver a biblioteca configurada e seu ambiente pronto, vamos prosseguir para a implementação do nosso gráfico de rosca.

## Guia de Implementação

### Criando um gráfico de rosca
Criar uma apresentação com um gráfico de rosca personalizado usando o Aspose.Slides envolve várias etapas. Vamos descrevê-las para maior clareza:

#### Inicializar objeto de apresentação
Comece criando uma instância do `Presentation` classe, representando seu documento do PowerPoint.
```java
// Crie uma instância da classe Presentation para representar um documento PPTX
Presentation presentation = new Presentation();
```
Esta etapa inicializa sua apresentação, onde você pode adicionar slides e gráficos.

#### Adicionar gráfico de rosca ao slide
Acesse o primeiro slide (ou crie um, se necessário) e adicione um gráfico de rosca:
```java
// Acesse o primeiro slide da apresentação
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Posição em (50, 50) com tamanho 400x400
```
Este trecho de código adiciona um gráfico de rosca ao primeiro slide. Os parâmetros definem sua posição e dimensões no slide.

#### Configurar tamanho do furo da rosca
Para dar ao seu gráfico de donuts uma aparência única, ajuste o tamanho do furo:
```java
// Defina o tamanho do furo para o gráfico de rosca para 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
Aqui, estamos definindo o tamanho do furo para 90%, tornando-o quase um círculo completo. Ajuste esse valor de acordo com as suas necessidades de design.

#### Salvar apresentação
Depois de configurar seu gráfico, salve a apresentação:
```java
// Salve a apresentação no disco no formato PPTX no diretório especificado
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
Esta linha grava suas alterações em um arquivo chamado `DoughnutHoleSize_out.pptx` no seu diretório designado.

#### Recursos de limpeza
Por fim, certifique-se de descartar o objeto de apresentação:
```java
// Descarte o objeto de apresentação para liberar recursos
if (presentation != null) presentation.dispose();
```
Esta etapa é crucial para o gerenciamento de recursos e para evitar vazamentos de memória.

### Aplicações práticas
Os gráficos de rosca são versáteis. Aqui estão alguns cenários em que eles se destacam:
1. **Alocação Orçamentária**: Exiba como um orçamento é distribuído entre os departamentos.
2. **Resultados da pesquisa**: Visualize respostas para perguntas com respostas de múltipla escolha.
3. **Fontes de tráfego do site**: Mostra a porcentagem de tráfego proveniente de diferentes fontes.

### Considerações de desempenho
Ao trabalhar com o Aspose.Slides, considere estas dicas para um desempenho ideal:
- Gerencie a memória descartando objetos quando eles não forem mais necessários.
- Use fluxos para grandes conjuntos de dados para minimizar o uso de memória.
- Otimize seu código reutilizando instâncias sempre que possível.

## Conclusão
Parabéns! Você aprendeu a criar e personalizar um gráfico de rosca usando o Aspose.Slides para Java. Este tutorial abordou a configuração da biblioteca, a adição de gráficos às apresentações e os ajustes na aparência.

Para continuar explorando os recursos do Aspose.Slides, considere experimentar outros tipos de gráficos ou se aprofundar nos recursos de automação de apresentações.

**Próximos passos:**
- Experimente diferentes configurações de gráficos.
- Explore a documentação adicional do Aspose.Slides para obter recursos mais avançados.

Pronto para criar seus próprios gráficos de rosca? Experimente implementar esta solução no seu próximo projeto!

## Seção de perguntas frequentes
1. **Posso ajustar as cores dos segmentos do meu gráfico de rosca?**
   Sim, você pode personalizar as cores dos segmentos usando `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` para definir um tipo de preenchimento sólido e especificar a cor desejada.

2. **Como adiciono rótulos de dados ao meu gráfico?**
   Usar `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` e métodos semelhantes para adicionar pontos de dados e rótulos programaticamente.

3. **É possível salvar gráficos em formatos diferentes do PPTX?**
   Com certeza! O Aspose.Slides suporta vários formatos de saída, como PDF, XPS e formatos de imagem como PNG ou JPEG.

4. **E se eu encontrar um erro ao salvar a apresentação?**
   Verifique se o caminho do diretório está correto e se você possui permissões de gravação para o local especificado. Verifique se a versão do Aspose.Slides que você está usando é compatível com o formato de arquivo que você está tentando salvar.

5. **Posso automatizar atualizações de gráficos com fontes de dados ao vivo?**
   Sim, ao integrar APIs ou bancos de dados ao seu aplicativo Java, você pode atualizar dinamicamente os dados do gráfico e atualizar as apresentações conforme necessário.

## Recursos
- **Documentação**: Explore referências detalhadas de API em [Aspose.Slides para Java](https://reference.aspose.com/slides/java/).
- **Download**: Obtenha a versão mais recente da biblioteca em [Lançamentos do Aspose.Slides](https://releases.aspose.com/slides/java/).
- **Comprar**:Para acesso total, adquira uma licença em [Aspose Compra](https://purchase.aspose.com/buy).
- **Teste grátis**: Teste o Aspose.Slides com uma avaliação gratuita disponível na página de downloads.
- **Licença Temporária**Obtenha uma licença temporária para testes estendidos sem limitações.
- **Apoiar**: Tem dúvidas? Visite o [Fórum Aspose](https://forum.aspose.com/c/slides/11) para assistência.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}