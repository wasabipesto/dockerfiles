FROM node:18

# For caching, only copy in package and yarn files
WORKDIR /opt/manifold
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/package.json ./
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/yarn.lock ./
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/common/package.json  ./common/
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/common/yarn.lock ./common/
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/docs/package.json ./docs/
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/functions/package.json ./functions/
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/og-image/package.json ./og-image/
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/og-image/yarn.lock ./og-image/
ADD https://raw.githubusercontent.com/manifoldmarkets/manifold/main/web/package.json ./web/
RUN ["yarn"]

# Grab the rest of the source, caching ends here
RUN git init && git remote add origin https://github.com/manifoldmarkets/manifold.git && git fetch && git checkout origin/main -ft

# Prepare to start web server
WORKDIR /opt/manifold/web
EXPOSE 3000

# For local development, run checks and deploy to dev db
#RUN ["yarn", "verify"]
#ENTRYPOINT ["yarn", "dev:dev"]

# For running normally
ENTRYPOINT ["yarn", "dev"]