### One-liner

    docker run --rm -p 3000:3000 -d $( docker build -q https://raw.githubusercontent.com/wasabipesto/dockerfiles/main/manifold/Dockerfile )