# Previsão de Demanda com Azure Machine Learning

## Visão Geral
Este projeto tem como objetivo prever a demanda de um produto (exemplo: sorvete) com base na temperatura e outros fatores relevantes. Utiliza-se **Azure Machine Learning** para treinamento e gestão do modelo, **MLflow** para rastreamento de experimentos e **Azure Blob Storage** para armazenar os dados.

## Tecnologias Utilizadas
- **Azure Machine Learning** para treinamento e gestão do modelo
- **MLflow** para rastreamento e gerenciamento de experimentos
- **Azure Data Factory** para ingestão e processamento de dados
- **Azure Blob Storage** para armazenar datasets
- **Python (Pandas, Scikit-Learn, TensorFlow/PyTorch)**

## Estrutura do Projeto
```
├── data/                  # Conjunto de dados utilizado
├── notebooks/             # Notebooks para exploração e treinamento
├── src/
│   ├── data_processing.py # Processamento de dados
│   ├── train_model.py     # Treinamento do modelo
│   ├── deploy_model.py    # Deploy do modelo
│   ├── inference.py       # Inferência e previsões
├── .gitignore             # Arquivos e pastas ignorados pelo Git
├── requirements.txt       # Dependências do projeto
├── README.md              # Documentação do projeto
```

## Configuração do Ambiente
1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-repositorio.git
   cd seu-repositorio
   ```
2. Crie um ambiente virtual e instale as dependências:
   ```bash
   python -m venv venv
   source venv/bin/activate  # No Windows use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```
3. Configure o Azure Machine Learning:
   ```bash
   az login
   az ml workspace create -n nome-do-workspace -g nome-do-grupo
   ```

## Treinamento do Modelo
Execute o script de treinamento:
```bash
python src/train_model.py
```
Isso irá carregar os dados, treinar um modelo e registrar os experimentos no MLflow.

## Deploy do Modelo
Para implantar o modelo:
```bash
python src/deploy_model.py
```

## Inferência e Previsões
Para fazer previsões com o modelo implantado:
```bash
python src/inference.py --input "dados_de_teste.csv"
```

## Monitoramento e Atualização do Modelo
1. **Monitoramento:** Use **Azure Monitor** para acompanhar a precisão do modelo e logs de inferência.
2. **Atualização:** Re-treine e re-implante o modelo regularmente conforme novos dados se tornem disponíveis.

## Contribuição
Contribuições são bem-vindas! Para sugerir melhorias:
1. Faça um fork do repositório
2. Crie uma branch para suas alterações: `git checkout -b minha-melhoria`
3. Envie um pull request

## Licença
Este projeto está sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.

