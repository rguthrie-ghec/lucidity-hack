ARG VARIANT=focal
ARG USERNAME=vscode

FROM mcr.microsoft.com/vscode/devcontainers/base:${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y git ca-certificates curl apt-transport-https lsb-release gnupg \
    && curl -sL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null \
    && echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ focal main" | tee /etc/apt/sources.list.d/azure-cli.list \
    && apt-get update \
    && apt-get -y install --no-install-recommends curl jq azure-cli unzip make

USER ${USERNAME}

WORKDIR /tmp

# Install Golang
RUN wget -O golang.tar.gz https://golang.org/dl/go1.15.6.linux-amd64.tar.gz  \
    && tar -xvf golang.tar.gz \
    && rm -rf /usr/local/go \
    && mv go /usr/local \ 
    && ln -s /usr/local/go/bin/go /usr/local/bin/go

# Install Terraform 0.14
RUN wget -O terraform.zip https://releases.hashicorp.com/terraform/0.14.2/terraform_0.14.2_linux_amd64.zip \
&& unzip terraform.zip \
&& mv terraform /usr/local/bin

# Install TFLint
RUN curl -L "$(curl -Ls https://api.github.com/repos/terraform-linters/tflint/releases/latest | grep -o -E "https://.+?_linux_amd64.zip")" -o tflint.zip && unzip tflint.zip && rm tflint.zip \
&& mv tflint /usr/local/bin

# Install TFLint Azure RM Ruleset
RUN git clone https://github.com/terraform-linters/tflint-ruleset-azurerm.git \
&& cd tflint-ruleset-azurerm \
&& make install \
&& mv /root/.tflint.d /home/vscode

ENV GO111MODULE=on
ENV CGO_ENABLED=0

WORKDIR /work

# Clone Terraform-Pipelines
RUN git clone https://csedevops@dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Pipelines
RUN chown -R vscode:vscode Terraform-Pipelines

# Clone Terraform-Code
RUN git clone https://csedevops@dev.azure.com/csedevops/terraform-template-public/_git/Terraform-Code
RUN chown -R vscode:vscode Terraform-Code

# Cleanup apt
RUN apt-get autoremove -y \
    && apt-get clean -y 

WORKDIR /work    