# typst-action
GitHub Action to compile Typst documents

# Inputs
- `input_files`

The Typst file(s) to be compiled. This input is required. You can also pass multiple files as a multi-line string to compile multiple documents. For example:
```
- uses:  Jarivanbakel/typst-action@v1
  with:
    input_files: |
      file1.typ 
      file2.typ
```
- `working_directory`
The working directory for this action.

# Example
```
name: Build Typst document
on: [push]
jobs:
  build_typst:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3
      - uses:  Jarivanbakel/typst-action@v1
        with:
          input_files: file1.typ
      - name: Upload PDF file
        uses: actions/upload-artifact@v3
        with:
          name: PDF
          path: main.pdf
```
# License
