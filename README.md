# Chrome Extension Development Template
This is a template repository that automates Chrome extension development and hosting in an enterprise environment. When you make changes to the code in the extension/ directory, a GitHub Action will take care of:
1. Compiling the extension.
2. Hosting the compiled extension on GitHub pages.
3. Providing the proper update.xml file so the extension auto-updates for browsers including force-installed extensions.

# Setup
1. [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) this repository.
2. Create your own extension private key with a Linux command like:
```
openssl genrsa 2048 | openssl pkcs8 -topk8 -nocrypt -out key.pem
```
IMPORTANT! Don't lose your extension private key! If you do you'll no longer be able to update the extension.

3. Save the private key [to a GitHub secret for the repository github actions](https://docs.github.com/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets#creating-secrets-for-a-repository). Name the secret `EXTENSION_KEY`.
4. Enable GitHub Actions for your repository (look under the Actions tab).
