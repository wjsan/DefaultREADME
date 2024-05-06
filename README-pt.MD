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

</details><p>

<details><summary><b>Linux (Arch)</b></summary>

## Linux (Arch)

1. Instale o pacote python:

    ```bash
    sudo pacman -S python
    ```

</details><p>

<details><summary><b>Windows (Chocolatey)</b></summary>

## Windows (Chocolatey)

1. Instale o pacote python:

    ```shell
    choco install python
    ```

</details><p>


<details><summary><b>Windows (Instalador)</b></summary>

## Windows (Instalador)

1. Instale o python usando o instalador:

   Para instalar o python, você precisará executar o instalador localizado no [site oficial do python](https://www.python.org/downloads/)

</details><p>

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

</details><p>

<details><summary><b>Preparação para a compilação</b></summary>

Pode ser necessário realizar alguns comandos antes da compilação do repositório, ou mesmo algum ajuste nas configurações do projeto. Em repositórios que usam node.js por exemplo, pode ser necessário o comando `npm install` ou `yarn install`. Em projetos que usam cmake pode ser necessário criar o diretório de build antes da compilação conforme exemplo abaixo. Assim nessa seção devem ser descritos esses procedimentos. Abaixo temos um exemplo demonstrando como preparar o ambiente para realizar a compilação de uma aplicação feita em ANSI C com cmake:

Agora, antes de executar o CMAKE, é necessário criar uma pasta chamada build e depois mudar para essa pasta. Isso pode ser feito usando o seguinte comando:

```bash
mkdir build && cd build
```

</details><p>

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

</details><p>

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

</details><p>

Adicionar ao final do readme, um exemplo de saída do console da aplicação após a compilação. Dessa forma, é possível ter uma referencia básica de como o programa deve se comportar durante as etapas inicias da sua execução. Grande parte dos problemas acontece nessa etapa, então isso pode ser útil para que seja possível identificar se algo deu errado. Abaixo segue um exemplo de saída da aplicação v3.4.0 do firmware do esp32 rodando em um HG3 V1:

```plain-text
rst:0x1 (POWERON_RESET),boot:0x12 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:1448
load:0x40078000,len:15548
ho 0 tail 12 room 4
load:0x40080400,len:4
0x40080400: _init at ??:?

load:0x40080404,len:3404
entry 0x40080614
I (586) cpu_start: Multicore app
I (595) cpu_start: Pro cpu start user code
I (595) cpu_start: cpu freq: 240000000 Hz
I (595) cpu_start: Application information:
I (598) cpu_start: App version:      v3.3.3-alpha.1-18-ga5895a91-dir
I (605) cpu_start: Compile time:     May  6 2024 10:44:14
I (611) cpu_start: ELF file SHA256:  6501359e6c327f1a...
I (617) cpu_start: ESP-IDF:          v5.2.1-dirty
I (622) cpu_start: Min chip rev:     v0.0
I (627) cpu_start: Max chip rev:     v3.99 
I (632) cpu_start: Chip rev:         v1.0
I (637) heap_init: Initializing. RAM available for dynamic allocation:
I (644) heap_init: At 3FFAE6E0 len 0000F480 (61 KiB): DRAM
I (650) heap_init: At 3FFCD098 len 00012F68 (75 KiB): DRAM
I (656) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (662) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (669) heap_init: At 40099388 len 00006C78 (27 KiB): IRAM
I (676) spi_flash: detected chip: generic
I (679) spi_flash: flash io: dio
I (684) coexist: coex firmware version: 77cd7f8
I (00:00:00.095) main_task: Started on CPU0
I (00:00:00.106) main_task: Calling app_main()
I (00:00:00.106) main: GTW Version: 3.4.0
I (00:00:00.109) main: GTW Hardware: HG3 V1
I (00:00:00.114) main: GTW Environment: prod
I (00:00:00.119) main: Heap: 242428
I (00:00:00.125) hg_app: Gateway Application Start
I (00:00:00.138) hg_flash: nvs initialized
I (00:00:00.139) gpio: GPIO[12]| InputEn: 1| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (00:00:00.143) gpio: GPIO[14]| InputEn: 1| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0 
I (00:00:00.154) gpio: GPIO[35]| InputEn: 1| OutputEn: 0| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:3
I (00:00:00.164) gpio: GPIO[4]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0
I (1797) wifi:wifi driver task: 3ffba5e4, prio:23, stack:6656, core=0
I (1797) wifi:wifi firmware version: a9f5b59
I (1797) wifi:wifi certification version: v7.0
I (1797) wifi:config NVS flash: enabled
I (1807) wifi:config nano formating: disabled
I (1807) wifi:Init data frame dynamic rx buffer num: 32
I (1807) wifi:Init static rx mgmt buffer num: 5
I (1817) wifi:Init management short buffer num: 32
I (1817) wifi:Init dynamic tx buffer num: 32
I (1827) wifi:Init static rx buffer size: 1600
I (1827) wifi:Init static rx buffer num: 10
I (1837) wifi:Init dynamic rx buffer num: 32
I (00:00:01.220) wifi_init: rx ba win: 6
I (00:00:01.224) wifi_init: tcpip mbox: 32
I (00:00:01.228) wifi_init: udp mbox: 6
I (00:00:01.233) wifi_init: tcp mbox: 6
I (00:00:01.237) wifi_init: tcp tx win: 5744
I (00:00:01.242) wifi_init: tcp rx win: 5744
I (00:00:01.247) wifi_init: tcp mss: 1440
I (00:00:01.252) wifi_init: WiFi IRAM OP enabled
I (00:00:01.257) wifi_init: WiFi RX IRAM OP enabled
I (1887) wifi:Set ps type: 0, coexist: 0

I (00:00:01.268) uart: queue free spaces: 20
I (00:00:01.273) gpio: GPIO[17]| InputEn: 0| OutputEn: 1| OpenDrain: 0| Pullup: 0| Pulldown: 0| Intr:0 
I (00:00:01.282) uart: queue free spaces: 20
         (00:00:01.561) uart: queue free spaces: 20
I (00:00:01.562) hdr_bsc: BSC Exp/Recv Code date: 250923 / 250923
I (00:00:01.566) hg_http_server: Server Started on port 80
I (00:00:01.574) hg_settings: hg settings is corrupted. mac 
I (00:00:01.744) phy_init: phy_version 4791,2c4672b,Dec 20 2023,16:06:06
I (2427) wifi:mode : sta (78:21:84:66:5c:c0) + softAP (78:21:84:66:5c:c1)
I (2427) wifi:enable tsf
I (2437) wifi:Total power save buffer number: 16
I (2437) wifi:Init max length of beacon: 752/752
I (2437) wifi:Init max length of beacon: 752/752
I (00:00:01.829) hg_app: WIFI_EVENT_STA_START
I (00:00:01.833) esp_netif_lwip: DHCP server started on interface WIFI_AP_DEF with IP: 192.168.4.1
I (00:00:01.840) hg_app: WIFI_EVENT_AP_START
I (00:00:01.865) ksz80xx: auto detected phy KSZ8051/81/91
I (00:00:01.867) esp_eth.netif.netif_glue: 78:21:84:66:5c:c3
I (00:00:01.868) esp_eth.netif.netif_glue: ethernet attached to netif
I (00:00:05.866) hg_app: Ethernet Started
I (00:00:05.867) main_task: Returned from app_main()
I (00:00:07.867) hg_app: HG_APP_MSG_ID_RESET_TASK_WDT
I (00:00:09.867) hg_app: HG_APP_MSG_ID_RESET_TASK_WDT
I (00:00:11.867) hg_app: HG_APP_MSG_ID_RESET_TASK_WDT
I (00:00:13.867) hg_app: HG_APP_MSG_ID_RESET_TASK_WDT
```

<details><summary><b>Formato da mensagem de saúde</b></summary>

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
    ESP_RST_INT_WDT,    ///< Reinicialização (software ou hardware) devido ao watchdog de interrupção
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

</details><p>

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

</details><p>
