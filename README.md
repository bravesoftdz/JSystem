# JSystem
Acessar porta serial a partir do JavaScript, usado principalmente para comunicação com impressoras de nota fiscal.

## Exemplo de Uso
```
<html>
  <head>
    <title>Teste do JSystem</title>
    <meta charset="UTF-8"/>
  <script type="text/javascript">
    var ser;
    function plugin0()  {
      return document.getElementById('jsystem');
    }
    plugin = plugin0;

    function recv(bytes, size)  {
      for(var i=0;i<size;++i) {
        ser.send(bytes[i]);
      }
    }

    function enviar(){
      ser = plugin().Serial;// pega porta serial
      ser.open("/dev/ttys001");// abre a conexão com a impressora (OBS: no windows são as portas COM)
      ser.set_option(115200,0,8,0,0);// adiciona opções da porta
      ser.recv_callback(recv); // resposta
      ser.sendmulti("Hello World");
    }

    function validar() {
      if(!plugin().valid){
        alert("Plugin JSystem não foi encontrado!");
        window.open("https://github.com/pedrosoares/JSystem");
      }
    }
  </script>
  </head>
  <body onload="validar()">
    <object id="jsystem" type="application/x-jsystem" width="0px" height="0px" ></object>
    <h1>Teste do JSystem</h1>
    <input type="submit" value="Imprimir Teste" onclick='enviar();'>
  </body>
</html>
```

## Instalação

### MAC Os
Copie o arquivo JSystem.plugin para "/Library/Internet Plug-Ins/". Pode-se usar o seguinte comando: 
```
sudo JSystem.plugin /Library/Internet Plug-Ins/
```
### Linux
Copie o arquivo JSystem.so para "~/.mozilla/plugins/". Pode-se usar o seguinte comando:
```
sudo cp JSystem.so ~/.mozilla/plugins/
```

### Windows
Abra o cmd e vá até a página do plugin, execute o seguinte comando:
```
regsvr32 npJSystem.dll
```
Não esqueça de reiniciar o computador.
