## ES-Linting Errors
After a pull request is approved, you may come across a situation where you get something similar to the following pipeline failure message:

```
/opt/atlassian/pipelines/agent/build/presentation/components/custom/content/BackorderInquiry/parts/table/index.tsx
  1:1  error  Run autofix to sort these imports!  simple-import-sort/imports
✖ 1 problem (1 error, 0 warnings)
  1 error and 0 warnings potentially fixable with the --fix option.
```

This indicates that the file you were working on never got properly formatted. Possible reasons this happened are:

1. You need to install the 'ES-Lint' VSCode plugin
2. You need to install the 'Prettier' VSCode plugin

Once you've ensured that your plugins are installed, you can run the following command to manually format your project: `yarn fix-lint`

After the process is done running, commit and push your changes. The pipeline should succeed if there are no other issues.