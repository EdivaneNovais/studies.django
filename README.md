# studies.django
- Criação do ambiente virtual: python -m virtualenv venv
- Ativarambiente virtual: source venv/Scripts/activate
- iniciar projeto na pasta principal:
- iniciar o projeto(muitos apps podem estar em um projeto): django-admin startproject alurareceita .
- altero a linguagem para português e a localização: LANGUAGE_CODE = 'pt-br'
TIME_ZONE = 'America/Sao_Paulo'
- python manage.py help
- para subir o servidor: python manage.py runserver
- iniciar um app(aplicação que faz uma determinada ação): python manage.py startapp receitas
- registrar o app no projeto, em apps.py pego o nome do app e pego o name 'receitas' e coloco no settings.py em installed_apps
- acessar o app de receitas: crio uma url para o app, pra condeguir importar as urls do django preciso importar com: from django.urls import path. e para importar todas a views relacionadas a url: from . import views
- o local host seja a pagina de receitas: urlpatterns = [
    path('', views.index, name='index')
]
- registrar nossas rotas no projeto alurasrecitas path('', include('receitas.urls'))
- Crio um arquivo que devolve todo pagina html, então vou renderizar um arquivo html, crio a pasta templates e crio o arquivo index.html.
- vou referência no projeto alurareceitas em settings.py onde está a minha pagina html no app receitas em tamplates/index.html:
STATIC_ROOT 
STATIC_URL 
STATICFILES_DIRS
- refencio onde está o diretório dos arquivos estaticos, que estará em alurareceitas/static:python manage.py collectstatic, ele faz uma cópia para conseguir manipular melhor esses arquivos
- epecifico para o django que tem arquvo staticos no index.html para colocar linguagem python coloco:{% load static %}
