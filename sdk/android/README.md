# SDK Android (referência)

`MediasoupEngine.kt` é o motor de voz nativo usado no app Android do Project Club, sobre
[`libmediasoup-android`](https://github.com/crow-misia/libmediasoup-android) 0.21. `CallAudio.kt`
cuida do roteamento (fone, alto-falante, Bluetooth) e do foco de áudio (muta durante ligações).

Ele espera a mesma sinalização do `media-server/` (WebSocket + JWT). Para usar no seu app,
troque o pacote `com.projectclub.android.voice` e ligue os callbacks na sua camada de UI.

Recursos: reconexão com ICE restart, `NetworkCallback` (troca de rede), mic publicado já pausado
quando mudo, Opus 64k com FEC/DTX/NACK, tela em 1080p30 com rotação, permissões vindas do servidor.
Ainda não tem: áudio interno na transmissão de tela (exige recompilar o libmediasoup).
