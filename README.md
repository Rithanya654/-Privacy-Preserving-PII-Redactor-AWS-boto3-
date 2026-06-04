# Hosted Download Page

This folder is ready to become your static hosted page.

## Build the downloadable artifacts

Run:

```bash
./build_hosted_assets.sh
```

That script populates `site/downloads/` with:

- `InvoicePIIRedactor-linux-x86_64.zip`
- `pii-redactor-backend.zip`
- `InvoicePIIRedactor-win64.exe` if a Windows build exists in `dist/`

If the Windows executable is still missing, the script writes `site/downloads/WINDOWS_BUILD_REQUIRED.txt` so you know what filename the page expects.

## Build the Windows executable

PyInstaller builds Windows executables on Windows. From a Windows machine with this repo checked out:

```powershell
.\build_windows.ps1
```

That produces:

- `dist\InvoicePIIRedactor.exe`
- `site\downloads\InvoicePIIRedactor-win64.exe`

## Local smoke test

You can open `site/index.html` directly, or serve the folder with any static file server before uploading it to AWS.

## Publish

Upload the contents of `site/` to your S3 static site bucket, CloudFront origin, or any other static host.
