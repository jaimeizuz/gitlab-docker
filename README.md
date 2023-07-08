gitlab-docker

Instrucciones de uso de docker-compose (ver https://www.czerniga.it/2021/11/14/how-to-install-gitlab-using-docker-compose/)
1. export GITLAB_HOME=$(pwd)/gitlab
2. docker-compose up -d
3. docker exec -it gitlab-ce grep 'Password:' /etc/gitlab/initial_root_password
4. Acceder a la URL de login y entrar con root/<password>.
5. Acceder a <URL>/admin/runners y copiar el token.
6. docker exec -it gitlab-runner gitlab-runner register --url "http://gitlab-ee-host" --clone-url "http://gitlab-ee-host"
7. sudo vi gitlab/gitlab-runner/config.toml y añadir al final 'network_mode = "gitlab-network"'

Listo.
