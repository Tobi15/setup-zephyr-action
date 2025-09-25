# Setup Zephyr Project Action

This GitHub Action installs the Zephyr SDK and sets up the environment for building Zephyr applications.

## Inputs
- `sdk_version`: Zephyr SDK version (default: `0.17.0`)
- `toolchains`: Space-separated toolchains (default: `arm-zephyr-eabi x86_64-zephyr-elf`)

## Usage
```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: <your-username>/setup-zephyr@v1
        with:
          sdk_version: "0.17.0"
          toolchains: "arm-zephyr-eabi"
      - run: west build -b nrf52840dk_nrf52840 samples/hello_world
```