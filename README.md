# PS2PC

Tool for automatic PS5 executables porting to Linux and Windows. A customized fork of [AnyPS5](https://github.com/boykopovar/AnyPS5), see [Credits](#credits).

[**Web converter**](https://vabxsen.github.io/PS2PC/) - files stay on your device.

![anyps5_collage1](https://github.com/user-attachments/assets/ed2f0b2d-33d3-46d7-ab88-767ca872fc99)

Includes a [relinker](core/relinker) that converts executable to the target system's native format and implementations of [system prx libraries](core/libs/prx) suitable for dynamic linking. No emulation or separate runtime process.

[**Issues**](https://github.com/vabxsen/PS2PC/issues), [**Discussions**](https://github.com/vabxsen/PS2PC/discussions), [Usage](docs/user/USAGE.md), [Build instructions](docs/dev/BUILD.md), [Architecture](docs/dev/ARCHITECTURE.md), [Technical debt of the project](docs/dev/TechnicalDebt.md), [code style conventions](docs/dev/CONVENTIONS.md), [contributing](CONTRIBUTING.md)

## Status

[![libraries](https://vabxsen.github.io/PS2PC/badge-libraries.svg)](https://vabxsen.github.io/PS2PC/progress.html) [![shaders](https://vabxsen.github.io/PS2PC/badge-shaders.svg)](https://vabxsen.github.io/PS2PC/progress.html)

[![progress map](https://vabxsen.github.io/PS2PC/progress.svg)](https://vabxsen.github.io/PS2PC/progress.html)

[Progress history](https://vabxsen.github.io/PS2PC/history.html)

<sub>* System libraries: percentage of the functions known to the project so far (declared in [core/libs/prx](core/libs/prx)), not of every PS5 system function. The total grows as more functions are declared.</sub>

Unsupported or unexpected states strictly throw `std::runtime_error`. `what()` is printed to stderr and the process terminates.

The [shader recompiler](core/shader/recompiler/Recompiler.cpp) successfully produces SPIR-V (validated via [Spirv-Tools](3rdparty/SPIRV-Tools) when built with `ANYPS5_ENABLE_SPIRV_TOOLS`).

## Compatibility

Test reports go in the [Discussions](https://github.com/vabxsen/PS2PC/discussions), one thread per title. Per-game progress of upstream AnyPS5 (stage reached, open blockers, libraries and GPU coverage) is tracked on its [blocker map](https://alxcbtw.github.io/anyps5-roadmap/), a community project built from public GitHub data ([source](https://github.com/AlxcBTW/anyps5-roadmap)).

## Input mapping

SDL-mapped game controllers are supported, including analog sticks and triggers. Keyboard and mouse controls can be configured with an `anyps5-input.ini` file. See [input mapping](docs/user/INPUT_MAPPING.md) for the supported devices and configuration format.

## Disclaimer

This project is intended for interoperability, research, preservation, and compatibility purposes. It does not include, distribute, or require copyrighted software, firmware, cryptographic keys, or proprietary libraries. Users are responsible for ensuring that any binaries used with this project are obtained and used in accordance with applicable laws and their respective license terms.

## Credits

PS2PC is based on [AnyPS5](https://github.com/boykopovar/AnyPS5) by boykopovar and its contributors, forked from upstream commit [`5d9dcc4`](https://github.com/boykopovar/AnyPS5/commit/5d9dcc42d) on 2026-10-16. All work up to that commit belongs to the AnyPS5 authors. This is a modified version; changes made since the fork are recorded in this repository's commit history.

## License

This project is licensed under the GNU General Public License version 2 only, the same license as AnyPS5.
