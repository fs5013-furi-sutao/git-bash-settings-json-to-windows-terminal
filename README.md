# Windows Terminal の settings.json に追記する Git Bash 設定



## GUID を生成する

Powershell で次のコマンドを実行して GUID を生成する。

``` console
[Guid]::NewGuid()
```

`実行結果: `
``` console
Guid
----
00000000-0000-0000-0000-000000000000
```

## 

``` json
{
    "$schema": "https://aka.ms/terminal-profiles-schema",
    "defaultProfile": "{00000000-0000-0000-0000-000000000000}",
    "profiles": {
        "defaults": {},
        "list": [
            {
                "guid": "{00000000-0000-0000-0000-000000000000}",
                "name": "Windows PowerShell",
                "commandline": "powershell.exe",
                "hidden": false
            },
            {
                "guid": "{00000000-0000-0000-0000-000000000000}",
                "name": "コマンド プロンプト",
                "commandline": "cmd.exe",
                "hidden": false
            },
            {
                "guid": "{00000000-0000-0000-0000-000000000000}",
                "name": "Ubuntu-20.04",
                "source": "Windows.Terminal.Wsl"
            },
            {
                "guid": "{00000000-0000-0000-0000-000000000000}",
                "name": "Azure Cloud Shell",
                "source": "Windows.Terminal.Azure"
            }
            // <-- ここの Git Bash の設定を追記する
        ]
    },
    "schemes": []
}
```

ユーザーは以下のパスが含まれる場合は、ユーザーホームのパスを `%USERPROFILE%` で指定すること。

``` json
{
    "acrylicOpacity": 1.0,
    "closeOnExit": "graceful",
    "colorScheme": "Campbell",
    "commandline": "\"C:\\Program Files\\Git\\bin\\bash.exe\" --login -i -l",  // <-- 自分の環境にインストールされている Git の bash.exe のパスを指定する
    "cursorColor": "#FFFFFF",
    "cursorShape": "bar",
    "fontFace": "Consolas",
    "fontSize": 12,
    "guid": "{83d9a4e0-7540-4884-a3a9-d1bb03e9167d}",
    "historySize": 9001,
    "icon": "C:\\Program Files\\Git\\mingw64\\share\\git\\git-for-windows.ico",  // <-- 自分の環境に格納されている git-for-windows.ico のパスを指定する
    "name": "Git Bash",
    "padding": "10, 0, 10, 0",
    "snapOnInput": true,
    "startingDirectory": "%USERPROFILE%"
}
```
