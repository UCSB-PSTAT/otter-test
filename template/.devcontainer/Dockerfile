# FROM docker.io/ucsb/pstat-126:v20230918
# FROM docker.io/jupyter/scipy-notebook:x86_64-lab-4.0.6
# FROM docker.io/ucsb/pstat-134-234:v20230928
FROM docker.io/ucsb/pstat234:v20231127

USER root

## ### Quarto
## # versions: https://quarto.org/docs/download/_download.json
## # neat setup: https://github.com/jeremiahpslewis/reproducibility-with-quarto
## # ENV QUARTO_VERSION 1.2.475
ENV QUARTO_VERSION 1.3.450
RUN curl --silent -L --fail \
        https://github.com/quarto-dev/quarto-cli/releases/download/v${QUARTO_VERSION}/quarto-${QUARTO_VERSION}-linux-amd64.deb > /tmp/quarto.deb && \
    apt-get update && \
    apt-get install -y --no-install-recommends /tmp/quarto.deb && \
    rm -rf /tmp/quarto.deb /var/lib/apt/lists/* /tmp/library-scripts

# USER root

# RUN apt-get update && \
#     apt-get install -y --no-install-recommends fonts-font-awesome lmodern

## USER ${NB_USER}

## # RUN quarto install tinytex
## RUN pip install jupyterlab_rise

USER ${NB_USER}

### Prints Jupyter server token when terminal is opened
RUN echo "echo \"Jupyter server token: \$(jupyter server list 2>&1 | grep -oP '(?<=token=)[[:alnum:]]*')\"" > ${HOME}/.get-jupyter-url.sh && \
    echo "sh \${HOME}/.get-jupyter-url.sh" >> ${HOME}/.bashrc

RUN pip install umap-learn