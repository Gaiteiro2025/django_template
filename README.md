# Django Authentication API

Este projeto fornece uma API de autenticação baseada em Django e Django Rest Framework (DRF), utilizando Docker para facilitar a configuração e o deploy.

## 🚀 Tecnologias

- Django
- Django Rest Framework (DRF)
- PostgreSQL
- Docker e Docker Compose
- Swagger (drf-yasg) para documentação

## 📦 Configuração do Projeto

### 1️⃣ Pré-requisitos

Antes de começar, certifique-se de ter instalado:
- Docker
- Docker Compose

### 2️⃣ Como rodar o projeto

```sh
# Clonar o repositório
git clone https://github.com/seu-repositorio/django_template.git
cd django_template

# Criar e subir os containers
docker-compose up --build -d

# Aplicar migrações
docker-compose exec web python manage.py migrate

# Criar superusuário (opcional)
docker-compose exec web python manage.py createsuperuser
```

O servidor estará disponível em `http://localhost:8000`

### 3️⃣ Endpoints disponíveis

A API segue as melhores práticas de autenticação com JWT.

- **Registro de usuário**: `POST /api/auth/register/`
- **Login**: `POST /api/auth/login/`
- **Logout**: `POST /api/auth/logout/`
- **Refresh Token**: `POST /api/auth/token/refresh/`
- **Detalhes do usuário**: `GET /api/auth/me/`

A documentação interativa pode ser acessada em:
```
http://localhost:8000/swagger/
http://localhost:8000/redoc/
```

## 🛠 Estrutura do projeto

```
django_template/
│-- app/
│   ├── auth/
│   │   ├── views.py
│   │   ├── serializers.py
│   │   ├── urls.py
│   │   ├── models.py
│-- config/
│   ├── settings.py
│   ├── urls.py
│-- docker/
│   ├── Dockerfile
│   ├── entrypoint.sh
│-- docker-compose.yml
```

## 🔐 Segurança

- Senhas armazenadas com hash bcrypt
- Tokens JWT com Refresh Token
- Rate limiting para proteção contra ataques brute-force
- Configuração de CORS para permitir apenas origens seguras

## 📌 Melhorias futuras

- Implementar autenticação via OAuth2
- Adicionar suporte a WebSockets para notificações
- Criar testes automatizados para garantir qualidade

---

## 📝 Licença

Este projeto está sob a licença MIT.

