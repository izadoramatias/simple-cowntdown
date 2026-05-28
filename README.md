# countdown-page

Página web simples e delicada para exibir uma contagem regressiva com:

- Título **"Liberado em Breve"**
- Subtítulo **"preparada?"**
- Visual em tons de rosa
- Corações flutuantes sutis

A data da contagem é configurada **somente** no arquivo `config.json`.

## Visão geral

- Layout suave em tons de rosa
- Decorações meigas com corações flutuantes
- Relógio no formato `dias:horas:minutos:segundos` (`00:00:00:00` inicialmente)
- Sem painel de configuração na interface
- Leitura da data diretamente de `config.json`
- Responsivo para celular

## Como configurar a data

1. Abra o arquivo `config.json`.
2. Preencha o campo `countdown.targetDate` com uma data válida.
3. Salve o arquivo.
4. Recarregue a página `index.html`.

Configuração inicial (sem data definida):

```json
{
  "countdown": {
    "targetDate": null,
    "timezone": "America/Sao_Paulo",
    "enabled": true
  }
}
```

## Formato da data (ISO 8601) no `config.json`

Use o formato:

```txt
AAAA-MM-DDTHH:mm:ss
```

Exemplos práticos:

- `2024-12-31T23:59:59`
- `2025-01-15T12:00:00`
- `2026-12-31T23:59:59-03:00` (com fuso horário)

### Explicação simples de cada parte

Formato completo: `AAAA-MM-DDTHH:mm:ss`

- `AAAA` = ano (ex.: `2025`)
- `MM` = mês (01 a 12)
- `DD` = dia (01 a 31)
- `T` = separador entre data e hora
- `HH` = hora (00 a 23)
- `mm` = minuto (00 a 59)
- `ss` = segundo (00 a 59)

Exemplo detalhado: `2025-01-15T12:00:00`

- `2025` = ano
- `01` = janeiro
- `15` = dia 15
- `12` = meio-dia
- `00` = zero minutos
- `00` = zero segundos

### Como fica no JSON

```json
{
  "countdown": {
    "targetDate": "2025-01-15T12:00:00",
    "timezone": "America/Sao_Paulo",
    "enabled": true
  }
}
```

### Observações importantes

- `targetDate: null` significa que nenhuma data foi configurada.
- Se a data estiver inválida, a contagem não inicia.
- Se `enabled` for `false`, o relógio permanece zerado.

## Deploy no GitHub Pages

1. Crie um repositório no GitHub (ex.: `countdown-page`).
2. Envie os arquivos da pasta para o repositório:
   - `index.html`
   - `config.json`
   - `README.md`
3. No GitHub, vá em **Settings > Pages**.
4. Em **Build and deployment**:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` (ou `master`) e pasta `/ (root)`
5. Salve e aguarde a publicação.
6. A URL ficará no formato:
   - `https://SEU-USUARIO.github.io/SEU-REPOSITORIO/`

## Estrutura de arquivos

```txt
countdown-page/
├── index.html
├── config.json
└── README.md
```
