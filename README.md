# Vila+Saúde — demonstração funcional

Projeto acadêmico do Grupo 03 Vila Nova, Tecnologia em Sistemas para Internet (UESPI/UAPI), conforme **Grupo 03 - Vila Nova.docx**. Apresenta cadastro, autenticação, agenda de consultas, fila virtual, avisos internos e painel da equipe da UBAS.

**AVISO: PROTÓTIPO ACADÊMICO. NÃO CONECTADO À UBAS. NÃO USAR COM DADOS REAIS DE PACIENTES.** Não é sistema de produção ou plataforma médica homologada. Os horários são fictícios, e a lista de atendimentos é demonstrativa. A fila é atualizada pelo painel com consultas periódicas de 12 segundos (não é push real-time). Notificações são internas e vistas quando o app está aberto (não são push, SMS ou WhatsApp). A estimativa de espera é um número ilustrativo, não uma previsão clínica.

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

prontuários, diagnóstico, prescrição, pagamentos ou integração com sistemas públicos.
