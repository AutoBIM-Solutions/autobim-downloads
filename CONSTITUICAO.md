# Constituição AutoBIM — plugins desktop

Vale para `AutoBIM-GEO_3D`, `AutoBIM-DRE_3D` e `AutoBIM-DRE_CAL`. A IA lê este arquivo antes de commitar.

## Versão

A versão de registro é o atributo `AppVersion` em `deploy/**/PackageContents.xml`.

No mesmo commit que muda essa versão, a IA atualiza o `<Version>` de `deploy/InstaladorGUI/*.csproj` para o mesmo número.

## Instalador (obrigatório no commit de versão)

Um commit que muda `AppVersion` só está completo quando o `.exe` correspondente existe na Release de `AutoBIM-Solutions/autobim-downloads`.

1. Gerar o instalador com `deploy/InstaladorGUI/gerar_instalador.ps1`. Esse script não abre o Civil 3D: ele zipa o bundle já compilado (a pasta `.bundle` com as DLLs) e faz `dotnet build` do projeto WinForms em .NET Framework 4.8. Precisa do .NET SDK e das referências do net48.
2. Criar a release. O git desse repositório não recebe o `.exe`.
3. Atualizar o `README.md` da pasta do produto em `autobim-downloads` com a versão, o que o instalador coloca no Civil 3D e o link da release.

| Produto | O que o .exe instala | Tag | Arquivo |
|---|---|---|---|
| GEO_3D | Geometria rodoviária, Civil 3D 2023–2027 | `GEO_3D-vX.Y.Z` | `AutoBIM-GEO_3D_Instalador_X.Y.Z.exe` |
| DRE_3D | Drenagem 3D (`DrenagemQTD`), Civil 3D 2023–2027 | `DRE_3D-vX.Y.Z` | `AutoBIM-DRE_3D_Instalador_X.Y.Z.exe` |
| DRE_CAL | Pré-dimensionamento de drenagem, Civil 3D 2026 | `DRE_CAL-vX.Y.Z` | `AutoBIM-DRE_CAL_Instalador_X.Y.Z.exe` |

Notas da release, em português: nome do produto, o que copia para o Civil 3D, anos suportados, versão e o commit de origem.

URL para a plataforma (`installer_url`):

`https://github.com/AutoBIM-Solutions/autobim-downloads/releases/download/<tag>/<arquivo>.exe`

## Quando não der para gerar o .exe

O Civil 3D entra na compilação das DLLs do plugin (`instalar_plugin.ps1` / `compilar_bundle.ps1`). Com o bundle já compilado em mãos, a IA gera e publica o `.exe` sem o Civil 3D.

Se o bundle não tiver as DLLs, ou se faltar o .NET SDK / as referências do net48, a IA para e diz que o instalador não foi publicado. Não escreve no commit, no PR ou na resposta que a release existe.

Commits que não mudam `AppVersion` não geram instalador.
