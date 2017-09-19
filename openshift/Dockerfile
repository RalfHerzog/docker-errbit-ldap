FROM centos/ruby-23-centos7

EXPOSE 8080

USER root

RUN git clone https://github.com/errbit/errbit.git errbit && mv errbit/* . && rm -rf errbit/

RUN chown -R default: /opt/app-root/src/

HEALTHCHECK CMD curl --fail http://localhost:$PORT/users/sign_in || exit 1

USER 1001

CMD ["bundle","exec","puma","-C","config/puma.default.rb"]
