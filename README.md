# PRICELESS — the site

This repository holds the **built** site, not its source. The source is private:
[\Sergey-Bar/Priceless\](https://github.com/Sergey-Bar/Priceless).

GitHub Pages serves this branch. The custom domain is **priceless.ai** — the \CNAME\ file at the
root is what GitHub reads, and it is copied from the build's \pps/web/public/CNAME\.

## What is published here

The marketing pages, the PWA shell, the locale catalogues and the service worker, built by the
web app's SSG and pushed by the publish step in the source repository.

The **product pages** are not in this build. The SSG writes them only from a **verified catalog
release** — an artifact with a digest, published to the isolated bucket by the backend's
\catalog-export\. There is no verified release yet, and the SSG is built to refuse an
unverified one rather than publish pages nobody can prove.

## The API

The site calls the comparison API at the CloudFront host in \VITE_API_BASE\. The API's CORS
allowlist carries \https://priceless.ai\ and \https://www.priceless.ai\.
