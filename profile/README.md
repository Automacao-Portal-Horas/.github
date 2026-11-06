# Robô do Ponto

## Objetivo

Reduzir o trabalho manual da revisão semanal do ponto, reunindo dados, saldos, ações sugeridas e exceções em um painel. A automação apoia a responsável, mas não substitui a revisão humana.

## Como funcionará

1. **Importar e validar** a planilha de colaboradores.
2. **Acessar o Portal de Horas** com Playwright e atualizar/calcular os registros.
3. **Analisar os resultados** e preparar um plano de ação por colaborador.
4. **Revisar e aprovar** as ações no painel.
5. **Executar apenas as ações aprovadas**, verificar o resultado e gerar relatório e auditoria.

## Regras de negócio principais

- A análise é feita **às sextas-feiras**.
- A tolerância semanal informada é de **30 minutos**; saldos acima dela devem ser sinalizados.
- A compensação foi descrita como ocorrendo **de segunda a quarta-feira**.
- Registros incompletos, falhas, divergências e situações excepcionais devem ser encaminhados para **revisão manual**.
- Para converter LNA, usar **650 — Crédito Banco Horas**. O evento **550 — Hora Extra é proibido**.
- Nenhuma alteração no portal deve ocorrer sem **aprovação explícita**.

## Tecnologias em avaliação para a versão Python

- **Playwright:** automação do portal pelo navegador.
- **SQLite:** armazenamento local das execuções e da auditoria.
- **openpyxl:** leitura da planilha e geração de relatórios.
- **pytest:** testes das regras e dos fluxos.
- **Interface:** decisão pendente entre **NiceGUI**, **Reflex** ou **PyQt/PySide**.

## Status da decisão técnica

O documento de concepção original propõe **Node.js, React e Fastify**. A alternativa Python é uma **mudança em avaliação**, ainda não uma decisão final.

- **NiceGUI** pode simplificar a criação de um painel local escrito em Python.
- **Reflex** pode se aproximar mais do conhecimento React do time.
- **PyQt/PySide** pode ser considerado se for necessária uma aplicação Windows nativa.

## Próximas validações

- Compatibilidade do Playwright com o Edge corporativo, SSO/MFA e políticas de acesso.
- Regras finais de tolerância, compensação e notificações.
- Permissões para operar com perfil delegado e disponibilidade de ambiente de teste.
- Escolha da interface e estratégia de instalação e distribuição.
