FROM alpine:3.4

ENV TERRAFORM_VERSION 0.7.3
ENV VAULT_VERSION 0.6.1
ENV PACKER_VERSION 0.10.1
ENV CONSUL_VERSION 0.6.4
ENV NOMAD_VERSION 0.4.1

RUN apk update && apk upgrade
WORKDIR /tmp
ADD https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip .
ADD https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_linux_amd64.zip .
ADD https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip .
ADD https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip .
ADD https://releases.hashicorp.com/nomad/${NOMAD_VERSION}/nomad_${NOMAD_VERSION}_linux_amd64.zip .
RUN unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && unzip vault_${VAULT_VERSION}_linux_amd64.zip && unzip packer_${PACKER_VERSION}_linux_amd64.zip && unzip consul_${CONSUL_VERSION}_linux_amd64.zip && unzip nomad_${NOMAD_VERSION}_linux_amd64.zip
RUN mv packer /usr/bin && mv vault /usr/bin && mv terraform /usr/bin && mv consul /usr/bin && mv nomad /usr/bin
RUN rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip && rm vault_${VAULT_VERSION}_linux_amd64.zip && rm packer_${PACKER_VERSION}_linux_amd64.zip && rm consul_${CONSUL_VERSION}_linux_amd64.zip && rm nomad_${NOMAD_VERSION}_linux_amd64.zip
WORKDIR /
