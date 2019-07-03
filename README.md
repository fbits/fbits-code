# Fbits{{Code}}
### Gerenciador de arquivos de templates da loja

O Fbits Code permite aos designers das agências a baixarem os templates da loja que estão trabalhando para customizarem como quiser localmente, 
testando em um servidor local, e então enviar novamente para o servidor para publicar através de uma CLI intuitiva.


# Download
[Windows 64-bits](https://static.fbits.net/fbits-code/windows/fbits-code.zip)

[MacOS](https://static.fbits.net/fbits-code/macos/fbits-code.zip)

# Instalação

### __Windows__
1. __Crie uma pasta__ para os arquivos e descompacte o .zip. Copie o caminho da pasta criada.
2. Clique no Iniciar e digite 'env', deve aparecer '__Editar variáveis de ambiente do sistema__', abra.
3. Na janela, clique em '__Variáveis de Ambiente...__'.
4. Nas variáveis do sistema (parte de baixo), encontre a variável '__Path__' e clique em '__Editar...__'.
5. Clique em '__Novo__' e adicione o caminho para a pasta que você copiou. Clique em '__OK__'.
6. Abra um Prompt de Comando ou PowerShell aonde desejar e teste a instalação com '__fbits-code__'

### __MacOS__
1. __Crie uma pasta__ para os arquivos e descompacte o .zip. Copie o caminho da pasta criada.
2. Abrir um __Terminal__ e executar o comando:
```sh
sudo nano /etc/paths
```
3. No fim do documento adicionar o caminho para pasta do fbits-code.
4. Aperte __control + x__ para sair, aperte __Y__ e então __Enter__ para salvar.
5. __Fechar o Terminal__, abrir outro e digitar o comando:
```sh
echo $PATH
```
Caso tenha dado certo, você conseguirá ver o caminho adicionado.

6. Agora abra o Terminal no local que desejar e teste a instalação com '__fbits-code__'


# Instruções de execução
### Inicializando um workspace
Para inicializar na pasta atual
```sh
fbits-code init -t meutoken
```
Para inicializar em uma subpasta
```sh
fbits-code init -t meutoken -o nomedapasta
```
### Baixando os templates
Para baixar o tema vinculado ao token
```sh
fbits-code pull
```
### Testar localmente
Para iniciar o servidor local
```sh
fbits-code serve
```
### Publicar
Para enviar o tema para o servidor
```sh
fbits-code publish
```

# Uso dos templates Core
Os templates Core foram feitos pela Fbits com o intuito de facilitar a inclusão de alguns elementos e em alguns casos garantir o funcionamento correto do tema.

### fbits_css e fbits_js
```sh
{{ fbits_css 'Home/home' }} -> Caso esteja dentro de uma pasta. Ex: ../Templates/CSS/Home/home.css
{{ fbits_js 'script' }} -> Caso esteja na pasta já. Ex: ../Templates/JS/script.js
```
### fbits_image
Parâmetros:
- __classes__: classes para passar para `<img>`
- __url__: a url da imagem, normalmente vindo do contexto
- __sizes__: tamanhos da imagem para passar no srcset
- __alt__: alt
```sh
{{ fbits_image classes: 'minha-classe outra-classe' url: urlDaImg sizes: '100,200,300' alt: 'umaImagem' }}
```


# Customização
### Criação de componentes
A criação de componentes deve ser feita dentro da pasta Components. Caso queira adicionar uma subpasta, é possível, contudo deve-se lembrar de referênciar a pasta criada na hora do include.
Exemplo:

```sh
-- PastaDosTemplates
    -- Templates
        -- Pages
        -- Components
            -- Novo
                -- NovoTemplate.html
```
Deve ser incluído como:
```sh
{{ include 'Novo/NovoTemplate' }}
```
> O mesmo pode ser feito para arquivos JS e CSS, contudo devem ser criados dentro de suas respectivas pastas!

# Informações do Demo Atual
O demo atual ainda não está integrado com os dados reais das lojas, portanto foram criados 2 arquivos json com dados para serem utilizados. __Apenas a página Product poderá ser vista em produção.__

### Dados globais
Esses dados estão disponíveis na página Product e em todos os componentes
```json
{
  "nome": "Tênis Converse Chuck Taylor All Star European Ox Branco CT04480001",
  "sku": "0001CT044803334",
  "preco": 229.9,
  "estoque": 3,
  "imagens": [
    {
      "url": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048/253307.jpg",
      "id": "253307/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048_70"
    },
    {
      "url": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048/253307-1.jpg",
      "id": "253307-1/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048_70"
    },
    {
      "url": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048/253307-2.jpg",
      "id": "253307-2/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048_70"
    },
    {
      "url": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048/253307-3.jpg",
      "id": "253307-3/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048_70"
    },
    {
      "url": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048/253307-4.jpg",
      "id": "253307-4/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048_70"
    },
    {
      "url": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048/253307-5.jpg",
      "id": "253307-5/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048_70"
    },
    {
      "url": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048/253307-6.jpg",
      "id": "253307-6/tenis-converse-chuck-taylor-all-star-european-ox-branco-ct04480001-66048_70"
    }
  ],
  "descricao": "<META content=\"text/html; charset=windows-1252\" http-equiv=Content-Type><META name=GENERATOR content=\"MSHTML 11.00.10570.1001\"><b>Linha:</b> Chuck Taylor All Star<br />\r\n<b>C&oacute;digo:</b> CT0448<br />\r\n<b>Material:</b> Couro<br />\r\n<b>Numera&ccedil;&atilde;o Fabricada:</b> 33 ao 44<br />\r\n<b>Vers&atilde;o:</b> Cano Baixo (Ox)<br />\r\n<b>Solado:</b> Borracha<br />\r\n<b>F&ocirc;rma:</b> Grande (Veja Guia de Medidas)<br />\r\n<b>Detalhes:</b> A <b>Converse</b> trouxe para esta cole&ccedil;&atilde;o, uma nova vers&atilde;o do modelo <b>Europen</b> agora com detalhes Clean, que o deixam ainda mais estiloso. Cabedal todo confeccionado em couro, promove conforto e maior durabilidade. Detalhe para os ilhoses pretos que se destacam no modelo. Para a transpira&ccedil;&atilde;o adequada dos p&eacute;s, o produto conta com dois ilh&oacute;ses na parte interna do cabedal. O solado e a vira s&atilde;o de borracha.<br />\r\n<b>Aten&ccedil;&atilde;o:</b> A quantidade de passadores (ilhoses) podem variar conforme o tamanho do produto. As cores do produto podem sofrer altera&ccedil;&otilde;es conforme a calibragem de cada monitor.<br />\r\n<b>G&ecirc;nero:</b> Unissex.<br />\r\n<b>Garantia:</b> Contra defeito de fabrica&ccedil;&atilde;o.<br />\r\n<img alt=\"?abela\" src=\"https://recursos.lojavirus.com.br/MediaCenter/converse_tradicional.jpg\" star=\"\" />",
  "irmaos": [
    {
      "valor": "Preto Branco",
      "imagem": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-preto-branco-ct04480002-66049/253319.jpg",
      "url": "https://www.lojavirus.com.br/produto/tenis-converse-chuck-taylor-all-star-european-ox-preto-branco-ct04480002-66049"
    },
    {
      "valor": "Chocolate",
      "imagem": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-chocolate-ct04480003-66050/253331.jpg",
      "url": "https://www.lojavirus.com.br/produto/tenis-converse-chuck-taylor-all-star-european-ox-chocolate-ct04480003-66050"
    },
    {
      "valor": "Borgonha",
      "imagem": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-borgonha-ct04480004-67800/265337.jpg",
      "url": "https://www.lojavirus.com.br/produto/tenis-converse-chuck-taylor-all-star-european-ox-borgonha-ct04480004-67800"
    }
  ],
  "variantes": [
    {
      "valor": "33",
      "disponivel": true
    },
    {
      "valor": "34",
      "disponivel": true
    },
    {
      "valor": "35",
      "disponivel": true
    },
    {
      "valor": "36",
      "disponivel": true
    },
    {
      "valor": "37",
      "disponivel": true
    },
    {
      "valor": "38",
      "disponivel": false
    },
    {
      "valor": "39",
      "disponivel": false
    },
    {
      "valor": "40",
      "disponivel": false
    },
    {
      "valor": "41",
      "disponivel": true
    },
    {
      "valor": "42",
      "disponivel": true
    },
    {
      "valor": "43",
      "disponivel": true
    },
    {
      "valor": "44",
      "disponivel": true
    }
  ]
}
```

### Dados por Componente
Eventualmente teremos diversos componentes com seus próprios contextos, como exemplo, temos no demo atual o componente Core Recomendados. Os dados dele podem ser acessados apenas a partir do componente ou de algum *include* feito dentro do componente.
#### Recomendados
```json
{
  "Recomendados": [
	{
	  "Id": 67875,
	  "Nome": "T&#234;nis Converse Chuck Taylor All Star 3V Branco Branco CT09840002",
	  "Imagem1": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-3v-branco-branco-ct09840002-67875/265968.jpg",
	  "Imagem2": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-3v-branco-branco-ct09840002-67875/265968-1.jpg",
	  "Alias": "tenis-converse-chuck-taylor-all-star-3v-branco-branco-ct09840002-67875",
	  "PrecoPor": 269.90,
	  "Tamanhos": ["33", "34", "36", "37", "38"]
	},
	{
	  "Id": 66169,
	  "Nome": "T&#234;nis Converse Chuck Taylor All Star European Hi Branco CT0449001",
	  "Imagem1": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-hi-branco-ct0449001-66169/253983.jpg",
	  "Imagem2": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-hi-branco-ct0449001-66169/253983-1.jpg",
	  "Alias": "tenis-converse-chuck-taylor-all-star-european-hi-branco-ct0449001-66169",
	  "PrecoPor": 249.90,
	  "Tamanhos": ["33", "34", "36", "37", "38", "39", "40", "41", "42", "43", "44"]
	},
	{
	  "Id": 66170,
	  "Nome": "T&#234;nis Converse Chuck Taylor All Star European Hi Preto Branco CT0449002",
	  "Imagem1": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-hi-preto-branco-ct0449002-66170/253995.jpg",
	  "Imagem2": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-hi-preto-branco-ct0449002-66170/253995-1.jpg",
	  "Alias": "tenis-converse-chuck-taylor-all-star-european-hi-preto-branco-ct0449002-66170",
	  "PrecoPor": 249.90,
	  "Tamanhos": ["33", "34", "35", "36", "37", "38", "39", "40", "42", "43", "44"]
	},
	{
	  "Id": 66049,
	  "Nome": "T&#234;nis Converse Chuck Taylor All Star European Ox Preto Branco CT04480002",
	  "Imagem1": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-preto-branco-ct04480002-66049/253319.jpg",
	  "Imagem2": "https://lojavirus.fbitsstatic.net/img/p/tenis-converse-chuck-taylor-all-star-european-ox-preto-branco-ct04480002-66049/253319-1.jpg",
	  "Alias": "tenis-converse-chuck-taylor-all-star-european-ox-preto-branco-ct04480002-66049",
	  "PrecoPor": 229.90,
	  "Tamanhos": ["33", "34", "35", "36", "37", "38", "39", "40", "41", "42", "43", "44"]
	}
  ]
}
```
