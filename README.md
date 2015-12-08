# JSystem
Acessar porta serial a partir do JavaScript, usado principalmente para comunicação com impressoras de nota fiscal.

## Instalação

###MAC Os
Copie o arquivo JSystem.plugin para "/Library/Internet Plug-Ins/". Pode-se usar o seguinte comando: 
```
sudo JSystem.plugin /Library/Internet Plug-Ins/
```
###Linux
Copie o arquivo JSystem.so para "~/.mozilla/plugins/". Pode-se usar o seguinte comando:
```
sudo cp JSystem.so ~/.mozilla/plugins/
```

###Windows
Abra o cmd e vá até a página do plugin, execute o seguinte comando:
```
regsvr32 npJSystem.dll
```
