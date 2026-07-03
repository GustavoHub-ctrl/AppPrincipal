# Requisitos — Task Manager DevSecOps

## Requisitos Funcionais
- **RF01 — Autenticar usuário:** login com credenciais e criação de sessão.
- **RF02 — Criar tarefa:** usuário autenticado registra nova tarefa.
- **RF03 — Editar tarefa:** atualização de título, descrição ou status.
- **RF04 — Excluir tarefa:** remoção controlada por usuário autenticado.
- **RF05 — Visualizar tarefas:** listagem das tarefas do usuário.
- **RF06 — Pesquisar tarefas:** filtro por palavra-chave.

## Requisitos Não Funcionais
- **RNF01 — Segurança:** autenticação, sessão e validação de entrada.
- **RNF02 — Auditoria:** registro de log para autenticação e operações.
- **RNF03 — Operação:** execução reprodutível com Docker e Docker Compose.
- **RNF04 — Manutenibilidade:** estrutura clara, dependências controladas e README.
- **RNF05 — Disponibilidade:** endpoint de saúde (/health) e validação do container.
- **RNF06 — Rastreabilidade:** uso de Git, commits claros e evidências técnicas.

## Casos de Uso
1. **UC01 — Login:** usuário informa credenciais e recebe acesso ou negação.
2. **UC02 — Criar tarefa:** usuário autenticado cadastra uma tarefa.
3. **UC03 — Editar tarefa:** usuário autenticado altera uma tarefa existente.
4. **UC04 — Excluir tarefa:** usuário autenticado remove uma tarefa.
5. **UC05 — Pesquisar tarefa:** usuário filtra tarefas por palavra-chave.
6. **UC06 — Gerar log:** sistema registra ações e autenticações automaticamente.

## Ameaças e Mitigações
| Ameaça | Mitigação |
|---|---|
| Acesso sem login | Sessão obrigatória para qualquer ação |
| Brute force (tentativas repetidas de login) | Registro de logs e alerta futuro |
| Senha exposta | Uso de hash de senha e variáveis de ambiente seguras |
| Dependência vulnerável | Análise SCA (Software Composition Analysis) nas próximas aulas |
| Código inseguro | Análise SAST (Static Application Security Testing) com Bandit nas próximas aulas |
| Falta de rastreabilidade | Geração de logs via syslog ou mecanismo equivalente |

## Evidências Esperadas
- Tela de login funcionando.
- CRUD de tarefas funcionando (criar, editar, excluir, visualizar, pesquisar).
- Logs de autenticação (sucesso e falha) e de operações em tarefas.
- Container Docker em execução (`docker ps`).
- Aplicação respondendo em `/health`.
- Comandos de execução documentados no README.md.
- Histórico de commits organizado no Git (`git log --oneline`).