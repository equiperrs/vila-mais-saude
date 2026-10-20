# Vila+Saúde — demonstração funcional

Projeto acadêmico do Grupo 03 Vila Nova, Tecnologia em Sistemas para Internet (UESPI/UAPI), conforme **Grupo 03 - Vila Nova.docx**. Apresenta cadastro, autenticação, agenda de consultas, fila virtual, avisos internos e painel da equipe da UBAS.

**AVISO: PROTÓTIPO ACADÊMICO. NÃO CONECTADO À UBAS. NÃO USAR COM DADOS REAIS DE PACIENTES.** Não é sistema de produção ou plataforma médica homologada. Os horários são fictícios, e a lista de atendimentos é demonstrativa. A fila é atualizada pelo painel com consultas periódicas de 12 segundos (não é push real-time). Notificações são internas e vistas quando o app está aberto (não são push, SMS ou WhatsApp). A estimativa de espera é um número ilustrativo, não uma previsão clínica.

## Executar localmente

Requer Python 3.9 ou superior. Não possui dependências externas.

```bash
export ADMIN_EMAIL="equipe@exemplo.test"
export ADMIN_PASSWORD="TroqueEstaSenhaForte123!"
python server.py
```

Abra http://127.0.0.1:8080. No Windows PowerShell, substitua `export VAR=...` por `$env:VAR="..."` e use `py server.py`.

- **Paciente:** faça um cadastro demonstrativo com CPF válido *fictício* e e-mail fictício. Selecione vaga em **Agendar**.
- **Equipe:** entre com e-mail e senha configurados via variáveis de ambiente. Abra **Painel da UBAS** para chamar/concluir atendimento ou marcar ausência.
- Os dados são mantidos no arquivo local `vila.sqlite3`, criado automaticamente e **ignorado pelo Git**.
- Para limpar a demonstração, pare o servidor e exclua `vila.sqlite3`.

## Estrutura

- `server.py`: servidor HTTP, API, autenticação com cookie, SQLite, fila e notificações.
- `static/index.html`: telas do paciente e equipe.
- `static/style.css`: visual responsivo.
- `static/app.js`: interação das telas.
- `tests/test_api.py`: teste de fluxo local.
- `.gitignore`: evita publicar banco, segredos e caches.

## Antes de qualquer produção

Necessário: aprovação da gestão da UBAS, avaliação de segurança e LGPD, autorização e base legal para tratamento de dados pessoais de saúde; HTTPS obrigatório, configuração `COOKIE_SECURE=1`, monitoramento, rate limiting persistente, rotinas de backup seguro e recuperação, autenticação/autorização reforçadas, reset de senha, proteção CSRF robusta, auditoria de acesso, política de retenção, consentimentos/avisos adequados, verificação de identidade, regras oficiais de vagas e prioridades, ajustes para acessibilidade e testes de carga. Mudar `HOST=0.0.0.0` **não torna este protótipo apto para produção**.

## Publicação

Suba estes arquivos em um **novo repositório privado** do GitHub. O GitHub Pages não executa o backend Python/SQLite. Para demonstrar online de forma protegida, configure um serviço de aplicação com Python e armazenamento persistente ou adapte para um banco gerenciado. Não publique em acesso aberto enquanto não forem implementados os requisitos de segurança e proteção de dados.

## Origem do escopo

Documento `Grupo 03 - Vila Nova.docx`: páginas 3–5 (objetivo e escopo), páginas 7–8 (RF/RNF), páginas 10–15 (modelagem, banco e protótipo). O demonstrador implementa os fluxos centrais, sem consultas clínicas, prontuários, diagnóstico, prescrição, pagamentos ou integração com sistemas públicos.
