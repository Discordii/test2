# FEDPromptly Desktop App — Setup

This folder contains a GitHub Actions workflow that packages
https://www.fedpromptly.com/home into a native desktop app (.exe / .msi)
using Pake (https://github.com/tw93/Pake).

## How to use

1. Unzip this into the ROOT of your GitHub repo, so the file ends up at:
   .github/workflows/build.yml

2. Commit and push it to GitHub.

3. In your repo: Settings -> Actions -> General -> Workflow permissions
   -> select "Read and write permissions" -> Save.

4. Go to the Actions tab -> click "Build FEDPromptly Desktop App"
   -> click "Run workflow".

5. Wait for the run to turn green (first run: ~10-15 min, it's compiling
   Pake itself). Open the finished run and scroll down to "Artifacts" --
   download the zip there. That's your actual installable app.

## Notes

- The built app just opens a window pointed at your live site. It needs
  internet to load, same as a browser tab -- it's not an offline copy.
- To also build for Mac/Linux, edit build.yml and add macos-latest and/or
  ubuntu-latest to the "matrix: os:" list.
- To use your own icon, uncomment the "icon:" line in build.yml and point
  it at a hosted image URL.
