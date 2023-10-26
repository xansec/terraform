FROM hashicorp/terraform

COPY testing/equivalence-tests/tests /tftests
RUN mkdir /testsuite
RUN for file in $(ls /tftests/*/*.tf); do cp $file /testsuite/$RANDOM.tf; done
RUN mkdir /workspace
WORKDIR /workspace
RUN terraform init --backend=false
