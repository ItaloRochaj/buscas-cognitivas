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
![print1](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print1.png)
![print2](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print2.png)
![print3](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print3.png)
![print4](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print4.png)
![print5](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print5.png)

No menu de opções na lateral esquerda, clicar em "IA + Machine Learning"
![print6](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print6.png)
Em "Detalhes do projeto", não alterar a opção de assinatura. Em "Grupo de recursos" escolha um já criado ou crie um novo no botão abaixo "Criar novo"
Descendo a tela, temos os detalhes da instância, é recomendado não utilizar servidores da região do Brasil, por questões de instabilidade, aqui utilize a já indicada pela Azure ou "East US". Em "Nome" coloque um nome de sua preferência. Em "Tipo de preço" escolha a opção padrão (Standard S0). E confirme a checkbox sobre os preços abaixo.
![print7](https://github.com/ItaloRochaj/
buscas-cognitivas/blob/main/assets/print7.png)
Revise tudo e clique no botão "Examinar + criar" na lateral inferior esquerda
![print8](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print8.png)
Você será redirecionado a outra página com os termos, clique em "Criar" na lateral inferior esquerda
![print9](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print9.png)
Após ser redirecionado, deve aparecer um card de exito. Volte a página inicial da Azure, Pesquise por "Storage Account" no buscador e clique em "Contas de armazenamento".
![print10](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print10.png)
Clique em "Criar" na aba de opções para criar uma nova conta de armazenamento.
![print11](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print11.png)
Em "Detalhes do projeto", não altere a opção de assinatura. Em "Grupo de recursos" escolha um já criado ou crie um novo no botão abaixo "Criar novo".
Descendo a tela, temos os detalhes da instância, coloque um nome de sua preferência. É recomendado não utilizar servidores da região do Brasil, por questões de instabilidade, aqui utilize a já indicada pela Azure ou "East US". Em "Desempenho" selecione a opção "Standard", em "Redundância" esolha a opção "LRS". Por fim clique em "Examinar".
Examine tudo e clique em "Criar".
![print12](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print12.png)
![print14](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print14.png)
Após ser redirecionado, deve aparecer um card de exito. Clique no botão "Ir para o recurso".
![print15](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print15.png)

Na barra de navegação lateral, encontre a opção "Configuração" e clique nela. 
![print16](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print16.png)
Habilite a opção "Permitir acesso anônimo ao Blob" e clique em Salvar na barra de opções.
![print17](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print17.png)
Na barra de navegação lateral, encontre a opção "Contêineres" e clique nela.
CLique em "Contêiner" para criar um novo Contêiner.

![print18](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print18.png)
CLique em "Contêiner" para criar um novo Contêiner.

![print19](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print19.png)
CLique em "Contêiner" para criar um novo Contêiner.
![print20](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print20.png)
![print21](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print21.png)
Confirme a inserção dos arquivos clicando em "Carregar".
![print23](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print23.png)
![print24](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print24.png)
Clique em "Importar dados".
![print25](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print25.png)
Ao abrir o import de dados selecione a opção "Armazenamento de Blob do Azure"
Na seção "Conectar a seus dados", mantenha a "Fonte de Dados", dê um nome de sua escolha a fonte de dados, mantenha a opção "Contéudo e metadados" em "Dados para extrair", em "Modo de análise" mantenha o padrão e por fim clique em "Escolher uma conexão existente" para o campo "Cadeia de conexão".
![print26](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print26.png)
Expanda a seção "Adicionar enriquecimentos".
![print27](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print27.png)
![print28](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print28.png)
Voltando no recurso do serviço de pesquisa, em "Gerenciador de pesquisa".

![print30](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print29.png)
Encontre a seção 4 do tópico e aperte no link "avaliações de café compactadas", ele deve iniciar um download no seu navegador, abra a pasta após concluir o download no seu explorador de arquivos.

![print29](https://github.com/ItaloRochaj/buscas-cognitivas/blob/main/assets/print29.png)
Faça uma busca clique em "Pesquisar" e veja que na seção "Resultado", temos a resposta da pesquisa em um formato JSON.





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

## 3. Criando uma Conta de Armazenamento no Azure
1. No portal do Azure, pesquise por **"Storage Account"** e clique em **Criar**.
2. Escolha um **Grupo de Recursos** existente ou crie um novo.
3. Defina:
   - **Nome da Conta de Armazenamento**
   - **Localização**: Recomenda-se "East US" para melhor desempenho.
   - **Desempenho**: Selecione "Standard".
   - **Redundância**: Escolha "LRS".
4. Clique em **Examinar + Criar** e finalize a criação.

---

## 4. Configurando a Conta de Armazenamento
1. Acesse o recurso criado e clique em **Configuração**.
2. Ative a opção **Permitir acesso anônimo ao Blob** e salve.
3. No menu lateral, clique em **Contêineres**.
4. Crie um novo contêiner e defina as permissões públicas conforme necessário.
5. Carregue os arquivos de dados para indexação.

---

## 5. Importando Dados para o Azure Cognitive Search
1. Acesse o **Azure Cognitive Search** e clique em **Importar dados**.
2. Selecione **Armazenamento de Blob do Azure** como fonte de dados.
3. Configure a conexão com a conta de armazenamento criada.
4. Escolha os dados a serem indexados.
5. Na seção "Adicionar enriquecimentos", expanda e ative opções avançadas, se necessário.
6. Clique em **Avançar** e confirme a importação dos dados.

---

## 6. Criando e Executando uma Pesquisa
1. No Azure Cognitive Search, acesse **Gerenciador de Pesquisa**.
2. Utilize a ferramenta de pesquisa integrada para realizar consultas.
3. Insira palavras-chave e execute a pesquisa.
4. Os resultados serão apresentados no formato JSON.


## 7. Insights e Benefícios do AI Search
- **Análise Semântica**: melhora a precisão das pesquisas.
- **Sugestões Inteligentes**: autocomplete e sugestões de busca baseadas em IA.
- **Relevância Personalizada**: ajuste do ranking de resultados conforme necessidade.
- **Facilidade de Integração**: compatível com aplicativos web e mobile.

---

## 8. Ferramentas que se Beneficiam do Azure Cognitive Search
- **E-commerce**: busca de produtos baseada em relevância.
- **Sistemas de Suporte**: pesquisas inteligentes em bases de conhecimento.
- **Análise de Documentos**: indexação e busca avançada de documentos.
- **Pesquisa Acadêmica**: mineração de conhecimento em artigos científicos.

---

## 9. Aprendizados Durante o Processo
Durante a implementação do **Azure Cognitive Search**, aprendemos a:
1. Criar e configurar um serviço de pesquisa na nuvem.
2. Indexar diferentes tipos de fontes de dados.
3. Construir consultas eficientes para explorar os dados.
4. Utilizar técnicas de AI Search para otimizar a experiência de pesquisa.

---

## Conclusão
Com esse guia, você configurou um serviço de pesquisa no **Azure Cognitive Search**, criou um repositório de dados, indexou arquivos e realizou buscas eficientes. Essa solução pode ser aplicada em diversos cenários, como buscas empresariais, análise de documentos e mineração de conhecimento.

