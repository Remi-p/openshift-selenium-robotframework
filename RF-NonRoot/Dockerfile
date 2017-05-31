FROM softsam/robotframework:latest

RUN apt-get -y update \
    && apt-get install -y git

RUN mkdir /rf
# See https://docs.openshift.org/latest/creating_images/guidelines.html
RUN chgrp -R 0 /rf \
  && chmod -R g+rwX /rf

# See http://ixday.github.io/post/docker_git_volume/
RUN git config --system core.logallrefupdates false

WORKDIR /rf

# ..?
USER robotframework

CMD ["tail", "-f", "/dev/null"]
