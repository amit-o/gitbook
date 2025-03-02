# cy2

{% hint style="info" %}
Please note:&#x20;

Cypress introduced a breaking change in versions 11 and 12. Please make sure to use the latest version of cy2. Read more at [https://currents.dev/readme/guides/cypress-compatibility](https://currents.dev/readme/guides/cypress-compatibility)
{% endhint %}

`cy2` is an [NPM package](https://www.npmjs.com/package/cy2) that Integrates Cypress with alternative cloud services like Sorry Cypress or Currents by setting the environment variable `CYPRESS_API_URL.`

The command passes down to cypress all the CLI flags, so you can just use it instead of `cypress`&#x20;

```bash
$ npm install -g cy2

$ export CYPRESS_API_URL="https://sorry.yourdomain.com/"
$ cy2 run --record --key XXX --parallel --ci-build-id `date +%s`
```

* Running the command above will invoke your default cypress version with the flags you've provided. It will also modify the internal cypress configuration to use a different API URL.
* If no URL is provided, it will use the default `cypress` package configuration
* On Windows set `CYPRESS_API_URL` in the CMD shell with `set CYPRESS_API_URL=https://sorry.yourdomain.com/` (Don't use quotes (`"`) because the Windows CMD takes them literally unlike the Linux shells)

{% hint style="warning" %}
MacOS Ventura users:

Running \`cy2\` in an interactive shell can fail with `EPERM: operation not permitted` unless you need to explicitly allow the shell app to modify other applications.

Add the shell app of your choice to the allowed list.

**Mac OS Settings > Privacy and Security > App Management**

![cy2 EPERM - adding shell to App Management allowed list](<../.gitbook/assets/CleanShot 2022-11-03 at 00.04.10@2x.png>)
{% endhint %}

****
