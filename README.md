# Checkpoint 2 Alura · Veículos elétricos

Projeto de ciência de dados sobre características de veículos elétricos, custos de uso e estimativa do valor de revenda. A base da Alura reúne 3.000 veículos fabricados entre 2015 e 2024.

O [notebook executado](checkpoint_2_alura.ipynb) contém as três entregas:

1. **Exploração estatística e comparação de grupos** com distribuições, testes de Kruskal–Wallis, correlações de Spearman e ajuste de Holm.
2. **Tendências de Mercado** com médias e totais por ano de fabricação, gráficos, checagem retrospectiva e projeção linear ilustrativa para duas coortes.
3. **Modelagem preditiva** com regressão Ridge, floresta aleatória, gradient boosting, combinação por média e referência pela mediana. A comparação usa MAE, RMSE e R², com análise de erros e importância por permutação.

## Executar localmente

Use Python 3.8 ou superior. A execução completa foi verificada em Python 3.12. As dependências incluem pandas, NumPy, Matplotlib, seaborn, SciPy, scikit-learn e statsmodels.

```bash
git clone https://github.com/zPaulo/checkpoint-2-alura.git
cd checkpoint-2-alura
python -m pip install -r requirements.txt notebook
python -m notebook checkpoint_2_alura.ipynb
```

Execute todas as células em ordem. No [Google Colab](https://colab.research.google.com/github/zPaulo/checkpoint-2-alura/blob/main/checkpoint_2_alura.ipynb), abra o notebook e execute as células. Se alguma dependência estiver ausente, instale-a com `%pip install` antes da primeira célula e reinicie a sessão se necessário.

## Resultados

- Capacidade da bateria e revenda tiveram correlação de Spearman de **0,921** na amostra.
- A revenda média foi de aproximadamente **US$ 19.978** na coorte de 2015 e **US$ 24.506** na de 2024.
- A combinação por média venceu na validação cruzada por uma margem pequena sobre a regressão Ridge. No teste, obteve **MAE de US$ 1.517**, **RMSE de US$ 1.753** e **R² de 0,900**.

## Dados e escopo

O [CSV original](data/electric_vehicle_analytics.csv) acompanha o projeto. Se o arquivo estiver ausente, o notebook baixa a [cópia disponibilizada pela Alura](https://cdn3.gnarususercontent.com.br/5210-projeto-cientista-dados-nivel-2/electric_vehicle_analytics%28in%29.csv). A [fonte indicada pela Alura está no Kaggle](https://www.kaggle.com/datasets/khushikyad001/electric-vehicle-analytics-dataset).

A série anual compara coortes de fabricação em uma única amostra. Para medir adoção e participação de mercado, seriam necessários dados de vendas ou emplacamentos por período, além do total do mercado. O alvo é um valor estimado na base. O uso para precificação requer validação em transações reais.
