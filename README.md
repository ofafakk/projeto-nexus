# ☁️ NexusCloud Solutions | DevOps & SRE Lab

> **Status do Projeto:** 🚀 Em Produção (Simulado)

Este repositório demonstra a implementação de uma esteira completa de **DevOps (CI/CD)** e orquestração de infraestrutura moderna. O objetivo foi simular um ambiente corporativo onde a entrega de valor é contínua, automatizada e segura.

## 🛠️ Stack Tecnológico

O projeto foi construído integrando as seguintes tecnologias:

* **Containerização:** Docker (Imagem Otimizada Nginx Alpine)
* **Orquestração:** Kubernetes (Deployments, Services, LoadBalancer)
* **CI/CD:** GitHub Actions (Automação End-to-End)
* **Cloud/Registry:** Docker Hub
* **Scripting:** Bash & YAML

## ⚙️ Arquitetura da Solução

O pipeline foi desenhado para eliminar intervenção manual (Toil), seguindo as práticas de SRE:

1.  **Code:** O desenvolvedor realiza o `push` na branch `main`.
2.  **CI (Integração Contínua):**
    * O GitHub Actions detecta a mudança.
    * Injeta dinamicamente o **Hash do Commit (SHA)** no código HTML para rastreabilidade de versão.
    * Constrói a imagem Docker.
3.  **CD (Entrega Contínua):**
    * Autentica de forma segura no Docker Hub (via Secrets).
    * Realiza o push da nova imagem versionada.
4.  **Deploy (Infrastructure):**
    * Os manifestos do Kubernetes (`deployment.yaml`) garantem a alta disponibilidade da aplicação (Self-Healing).

## 📂 Estrutura do Projeto

```text
/
├── .github/workflows  # Definição do Pipeline CI/CD
├── k8s/               # Manifestos de Infraestrutura (IaC)
├── Dockerfile         # Receita da Imagem do Container
└── index.html         # Aplicação Frontend