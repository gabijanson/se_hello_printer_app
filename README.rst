Simple Flask App
================

Aplikacja Dydaktyczna wyświetlająca imię i wiadomość w różnych formatach dla zajęć
o Continuous Integration, Continuous Delivery i Continuous Deployment.

- Rozpocząnając pracę z projektem (wykorzystując virtualenv). Hermetyczne środowisko dla pojedyńczej aplikacji w python-ie:

  ::

    source /usr/local/bin/virtualenvwrapper.sh # do ~/.bashrc
    mkvirtualenv wsb-simple-flask-app

    można użyć:

    pip install -r requirements.txt
    pip install -r test_requirements.txt

    lub też:

    make deps


- Uruchamianie applikacji:

  ::
    make run

    lub:

    # jako zwykły program
    python main.py

    # albo:
    PYTHONPATH=. FLASK_APP=hello_world flask run

- Uruchamianie testów (see: http://doc.pytest.org/en/latest/capture.html):

  ::
    make test

    lub:

    PYTHONPATH=. py.test
    PYTHONPATH=. py.test  --verbose -s

    dodatkowo:

    make lint

- Kontynuując pracę z projektem, aktywowanie hermetycznego środowiska dla aplikacji py:

  ::

    source /usr/local/bin/virtualenvwrapper.sh # nie trzeba, jeśli już w .bashrc
    workon wsb-simple-flask-app


- Integracja z TravisCI:

    plik .travis.yml zawiera informacje i skrypty które wykonywać ma travis podczas builda


- Integracja z Heroku:
    plik .travis.yml zawiera ustawienia do automatycznego deployu na heroku,
    gdzie dodana jest nazwa aplikacji z Heroku
    oraz zmienna HEROKU_API_KEY, która dodana jest w ustawieniach Travisa dla aplikacji

- Monitoring ze Statuscake

    aplikacja monitorowana jest przez Statuscake, pod adresem aplikacji na Heroku


Pomocnicze
==========

- Instalacja python virtualenv i virtualenvwrapper:

  ::

    yum install -y python-pip
    pip install -U pip
    pip install virtualenv
    pip install virtualenvwrapper

- Instalacja docker-a:

  ::

    yum remove docker \
        docker-common \
        container-selinux \
        docker-selinux \
        docker-engine

    yum install -y yum-utils

    yum-config-manager \
      --add-repo \
      https://download.docker.com/linux/centos/docker-ce.repo

    yum makecache fast
    yum install -y docker-ce
    systemctl start docker

Materiały
=========

- https://virtualenvwrapper.readthedocs.io/en/latest/

Nowa wersja lepsza dokumentacja
