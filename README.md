# Air

Hello cloud!

## Code

The source is hosted in multiple locations, by design[^1]. 😉

[GitLab](https://gitlab.com/) supports project hierarchies whereas GitHub doesn't; no problem.

```sh
export PROJECTS=~/code # your code location
mkdir -p $PROJECTS/deposition/apps/
cd $PROJECTS/deposition/apps/
```

```sh
git clone git@github.com:deposition-cloud/air.git --origin github
git remote add gitlab git@gitlab.com:deposition.cloud/apps/air.git
```

We can do this because git is a *distributed* version control system, whereas GitHub and GitLab are value-added SaaS that enable Pull Request-based workflows and other useful stuff like GitLab-CI pipelines.

Or

```sh
git clone git@gitlab.com:deposition.cloud/apps/air.git --origin gitlab
git remote add github git@github.com:deposition-cloud/air.git
```

TODO: add self-hosted git option

`git push` will use whichever remote you're tracking

TODO: ensure all public git repos are kept in sync

To push changes to both remotes

```sh
git push
git push gitlab # or, depending on your preferred default
git push github
```

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanations on how things work, consult the [Nuxt.js docs](https://nuxtjs.org).

## License

Ethically sourced under the [Atmosphere License](https://www.open-austin.org/atmosphere-license/)—like open source, for good.

[^1] it helps to be hands on with interoperability between SaaS providers, hence working with multiple developer communities is in and of itself an exercise in depositing the cloud
