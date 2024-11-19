# Principais Funcionalidades

## Autenticação com GitHub
O código utiliza um **JWT (JSON Web Token)** para autenticar um GitHub App. Ele lê uma chave privada de um arquivo PEM e gera um token de acesso para interagir com a API do GitHub.

## Interação com Pull Requests
- O script pode buscar informações sobre um PR específico, incluindo seus commits e diffs (as alterações feitas).
- Ele pode criar comentários em PRs, tanto em geral quanto em arquivos específicos dentro de um commit.

## Análise de Código
O código carrega arquivos de prompts de análise de um diretório local e utiliza a API do OpenAI para avaliar o conteúdo do PR ou dos commits. Dependendo da configuração (basic), ele pode realizar:
- Análise básica
- Análise detalhada por commit

## Refatoração de Código
Após a análise, o script pode sugerir refatorações para o código modificado. Ele envia o código original e as sugestões de análise para a API do OpenAI, que retorna uma versão refatorada do código. O código refatorado é então enviado de volta ao repositório como um novo commit em uma nova branch.

## Criação de Branches e Commits
- O script verifica se uma branch já existe e, se não, cria uma nova branch a partir de um commit base.
- Ele realiza commits das alterações refatoradas e pode criar um novo PR para essas alterações.
