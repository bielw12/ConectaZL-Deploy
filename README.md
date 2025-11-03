# 🗞️ Portal de Notícias - Django

Portal de notícias completo desenvolvido com Django + Python, incluindo sistema de autenticação, publicação de artigos, comentários moderados, curtidas dinâmicas, geolocalização e API REST.

## 🚀 Como Começar

### 1. Criar um Superusuário (Administrador)

Para acessar o painel administrativo e gerenciar o site, você precisa criar um superusuário:

```bash
python manage.py createsuperuser
```

Siga as instruções no terminal:
- Escolha um **nome de usuário**
- Digite seu **email** (opcional)
- Crie uma **senha segura**

### 2. Acessar o Painel Admin

Acesse: **`/admin/`**

Use as credenciais que você criou no passo anterior.

No painel admin você pode:
- ✅ Gerenciar usuários e perfis
- ✅ Aprovar/moderar comentários
- ✅ Marcar artigos como destaque
- ✅ Promover usuários para Jornalista ou Admin
- ✅ Gerenciar tags
- ✅ Ver estatísticas de curtidas

### 3. Criar Sua Primeira Conta de Usuário

Acesse: **`/register/`**

Escolha entre:
- **Leitor**: pode ler, comentar e curtir artigos
- **Jornalista**: pode criar e gerenciar próprios artigos

**Nota importante**: O perfil de **Administrador** só pode ser atribuído através do painel admin por questões de segurança.

### 4. Criar Seu Primeiro Artigo

1. Faça login como **Jornalista** ou **Admin**
2. Clique em **"Criar Artigo"** no menu superior
3. Preencha:
   - **Título** da notícia
   - **Resumo** (breve descrição)
   - **Conteúdo** (texto completo)
   - **Imagem** (opcional)
   - **Tags** (separadas por vírgula)
   - **Localização** (opcional: latitude, longitude, nome do local)
   - Marque **"Publicar artigo"** para torná-lo visível

## 📋 Tipos de Perfil

### 👤 Leitor
- Visualizar artigos publicados
- Comentar em artigos (sujeito a moderação)
- Curtir artigos
- Deletar próprios comentários

### ✍️ Jornalista
- Tudo que o Leitor pode fazer
- Criar novos artigos
- Editar próprios artigos
- Deletar próprios artigos
- Upload de imagens

### 👨‍💼 Administrador
- Todas as permissões
- Editar/deletar qualquer artigo
- Marcar artigos como **destaque** (aparecem no topo)
- Aprovar/moderar comentários
- Gerenciar usuários e perfis
- Promover usuários para outros perfis

## 🔧 Funcionalidades Principais

### 📰 Artigos
- CRUD completo (Criar, Ler, Atualizar, Deletar)
- Editor de texto rico
- Upload de imagens
- Sistema de tags
- Geolocalização com mapas interativos
- Contador de visualizações
- Sistema de destaques para página inicial

### 💬 Comentários
- Sistema de comentários moderados
- Aprovação manual via painel admin
- Usuários podem deletar próprios comentários

### ❤️ Curtidas
- Sistema de curtir/descurtir dinâmico
- JavaScript Vanilla (sem reload da página)
- Contador de curtidas

### 🗺️ Mapas
- Integração com Folium
- Visualização de localização em artigos
- Marcadores interativos

### 🔌 API REST

Acesse: **`/api/`**

Endpoints disponíveis:

**Artigos:**
- `GET /api/articles/` - Listar todos os artigos
- `GET /api/articles/{slug}/` - Detalhe de um artigo
- `POST /api/articles/` - Criar artigo (requer autenticação como jornalista)
- `PUT /api/articles/{slug}/` - Atualizar artigo (requer ser autor ou admin)
- `DELETE /api/articles/{slug}/` - Deletar artigo (requer ser autor ou admin)

**Comentários:**
- `GET /api/comments/` - Listar comentários aprovados
- `POST /api/comments/` - Criar comentário (requer autenticação)

**Filtros e Ordenação:**
- `?search=termo` - Buscar artigos
- `?ordering=-created_at` - Ordenar por data
- `?page=2` - Paginação

## 📁 Estrutura do Projeto

```
portal_noticias/
├── articles/          # App de artigos e curtidas
├── comments/          # App de comentários
├── users/             # App de autenticação e perfis
├── api/               # API REST (Django REST Framework)
├── templates/         # Templates HTML
│   ├── base/         # Template base
│   ├── articles/     # Templates de artigos
│   └── users/        # Templates de autenticação
├── static/           # CSS, JavaScript
├── media/            # Uploads de usuários
├── manage.py         # Comando principal Django
└── requirements.txt  # Dependências Python
```

## 🛠️ Comandos Úteis

```bash
# Criar migrações após mudanças nos models
python manage.py makemigrations

# Aplicar migrações ao banco de dados
python manage.py migrate

# Criar superusuário
python manage.py createsuperuser

# Executar servidor de desenvolvimento
python manage.py runserver 0.0.0.0:5000

# Acessar shell do Django
python manage.py shell

# Coletar arquivos estáticos
python manage.py collectstatic
```

## 🔒 Segurança

O projeto implementa várias medidas de segurança:
- ✅ Proteção CSRF para todos os formulários
- ✅ Autenticação obrigatória para ações sensíveis
- ✅ Validação de permissões baseada em roles
- ✅ Comentários moderados antes de publicação
- ✅ Upload de arquivos com validação
- ✅ Prevenção de auto-promoção para admin
- ✅ API com permissões baseadas em ownership

## 📚 Bibliotecas Utilizadas

- **Django 4.2.7** - Framework web
- **Django REST Framework** - API REST
- **django-taggit** - Sistema de tags
- **django-summernote** - Editor de texto rico
- **Pillow** - Processamento de imagens
- **folium** - Mapas interativos
- **psycopg2-binary** - Conexão PostgreSQL
- **TailwindCSS** - Framework CSS

## 🎯 Próximos Passos

Depois de explorar o sistema, você pode:

1. **Personalizar o design** - Editar templates em `templates/`
2. **Adicionar mais funcionalidades** - Criar novos apps Django
3. **Configurar email** - Para notificações e recuperação de senha
4. **Adicionar testes** - Criar testes unitários e de integração
5. **Otimizar performance** - Configurar cache e otimizações de queries
6. **Deploy em produção** - Publicar no Replit ou outro servidor

## 📖 Documentação

Para mais detalhes técnicos, consulte:
- **`replit.md`** - Documentação técnica completa
- [Documentação do Django](https://docs.djangoproject.com/)
- [Django REST Framework](https://www.django-rest-framework.org/)

## 💡 Dicas

1. **Teste o sistema**: Crie várias contas com diferentes perfis para testar as permissões
2. **Use o admin**: O painel admin do Django é muito poderoso para gerenciamento
3. **Explore a API**: Use ferramentas como Postman ou curl para testar os endpoints
4. **Moderação**: Lembre-se de aprovar comentários no painel admin
5. **Backup**: Faça backup regular do banco de dados

## ❓ Suporte

Se tiver dúvidas ou problemas:
1. Verifique os logs do servidor Django
2. Consulte a documentação em `replit.md`
3. Verifique o painel admin para configurações

---

**Desenvolvido com Django + Python** 🐍
