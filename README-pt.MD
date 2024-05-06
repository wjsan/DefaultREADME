# Nome do Repositório

Aqui você deve colocar um pequeno resumo do que está neste repositório, por que é importante e explicar um pouco sobre como o problema foi resolvido.

Se houver alguma versão deste readme em outro idioma, por favor, coloque o link aqui. Exemplo:

Inglês | [Português](README-pt.md)

# Índice

- [Nome do Repositório](#nome-do-repositório)
- [Índice](#índice)
- [Pré-instalação](#pré-instalação)
  - [Linux (Debian)](#linux-debian)
  - [Linux (Arch)](#linux-arch)
  - [Windows (Chocolatey)](#windows-chocolatey)
  - [Windows (Instalador)](#windows-instalador)
- [Instalação](#instalação)
- [Como usar o programa](#como-usar-o-programa)
  - [Iniciar Interface Ethernet](#iniciar-interface-ethernet)
    - [Solicitação](#solicitação)
    - [Resposta](#resposta)

# Pré-instalação

Nesta seção, você explicará o que é necessário e recomendado já ter instalado para usar o programa.
Exemplo:

<details><summary><b>Linux (Debian)</b></summary>

## Linux (Debian)

1. Instale o pacote python3:

    ```bash
    sudo apt install python3
    ```

</details>

<details><summary><b>Linux (Arch)</b></summary>

## Linux (Arch)

1. Instale o pacote python:

    ```bash
    sudo pacman -S python
    ```

</details>

<details><summary><b>Windows (Chocolatey)</b></summary>

## Windows (Chocolatey)

1. Instale o pacote python:

    ```shell
    choco install python
    ```

</details>


<details><summary><b>Windows (Instalador)</b></summary>

## Windows (Instalador)

1. Instale o python usando o instalador:

   Para instalar o python, você precisará executar o instalador localizado no [site oficial do python](https://www.python.org/downloads/)

</details>

# Instalação

Nesta seção, você deve começar com a instalação do próprio projeto. Para manter o repositório bem organizado, você também pode criar várias subseções quebrando o processo de instalação em partes menores para ajudar na
melhor compreensão do processo.

Se alguma parte da instalação for considerada complexa, adicionar imagens e GIFs também pode ajudar, especialmente quando for necessário encontrar um botão em uma interface ou clicar em várias configurações em um menu seguindo uma ordem específica.

Exemplo:

<center>
 <img src="https://raw.githubusercontent.com/espressif/vscode-esp-idf-extension/master/media/tutorials/setup/install-extension.png" alt="Assistente de configuração">
</center>

Na imagem acima, você pode entender facilmente quais passos deve seguir e em que ordem, mas é uma boa prática explicar o conteúdo na imagem para garantir que seja entendido corretamente.

Dar preferência para imagens que estejam hospedadas na internet, para não poluir o repositório com arquivos de imagens. Mas caso seja necessário, adicionar uma pasta "images", inserir as imagens nesse repostitório com o nome no seguinte formato: "1_nome_da_imagem.png", e referenciá-la no readme de forma relativa: 

```markdown
![import_file](images/1_nome_da_imagem.png)
```

<details><summary><b>Clonando o repositório</b></summary>


Primeiro, é necessário clonar o repositório, o que pode ser feito pelo seguinte comando:

```bash
git clone (URL do repositório)
```

</details>

<details><summary><b>Preparação para a compilação</b></summary>

Pode ser necessário realizar alguns comandos antes da compilação do repositório, ou mesmo algum ajuste nas configurações do projeto. Em repositórios que usam node.js por exemplo, pode ser necessário o comando `npm install` ou `yarn install`. Em projetos que usam cmake pode ser necessário criar o diretório de build antes da compilação conforme exemplo abaixo. Assim nessa seção devem ser descritos esses procedimentos. Abaixo temos um exemplo demonstrando como preparar o ambiente para realizar a compilação de uma aplicação feita em ANSI C com cmake:

Agora, antes de executar o CMAKE, é necessário criar uma pasta chamada build e depois mudar para essa pasta. Isso pode ser feito usando o seguinte comando:

```bash
mkdir build && cd build
```

</details>

<details><summary><b>Compilando o programa</b></summary>

```bash
cmake ..
```

Em algumas partes da instalação, onde erros comuns podem ocorrer, é recomendável usar um aviso explicando como as coisas podem dar errado e erros comuns que podem ser cometidos. Exemplo:

> **Aviso:** Tenha cuidado para não executar o MAKEFILE como superusuário, isso pode danificar seu sistema operacional.

Outra recomendação é colocar uma tabela simples de compilação com os parâmetros que você pode usar para compilar o programa, por exemplo:

| Comando    | Função                                                                      |
|------------|-------------------------------------------------------------------------------|
| make clean | Exclui os arquivos criados pela última compilação na pasta build          |
| make       | Compila o programa com o compilador g++, o resultado está na pasta build |
| make run   | Compila e depois executa o programa na pasta build                    |

</details>

# Como usar o programa

Antes da instalação (não seria após a instalação, já que essa seção está após a seção de isntalação?) , é bom ter uma seção para explicar como usar o programa da maneira como foi pretendido ser usado, então explique quais parâmetros ele pode receber, entradas comuns e suas saídas esperadas, etc. Se necessário, você também pode criar uma seção de **Configuração** para explicar melhor como configurar o programa. Dependendo do programa, é possível criar outra seção apenas para explicar quais são os formatos de pacote usados e exemplos de mensagens com eles sendo enviados.

Exemplo:

<details><summary><b>Firewall</b></summary>


1. Firewall

    + Ativar Firewall?
        - Isso ajuda a proteger seu Mac contra ataques pela internet.
    + Ativar log?
        - Se HOUVER uma infecção, os logs são úteis para determinar a origem.
    + Ativar modo stealth?
        - Seu Mac não responderá a solicitações de ping ICMP ou tentativas de conexão de redes TCP e UDP fechadas.

    2. Proteção Geral do Sistema

        + Habilitar Gatekeeper?
            - Defenda-se contra malware, forçando a assinatura de código e verificando aplicativos baixados antes de permitir que eles sejam executados.
        + Prevenir o whitelisting automático de software?
            - Tanto o software integrado quanto o baixado precisarão de aprovação do usuário para whitelisting.
        + Desativar o Captive Portal Assistant e forçar o login através do navegador em redes não confiáveis?
            - O Captive Portal Assistant poderia ser acionado e direcioná-lo para um site malicioso SEM qualquer interação do usuário.

</details><details><summary><b>Formato da mensagem de saúde</b></summary>

A cada dez segundos, o gateway envia uma mensagem de saúde para o broker. Através dessa mensagem, é possível monitorar certos aspectos da operação do dispositivo.

```c
{
  "t": time_t,                        ///< Carimbo de hora da mensagem
  "rssi": int8_t,                     ///< rssi WiFi
  "ssid": string,                     ///< ssid WiFi
  "ip": string,                       ///< IP do dispositivo
  "bsc": hdr_bsc_err_t,               ///< Código de erro do Scanner Ble
  "performance": float,               ///< Performance do dispositivo (Taxa de Pacotes Recebidos/Perdidos)
  "boot": uint16_t,                   ///< Contagem de inicialização após a última ligação
  "reason": esp_reset_reason_t,       ///< Último motivo de reinicialização
  "memory": uint16_t,                 ///< Heap de memória livre
  "lifetime": uint64_t                ///< Tempo de vida após a última ligação em minutos
}
```

O valor da chave "bsc" pode representar os seguintes erros:

```c
typedef enum hdr_bsc_err
{
    BSC_ERROR_NOERROR = 48,           ///< Sem erro
    BSC_ERROR_UNEXPECTED_CMD = 49,    ///< Comando inesperado recebido pelo nrf
    BSC_ERROR_UNKNOWN_CMD = 50,        ///< Comando desconhecido recebido pelo nrf
    BSC_ERROR_RQMBUSY = 51,           ///< RQM está ocupado
    BSC_ERROR_UARTCOMM = 52,          ///< Erro de comunicação UART
    BSC_ERROR_UARTUFIFO = 53,         ///< Overflow de FIFO UART
    BSC_ERROR_ADVLOST = 54,           ///< ADV está perdido
    BSC_ERROR_UNKNOWN_SEQ = 55,        ///< Sequência de dados desconhecida recebida pelo nrf
    BSC_ERROR_CNNT_TIMEOUT = 56,        ///< Timeout de conexão <OBSOLETO>
    BSC_ERROR_CNNT_OVERFLOW = 57,     ///< Overflow de conexão <OBSOLETO>
    BSC_ERROR_STARTUP = 58            ///< Erro no Início do Scanner Ble
} hdr_bsc_err_t;
```

O valor da chave "reason" pode representar os seguintes erros:

```c
typedef enum {
    ESP_RST_UNKNOWN,    ///< O motivo da reinicialização não pode ser determinado
    ESP_RST_POWERON,    ///< Reinicialização devido a evento de ligação
    ESP_RST_EXT,        ///< Reinicialização por um pino externo (não aplicável ao ESP32)
    ESP_RST_SW,         ///< Reinicialização de software via esp_restart
    ESP_RST_PANIC,      ///< Reinicialização de software devido a exceção/pancada
    ESP_RST_INT_WDT,    ///< Reinicialização (

software ou hardware) devido ao watchdog de interrupção
    ESP_RST_TASK_WDT,   ///< Reinicialização devido a watchdog de tarefa
    ESP_RST_WDT,        ///< Reinicialização devido a outros watchdogs
    ESP_RST_DEEPSLEEP,  ///< Reinicialização após sair do modo de hibernação profunda
    ESP_RST_BROWNOUT,   ///< Reinicialização por brownout (software ou hardware)
    ESP_RST_SDIO,       ///< Reinicialização via SDIO
} esp_reset_reason_t;
```

Exemplo de mensagem:

```json
{
  "t": 1654689408,
  "rssi": -55,
  "ssid": "CABO CANAVERAL",
  "ip": "192.168.1.13",
  "bsc": 48,
  "performance": 99.16,
  "boot": 0,
  "reason": 1,
  "memory": 75272,
  "lifetime": 30
}
```

</details>

Se o programa também puder se comunicar com alguma API, você também pode criar uma seção e colocar as informações nela, com exemplos de uma solicitação e resposta da API. Exemplo:

<details><summary><b>API de Gateway</b></summary>

É possível se comunicar com o dispositivo usando a API de Gateway que pode ser acessada por um cliente HTTP local ou um cliente MQTT conectado ao mesmo broker do dispositivo.

Para usar esta API no MQTT, publique solicitações para `B2D/$companyId/$mac/$deviceId` e inscreva-se em `C2B/$companyId/$mac/$deviceId/ackGtw` para receber respostas do dispositivo.

## Iniciar Interface Ethernet

### Solicitação

`POST /v1/hg/queue`

```json
{
    "id": 0,
    "timeout": 5000,
    "disabled": false,
    "ip": {
        "enabled": false,
        "ip": "",
        "netmask": "",
        "gw": "",
        "dns": ""
    }
}
```

### Resposta

`HTTP 200 OK`

```json
{
	"err": 0,
	"msg": "ESP_OK(0x0)"
}
```

</details>
