# 🚀 Projeto CI/CD Pipeline Demo

![CI Pipeline](https://github.com/ArthurVeraci/ci-cd-pipeline-/actions/workflows/ci.yml/badge.svg)

## 📘 Descrição

Este projeto foi desenvolvido com o objetivo de praticar **Integração Contínua (CI)** utilizando **GitHub Actions**, simulando um fluxo real de validação de código e testes automatizados.

Ele é um dos projetos do meu plano de estudos focado em **DevOps Junior**, com o propósito de adquirir experiência prática e demonstrar conhecimentos em automação de pipelines.

---

## 🧩 Tecnologias Utilizadas

- **Python 3.10**
- **Flask** – para criar uma aplicação web simples
- **Pytest** – para testes automatizados
- **GitHub Actions** – para orquestrar o pipeline CI

---

## ⚙️ Pipeline CI

O pipeline executa automaticamente sempre que há um **push** ou **pull request** na branch `main`.  
As etapas são:

1. **Checkout do código**  
   - Baixa o código do repositório para o runner do GitHub.

2. **Configuração do ambiente Python**  
   - Instala a versão definida no workflow (`3.10`).

3. **Instalação de dependências**  
   - Lê o arquivo `requirements.txt` e instala as bibliotecas necessárias.

4. **Execução de testes automatizados**  
   - Roda os testes do `pytest` e valida se a aplicação está funcionando corretamente.

---

## 🧪 Testes Automatizados

O teste localizado em `tests/test_app.py` garante que a rota principal (`/`) da aplicação Flask esteja retornando a resposta esperada.

```python
def test_home_route():
    response = app.test_client().get('/')
    assert response.status_code == 200
    assert b"Hello, DevOps Lab!" in response.data
