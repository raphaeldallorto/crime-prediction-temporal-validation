# Predição de Crimes com Validação Temporal
🇺🇸 *English version available at [README.md](README.md)*

> **Nota:** O código-fonte e comentários estão em português (pt-BR), pois este projeto aborda o contexto de segurança pública brasileira e é destinado a stakeholders locais.

> Sistema de previsão e classificação de crimes urbanos usando aprendizado de máquina com validação temporal rigorosa para prevenir vazamento de dados

## 📊 Visão Geral

Sistema integrado de predição criminal com dois módulos complementares:

1. **Previsão de Volume (Regressão)**: Prevê a contagem diária de crimes por localização usando Random Forest Regressor
2. **Classificação de Tipos de Crime**: Predição probabilística multiclasse usando Random Forest e XGBoost

**Principais Características:**
- ✅ Validação K-Fold temporal com janelas expansivas (previne vazamento de dados)
- ✅ Teste out-of-time em 9 meses de dados futuros (Jan-Set 2025)
- ✅ Sistema automatizado de monitoramento de drift
- ✅ Modelos prontos para produção com reprodutibilidade completa

## 🎯 Resultados

| Módulo | Modelo | Métrica | Performance |
|--------|-------|---------|-------------|
| Predição de Volume | Random Forest | MAE | 0,52 crimes/dia |
| Predição de Volume | Random Forest | R² | 0,655 |
| Classificação de Crimes | XGBoost | F1-Score | 0,903 |
| Classificação de Crimes | XGBoost | Acurácia | 90,0% |

**Estudo de Caso:** 75.029 registros criminais do Espírito Santo, Brasil (2024-2025)

## 🔬 Destaques Metodológicos

- Validação temporal com validação cruzada 3-fold (sem vazamento de dados futuros)
- Otimização por grid search (81, 54 e 18 combinações de hiperparâmetros)
- Engenharia de features espaciais (100 regiões geográficas)
- Features de lag temporal (1, 7, 30 dias + média móvel de 7 dias)
- Monitoramento de performance com limiares de detecção de drift

## 📂 Estrutura do Repositório

```
crime-prediction-temporal-validation/
│
├── data/
│   ├── raw/                    # Dataset completo de 2024 a Set/2025
│   └── future/                 # Datasets mensais de 2025 (Jan-Set)
│
├── predictions/
│   ├── volume/                 # Saídas de predição de volume (CSV)
│   └── classification/         # Saídas de classificação de tipos (CSV)
│
├── results/
│   ├── figures/                # Gráficos e visualizações gerados
│   └── screenshots/            # Screenshots de saídas de treinamento/avaliação
│
├── notebooks/                  # Jupyter notebooks para análise
├── requirements.txt
├── README_pt-BR.md
└── README.md
```

### 📝 Descrição dos Diretórios

- **`data/raw/`**: Registros criminais originais não processados da base pública do Espírito Santo
- **`data/future/`**: Arquivos de dados criminais mensais usados para validação out-of-time (2025)
- **`predictions/volume/`**: Previsões de volume diário de crimes por localização
- **`predictions/classification/`**: Predições de tipos de crime com probabilidades
- **`results/figures/`**: Gráficos de performance, plots de monitoramento de drift e visualizações
- **`results/screenshots/`**: Saídas do console e logs de treinamento
- **`notebooks/`**: Análise exploratória de dados, treinamento e avaliação de modelos

> **Nota:** O diretório `data/` não está incluído no repositório por considerações de privacidade. Consulte a base de dados pública de segurança do Espírito Santo para acesso ao dataset.

## 🚀 Início Rápido

```bash
# Clonar repositório
git clone https://github.com/raphaeldallorto/crime-prediction-temporal-validation.git
cd crime-prediction-temporal-validation

# Instalar dependências
pip install -r requirements.txt
```

## 📄 Citação

Se você usar este trabalho, por favor cite:

```bibtex
@mastersthesis{dallorto2025crime,
  title={Predição de Volume e Classificação de Crimes Urbanos Utilizando Random Forest e XGBoost: Uma Abordagem com Validação Temporal},
  author={Dall'Orto, Raphael Lugon Campo},
  year={2025},
  school={Universidade Federal do Espírito Santo}
}
```

## 👤 Autor

**Raphael Lugon Campo Dall'Orto**
- GitHub: [@raphaeldallorto](https://github.com/raphaeldallorto)

## 📜 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

