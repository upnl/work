FROM debian:bullseye-slim
RUN apt update && apt install -y tini && apt clean

# 마이스누에서 다운로드한 wagent
ADD wagent.tar /
RUN mv /wagent_* /wagent
WORKDIR /wagent
# 에이전트가 셸의 background job으로 뜨기 때문에 이게 없으면 바로 꺼져버린다
RUN echo 'tail -f /dev/null' >> wagent_run.sh

EXPOSE 12251-12259
ENTRYPOINT ["/usr/bin/tini", "--"]
CMD ["/bin/bash", "./wagent_run.sh"]
