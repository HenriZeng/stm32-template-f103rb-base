# Rename Guide

When you create a new project from this template, rename `stm32_template` to your real project name before starting development.

## Files to Rename
- `stm32_template.ioc`
- `stm32_template Debug.launch`

Example:
- `stm32_template.ioc` -> `motor_controller.ioc`
- `stm32_template Debug.launch` -> `motor_controller Debug.launch`

## Files That Contain the Project Name
Replace `stm32_template` in:
- `.project`
- `.cproject`
- `.mxproject`
- `.osx.project`
- `stm32_template.ioc`
- `stm32_template Debug.launch`

## Recommended Rename Procedure
1. Duplicate the template repository into a new repository.
2. Rename the two top-level files listed above.
3. Replace all internal `stm32_template` references with your new project name.
4. Open the project in STM32CubeIDE.
5. Run a clean build and verify the generated `Debug/` output uses the new name.

## What Can Stay Unchanged
You usually do not need to change:
- `Core/`
- `Drivers/`
- `STM32F103RBTX_FLASH.ld`
- HAL/CMSIS source tree

## What to Review After Renaming
- Debug launch configuration
- `.project` display name in STM32CubeIDE
- `.cproject` build output path
- `.ioc` project metadata

If the project opens correctly in STM32CubeIDE and builds into `Debug/<your_project_name>.elf`, the rename is complete.
