# django wiki 하는 법

1. workspace를 만든다.

2. python 버전 세팅을 한다.

   ```shell
   git clone https://github.com/pyenv/pyenv.git ~/.pyenv
   echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
   echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
   echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc
   exec "$SHELL"
   
   git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv
   echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
   exec "$SHELL"
   ```

   ```shell
   pyenv install 3.6.7
   pyenv global 3.6.7
   python --version #으로 확인
   ```

3. 폴더 만들기

   ```shell
   mkdir wikifolder
   cd wikifolder
   ```

4. 가상환경 설정하기

   ```shell
   pyenv virtualenv 3.6.7 wiki-venv
   pyenv local wiki-venv
   ```

5. **장고 설치**

   ```shell
   pip install django==2.1.7
   ```

6. git clone하기

   ```shell
   git init
   git clone https://github.com/django-wiki/django-wiki.git
   ```

7. ALLOWED HOSTS 설정하기

   > wikifolder / django-wiki / testproject / testproject / settings / base.py

   ```python
   ...
   ...
   ALLOWED_HOSTS = ['*']
   ...
   ...
   ```

8. wiki 라이브러리 설치하기

   ```shell
   pip install wiki
   ```

9. migrate 하기

   ```shell
   cd django-wiki/testproject
   python manage.py migrate # makemigrtaions는 필요없다. 
   ```

10. 서버 실행

    ```shell
    python manage.py runserver $IP:$PORT
    ```

    
