# Biblioteca Virtual

Sistema de acervo de biblioteca em Django, feito como Trabalho de Conclusão de
Curso do Ensino Médio Técnico em Informática para Internet. Entregue e aprovado
em novembro de 2024, na Escola Estadual Prof. Luiz Simione Sobrinho.

## Quem fez

- Caio Cardoso Silva
- Felipe Faria da Fonseca
- Gabriel Medeiros
- Heloisa Teodozio

## De onde ele parte

O projeto foi construído em cima do tutorial
[LocalLibrary da MDN](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Server-side/Django/Tutorial_local_library_website),
o guia de Django da Mozilla, com acréscimos do grupo: o modelo `Language`, o
índice reescrito, o CSS e a identidade visual da escola.

## O que ele faz

- Cadastro de livro, autor, gênero e idioma.
- Distinção entre a obra (`Book`) e o exemplar físico na prateleira
  (`BookInstance`), cada exemplar com status de empréstimo.
- Login de usuário, com recuperação de senha.
- Área de bibliotecário, acessível só por permissão, que renova prazo de
  empréstimo.

## Como rodar

Requer Python 3.12 ou superior.

```bash
git clone https://github.com/lipfelipef/BibliotecaTCC.git
cd BibliotecaTCC

python -m venv .venv
.venv\Scripts\activate        # Windows
source .venv/bin/activate     # Linux e macOS

pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

O site sobe em `http://127.0.0.1:8000/` e a administração em
`http://127.0.0.1:8000/admin/`.

O banco não vem no repositório: o `migrate` cria um `db.sqlite3` vazio na
primeira execução, e o `createsuperuser` cria o acesso de bibliotecário.

## Configuração

| Variável | Para que serve | Padrão |
| --- | --- | --- |
| `DJANGO_SECRET_KEY` | Chave de assinatura do Django | uma chave de desenvolvimento, marcada com o prefixo `django-insecure-` |

O padrão serve para rodar na sua máquina. Em produção a chave tem que vir do
ambiente, e o `settings.py` ainda está com `DEBUG = True` e `ALLOWED_HOSTS`
vazio, ou seja, este projeto está configurado para desenvolvimento.

## Sobre o histórico

Este repositório foi limpo em agosto de 2026. Saíram o banco de
desenvolvimento, os arquivos `__pycache__` e uma pasta duplicada de templates,
e a chave secreta passou a vir de variável de ambiente. O código entregue em
2024 continua igual, arquivo por arquivo.

O que motivou a limpeza está escrito em
[Biblioteca Virtual: meu TCC, dois anos depois](https://fariagallery.com/blog/biblioteca-virtual).

## Versão usada na entrega

Django 5.0.8, conforme registrado no cabeçalho das migrações.
