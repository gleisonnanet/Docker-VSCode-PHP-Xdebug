# Configurando Xdebug em servidor remoto

![Fluxo](fluxo.gif)

# Configure o  Xdebug
#### <span style="color:red">Atenção o  xdebug.remote_port é a Porta do config vscode </span>.


    zend_extension=xdebug.so
    xdebug.remote_enable=on
    xdebug.remote_handler=dbgp
    xdebug.remote_port=9000
    xdebug.remote_autostart=on
    xdebug.remote_connect_back=on
    xdebug.idekey=docker
    xdebug.remote_log=/var/log/xdebug.log
    xdebug.default_enable=on



# vs code 
#### <span style="color:red"> o arquivo .vscode/launch.json </span>.
 
#### <span style="color:red"> Atenção para o mapeamento de arquivos </span>.

"pathMappings": {
                    "servidor remoto": "pasta local de sesenvolvimento"
                }

    {
        "version": "0.2.0",
        "configurations": [
            {
                "name": "Listen for XDebug",
                "type": "php",
                "request": "launch",
                "port": 9000,
                "log" : true,
                "stopOnEntry": true,
                "pathMappings": {
                    "/var/www/html": "/home/gleison/Workspace/TemplateMagento/src"
                }
            },
            {
                "name": "Launch currently open script",
                "type": "php",
                "request": "launch",
                "program": "${file}",
                "cwd": "${fileDirname}",
                "port": 9000
            }
        ]
    }

