# Vila+Saúde — protótipo acadêmico

Sistema demonstrativo de agendamento de consultas e fila virtual da UBAS de Vila Nova do Piauí, inspirado no projeto do Grupo 03 (UESPI/UAPI).

**ATENÇÃO:** Protótipo acadêmico, não homologado pela UBAS. Não insira dados reais de pacientes.

## Instalação
Baixe o pacote `Vila_Mais_Saude_Projeto_Funcional.zip` fornecido na conversa e envie o conteúdo da pasta `vila-mais-saude/` para a raiz deste repositório.

Requer Python 3.9+. No terminal:

```bash
export ADMIN_EMAIL="equipe@exemplo.test"
export ADMIN_PASSWORD="EscolhaUmaSenhaForte!"
python server.py
```

Abra http://127.0.0.1:8080. No Windows PowerShell, use `$env:ADMIN_EMAIL="..."` e `$env:ADMIN_PASSWORD="..."` antes de `py server.py`.

O banco SQLite é criado localmente e ignorado no GitHub. GitHub Pages não executa o backend Python/SQLite.

## Avisos
Horários fictícios. Fila consultada periodicamente, avisos apenas internos. Para colocar em uso real são necessários segurança, proteção de dados pessoais, regras oficiais, backups, HTTPS, avaliação LGPD e autorização da gestão.
