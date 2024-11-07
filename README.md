# modelo-previsao
# Previsão de Preços do Bitcoin com Azure Machine Learning

## Introdução
Este repositório contém um modelo de previsão de preços do Bitcoin criado e implantado utilizando o Azure Machine Learning. Abaixo está o passo a passo detalhado de todo o processo.

## Passos

### 1. Configurar o Azure Machine Learning Workspace
1. Acesse o [portal do Azure](https://portal.azure.com/).
2. No menu esquerdo, clique em **"Create a resource"** e procure por **"Machine Learning"**.
3. Selecione **"Machine Learning"** e clique em **"Create"**.
4. Preencha as informações necessárias (Subscription, Resource group, Workspace name, Region) e clique em **"Review + create"** e depois em **"Create"**.

### 2. Upload dos Dados
1. No painel esquerdo, clique em **"Datasets"** e depois em **"Create dataset"**.
2. Selecione **"From local files"**.
3. Carregue o arquivo CSV com o histórico de preços do Bitcoin.
4. Siga as instruções para nomear e descrever o dataset e finalize o upload.

### 3. Criar um Novo Experimento
1. No Azure Machine Learning Studio, vá para a seção **"Designer"** no menu esquerdo.
2. Clique em **"Create new"** para iniciar um novo pipeline.
3. Dê um nome ao seu pipeline, algo como **"Bitcoin Price Prediction"**.

### 4. Adicionar e Preparar os Dados no Pipeline
1. No Designer, arraste o dataset carregado para a área de trabalho.
2. Adicione os módulos necessários para preparar os dados, como **"Select Columns in Dataset"** e **"Edit Metadata"**.
3. Configure esses módulos para selecionar as colunas de interesse e ajustar os tipos de dados conforme necessário.

### 5. Treinar o Modelo
1. Adicione o módulo **"Train Model"** ao pipeline.
2. Adicione um algoritmo de aprendizado, como **"Linear Regression"**.
3. Conecte os módulos: 
    - Conecte a saída do módulo **"Split Data"** à entrada do módulo **"Train Model"** para o conjunto de treinamento.
    - Conecte o algoritmo de aprendizado ao módulo **"Train Model"**.

### 6. Avaliar o Modelo
1. Adicione o módulo **"Score Model"** ao pipeline.
2. Conecte a saída do módulo **"Split Data"** à entrada do módulo **"Score Model"** para o conjunto de teste.
3. Conecte a saída do módulo **"Train Model"** à outra entrada do módulo **"Score Model"**.
4. Adicione o módulo **"Evaluate Model"** para avaliar o desempenho do modelo.

### 7. Executar o Pipeline
1. Clique em **"Submit"** no topo da página para executar o pipeline.
2. Acompanhe o progresso e aguarde a conclusão do treinamento.

### 8. Implantar o Modelo
1. Após o treinamento, clique em **"Deploy"** no painel de resultados do experimento.
2. Escolha **"Real-time endpoint"** e configure as opções de implantação.
3. Defina os pontos de extremidade e clique em **"Deploy"**.

### 9. Testar o Endpoint
1. Após a implantação, você terá um URL para o endpoint. Use essa URL para fazer previsões.
2. Você pode testar o endpoint usando ferramentas como Postman ou diretamente no seu código Python com bibliotecas como `requests`.

### 10. Compartilhar o Link do Repositório
1. Adicione os arquivos ao seu repositório no GitHub.
2. Faça commit e push das alterações:
    ```sh
    git add README.md
    git commit -m "Add README"
    git push origin main
    ```

3. No GitHub, acesse a página do repositório.
4. Copie a URL do repositório.
5. Use o botão **'entregar projeto'** para compartilhar o link.

## Como Rodar
- Clone este repositório: `git clone [URL do repositório]`
- Siga as instruções detalhadas acima para configurar e rodar o modelo.

## Contribuição
- Sinta-se à vontade para abrir issues e enviar pull requests.

