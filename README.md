# Sistema de Gerenciamento de Presentes

Este projeto é uma aplicação Django para gerenciar presentes de um casamento. Ele inclui funcionalidades para gerenciamento de convidados e presentes, permitindo que os noivos adicionem presentes e convidados reservem os que desejarem para presentear os noivos.

---

## Funcionalidades

### Noivos
- **Página Inicial**: Exibe os presentes cadastrados e sua disponibilidade.
- **Cadastro de Presentes**: Permite que os noivos cadastrem presentes com nome, preço, importância (1 a 5) e uma foto.
- **Lista de Convidados**: Permite visualizar e cadastrar convidados com nome e contato.

### Convidados
- **Página de Convidados**: Acessível via link único gerado para cada convidado.
  - Visualizar status de presença e lista de presentes disponíveis.
- **Confirmação de Presença**: O convidado pode confirmar ou recusar o convite.
- **Reserva de Presentes**: O convidado pode reservar presentes disponíveis.

---

## Estrutura do Projeto
├── convidados/ │ ├── migrations/ │ ├── templates/ │ ├── init.py │ ├── admin.py │ ├── apps.py │ ├── models.py │ ├── tests.py │ ├── urls.py │ └── views.py ├── core/ ├── media/ ├── noivos/ │ ├── migrations/ │ ├── templates/ │ ├── init.py │ ├── admin.py │ ├── apps.py │ ├── models.py │ ├── tests.py │ ├── urls.py │ └── views.py ├── templates/ ├── db.sqlite3 ├── manage.py └── venv/


---

## Requisitos

- **Python**: 3.8 ou superior
- **Django**: 4.0 ou superior
- **Banco de Dados**: SQLite (incluso por padrão)
- Módulo `secrets` (`pip install secrets`)

---

## Configuração

1. Clone o repositório:
   ```bash
   git clone <url-do-repositorio>
   cd <nome-do-repositorio>
2. Crie um ambiente virtual
   ```bash
    python -m venv venv
    source venv/bin/activate  # Linux/Mac
    venv\Scripts\activate  # Windows
3.Instale as dependências.

4. Configure o banco de dados
   ```bash
    python manage.py migrate
5. Inicie o servidor
   ```bash
    python manage.py runserver

## Detalhes Adicioais:
### Gerenciamento de Convidados
Ao cadastrar um convidado, um token único é gerado automaticamente. Este token é utilizado para gerar um link exclusivo para o convidado, permitindo acesso à sua página pessoal.

Exemplo de link:
http://127.0.0.1:8000/convidados/?token=<TOKEN>

### Gerenciamento de Presentes
Os presentes podem ser cadastrados com:
- Nome
- Foto
- Preço
- Nível de importância (1-5)

Os presentes podem ser reservados pelos convidados diretamente via link exclusivo.

## Melhorias Futuras
- Implementação de autenticação para noivos.
- Notificações automáticas por e-mail para convidados.
- Exportação de listas (presentes e convidados) em formato PDF.

## Licença
Esse README cobre todos os pontos principais, incluindo a estrutura, uso e explicações detalhadas sobre os módulos e classes do projeto.
