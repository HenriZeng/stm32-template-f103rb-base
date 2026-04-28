# STM32 Template for Nucleo-F103RB

A clean STM32CubeIDE / STM32CubeMX project template for the STM32 Nucleo-F103RB (`STM32F103RBT6`).

This repository is intended to be used as a starting point for new STM32 projects. It keeps the common board configuration and generated HAL/CMSIS structure, while removing all application-specific demo logic.

## Template Baseline
- Board: STM32 Nucleo-F103RB
- MCU: STM32F103RBT6
- Development environment: macOS + STM32CubeIDE + STM32CubeMX
- System clock source: `HSI`
- User LED GPIO: `PA5`
- UART peripheral: `USART2`
- UART TX: `PA2`
- UART RX: `PA3`
- UART configuration: `115200 8N1`

## Included in the Template
- STM32CubeMX-generated project structure
- HAL and CMSIS driver tree
- Basic system clock initialization
- `GPIOA` enable and `PA5` output initialization
- `USART2` initialization
- Startup file and linker script
- Empty application skeleton in `main.c`

## Removed from the Source Demo
- UART test message transmission
- LED blink demo loop
- Temporary or generated build output

## Repository Structure
```text
.
├── Core/
├── Drivers/
├── .project
├── .cproject
├── .mxproject
├── .settings/
├── STM32F103RBTX_FLASH.ld
├── stm32_template.ioc
├── stm32_template Debug.launch
├── RENAME_PROJECT.md
├── .gitignore
└── README.md
```

## How to Use This Template

### Option 1: Use as a GitHub Template Repository
1. Push this directory as a standalone GitHub repository.
2. Mark the repository as a template repository in GitHub settings.
3. Create a new project from this template.
4. Rename the project from `stm32_template` to your real project name.

### Option 2: Clone and Reuse Manually
```bash
git clone <your-template-repo-url> my_new_project
cd my_new_project
```

Then follow the renaming steps in [RENAME_PROJECT.md](RENAME_PROJECT.md).

## Where to Add Application Code
- Startup initialization: `Core/Src/main.c` inside `USER CODE BEGIN 2`
- Main loop logic: `Core/Src/main.c` inside `USER CODE BEGIN 3`
- User modules: create additional files under `Core/` or your own module folders

## Recommended Workflow
1. Open the project in STM32CubeIDE.
2. Build once to regenerate local build output.
3. Rename the project if this is a new product.
4. Add application code only inside `USER CODE` sections or separate user modules.
5. If hardware changes are needed, edit `stm32_template.ioc` and regenerate with STM32CubeMX.

## Notes
- This template intentionally keeps `USART2` and `PA5` configured because they are useful for early bring-up and diagnostics.
- Generated folders such as `Debug/`, `Release/`, and `build/` are excluded by `.gitignore`.
