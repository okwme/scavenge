# Scaffold

We'll be using a tool called `scaffold` to help us spin up a boilerplate app quickly. To use `scaffold` first clone and install it on your local machine:
```bash
git clone git@github.com:cosmos/scaffold.git
cd scaffold
make install
scaffold --help
```

Afterwards, you should see the following help screen displayed:
```bash
This CLI helps in scaffolding out CosmosSDK based applications

Usage:
  scaffold [command]

Available Commands:
  app         Generates an empty application boilerplate
  help        Help about any command
  module      Generate an empty module for use in the Cosmos-SDK
  tutorial    Generates one of the tutorial apps, currently either the 'nameservice' or 'hellochain'

Flags:
  -c, --config string        config file (default is $HOME/.scaffold.yaml)
  -h, --help                 help for scaffold
  -o, --output-path string   Path to output
  -t, --toggle               Help message for toggle

Use "scaffold [command] --help" for more information about a command.
```

Now that you have the `scaffold` command available try looking at the help screen of the `app` command by typing `scaffold app --help`.
```bash
Generates an empty application boilerplate

Usage:
  scaffold app [lvl] [user] [repo] [flags]

Flags:
  -h, --help   help for app

Global Flags:
  -c, --config string        config file (default is $HOME/.scaffold.yaml)
  -o, --output-path string   Path to output
```
We will use this command to generate a basic boilerplate application. The parameter `lvl` should be filled with `lvl-1` (which is currently the only lvl available). You should use your own github username for `user` and come up with a name for `repo`. I will be using `scavenge` as the repo name for this tutorial. Using my github handle (`okwme`) the final command should look like:
```bash
scaffold app lvl-1 okwme scavenge
```
This should generate a folder structure inside of a directory called `scavenge` of your current working directory. Now that we have an app boilerplate we want to add some custom functionality to it and build our scavenge module. First change into the app directory with `cd scavenge` then change into the modules directory with `cd x`. Now you can run the `module` command of the `scaffold` tool, but first check out the help screen of it with `scaffold module --help`:
```bash
Generate an empty module for use in the Cosmos-SDK

Usage:
  scaffold module [user] [repo] [moduleName] [flags]

Flags:
  -h, --help   help for module

Global Flags:
  -c, --config string        config file (default is $HOME/.scaffold.yaml)
  -o, --output-path string   Path to output
```
Similarly it asks for your github username as `user` and the name repository name as `repo`. It also asks for the name you'd like to give to this new module. I will also be using the name `scavenge` for the module name during this tutorial.
```bash
scaffold module okwme scavenge scavenge
```
Now we have generated a boilerplate application with a boilerplate module. Our next step will be to [define Messages]("04-messages.md").