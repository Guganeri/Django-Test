**Instruções para instalação e configuração do Django**

**Instalação do Virtualenv**

Para usar o Django com o virtualenv, primeiro é necessário instalá-lo:

```
pip install virtualenv
```

Em seguida, crie um novo virtualenv no diretório raiz do projeto:

```
virtualenv .venv
```

Ative o virtualenv:

```
source .venv/bin/activate
```

Você saberá que o virtualenv está ativado porque seu terminal mostrará algo como:

```
(.venv) android@Neri-Desktop:~/Django$
```

**Instalação do Django**

No virtualenv, instale o Django:

```
pip install django
```

**Verificação das dependências**

Para verificar todas as dependências instaladas no virtualenv, use o comando:

```
pip freeze
```

Para criar um arquivo com as dependências, use o comando:

```
pip freeze > requirements.txt
```

**Comandos do Django**

Para ver uma lista de todos os comandos do Django, use o comando:

```
django-admin help
```

**Inicialização do projeto**

Para iniciar um novo projeto Django, use o comando:

```
django-admin startproject nome_do_projeto
```

Por exemplo, para iniciar um projeto chamado "setup", use o comando:

```
django-admin startproject setup
```

**Inicialização do servidor**

Para iniciar o servidor de desenvolvimento do Django, use o comando:

```
python manage.py runserver
```

**Utilização de variáveis de ambiente**

Para usar variáveis de ambiente no Django, instale o pacote `python-dotenv`:

```
pip install python-dotenv
```

Em seguida, crie um arquivo `.env` no diretório raiz do projeto. Nesse arquivo, você pode definir variáveis de ambiente em formato `KEY=VALUE`.

Para que o Django reconheça as variáveis de ambiente, adicione a seguinte linha ao arquivo `settings.py`:

```
import dotenv
dotenv.load_dotenv(os.path.join(BASE_DIR, '.env'))
```

**Criação de um novo aplicativo**

Para criar um novo aplicativo Django, use o comando:

```
python manage.py startapp nome_do_aplicativo
```

Por exemplo, para criar um aplicativo chamado "galeria", use o comando:

```
python manage.py startapp galeria
```

**Mapeamento de um endpoint**

Para mapear um endpoint, adicione uma entrada à lista `INSTALLED_APPS` no arquivo `settings.py`.

Por exemplo, para mapear o endpoint "galeria", adicione a seguinte linha ao arquivo `settings.py`:

```
INSTALLED_APPS = [
    ...
    'galeria',
]
```

Após mapear o endpoint, você pode criar a view e a url correspondentes.

**Criação de uma view**

As views são responsáveis por lidar com as solicitações HTTP recebidas pelo servidor. Para criar uma view, crie um arquivo `views.py` no aplicativo correspondente.

Por exemplo, para criar uma view para o endpoint "galeria", crie um arquivo `views.py` no aplicativo "galeria":

```python
from django.http import HttpResponse

def index(request):
    return HttpResponse('Olá, mundo!')
```

**Mapeamento de uma url**

As urls são responsáveis por mapear endpoints a views. Para mapear uma url, crie um arquivo `urls.py` no aplicativo correspondente.

Por exemplo, para mapear a url "/galeria/" ao endpoint "galeria", crie um arquivo `urls.py` no aplicativo "galeria":

```python
from django.urls import path

from .views import index

urlpatterns = [
    path('', index, name='index'),
]
```

**Coleção de arquivos estáticos**

Para coletar todos os arquivos estáticos do projeto, use o comando:

```
python manage.py collectstatic
```

Esse comando copia todos os arquivos estáticos dos aplicativos para o diretório `staticfiles` do projeto.


As configurações de paginas estaticas ficam no settings.py no setup, com três configurações
STATIC_ROOT,STATICFILES_DIRS,STATIC_URL = 'static/'
**deactivate // source .venv/bin/activate**