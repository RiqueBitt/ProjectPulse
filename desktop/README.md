# Integração Electron — áudio da tela

`screenAudio.js` (Electron ≥ 37, testado no 44):

- **Windows 10 22H2+ / 11:** responde ao `getDisplayMedia` com `loopbackWithoutChrome` — o som do PC vai junto, **sem** as vozes da chamada (sem eco para quem assiste).
- **Linux (PipeWire):** usa [`@vencord/venmic`](https://github.com/Vencord/venmic) (MPL-2.0, sem modificações) para criar o microfone virtual `vencord-screen-share` com o som de todos os apps, menos o do próprio app.
- Variável `PROJECT_CLUB_SCREEN_AUDIO=loopback|nochrome|off` força o modo.

O passo a passo do lado da página está em [`../docs/api.md`](../docs/api.md), seção "Desktop: áudio da tela".

## Apertar-pra-falar global

`globalPtt.js` usa [`uiohook-napi`](https://github.com/SnosMe/uiohook-napi) (MIT; inclui libuiohook LGPL, sem modificação) para ouvir a tecla do PTT com o app sem foco. Carrega só durante a chamada com PTT ligado; sem o binário, o PTT segue funcionando com a janela em foco.
