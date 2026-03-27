# Skill_Curriculo_Ats

# 💼 Placed — Skill para Claude

Skill de integração com a plataforma [Placed](https://placed.exidian.tech) para uso no Claude (claude.ai). Permite que o Claude atue como um assistente completo de carreira — construindo currículos, simulando entrevistas, rastreando candidaturas e muito mais — diretamente na conversa, sem necessidade de servidor MCP.

---

## ✨ O que esta skill faz

| Funcionalidade | Descrição |
|---|---|
| 📄 **Currículo** | Cria e gerencia currículos com mais de 37 templates profissionais |
| 🎯 **Otimização ATS** | Analisa e otimiza o currículo para sistemas de rastreamento (ATS) |
| 🗂️ **Rastreamento de candidaturas** | Pipeline de candidaturas com analytics |
| 🎤 **Simulação de entrevistas** | Entrevistas técnicas, comportamentais e de system design |
| ⭐ **Método STAR** | Salva e organiza histórias comportamentais no formato STAR |
| ✉️ **Carta de apresentação** | Gera cartas personalizadas para cada vaga |
| 🔗 **LinkedIn** | Sugere headline e seção "Sobre" otimizados |
| 💰 **Faixa salarial** | Pesquisa salários por cargo e região |
| 🏢 **Pesquisa de empresas** | Levanta informações sobre empresas de interesse |

> ⚠️ **Atenção:** Esta skill **não** realiza busca ou listagem de vagas de emprego. Para isso, use LinkedIn, Indeed ou Glassdoor.

---

## 🚀 Como instalar

### 1. Crie uma conta no Placed

Acesse [placed.exidian.tech](https://placed.exidian.tech), crie sua conta e vá em **Settings → API Keys** para gerar sua chave de API.

### 2. Copie o `SKILL.md` para o Claude

Adicione o arquivo `SKILL.md` deste repositório na sua configuração de skills do Claude.

### 3. Configure sua API Key

Na primeira vez que usar, o Claude pedirá sua chave. Ela será salva automaticamente em:

```
~/.config/placed/credentials
```

Ou configure manualmente:

```bash
mkdir -p ~/.config/placed
echo "export PLACED_API_KEY=sua_chave_aqui" > ~/.config/placed/credentials
```

---

## 🛠️ Como funciona

Toda ação é feita via uma única chamada POST à API do Placed:

```bash
curl -s -X POST https://placed.exidian.tech/api/mcp \
  -H "Authorization: Bearer $PLACED_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"<tool_name>","arguments":{}}}'
```

A resposta tem o formato:

```json
{
  "result": {
    "content": [{ "type": "text", "text": "<json_string>" }]
  }
}
```

---

## 📦 Skills disponíveis

| Nome | Função |
|---|---|
| `placed-resume-builder` | Gerenciamento de currículo + 37 templates |
| `placed-interview-coach` | Entrevistas simuladas + coaching STAR |
| `placed-career-tools` | Job tracker, cartas, salários, pesquisa de empresas |
| `placed-resume-optimizer` | Otimização de currículo por descrição de vaga |
| `placed-job-tracker` | Pipeline de candidaturas |

---

## 💬 Exemplos de uso no Claude

Após instalar a skill, você pode pedir ao Claude:

- *"Crie um currículo profissional para desenvolvedor backend"*
- *"Otimize meu currículo para esta descrição de vaga: [cole aqui]"*
- *"Simule uma entrevista técnica de Python comigo"*
- *"Gere uma carta de apresentação para a empresa X"*
- *"Qual a faixa salarial de um Product Manager em São Paulo?"*
- *"Registre que me candidatei para a vaga Y hoje"*

---

## 🔗 Links úteis

- 🌐 Plataforma: [placed.exidian.tech](https://placed.exidian.tech)
- 🔑 API Keys: [placed.exidian.tech/settings/api](https://placed.exidian.tech/settings/api)

---

## 📄 Licença

MIT — sinta-se livre para usar, modificar e compartilhar.
