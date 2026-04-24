# Passo a Passo: Configuração do Ambiente

#### Execute os comandos abaixo no seu terminal para preparar a base do nosso projeto com Node.js, TypeScript e WebSockets.
<br>

**1. Inicialização do Projeto**

```bash
npm init -y
```
Inicializa um novo projeto Node.js criando o arquivo package.json com as configurações padrão (a flag -y pula as perguntas iniciais).
<br><br><br>

**2. Instalação das Dependências Principais**

```bash
npm install ws uuidv4
```
***ws***: Instala a biblioteca de WebSockets, que será o motor para criar nosso servidor e gerenciar a comunicação em tempo real.

***uuidv4***: Instala a biblioteca para gerar identificadores únicos (UUIDs). Muito útil para atribuir um ID exclusivo para cada cliente/jogador que se conectar ao servidor.
<br><br><br>

**3. Instalação das Dependências de Desenvolvimento (TypeScript)**

```bash
npm install -D @types/node @types/ws @types/uuid
```
A flag -D instala estes pacotes apenas para o ambiente de desenvolvimento. Os pacotes @types/* fornecem as tipagens oficiais para o TypeScript entender o Node.js, o WebSockets e o UUID, habilitando o autocompletar e a verificação de erros no seu editor de código.
<br><br><br>

**4. Configuração do TypeScript**

```bash
npx tsc --init
```
Cria o arquivo tsconfig.json. É nele que definimos as regras do compilador TypeScript, como a versão do JavaScript que será gerada e as pastas de entrada (src) e saída (build ou dist).
<br><br><br>

**5. Estrutura de Pastas**

```bash
mkdir -p src/core
```
Cria a estrutura inicial de diretórios do projeto. O parâmetro -p garante que o terminal crie a pasta src e a subpasta core de uma vez só, ignorando erros caso elas já existam.
<br><br><br>

### Scripts de Compilação e Execução
Para transformar o código TypeScript em JavaScript e rodar o servidor, utilizamos os seguintes comandos:

**Compilar o código:**

```bash
npx tsc
```
Executa o compilador do TypeScript. Ele lê todos os seus arquivos .ts e os converte para arquivos .js na pasta de destino configurada (geralmente a pasta build).
<br><br><br>

**Rodar em Desenvolvimento:**

```bash
npx ts-node src/server.ts
```
***Nota***: Requer que o pacote ts-node esteja instalado (*npm install -D ts-node*).
Executa o servidor lendo diretamente o arquivo TypeScript, sem precisar compilar antes. É a forma mais rápida de testar o código enquanto você o desenvolve.

**Rodar em Produção:**

```bash
node build/server.js
```
Executa a versão final já compilada (JavaScript puro). Este é o comando oficial que deve ser usado quando o projeto for para o ar (por exemplo, ao rodar dentro de um contêiner Docker no seu ambiente em nuvem).
