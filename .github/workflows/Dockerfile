FROM zmkfirmware/zmk-build-arm:stable

ENV ZEPHYR_TOOLCHAIN_VARIANT=zephyr
WORKDIR /opt/zmk-env

# Fetch ZMK main and the projects in its west.yml
RUN west init -m https://github.com/zmkfirmware/zmk --mr main --mf app/west.yml . && \
    west update --fetch-opt=--filter=tree:0

# Ensure Zephyr SDK paths are available
ENV ZEPHYR_BASE=/opt/zmk-env/zephyr
ENV CMAKE_PREFIX_PATH=${ZEPHYR_BASE}