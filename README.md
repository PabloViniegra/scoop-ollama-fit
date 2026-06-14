# scoop-ollama-fit

[Scoop](https://scoop.sh) bucket for [ollama-fit](https://github.com/PabloViniegra/tui-ollama-go), a CLI to check if a model fits your hardware.

## Install

```powershell
scoop bucket add PabloViniegra/scoop-ollama-fit
scoop install ollama-fit
```

## Usage

After installing, run:

```powershell
ollama-fit fit <modelo>
```

Or use the TUI:

```powershell
ollama-fit
```

## Bump flow

When a new version of `ollama-fit` is released, update the manifest with the new version and hash.

1. Download the Windows release asset:

```powershell
Invoke-WebRequest -Uri "https://github.com/PabloViniegra/tui-ollama-go/releases/download/v0.2.1/tui-ollama-go_0.2.1_windows_amd64.zip" -OutFile "tui-ollama-go_0.2.1_windows_amd64.zip"
```

2. Compute the SHA256 hash:

```powershell
Get-FileHash -Algorithm SHA256 -Path "tui-ollama-go_0.2.1_windows_amd64.zip"
```

3. Update `bucket/ollama-fit.json`:
   - Replace `"version"` with the new version number.
   - Replace `"hash"` with the computed SHA256 hash.
   - Replace the `"url"` with the new release asset URL.

4. Stage, commit, and push:

```powershell
git add bucket/ollama-fit.json
$ver = "0.2.1" # or new version
git commit -m "feat: bump ollama-fit to $ver"
git push origin main
```
