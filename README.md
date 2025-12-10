# Gemstash Docker Image

This repository contains a Dockerfile for building a Docker image of **Gemstash**, a private RubyGems server used for caching, mirroring, and hosting private gems.

Gemstash is commonly used to:
- Cache public Ruby gems
- Host private/internal gems
- Improve reliability and speed of Bundler installs
- Isolate builds from external network dependencies

---

## Building the Docker Image

To build the Docker image, navigate to the `gemstash` directory and run:

```bash
cd gemstash
docker build -t TAG .
````

Replace `TAG` with your desired image tag.

---

## Pushing the Docker Image

To push the Docker image to a container registry:

```bash
docker push TAG
```

Replace `TAG` with the tag you used when building the image.

---

## GitHub Container Registry (GHCR)

The Docker image is published on GitHub Container Registry at:

```text
ghcr.io/codevedas/gemstash
```

Pull the image using:

```bash
docker pull ghcr.io/code-vedas/gemstash:main
```

---

## Running Gemstash

Example command to run Gemstash locally:

```bash
docker run -p 9292:9292 ghcr.io/code-vedas/gemstash:main
```

By default, Gemstash will be available at:

```text
http://localhost:9292
```

You can then configure Bundler to use it as a source or mirror.

---

## Disclaimer

This Docker image is **not officially affiliated with or endorsed by the Gemstash project**.
It is provided as-is for convenience and may not include all features or configurations of the official Gemstash distribution. Users are advised to review and modify the Dockerfile as needed to suit their specific requirements.

---

## License

The Dockerfile and all associated files in this repository are licensed under the **MIT License**.

Gemstash itself is licensed under the **MIT License**.
Source: [https://github.com/bundler/gemstash](https://github.com/bundler/gemstash)