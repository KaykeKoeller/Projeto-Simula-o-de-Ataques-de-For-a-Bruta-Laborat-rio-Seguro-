# Projeto: Simulação de Ataques de Força Bruta (Laboratório Seguro)

**Idioma:** Português (pt-BR)
**Language:** English

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

> “A maior ameaça à segurança da informação é acreditar que você está seguro.”

---

## Observações finais
Este material é parte de um trabalho educacional realizado exclusivamente em ambiente controlado. Ao publicar qualquer evidência ou relatório, recomenda-se sempre sanitizar dados sensíveis e explicitar o propósito e o escopo do experimento.

---

# Project: Brute-Force Simulation (Secure Lab)

---

## Exercise Summary
In this exercise I applied Offensive Security and Vulnerability Management concepts in an isolated, fully controlled lab environment. The goal was to simulate brute-force and password spraying scenarios for educational purposes, gather sanitized evidence, and evaluate mitigation measures.

### Lab Setup
- **Kali Linux** — attacker machine.  
- **Metasploitable 2** — vulnerable target VM.  
- **Host-Only Network (VirtualBox)** — direct and isolated communication between the VMs.

---

## 1. Service Enumeration
The first step was identifying active services on the target VM. I discovered services such as FTP, SSH, HTTP, SMB, and MySQL, which defined the attack vectors for subsequent evaluations.

This stage highlights the importance of reconnaissance: gathering service information is the foundation of any security audit.

---

## 2. FTP Brute-Force Tests
After identifying a vulnerable FTP service, I performed controlled automated authentication attempts against the `ftp` account. The test confirmed weak credentials and demonstrated how simple passwords can quickly compromise a service.

> Lesson: weak password policies expose entire systems — strong authentication is essential.

---

## 3. SMB Password Spraying
I enumerated user accounts on the SMB server and performed a password spraying exercise (testing common passwords against multiple users). In this specific experiment I **managed to gain access** to one system account, demonstrating the effectiveness of this technique against weak credentials.

**Note:** lack of success in other tests is also valuable information and contributes to a complete security assessment.

---

## 4. SSH and MySQL Tests
Controlled authentication attempts were made against SSH (user `msfadmin`) and MySQL. No compromises were observed in these services, reinforcing that mapping both weaknesses and resilient points is important for a full attack surface assessment.

---

## 5. Evidence Collection and Documentation
All findings were recorded and organized with attention to anonymization and data safety:
- Sanitized files in `/outputs` (no real passwords);
- Technical report in `report.md`;
- Project structure versioned and prepared for GitHub (example repository pattern `username/repo-lab`).

During the process I practiced version control with Git/GitHub (SSH keys, commits, pushes, and Markdown documentation).

---

## 6. Technical and Conceptual Takeaways
- Building isolated labs with VirtualBox Host-Only networks;  
- Using open-source tools for reconnaissance and lab auditing;  
- Workflow: reconnaissance → controlled testing → evidence collection → analysis → mitigation;  
- The importance of ethics and scoped authorization for testing;  
- How to document technical results clearly, safely, and verifiably.

---

## 7. Conclusion
This exercise went beyond a mere attack simulation: it was an exercise in critical thinking, technical writing, and ethical conduct. A security professional must not only find vulnerabilities but also document, mitigate, and communicate risks responsibly.

> "The biggest threat to information security is believing you are secure."

---

## Final Notes
This material is part of an educational project executed exclusively in a controlled environment. When publishing evidence or reports, always sanitize sensitive data and clearly state the experiment’s purpose and scope.
