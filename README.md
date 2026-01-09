# Tech Challenge - Fase 4: Sistema de Análise de Vídeo Inteligente
Este projeto é parte integrante do **Tech Challenge da Fase 4** da Pós-Tech em IA para Devs. Consiste em uma aplicação robusta de visão computacional capaz de analisar fluxos de vídeo para extrair métricas comportamentais, identificar indivíduos e detectar padrões de atividade.

## Como Executar o Projeto
### Pré-requisitos
1. Baixar as bibliotecas
```bash
pip install opencv-python deepface tf-keras numpy matplotlib seaborn tqdm
```
2. Baixar o vídeo Unlocking Facial Recognition_ Diverse Activities Analysis
3. Ajustar o caminho para o diretório onde ele está salvo (célula 4)
```bash
video_path = "/content/Unlocking Facial Recognition_ Diverse Activities Analysis.mp4"
```
4. Ajustar o caminho para o diretório de saída do vídeo analisado (célula 4)
```bash
output_path = "/content/video_analisado.mp4"
```

## Funcionalidades Principais
A aplicação executa quatro tarefas críticas de processamento:
1.  **Reconhecimento Facial**: Localiza e marca rostos em tempo real utilizando o backend RetinaFace para alta precisão.
2.  **Análise de Expressões Emocionais**: Classifica as emoções dominantes (ex: Feliz, Neutro, Triste, Surpresa) de cada rosto detectado através da biblioteca DeepFace.
3.  **Detecção de Atividades e Anomalias**: Categoriza o nível de movimento (Estático, Moderado ou Excessivo) e identifica comportamentos anômalos (gestos bruscos ou atípicos) baseando-se em cálculos estatísticos de fluxo óptico ($Z-Score$).
4.  **Resumo Automático**: Ao final do processamento, gera um relatório detalhado com estatísticas e gráficos de distribuição de dados.

## Tecnologias Utilizadas
* **Python**: Linguagem base do projeto.
* **OpenCV**: Para manipulação de frames, desenho de HUD (Heads-Up Display) e análise de movimento.
* **DeepFace**: Framework de IA para reconhecimento facial e análise de atributos.
* **Matplotlib/Seaborn**: Para geração automática dos gráficos de resumo.
  
## Visualização em Tempo Real (HUD)
O sistema exibe no canto superior esquerdo de cada frame um painel informativo contendo:
* **Status da Atividade**: Descrição da intensidade do movimento.
* **Contagem de Rostos**: Quantidade exata de pessoas identificadas no frame atual.
* **Lista de Emoções**: Todas as emoções presentes no momento (ex: "Emotions: Happy, Neutral").
* **Alerta de Anomalia**: Destaque visual em vermelho caso um movimento brusco seja detectado.
