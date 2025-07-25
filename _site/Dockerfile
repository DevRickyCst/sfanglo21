FROM ruby:3.2

WORKDIR /app

# Installation des dépendances système
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Copie des fichiers de dépendances
COPY Gemfile Gemfile.lock ./

# Installation des gems Ruby
RUN bundle install

# Copie du reste du projet
COPY . .

# Exposition du port 4000
EXPOSE 4000

# Commande par défaut pour démarrer Jekyll
CMD ["bundle", "exec", "jekyll", "serve", "--host", "0.0.0.0"] 