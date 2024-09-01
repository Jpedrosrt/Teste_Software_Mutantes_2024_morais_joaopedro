# Teste de Mutação no Projeto Phonebook

### Tutorial PDF
[Acesse o tutorial em PDF](https://drive.google.com/file/d/1oJYYiY_k3yBouu58gbNFqT_wlER7F4qY/view?usp=sharing)

## Introdução

No desenvolvimento de software, a criação de testes eficazes é crucial para garantir a qualidade e a robustez do código. Entre as diversas técnicas disponíveis, os testes de mutação se destacam por sua capacidade de identificar falhas e pontos fracos nos casos de teste existentes. Esta metodologia envolve a introdução de defeitos no código, conhecidos como "mutações", para avaliar se os casos de teste são eficazes em detectar essas falhas.

Este repositório contém a aplicação dos testes de mutação no projeto Python "Phonebook", desenvolvido por Emily Bache no [GitHub](https://github.com/emilybache/Phonebook-Python-Example-Project). Utilizamos as ferramentas `pytest` para a execução de testes unitários, `pytest-cov` para a avaliação da cobertura dos testes, e `mutmut` para a realização dos testes de mutação.

## Estrutura do Projeto Phonebook

O projeto Phonebook é uma aplicação Python simples que gerencia um catálogo de números de telefone. Ele é composto por três arquivos principais:

- **phonenumbers.py**: Contém a classe `Phonebook`, que permite armazenar e manipular números de telefone. Também verifica a consistência dos números para evitar conflitos.
- **data_processing.py**: Fornece a função `clean_phonenumber`, que limpa e padroniza os números de telefone.
- **cli.py**: Implementa uma interface de linha de comando (CLI) que permite carregar e verificar listas de números de telefone a partir de um arquivo CSV.

## Configuração do Ambiente

1. **Criação do Repositório:**
   - Criei o repositório `Teste_Software_Mutantes_2024_morais_joaopedro` no GitHub.
   - Fiz um fork do projeto Phonebook da usuária Emily Bache (emilybache) e adicionei-o como um submódulo.

2. **Configuração do Ambiente Virtual:**
   - Criei um ambiente virtual Python dentro do fork do projeto com o comando:
     ```bash
     python -m venv venv
     ```
   - Ativei o ambiente virtual com:
     ```bash
     source venv/scripts/activate
     ```

3. **Instalação das Dependências:**
   - Usei o arquivo `requirements.txt` presente no repositório e executei:
     ```bash
     pip install -r requirements.txt
     ```
   - Instalei o projeto em modo editável para evitar a reinstalação manual após cada modificação:
     ```bash
     pip install -e .
     ```

## Execução dos Testes

1. **Testes Unitários:**
   - O projeto contém três arquivos de testes principais: `test_data_processing.py`, `test_large_books.py`, e `test_phonenumbers.py`.
   - Executei os testes unitários com o comando:
     ```bash
     python -m pytest
     ```
   - Todos os testes foram bem-sucedidos.

2. **Análise de Cobertura:**
   - Avaliei a cobertura dos testes com o comando:
     ```bash
     pytest -vv test/ --cov=phonebook
     ```
   - A cobertura alcançada foi de 59%. Excluindo arquivos não essenciais, a cobertura aumentou para 92%.

3. **Testes de Mutação:**
   - Executei os testes de mutação com o comando:
     ```bash
     mutmut run
     ```
   - O projeto Phonebook teve 14 mutações eliminadas e 12 mutantes sobreviventes.

4. **Refinamento dos Testes:**
   - Após a criação de novos testes, a cobertura de 92% foi mantida, mesmo com a inclusão de arquivos auxiliares como `__init__.py` e `cli.py`.
   - Dois mutantes sobreviveram, mas foram considerados menos críticos para a funcionalidade da aplicação.

## Conclusão

Os testes de mutação aplicados ao projeto Phonebook demonstraram a eficácia dos casos de teste em detectar falhas críticas. Com uma cobertura de 92% e apenas dois mutantes sobreviventes, o conjunto de testes foi considerado robusto e eficaz.
