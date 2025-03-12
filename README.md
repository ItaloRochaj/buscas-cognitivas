# Azure Cognitive Search

## Introdução
O **Azure Cognitive Search** é um serviço de pesquisa baseado em nuvem que utiliza inteligência artificial para indexação e consulta de dados. Neste guia, configuraremos uma pesquisa utilizando **AI Search**, explorando suas funcionalidades e insights.

---

## 1. Pré-requisitos
Antes de iniciar a configuração, certifique-se de ter:
- Uma conta ativa no **Microsoft Azure**.
- Um recurso **Azure Cognitive Search** criado.
- Dados para indexação (JSON, CSV, ou Banco de Dados conectado ao Azure).
- Conhecimento básico em **Azure Portal** e **API REST/SDK**.

---

## 2. Criando um Serviço de Pesquisa no Azure
1. Acesse o [Portal do Azure](https://portal.azure.com) e faça login.
2. Pesquise por **"Cognitive Search"** e clique em **Criar**.
3. Defina:
   - **Nome do Serviço**
   - **Grupo de Recursos**
   - **Localização** (preferencialmente "East US")
   - **Plano de Preço** (Free para testes, Standard ou superior para produção)
4. Clique em **Revisar + Criar** e confirme a criação do serviço.

---

## 3. Configuração da Indexação de Dados
### 3.1 Criando um Índice
1. Acesse o **Azure Cognitive Search** no portal do Azure.
2. Vá para a guia **Índices** e clique em **Adicionar Índice**.
3. Defina os seguintes campos:
   - Nome do índice
   - Estrutura do índice (campos, tipos de dados, chaves de pesquisa)
   - Habilite o suporte à pesquisa **Full-Text**.
4. Clique em **Salvar**.

### 3.2 Criando um Data Source (Fonte de Dados)
1. Vá até a aba **Fontes de Dados** e clique em **Adicionar**.
2. Escolha o tipo de fonte (Blob Storage, SQL Database, CosmosDB, etc.).
3. Configure a conexão com os dados e forneça credenciais se necessário.
4. Salve a configuração.

### 3.3 Criando um Indexador
1. Vá até a aba **Indexadores** e clique em **Adicionar**.
2. Escolha a **Fonte de Dados** criada anteriormente.
3. Defina a frequência de atualização dos dados.
4. Associe ao **Índice** criado.
5. Clique em **Executar Indexação**.

---

## 4. Consultando os Dados Indexados
### 4.1 Testando Consultas no Portal do Azure
1. Acesse o **Índice** criado.
2. Vá até a aba **Explorador de Pesquisa**.
3. Execute consultas usando **OData** ou **Lucene Query Syntax**.

Exemplo de consulta simples:
```json
GET https://<NOME_DO_SERVICO>.search.windows.net/indexes/<NOME_DO_INDICE>/docs?api-version=2023-07-01&search=*
```

### 4.2 Utilizando a API REST
```bash
curl -X GET "https://<NOME_DO_SERVICO>.search.windows.net/indexes/<NOME_DO_INDICE>/docs?api-version=2023-07-01&search=*" \
-H "Content-Type: application/json" \
-H "api-key: <SUA_CHAVE_DE_ADMIN>"
```

### 4.3 Utilizando SDKs
O **Azure Cognitive Search** possui SDKs para **Python, C#, Java e Node.js**.
Exemplo em Python:
```python
from azure.search.documents import SearchClient
from azure.core.credentials import AzureKeyCredential

service_name = "<NOME_DO_SERVICO>"
index_name = "<NOME_DO_INDICE>"
api_key = "<SUA_CHAVE_DE_ADMIN>"

search_client = SearchClient(endpoint=f"https://{service_name}.search.windows.net/",
                             index_name=index_name,
                             credential=AzureKeyCredential(api_key))

results = search_client.search("Azure AI")
for result in results:
    print(result)
```

---

## 5. Insights e Benefícios do AI Search
- **Análise Semântica**: melhora a precisão das pesquisas.
- **Sugestões Inteligentes**: autocomplete e sugestões de busca baseadas em IA.
- **Relevância Personalizada**: ajuste do ranking de resultados conforme necessidade.
- **Facilidade de Integração**: compatível com aplicativos web e mobile.

---

## 6. Ferramentas que se Beneficiam do Azure Cognitive Search
- **E-commerce**: busca de produtos baseada em relevância.
- **Sistemas de Suporte**: pesquisas inteligentes em bases de conhecimento.
- **Análise de Documentos**: indexação e busca avançada de documentos.
- **Pesquisa Acadêmica**: mineração de conhecimento em artigos científicos.

---

## 7. Aprendizados Durante o Processo
Durante a implementação do **Azure Cognitive Search**, aprendemos a:
1. Criar e configurar um serviço de pesquisa na nuvem.
2. Indexar diferentes tipos de fontes de dados.
3. Construir consultas eficientes para explorar os dados.
4. Utilizar técnicas de AI Search para otimizar a experiência de pesquisa.

---

## Conclusão
Com este guia, você pode configurar e explorar o **Azure Cognitive Search**, aproveitando seu potencial para **indexação inteligente e pesquisa avançada**. Para mais detalhes, confira a [documentação oficial](https://learn.microsoft.com/en-us/azure/search/).
