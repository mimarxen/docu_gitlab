
https://docs.gitlab.com/runner/install/docker.html
https://docs.gitlab.com/runner/register/index.html#docker


https://embeddedinventor.com/complete-guide-to-setting-up-gitlab-locally-on-windows-pc/#STEP6_Download_GitLab_runners

docker volume create gitlab-runner-config
docker run -d --name gitlab-runner --restart always \
-v /var/run/docker.sock:/var/run/docker.sock \
-v gitlab-runner-config:/etc/gitlab-runner \
-v /srv/gitlab-runner/docker-machine-config:/root/.docker/machine \
gitlab/gitlab-runner:latest