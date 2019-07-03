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
