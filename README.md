## WireMock 
O WireMock é uma ferramenta poderosa para simulação de APIs durante o desenvolvimento e teste de software. Este guia oferece instruções sobre como configurar e executar o WireMock em seu ambiente local.

## Pré-requisitos
Certifique-se de ter instalado o Java Development Kit (JDK) em sua máquina. O WireMock é executado na JVM (Java Virtual Machine), então o JDK é necessário para rodar o servidor.

## Instalação
Faça o download do JAR standalone presente neste projeto

## Configuração
- Crie um diretório para armazenar seus arquivos de configuração do WireMock.
- Crie arquivos JSON para definir os stubs da API. Por exemplo, você pode criar um arquivo stub.json com o seguinte conteúdo:

- Vamos criar importar o seguinte endpoint via cURL (Pode ser no postman):
 
```json
  curl --location 'http://localhost:8080/__admin/mappings' \
--header 'Content-Type: application/json' \
--data '{
    "request": {
        "url": "/tempo-api/temperatura?regiao=oeste",
        "method": "GET"
    },
    "response": {
        "status": 200,
        "body": "{\"data\":{\"temperatura\":00.00,\"regiao\":\"oeste\"}}"
    }
}
'
```
## Execução
- Navegue até o diretório onde você baixou ou instalou o WireMock.
- Clique com o botão direito sobre o arquivo ```java -jar wiremock-standalone-2.27.2.jar``` e execute o terminal a partir do arquivo.
- Execute o comando para iniciar o servidor:

```
java -jar wiremock-standalone-2.27.2.jar --port 8080 --root-dir /caminho/para/seu/diretorio/de/configuracao
```

- Certifique-se de substituir /caminho/para/seu/diretorio/de/configuracao pelo caminho real do diretório onde estão seus arquivos de configuração.
Espere até ver a mensagem abaixo de que o WireMock foi iniciado com sucesso.

## Teste
- Envie a requisição que você criou no postman
- Você pode testar o WireMock acessando a URL localhost:8080/tempo-api/temperatura?regiao=oeste em seu navegador ou usando ferramentas como cURL ou Postman.
