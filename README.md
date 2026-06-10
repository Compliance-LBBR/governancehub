# LBBR Governance Hub

Portal Corporativo de Compliance, PLD/FTP, Integridade e Governança do Grupo LBBR.

Arquivo único, HTML, CSS e JavaScript puro. Pronto para GitHub Pages.

## Publicar no GitHub Pages

1. Envie todo o conteúdo desta pasta para a raiz do repositório.
2. Settings, Pages, Source: branch principal, pasta `/ (root)`.
3. O portal ficará disponível em `https://<usuario>.github.io/<repositorio>/`.

Abrir o `index.html` diretamente no navegador tambem funciona, sem servidor.

## Estrutura

```
index.html        Portal completo (estilo, conteudo e logica em um unico arquivo)
assets/docs/      PDFs dos documentos (incluir os arquivos aqui)
assets/images/    Imagens e logotipos
README.md         Este arquivo
```

## Incluir ou atualizar documentos

Toda a base de conteúdo fica dentro do `index.html`, no objeto `LBBR_DATA` (procure por `const LBBR_DATA`). Para adicionar um documento, inclua um objeto no array `documentos`:

```js
{
  id: "POL-XXXX-001",
  titulo: "Nome do documento",
  codigo: "POL-XXXX-001",
  area: "compliance",            // compliance | pldftp | integridade
  tipo: "Politica",
  versao: "1.0",
  status: "vigente",             // vigente | em-revisao | revogado | substituido
  dataAprovacao: "2026-00-00",
  aprovador: "Diretoria de Compliance",
  proximaRevisao: "2027-00-00",
  resumo: "Resumo executivo.",
  conteudo: [ { titulo: "Secao", texto: "..." } ],
  historico: [ { versao: "1.0", data: "2026-00-00", responsavel: "Diretoria de Compliance", descricao: "Criacao" } ],
  relacionados: ["OUTRO-ID"]
}
```

O PDF correspondente deve ser salvo em `assets/docs/POL-XXXX-001.pdf`.

Comunicados, treinamentos, formularios, marco regulatorio e FAQ seguem o mesmo padrao, cada um em seu array dentro de `LBBR_DATA`.

Diretoria de Compliance, Grupo LBBR.
