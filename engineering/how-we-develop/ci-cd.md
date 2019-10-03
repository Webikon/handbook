# CI/CD

## How to test locally?

You can test all the commands from CI/CD pipeline in local interactive bash shell.

We use these Docker images for test PHP applications with Gitlab CI \(or any other CI plataform!\) [https://github.com/edbizarro/gitlab-ci-pipeline-php](https://github.com/edbizarro/gitlab-ci-pipeline-php).

```text
docker run -it edbizarro/gitlab-ci-pipeline-php:7.3-alpine bash
```

#### Alternative

Download/pull a Git repository to _/path/to/local/folder_ but don't run any build scripts on your host machine. Start a Bash session with the following command instead.

```text
docker run -it -v /path/to/local/folder:/var/www/html edbizarro/gitlab-ci-pipeline-php:7.3-alpine bash
```

Then, you can run any commands or scripts you would run in the pipeline. For example:

```text
##
## Install ssh-agent if not already installed, it is required by Docker.
##
'which ssh-agent || ( apt-get update -y && apt-get install openssh-client git -y )'

##
## Run ssh-agent (inside the build environment)
##
eval $(ssh-agent -s)

##
## Add your SSH key
##
echo "<YOUR_SSH_PRIVATE_KEY>" | tr -d '\r' | ssh-add - > /dev/null

##
## Create the SSH directory and give it the right permissions
##
mkdir -p ~/.ssh
chmod 700 ~/.ssh

##
## Use ssh-keyscan to scan the keys of your private server. Replace <DEV_REMOTE_SERVER> and <DEV_REMOTE_PORT>
## with your server IP/domain and port. You can copy and repeat that command if you have
## more than one server to connect to.
##
ssh-keyscan -p <DEV_REMOTE_PORT> <DEV_REMOTE_SERVER> >> ~/.ssh/known_hosts
#ssh-keyscan -p <TEST_REMOTE_PORT> <TEST_REMOTE_SERVER> >> ~/.ssh/known_hosts
#ssh-keyscan -p <LIVE_REMOTE_PORT> <LIVE_REMOTE_SERVER> >> ~/.ssh/known_hosts
chmod 644 ~/.ssh/known_hosts

##
## Project build commands
##
cp .env.sample .env
composer install
cd htdocs/content/themes/<WP_THEME>
npm install
npm run dev

##
## Upload (sync) build (processed) project files to remote location
##
rsync -azC --exclude "htdocs/content/themes/<WP_THEME>/node_modules" --exclude ".env"  -e "ssh -p <REMOTE_PORT>"  <CI_PROJECT_PATH> <REMOTE_USER>@<REMOTE_SERVER>:<REMOTE_PATH>
```



