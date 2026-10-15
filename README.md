# ORBIT: atualizações

Este repositório guarda só os pacotes de instalação e atualização do ORBIT. O código-fonte fica em outro repositório, que é privado.

## Instalar numa máquina nova

1. Baixe o instalador: [instalador/ORBIT-Setup.exe](instalador/ORBIT-Setup.exe). Na página do arquivo, clique em **Download raw**.
2. Rode o instalador. Se aparecer "O Windows protegeu o computador", clique em **Mais informações** e depois em **Executar assim mesmo**.
3. Depois disso, o ORBIT se atualiza sozinho.

## Como funciona

O atualizador instalado lê [`updates/manifest.json`](updates/manifest.json). Esse arquivo lista três pacotes, cada um com a sua versão:

| Pacote | Conteúdo | Onde instala |
|---|---|---|
| `system` | ORBIT.exe, plugin VST3, atualizador e manual | `%LOCALAPPDATA%\Programs\ORBIT` e `%LOCALAPPDATA%\Programs\Common\VST3` |
| `tones` | timbres oficiais (`.orbit`) | `Documentos\ORBIT\Presets\ORBIT Timbres` |
| `images` | imagens dos equipamentos, em partes de até 80 MB | `Documentos\ORBIT\Images` |

Cada arquivo tem um SHA-256 no manifest. O atualizador só instala o que bater com ele.

Os pacotes são gerados e publicados pelo `installer/build-pack.ps1 -Publish` do repositório do código.
