
ARG VARIANT=3-bookworm
FROM mcr.microsoft.com/vscode/devcontainers/python:${VARIANT}

ENV PYTHONUNBUFFERED=1

# Node.js version
ARG NODE_VERSION="none"
RUN if [ "${NODE_VERSION}" != "none" ]; then \
    su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; \
    fi

# Install PostgreSQL client
RUN apt-get update \
    && apt-get install -y --no-install-recommends postgresql-client \
    && rm -rf /var/lib/apt/lists/*
