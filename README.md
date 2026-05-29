# Protactic Champions League Predictor Engine & Dashboard

Uma plataforma analítica de alta fidelidade e dashboard estatístico projetado para prever o confronto entre **Arsenal** e **Paris Saint-Germain** na final da Champions League. A aplicação integra um motor de simulação matemática em Python com uma interface web interativa de nível sênior.

---

## 🧠 Como Funciona o Algoritmo

O motor de previsão utiliza uma abordagem híbrida baseada em dados reais extraídos do Sofascore (`arsenal_psg_jogos.csv` e `tabelas_finais.csv`) com 5 pilares matemáticos:

1. **Peso Temporal Exponencial**: Jogos mais recentes possuem peso exponencialmente maior do que partidas antigas para refletir o momento real de cada equipe.
2. **Cadeias de Markov**: Prediz a formação tática mais provável de cada equipe com base em uma matriz de transição de jogos anteriores.
3. **Escalação por Slot Tático**: Mapeia de forma inteligente a melhor escalação possível atribuindo pontuações de relevância individual para cada jogador.
4. **Peso por Força do Adversário**: Ajusta o peso do rendimento histórico baseando-se na posição do adversário na tabela final do campeonato.
5. **Simulações de Monte Carlo**: Executa até 100.000 simulações de cenários de jogo utilizando Distribuições de Poisson para a média de gols de cada equipe.

---

## ⚡ Principais Recursos do Dashboard

* **Visualização de Campo Tático Interativo**: Renderiza o campo em 2D com a escalação prevista posicionada geograficamente com base na formação tática (4-2-3-1, 4-3-3 ou 4-4-2).
* **Avatares Dinâmicos do Sofascore**: Carrega automaticamente a imagem oficial de cada um dos 56 jogadores cadastrados a partir da CDN do Sofascore.
* **Tooltips Táticos Avançados**: Passe o mouse sobre qualquer jogador para ver o seu slot de posicionamento e as chances individuais dele de marcar um gol ou dar uma assistência.
* **Gerenciador de Desfalques em Tempo Real**: Adicione ou remova jogadores machucados/suspensos para recalcular instantaneamente as forças de ataque, defesa e chances finais de vitória.
* **Ajuste de Iterações**: Controle deslizante para ajustar o tamanho da amostra da simulação (10.000 a 100.000 iterações).
* **Análise de Placares Prováveis**: Gráficos de barra horizontais elegantes desenvolvidos em Chart.js exibindo as probabilidades dos placares exatos.
* **Cenário de Mata-Mata**: Predição para prorrogação e probabilidades de vitória em disputa de pênaltis.

---

## 🛠️ Stack Tecnológica

* **Backend**: Python 3.11+, Flask.
* **Bibliotecas Matemáticas**: Pandas, Numpy.
* **Frontend**: HTML5 Semântico, CSS3 Customizado (Variáveis CSS, Flexbox, Grid, Animações, Glassmorphic Glass-Cards), Vanilla Javascript.
* **Gráficos**: Chart.js via CDN.
* **Banco de Dados**: JSON nativo para mapeamento de IDs de imagem (`player_ids.json`).

---

## 🚀 Como Rodar o Projeto

### Pré-requisitos

Certifique-se de ter o Python 3 instalado em sua máquina e as dependências necessárias:

```bash
pip install pandas numpy flask
```

### Passo a Passo

1. Navegue até o diretório do projeto no terminal:
   ```bash
   cd "caminho/para/Protactic Champions League"
   ```

2. Execute o servidor Flask do backend:
   ```bash
   python app.py
   ```

3. Abra o seu navegador e acesse a aplicação:
   **[http://localhost:5000](http://localhost:5000)**

---

## 📁 Estrutura de Arquivos

* [app.py](file:///d:/Protactic%20Champions%20League/app.py): Servidor HTTP e API de simulação.
* [prev.py](file:///d:/Protactic%20Champions%20League/prev.py): Algoritmo estatístico original com as fórmulas matemáticas.
* [index.html](file:///d:/Protactic%20Champions%20League/index.html): Estrutura semântica do dashboard.
* [style.css](file:///d:/Protactic%20Champions%20League/style.css): Estilos do painel, incluindo o campo de futebol 2D e paleta de cores da marca.
* [script.js](file:///d:/Protactic%20Champions%20League/script.js): Lógica de renderização dinâmica de jogadores, tooltips e requisições assíncronas à API.
* [player_ids.json](file:///d:/Protactic%20Champions%20League/player_ids.json): Mapeamento de nomes de jogadores com seus IDs oficiais do Sofascore.
