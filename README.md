# DTunnel - Documentação da API

Esta é a documentação da API JavaScript para uso dos hooks nativos fornecidos pelo sistema DTunnel, disponível via `window.Dt*`. Abaixo estão listados todos os métodos/interfaces disponíveis, agrupados por categoria, com descrições, parâmetros, retornos e exemplos de uso.

> **Importante:** Todos os métodos devem ser chamados a partir de JavaScript. Certifique-se de que o contexto `window.Dt*` está disponível antes de utilizá-los.

---

## Índice

- [Configuração](#configuração)
- [Ambiente de Rede](#ambiente-de-rede)
- [VPN](#vpn)
- [Interface Nativa](#interface-nativa)
- [Informações de Dispositivo](#informações-de-dispositivo)
- [Usuário e Autenticação](#usuário-e-autenticação)
- [Logs](#logs)
- [Tradução](#tradução)
- [Notificações](#notificações)
- [Web Views e URLs Externas](#web-views-e-urls-externas)
- [HotSpot](#hotspot)
- [Modo Avião](#modo-avião)
- [Outros](#outros)

---

## Configuração

### `window.DtGetConfigs.execute()`

Retorna um _array_ de categorias com itens de configuração.

```js
const configs = window.DtGetConfigs.execute();
// Exemplo de retorno:
// [ { id:1, name:'Categoria', sorter:1, color:'#FFF', items:[ {...} ] } ]
```

### `window.DtSetConfig.execute(id: number): void`

Define o item de configuração ativo pelo seu `id`.

```js
window.DtSetConfig.execute(1000);
```

### `window.DtGetDefaultConfig.execute(): Config | undefined`

Retorna o item selecionado ou `undefined` se nenhum estiver ativo.

```js
const current = window.DtGetDefaultConfig.execute();
if (current) console.log(current.name);
```

---

## Ambiente de Rede

### `window.DtGetLocalIP.execute(): string`

Retorna o IP local (e.g., `'192.168.1.100'`).

### `window.DtGetNetworkName.execute(): string`

Nome da rede atual (e.g., `'WIFI'`, `'MOBILE'`).

### `window.DtGetPingResult.execute(): number`

Tempo de ping em milissegundos.

### `window.DtGetNetworkData.execute(): { type_name:'MOBILE'|'WIFI', type:number, extra_info:string, detailed_state:string, reason?:string }`

Retorna objeto com detalhes do estado de rede.

---

## VPN

### `window.DtGetVpnState.execute(): 'CONNECTED'|'DISCONNECTED'|'CONNECTING'|'STOPPING'|'NO_NETWORK'|'AUTH'|'AUTH_FAILED'`

Estado atual da VPN.

### `window.DtExecuteVpnStart.execute(): void`

Inicia a conexão VPN.

### `window.DtExecuteVpnStop.execute(): void`

Para a conexão VPN.

---

## Interface Nativa

### `window.DtExecuteDialogConfig.execute(): void`

Abre diálogo de configurações nativo.

### `window.DtShowLoggerDialog.execute(): void`

Abre diálogo de logs de conexão.

### `window.DtShowMenuDialog.execute(): void`

Abre menu de ferramentas nativas.

---

## Informações de Dispositivo

### `window.DtGetStatusBarHeight.execute(): number`

Altura da barra de status (pixels).

### `window.DtGetNavigationBarHeight.execute(): number`

Altura da barra de navegação (pixels).

### `window.DtGetDeviceID.execute(): string`

ID único do dispositivo.

### `window.DtAppVersion.execute(): string`

Versão atual do aplicativo.

---

## Usuário e Autenticação

#### `window.DtUsername.get(): string` / `DtUsername.set(username: string): void`

Obtem/define nome de usuário.

#### `window.DtPassword.get(): string` / `DtPassword.set(password: string): void`

Obtem/define senha.

#### `window.DtUuid.get(): string` / `DtUuid.set(uuid: string): void`

Obtem/define UUID (v2ray).

---

## Logs

### `window.DtGetLogs.execute(): string`

Retorna JSON com todos os logs.

### `window.DtClearLogs.execute(): void`

Limpa todos os logs.

---

## Tradução

### `window.DtTranslateText.execute(label: string): string`

Retorna texto traduzido para a chave.

```js
const label = window.DtTranslateText.execute("LBL_START");
```

---

## Notificações

### `window.DtSendNotification.execute(title: string, message: string, imageUrl: string): void`

Envia notificação local.

---

## Web Views e URLs Externas

### `window.DtStartWebViewActivity.execute(url: string): void`

Abre página interna via WebView.

### `window.DtOpenExternalUrl.execute(url: string): void`

Abre URL no navegador padrão.

---

## HotSpot

### `window.DtGetStatusHotSpotService.execute(): 'STOPPED'|'RUNNING'`

Status do serviço HotSpot.

### `window.DtStartHotSpotService.execute(): void`

Inicia HotSpot.

### `window.DtStopHotSpotService.execute(): void`

Para HotSpot.

### `window.DtGetNetworkDownloadBytes.execute(): number`

Total de bytes baixados.

### `window.DtGetNetworkUploadBytes.execute(): number`

Total de bytes enviados.

---

## Modo Avião

### `window.DtAirplaneState.execute(): 'ACTIVE'|'INACTIVE'`

Estado do modo avião.

### `window.DtAirplaneActivate.execute(): void`

Ativa modo avião.

### `window.DtAirplaneDeactivate.execute(): void`

Desativa modo avião.

---

## Outros

### `window.DtGetLocalConfigVersion.execute(): string`

Versão da configuração local (e.g., `'1.2.3'`).

### `window.DtStartAppUpdate.execute(): void`

Inicia processo de atualização da aplicação.

### `window.DtStartCheckUser.execute(): void`

Abre diálogo de checagem de usuário.

### `window.DtAppIsCurrentAssistant.execute(): boolean`

Verifica se app é assistente de voz padrão.

### `window.DtGoToVoiceInputSettings.execute(): void`

Abre configurações de assistente de voz.

---

_Esta documentação será atualizada conforme novos métodos forem adicionados._
