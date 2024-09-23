### Load Fixtures
    docker compose run --rm php bin/console doctrine:fixtures:load --no-interaction

### Cache Playwright Binaries
    mkdir -p ~/.cache/ms-playwright
    docker compose run pwa /bin/sh -c 'mkdir -p /root/.cache/ms-playwright'
### Note: Caching mechanism would need to be implemented manually

### Install PNPM
    curl -fsSL https://get.pnpm.io/install.sh | sh -

### Cache PNPM
### Note: Caching mechanism would need to be implemented manually

### Install Dependencies
    cd pwa
    pnpm install

### Install Playwright Browsers with Deps (if cache miss)
    pnpm exec playwright install --with-deps

### Install Playwright Browsers (if cache hit)
    pnpm exec playwright install

### Run Playwright
    pnpm exec playwright test --workers=1 --grep $ANNOTATION
### Run Playwright
    pnpm exec playwright test