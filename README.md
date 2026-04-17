# 🚀 API de Tarefas — Django + AWS EC2

> API REST de gerenciamento de tarefas desenvolvida com Python e Django, hospedada em produção na AWS EC2.

🔗 **[Ver projeto ao vivo](http://15.229.17.21:8000)**  
📄 **[Documentação Swagger](http://15.229.17.21:8000/api/docs/)**

---

## 🏗️ Arquitetura

```
Usuário → EC2 (Ubuntu 22.04) → Gunicorn → Django → SQLite
```

```
┌─────────────┐     ┌──────────────────────┐     ┌─────────────┐
│   Usuário   │────▶│   AWS EC2 t2.micro   │────▶│   Django    │
│  (Browser)  │     │  Ubuntu 22.04 LTS    │     │  + Gunicorn │
└─────────────┘     └──────────────────────┘     └─────────────┘
```

---

## ☁️ Infraestrutura AWS

| Serviço | Função |
|---|---|
| **Amazon EC2** | Servidor virtual t2.micro (Free Tier) |
| **Security Group** | Firewall com regras para SSH, HTTP, HTTPS e porta 8000 |
| **Ubuntu 22.04** | Sistema operacional do servidor |
| **Gunicorn** | Servidor WSGI para produção |
| **Systemd** | Daemon para manter a API rodando automaticamente |

- **Região:** `sa-east-1` (São Paulo)
- **IP Público:** `15.229.17.21`

---

## 🛠️ Stack Técnica

![Python](https://img.shields.io/badge/Python-3.12-blue?style=flat&logo=python)
![Django](https://img.shields.io/badge/Django-6.0-green?style=flat&logo=django)
![DRF](https://img.shields.io/badge/Django_REST_Framework-3.17-red?style=flat)
![AWS](https://img.shields.io/badge/AWS-EC2-orange?style=flat&logo=amazonaws)
![Gunicorn](https://img.shields.io/badge/Gunicorn-WSGI-green?style=flat)

---

## 📡 Endpoints da API

| Método | Endpoint | Descrição |
|---|---|---|
| GET | `/api/tarefas/` | Listar todas as tarefas |
| POST | `/api/tarefas/` | Criar nova tarefa |
| GET | `/api/tarefas/{id}/` | Buscar tarefa por ID |
| PUT | `/api/tarefas/{id}/` | Atualizar tarefa |
| PATCH | `/api/tarefas/{id}/` | Atualizar parcialmente |
| DELETE | `/api/tarefas/{id}/` | Deletar tarefa |

---

## 🚀 Como foi feito o deploy

1. Criação da instância EC2 t2.micro com Ubuntu 22.04 na região sa-east-1
2. Configuração do Security Group com regras de entrada (SSH, HTTP, HTTPS, 8000)
3. Conexão via SSH com chave `.pem`
4. Instalação do Python, pip e dependências
5. Clone do repositório via GitHub
6. Configuração do `ALLOWED_HOSTS` com o IP público
7. Instalação e configuração do Gunicorn
8. Criação do serviço systemd para rodar como daemon permanente
9. API acessível publicamente em `http://15.229.17.21:8000`

---

## 📁 Estrutura do Projeto

```
api-aws/
├── config/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── tarefas/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   └── urls.py
├── templates/
│   └── index.html
├── requirements.txt
└── manage.py
```

---

## 👨‍💻 Sobre

**Flávio da Paixão Nunes** — Desenvolvedor Backend Python | AWS Cloud  
Estudante de Engenharia de Software (Ampli/Anhanguera) — 2º ano  
Santos, São Paulo - SP

[![LinkedIn](https://img.shields.io/badge/LinkedIn-flaviopx-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/flaviopx)
[![GitHub](https://img.shields.io/badge/GitHub-Flavio--Paixao-black?style=flat&logo=github)](https://github.com/Flavio-Paixao)
[![Portfolio](https://img.shields.io/badge/Portf%C3%B3lio-AWS-orange?style=flat&logo=amazonaws)](https://projeto-aws-681892816208-sa-east-1-an.s3.sa-east-1.amazonaws.com/index.html)
