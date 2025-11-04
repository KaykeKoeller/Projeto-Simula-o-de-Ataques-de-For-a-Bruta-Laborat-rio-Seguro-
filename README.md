# Projeto: Simulação de Ataques de Força Bruta (Laboratório Seguro)

**Idioma:** Português (pt-BR)

---

## Resumo do exercício prático
Neste desafio apliquei conceitos de Segurança Ofensiva e Gestão de Vulnerabilidades em um laboratório isolado e totalmente controlado por mim. O objetivo foi simular cenários de força-bruta e password spraying de forma educativa, coletando evidências e avaliando medidas de mitigação.

### Ambiente utilizado
- **Kali Linux** — máquina atacante.
- **Metasploitable 2** — máquina vulnerável (alvo).
- **Rede Host-Only (VirtualBox)** — comunicação direta e isolada entre as VMs.

---

## 1. Enumeração de serviços
O primeiro passo foi realizar a descoberta de serviços ativos na VM alvo. Identifiquei portas e serviços como FTP, SSH, HTTP, SMB e MySQL, o que definiu os vetores de avaliação para as etapas seguintes.

Esta fase ressalta a importância do reconhecimento: coletar informações sobre os serviços em execução é a base de qualquer auditoria.

---

## 2. Testes de força-bruta (FTP)
Com o serviço FTP vulnerável identificado, conduzi tentativas automatizadas de autenticação contra a conta `ftp`. O teste evidenciou senhas fracas na account e demonstrou como credenciais simples comprometem rapidamente um serviço.

> Aprendizado: políticas de senha fracas expõem sistemas inteiros — autenticação sólida é fundamental.

---

## 3. Password spraying (SMB)
Realizei enumeração de usuários do servidor SMB e, a partir dessa lista, apliquei um teste de password spraying (tentativas de senhas comuns contra múltiplos usuários). Nesse experimento específico **consegui obter acesso** a uma conta do sistema, demonstrando a eficácia dessa técnica contra credenciais fracas.

**Observação:** a ausência de sucesso em outros testes também é informação relevante para a avaliação de segurança e ajuda a compor um panorama completo do ambiente.

---

## 4. Testes sobre SSH e MySQL
Foram feitos testes controlados de autenticação contra SSH (usuário `msfadmin`) e MySQL. Ambos não resultaram em compromissos, reforçando que mapear tanto falhas quanto pontos seguros contribui para um panorama mais completo da superfície de ataque.

---

## 5. Coleta de evidências e documentação
Registrei e organizei todas as evidências do experimento, priorizando a anonimização e a segurança dos dados:
- Arquivos sanitizados em `/outputs` (sem senhas reais);
- Relatório técnico em `report.md`;
- Estrutura do projeto versionada e organizada para publicação no GitHub (repositório de exemplo no formato `usuario/repo-lab`).

Durante o processo, pratiquei controle de versão com Git/GitHub (chaves SSH, commits, pushes e documentação em Markdown).

---

## 6. Lições técnicas e conceituais
- Montagem de ambientes isolados com VirtualBox e redes Host-Only;
- Uso de ferramentas open-source para reconhecimento e auditoria em laboratório;
- Fluxo de trabalho: reconhecimento → tentativa controlada → coleta de evidências → análise → mitigação;
- Importância da ética e do escopo autorizado para todos os testes;
- Como documentar resultados técnicos de forma clara, segura e verificável.

---

## 7. Conclusão
O desafio foi além de uma simples simulação: serviu como exercício de análise crítica, escrita técnica e postura ética. Entendi que um profissional de segurança deve saber identificar vulnerabilidades, mas igualmente saber documentar, mitigar e comunicar riscos de forma responsável.

> “Segurança não é um estado fixo — é um processo contínuo.”

---

## Observações finais
Este material é parte de um trabalho educacional realizado exclusivamente em ambiente controlado. Ao publicar qualquer evidência ou relatório, recomenda-se sempre sanitizar dados sensíveis e explicitar o propósito e o escopo do experimento.

---
