---
"date": "2025-04-23"
"description": "Aprenda a personalizar as escalas dos eixos do gráfico usando o Aspose.Slides em Python, com etapas detalhadas e exemplos de código."
"title": "Como definir a escala do eixo do gráfico como NENHUM no Aspose.Slides para Python (gráficos e tabelas)"
"url": "/pt/python-net/charts-graphs/aspose-slides-python-chart-axis-scale-none/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como definir a escala do eixo do gráfico como NENHUM usando Aspose.Slides Python
## Introdução
A criação de gráficos visualmente atraentes geralmente requer o ajuste fino das escalas dos eixos. Este tutorial demonstra como definir a escala da unidade principal do eixo horizontal para `NONE` para um gráfico usando Aspose.Slides em Python, perfeito para personalizar a visualização de dados em suas apresentações.
**O que você aprenderá:**
- Configurar Aspose.Slides para Python.
- Crie e personalize gráficos com configurações de eixos específicas.
- Salve apresentações programaticamente.
- Solucione problemas comuns ao trabalhar com eixos de gráficos.

## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
### Bibliotecas necessárias
- **Aspose.Slides para Python**: Instalar via pip. Requer Python 3.x ou posterior.
### Configuração do ambiente
- Instalar Python a partir de [python.org](https://www.python.org/).
- Use um editor de código como VSCode ou PyCharm.
### Pré-requisitos de conhecimento
- Noções básicas de programação em Python.
- A familiaridade com o manuseio de apresentações e gráficos é útil, mas não obrigatória.

## Configurando Aspose.Slides para Python
Para usar o Aspose.Slides em seus projetos:
**Instalação:**
```bash
pip install aspose.slides
```
### Etapas de aquisição de licença
- **Teste grátis**: Baixe a versão de teste para testar os recursos.
- **Licença Temporária**: Obtenha uma licença temporária para testes estendidos.
- **Comprar**: Compre uma licença completa para acesso de longo prazo.

**Inicialização básica:**
```python
import aspose.slides as slides
```
Isso importa todas as funcionalidades do Aspose.Slides.

## Guia de Implementação
### Criando um gráfico com escala de eixo personalizada
#### Visão geral
Criaremos um gráfico do tipo ÁREA e definiremos a escala da unidade principal do eixo horizontal como `NONE`.
**Etapa 1: Inicializar a apresentação**
Comece criando uma nova instância de apresentação:
```python
with slides.Presentation() as pres:
    # Outras operações serão realizadas aqui.
```
Este gerenciador de contexto garante um gerenciamento eficiente de recursos.
#### Etapa 2: Adicionar um gráfico
Adicione um gráfico do tipo ÁREA ao seu slide em coordenadas e dimensões específicas:
```python
chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.AREA, 10, 10, 400, 300, True)
```
Isso adiciona um gráfico de tamanho 400x300 pixels na posição (10, 10) no primeiro slide.
#### Etapa 3: defina a escala do eixo como NENHUM
Modifique a escala da unidade principal do eixo horizontal:
```python
chart.axes.horizontal_axis.major_unit_scale = slides.charts.TimeUnitType.NONE
```
Definir esta propriedade remove intervalos de escala predefinidos ao longo do eixo x.
#### Etapa 4: Salve a apresentação
Salve suas alterações em um arquivo no formato PPTX:
```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_time_unit_type_enum_out.pptx", slides.export.SaveFormat.PPTX)
```
Isso salva seu gráfico personalizado em um novo arquivo de apresentação.
### Dicas para solução de problemas
- Garantir a `aspose.slides` o pacote está instalado corretamente. Use `pip show aspose.slides` para verificar.
- Verifique se o diretório de saída existe e tem permissões de gravação apropriadas.

## Aplicações práticas
Definir escalas de eixo pode ser útil em:
1. **Relatórios Financeiros**: Concentre-se em períodos de tempo ou pontos de dados específicos, sem intervalos predefinidos.
2. **Apresentações Científicas**: Controle preciso sobre a visualização de dados para resultados de pesquisas.
3. **Análise de Marketing**: Destaque as principais métricas removendo a escala que distrai.

## Considerações de desempenho
Ao trabalhar com Aspose.Slides:
- Use gerenciadores de contexto (`with` declarações) para gerenciar recursos de forma eficiente.
- Manipule dados de forma eficiente em Python para minimizar o consumo de memória.
- Atualize as versões da biblioteca regularmente para melhorias de desempenho e correções de bugs.

## Conclusão
Você aprendeu a personalizar as escalas dos eixos dos gráficos usando o Aspose.Slides para Python, aprimorando a clareza das apresentações. Explore outros recursos, como controles de animação, para aprimorar ainda mais suas apresentações.
**Próximos passos:**
Implemente esta solução em um projeto para melhorar a apresentação de dados!

## Seção de perguntas frequentes
1. **Como atualizo o Aspose.Slides?**
   - Usar `pip install --upgrade aspose.slides`.
2. **Posso definir as escalas dos eixos horizontal e vertical como NENHUM?**
   - Sim, use `chart.axes.vertical_axis.major_unit_scale = slides.charts.TimeUnitType.NONE`.
3. **E se meu gráfico não for salvo corretamente?**
   - Verifique os caminhos dos arquivos e certifique-se de que o diretório de saída seja gravável.
4. **Existe uma maneira de visualizar as alterações antes de salvar?**
   - O Aspose.Slides não fornece visualização direta, mas itera com scripts menores até ficar satisfeito.
5. **Como lidar com diferentes tipos de gráficos?**
   - Substituir `ChartType.AREA` com outros tipos como `Bar`, `Line`, etc., conforme necessário.

## Recursos
- [Documentação do Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Baixe Aspose.Slides para Python](https://releases.aspose.com/slides/python-net/)
- [Comprar uma licença](https://purchase.aspose.com/buy)
- [Teste grátis](https://releases.aspose.com/slides/python-net/)
- [Licença Temporária](https://purchase.aspose.com/temporary-license/)
- [Fórum de Suporte Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}