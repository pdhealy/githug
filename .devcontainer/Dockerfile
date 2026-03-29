FROM ruby:slim

# Development tools needed by githug and common workflows.
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        git \
        less \
        man-db \
        openssh-client \
    && rm -rf /var/lib/apt/lists/*

# Keep bundler current for dependency resolution.
RUN gem install bundler -v "~> 2.4"

# Ruby 4 no longer includes logger as a default gem; grit needs it at runtime.
RUN gem install logger -N

WORKDIR /workspaces/githug
