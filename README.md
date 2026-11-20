# AutoBIM downloads

Repositório só de **GitHub Releases**. O git não guarda `.exe` nem `.dll`.

Cada produto tem uma release por versão. A tag diz qual produto é; o arquivo diz a versão.

| Produto | O que o instalador traz | Tag | Arquivo |
|---|---|---|---|
| [AutoBIM-GEO_3D](https://github.com/AutoBIM-Solutions/AutoBIM-GEO_3D) | Plugin de geometria rodoviária (bundle `AutoBIM.Geo3D`) para Civil 3D 2023–2027 | `GEO_3D-vX.Y.Z` | `AutoBIM-GEO_3D_Instalador_X.Y.Z.exe` |
| [AutoBIM-DRE_3D](https://github.com/AutoBIM-Solutions/AutoBIM-DRE_3D) | Plugin de drenagem 3D (`DrenagemQTD`) para Civil 3D 2023–2027 | `DRE_3D-vX.Y.Z` | `AutoBIM-DRE_3D_Instalador_X.Y.Z.exe` |
| [AutoBIM-DRE_CAL](https://github.com/AutoBIM-Solutions/AutoBIM-DRE_CAL) | Pré-dimensionamento de drenagem para Civil 3D 2026 | `DRE_CAL-vX.Y.Z` | `AutoBIM-DRE_CAL_Instalador_X.Y.Z.exe` |

O `.exe` é gerado no repositório do produto com `deploy/InstaladorGUI/gerar_instalador.ps1`, depois que o bundle foi compilado numa máquina com Civil 3D. A publicação acontece depois do commit da versão, não a cada commit.

URL estável para a plataforma (`installer_url`):

`https://github.com/AutoBIM-Solutions/autobim-downloads/releases/download/<tag>/<arquivo>.exe`

As notas da release devem dizer: nome do produto, o que instala no Civil 3D, anos suportados, versão e o commit de origem.
