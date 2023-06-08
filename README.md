# cmake-and-upload

## Usage

```yaml
# # Required
#   token:
#     description: 'Personal token'
#     required: true
#     default: ${{ github.token }}

name: CMake_And_Upload

permissions:
  contents: write
  actions: write

on: 
  workflow_run:
    workflows:
      - Release_Version
    types:
      - completed

jobs:
  cmake_and_upload:
    runs-on: windows-2019
    steps:
      - name: cmake-and-upload
        uses: gendloop/cmake-and-upload@main
        with:
          token: ${{ secrets.GITHUB_TOKEN }}

```

