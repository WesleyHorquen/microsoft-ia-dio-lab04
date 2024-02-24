# Microsoft IA 900 - Laboratório 4
- Nesse exercício vamos simular que trabalhamos no renomado **"Fourth Coffee"**, e precisamos ajudar a criar uma solução de mineração de conhecimento para buscar as avaliações de clientes.
- Documentação de apoio https://aka.ms/ai900-ai-search

## Neste laboratório vamos:

- Criar recursos do Azure
- Extrair dados de uma fonte de dados
- Enriquecer os dados com habilidades de IA
- Utilizar o indexador do Azure no portal do Azure
- Consultar o índice de pesquisa
- Revisar os resultados salvos em uma Loja de conhecimento

## Explore um índice do Azure AI Search
- Abrimos nosso Dashboard em https://portal.azure.com/ e vamos **Criar um recurso** e procurar por **Azure Ia Search**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/19d47178-4018-4d19-ba0c-0afb588b406f)
- Vamo em **Criar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/e75c1cf5-0e4a-49ce-af70-9e614e5e0ec7)
- Iremos escolher o **Plano de assinatura**, **Grupo de Recursos**, o **Nome do Serviço**, **Local**, **Camada de Preços** manteremos o **básico**, depois só ir em **Revisar + Criar** e após em **Criar** novamente

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/645c17c3-b4a0-49f3-9562-bb7175ca0056)
- Após a implantação vamos em **Ir para o recurso**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/c750374f-9bac-4810-9bf5-f3f1eadf6906)
- Depois retornameros a página inicial do Azure, vamos em **Criar um recurso** depois criamos **Azure AI services**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/5ccd2479-d1b4-42e5-a397-010c0bdbd22f)
- Devemos preencher com os mesmos dados de antes, se atentando a **marcar a caixa** depois **Examinar + criar** e **Criar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/6c34d955-745b-4cec-9c7a-312f1ca53d45)
- Agora para criar uma conta de armazenamento, vamos retornar ao Deshboard do Azure e acessar o botão **Criar um recurso** e pesquisar e criar **Conta de armazenamento**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/ba104651-9869-4cf6-b36e-dcc167e312da)
- Vamos preencher os mesmos dados como anteriormente, única mudança será um **Nome da conta de armazenamento** exclusivo, **Desempenho: Standard** e **Redundância: armazenamento localmente redundante (LRS)** como na imagem, ai é só **Examinar** e **Criar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/0641f34e-2a83-4c37-8de5-377eab8bbe82)
- Após criado vamos em **Ir para o recurso**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/9ea3434b-415a-4d21-b755-8575be15125c)
- Já no recurso, ao lado esquerdo vamos em **Contêineres**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/dc7671cf-865b-4a6e-aada-33f76c7e38f3)
- Depois clicamos em **+ Contêineres**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/f81a3624-5fb2-4281-9788-e250c65e9bf7)
- Vai aparecer uma tela, nela definiremos o **Nome** para **"cofee-reviews"**, **Nível de acesso** **Container (acesso de leitura anônimo para containers e blobs)**, **Avançado** sem alterações, ai basta **criar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/64da34e7-a8e4-4ef7-be02-9491bb7b8153)
- Devemos agora abrir uma nova guia do navegador e baixar os arquivos compactados https://aka.ms/mslearn-coffee-reviews
- Depois de baixado vamos abrir nosso **cofee-reviews**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/a44d1795-d3d1-4259-895d-6a72c16769f4)
- Vamos fazer o upload dos arquivos baixados anteriormente

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/c58bfde1-2ad0-42ca-90fe-756a6212ab31)
- Faça os uploads dos arquivos depois clique em **Carregar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/387e4fb7-8462-4d73-9e6e-4c988007fb50)
- Deve ficar uma tela como na imagem

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/f92474bf-62d9-49ed-9d92-d3dee4c45e4c)
 
## Para darmos continuidade, vamos Indexar os documentos

- Voltando ao portal do azure, vamos no recurso **IA Source**, abrimos o criado anteriormente e clicamos em **Importar dados**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/b2ebc14b-e5cc-4328-9344-a2e6b9920f3a)
- Vamos em **Conectar a seus dados**, na aba **Fonte de Dados** escolheremos **Armazenamento de Blob do Azure**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/9021dddf-b7e9-4b84-966b-ed2cd2391737)
- No momento, vamos preencher exatamente como na imagem

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/cb458a7c-9764-46db-8f46-a57660069f9e)
- Em **Cadeia de conexão** vamos clicar logo abaixo em **Exolher uma conexão existente**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/54acfb94-7a3b-48e0-8e5e-df0b6d585b4f)
- Irá mudar de página aparecendo o recurso que criamos anteriormente, basta clicar nele

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/38ba107e-5616-4106-823e-c1a6cf524517)
- Vai aparecer a lista de contêineres, clicamos em nosso **coffee-reviews** e logo abaixo em **Selecionar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/d2cdd36b-eec7-4324-8ea3-2b5422886c32)
- Logo abaixo em **Autenticação de identidade** deixaremos em **Nenhum**, **Nome do contêiner** puxa automáticamente, **Pasta de blobs** deixamos em branco e em **Descrição** colocaremos **Avaliações sobre Fourth Coffee Shops.** e finalmente logo abaixo **Próximo: Adicionar habilidades cognitivas(Opcional)**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/762a626a-ab51-44f4-8a77-7d3aedbe3527)
- Na secção **Anexar Serviços Cognitivos**, selecione o seu recurso de serviços Azure AI.

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/082c99d7-2792-4c49-b1ee-b842445dd3fa)
- Na parte de **Adicionar enriquecimentos** preencheremos conforme a imagem abaixo

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/0e659285-3cc5-481c-ac63-16d0831fedb9)
- Em **Salvar os enriquecimentos em um repositório de conhecimento** vamos preencher os seguintes box como na imagem

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/fc32efd6-5c46-4e02-857b-4f65c281c9f6)
- Irá aparecer um **"Erro"** basta clicarmos em **Escolher uma conexão existente**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/147bcad7-3895-4e1a-91cc-ebb4e4c58bea)
- Vamos escolher o que criamos anteriormente

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/daaff754-2a75-4d7a-980b-b81b5d39f381)
- E vamos criar um novo **Contêiner** como na imagem, depois basta clicar logo abaixo em **Criar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/89d1c64b-c42a-4ff2-a174-b669e18f55ab)
- Selecionamos o nosso contêiner recêm criado e logo abaixo **Selecionar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/c0fd2993-d456-48f8-8358-44c2b3cce2bb)
- Vamos selecionar o box **Documento** e logo abaixo **Próximo: Personalizar índice de destino**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/9af3796b-33cb-4d01-9c80-a5b6fc9be524)
- Em **Nome** definiremos **coffee-index**, **Chave** verificamos se está **metadata_storage_path** e logo abaixo em **content** precisamos selecionar a box do campo **Filtrável**, depois basta clicar em **Próximo: Criar um indexador**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/42c628cc-0f00-4718-b26f-06c95f783e61)
- No **Indexador** alteramos o **Nome** para **coffee-indexer**, certificamos que esteja selecionado **Uma vez** e em **Opções avançadas** o box **Chaves de codificação de Base 64**, depois basta **Enviar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/72fee036-7ea3-48ad-a944-4e1ddaabfbc9)
- No canto esquerdo da página **Azure AI Search** vamos selecionar **Indexadores**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/d7fe8724-81c7-46eb-bf2c-4c8c95fa4902)
- Selecione o **Indexador** para vermos mais detalhes

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/91898f54-db41-4bd6-b747-2e383f7d8c52)
- Vamos retornar ao **IA Search** e clicar em **Gerenciador de pesquisa**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/473430ba-af0a-4e38-862e-434c1aa414e2)
- Ao lado direito em **Exibir** vamos alterar para **jSON View**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/a3697c90-4fb7-4215-854b-952a00b40db8)
- No campo **Editor de consulta JSON** copie e cole:
{
    "search": "*",
    "count": true
}

Depois em clique **Pesquisar**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/d36deb15-4ee6-4652-905b-95f1cadb8493)
- Como resultado teremos todo o código abaixo

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/b1eff7a5-58c4-49f0-93bf-d97ca50a9c74)
- Vamos filtrar por localização digitando o código como na imagem

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/31e079c1-eb81-4a3a-b2cf-0091d8d7b12f)
- Devemos obter o resultado **3** em **@odata.count**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/e2c8b5b2-9570-481e-81ee-007c7a9cb54f)
- Vamos filtrar por **Sentimento** com o código a seguir

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/79827e37-4cdc-46ef-9d1c-5b6a44106282)
- Devemos obter como resultado **1** em **@odata.count**

![image](https://github.com/WesleyHorquen/microsoft-ia-dio-lab04/assets/89001286/8c701fb6-df51-4b00-ba9d-056d96ce820a)

### Assim podemos verificar como está sendo as avaliações de nosso café, e o que precisamos melhorar, não só nesse, mas em nossos outros cafés espalhados pelo mundo sem que necessitemos estar presentes no momento para colher estas informações.














