File operators are most often used with merge when needing to merge specific files together. Note that when doing this, you will need to use `eval-all` to ensure all yaml documents are loaded into memory before performing the merge (as opposed to `eval` which runs the expression once per document).

## Merging files
Note the use of eval-all to ensure all documents are loaded into memory.
```bash
yq eval-all 'select(fileIndex == 0) * select(filename == "file2.yaml")' file1.yaml file2.yaml
```