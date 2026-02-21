# stellar-classification-model

🌌 Classificação de Objetos Astronômicos (Star, Galaxy, QSO)

📌 Objetivo
Construir um modelo de Machine Learning capaz de classificar objetos astronômicos em:

Estrelas (STAR), 
Galáxias (GALAXY) e
Quasares (QSO)

A partir de medições fotométricas e espectrais.

O foco do projeto é:

Entender quais variáveis carregam mais informação física

Avaliar relações não lineares entre atributos

Construir um modelo robusto e bem validado

📂 Dataset

O conjunto de dados contém 100.000 observações com as seguintes variáveis principais:

Variáveis Fotométricas

u → Filtro ultravioleta

g → Filtro verde

r → Filtro vermelho

i → Infravermelho próximo

z → Infravermelho

Esses filtros representam intensidades da radiação eletromagnética em diferentes comprimentos de onda.

Variável Espectral

redshift → Deslocamento para o vermelho

O redshift mede o aumento do comprimento de onda da luz emitida por objetos distantes.
Fisicamente, está associado à expansão do universo e à distância do objeto.

Target

class → GALAXY, STAR ou QSO

🔎 Metodologia
1️⃣ Análise Exploratória

Distribuição das classes

Histogramas por classe

Boxplots comparativos

Scatterplots entre variáveis

Análise de correlação

Pairplots para observar relações não lineares

Durante a EDA foi observado que:

As classes formam regiões não linearmente separáveis

O redshift apresenta forte poder discriminativo

Combinações como u-g, g-r, etc. (cores astronômicas) ajudam na separação

2️⃣ Feature Engineering

Foram criadas novas variáveis:

u_g

g_r

r_i

i_z

Essas diferenças representam “cores astronômicas”, que descrevem o espectro relativo do objeto.

3️⃣ Seleção de Features

Correlação de Pearson

Mutual Information

Importância de features da árvore

Resultado importante:

O redshift é a variável com maior quantidade de informação sobre a classe.

4️⃣ Modelagem

Foi utilizado:

Decision Tree Classifier

Justificativa:

As relações entre variáveis são não lineares

Árvores capturam regras condicionais naturalmente

Interpretabilidade estrutural

5️⃣ Avaliação

Métricas obtidas:

Acurácia treino: ~97.37%

Acurácia teste: ~97.57%

Validação Cruzada (5-fold):

CV média: 0.9734

CV desvio: 0.0005

Interpretação:

Não há evidência de overfitting

O modelo é estável

A generalização é consistente

Teste adicional:

Removendo redshift, a acurácia caiu para ~82%.

Isso confirma a importância física dessa variável no problema.

📊 Resultados

✔ Separação clara de Quasares via redshift
✔ Modelo robusto e estável
✔ Dependência física coerente com conhecimento astronômico

🧠 Conclusões

O redshift carrega a maior quantidade de informação discriminativa.

Relações entre filtros fotométricos ajudam na separação entre estrelas e galáxias.

A árvore de decisão apresentou excelente desempenho sem evidência de overfitting.
