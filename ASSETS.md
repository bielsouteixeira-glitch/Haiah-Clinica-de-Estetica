# Haiah Clínica Estética & Emagrecimento — Mídias, testes e publicação

Site desenvolvido pela **Moon Creative**. Nesta entrega o site passou a servir todas
as mídias direto do Google Drive da clínica, pelo método indicado pela agência:
**imagens via `drive.google.com/thumbnail?id=…&sz=w1600`** e **vídeos via player
incorporado `drive.google.com/file/d/…/preview`**. As URLs ficam no código
(`src/data.ts`), então funcionam na prévia e em qualquer publicação — sem depender
de arquivos locais.

## ⚠️ Arquivos substituídos no Drive (causa das “fotos trocadas”)

Conferindo imagem por imagem (folha de contato gerada nesta entrega), constatou-se
que **arquivos foram substituídos no Drive mantendo os mesmos links**. Mapa
ATUALIZADO e verificado do conteúdo real:

| ID (Drive) | Conteúdo real HOJE | Onde aparece no site |
|---|---|---|
| `15pZGzS7bhfj9Z5HMI6g8XfS_bG9e_jrU` | Logo “Clínica Haiah” (preto s/ branco) | Cabeçalho, menu, rodapé, favicon (recorte CSS da faixa do logotipo, sem distorcer) |
| `1Mqc1L9mLfHgxIVDNtjMSToa2PFYCcCzW` | Retrato atual da Dra. Sheila | Início (hero) e Equipe |
| `1EmlK_5TpQC5B555i94B1pts_dlKds08q` | **Fachada externa: totem “Haiah” na rua** (não é mais a recepção interna) | Seção A Clínica (“Nossa fachada”) e imagem de compartilhamento |
| `1CykU3mhAqzOFV9sIIN3vuJKv-wsAhaSn` | Antes/depois facial (perfis) | Resultados |
| `1EjMBj9SxUL8z08feVkCtpOJNPyPYYu12` | Antes/depois facial (frente) | Resultados |
| `1KAOQ9B_vRfJZmvbxb5nCJTIYjjpBntfK` | Antes/depois **facial** (perfis c/ faixa Haiah) | Resultados |
| `1DQo6qkG4N5IKl0Sc5K8MdlOukRskfcer` | Antes/depois corporal (cartão 3 painéis) | Resultados |
| `1tOHWxZqDVSqo5VnT07ZVH-9v7tmuet6M` | Antes/depois **corporal** (costas/lateral) | Resultados |
| `1-I0n-O95iiRBGRhJ4Ni-q1N5Woi0LC_R` | Antes/depois harmonização de glúteos | Resultados |
| `128VAVcu-fzrk2rss-2U3K8qvFztq_P_b` | Antes/depois de **endolaser abdominal** | Seção Corpo & tecnologia |

Vídeos (player incorporado do Drive):

| ID (Drive) | Conteúdo | Onde aparece |
|---|---|---|
| `1A_EePbefpIF276qUaNnF1ZiWmzLzNglu` | Dra. Sheila explica caso de preenchimento labial | Seção Preenchimento labial (principal) |
| `1GLkm548YOwOnAlzBKLfQVyt2sJga-A31` | Processo de preenchimento labial | Seção Preenchimento labial |
| `1boPQz1C3nTbU24DXuEVONEwyVThDLTo1` | Cuidado/relaxamento facial | Seção Preenchimento labial |
| `1c3zFLw8v-CIzhgb0h4a7JIRnqTMhsTpP` | HiPRO — cuidado corporal | Seção Corpo & tecnologia |
| `14pmY7fCE2pMU7i1SlFBA5GwrNTmcjMO8` | Detox corporal | Seção Corpo & tecnologia |
| `1kIihrPkt4mBJoE8d61fBmdUDkEKA6grO` | Antes/depois de preenchimento labial | Seção Resultados |

**Atenção:** se algum arquivo for substituído de novo no Drive (mesmo link), o site
passa a exibir o arquivo novo automaticamente. Para manter foto/legenda sempre em
sincronia, avise a agência quando trocar arquivos — ou suba como arquivo novo e
passe o link novo.

## Testes executados nesta entrega (reais)

- **10/10 imagens**: thumbnail respondeu **HTTP 200 · image/jpeg** (teste individual
  por ID, a partir do código final). Conteúdo de cada uma conferido visualmente em
  folha de contato rotulada.
- **6/6 vídeos**: página `/preview` respondeu **HTTP 200** com a página completa do
  player do Drive (~128 KB cada). A reprodução dentro do navegador não é executável
  neste ambiente — validar o play na primeira abertura do site publicado.
- Build de produção sem erros; **0 imports de arquivos locais**; página final com
  320 KB servida localmente com HTTP 200. Favicon (thumbnail w256): 200.

## Publicação

Como as mídias vêm do Drive, o pacote é só o site: **`haiah-site-producao.zip`**
(contém `index.html`) ou o conteúdo de `dist/`. Pré-requisito: os arquivos do Drive
precisam permanecer compartilhados como **“qualquer pessoa com o link pode ver”** —
é essa permissão que permite ao site exibir as fotos e os vídeos.
