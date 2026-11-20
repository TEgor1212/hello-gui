# hello-gui 🎨🐹

A cross-platform desktop GUI application built with Go and [Fyne](https://fyne.io/). Features a greeting button, an output label, and version information — packaged for Linux, macOS, and Windows via GitHub Releases.

[![Go GUI CI/CD](https://github.com/TEgor1212/hello-gui/actions/workflows/ci.yml/badge.svg)](https://github.com/TEgor1212/hello-gui/actions/workflows/ci.yml)

## How to run

```bash
go run .
```

Requires Go 1.23+ and Fyne system dependencies. See [Fyne prerequisites](https://developer.fyne.io/started/#prerequisites).

## Features

- Greeting button that displays a message
- Version label (injected at build time via `-ldflags`)
- Cross-platform: runs on Linux, macOS, and Windows

## CI/CD

On every push to `main`:

- **Format check:** `gofmt -l .`
- **Lint:** `go vet ./...`
- **Test:** `go test ./... -v`
- **Smoke build:** `go build`

On pushing a tag `v*`:

- **Cross-platform release binaries** are built and uploaded to GitHub Releases:
  - `hello-gui-linux-x64`
  - `hello-gui-macos-arm64`
  - `hello-gui-windows-x64.exe`