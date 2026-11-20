# AutoBIM downloads

Cada produto tem uma pasta com o texto da versão. O `.exe` não entra no git: ele vai na **Release** com a tag daquela versão. É o mesmo desenho do winget e das releases do GitHub (VS Code, por exemplo): a pasta descreve, o binário fica no anexo da release. Colocar o `.exe` na pasta incha o histórico para sempre.

| Pasta | Produto |
|---|---|
| [GEO_3D](GEO_3D/README.md) | Geometria rodoviária, Civil 3D 2023–2027 |
| [DRE_3D](DRE_3D/README.md) | Drenagem 3D, Civil 3D 2023–2027 |
| [DRE_CAL](DRE_CAL/README.md) | Pré-dimensionamento de drenagem, Civil 3D 2026 |

Tag: `<PRODUTO>-vX.Y.Z`. Arquivo: `AutoBIM-<PRODUTO>_Instalador_X.Y.Z.exe`.

URL para a plataforma:

`https://github.com/AutoBIM-Solutions/autobim-downloads/releases/download/<tag>/<arquivo>.exe`
