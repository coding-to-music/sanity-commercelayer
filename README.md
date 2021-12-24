# Commerce Layer Starter

A multi-country ecommerce starter that features the sanity studio built with Commerce Layer, Next.js, and deployed to Netlify.

![](https://raw.githubusercontent.com/commercelayer/sanity-template-commercelayer/main/.sanity-template/assets/preview.jpg 'A preview image showing the frontend demo with some products.')

![](https://raw.githubusercontent.com/commercelayer/sanity-template-commercelayer/main/.sanity-template/assets/studio.png 'A screenshot of Commerce Layer Sanity studio')

## What is Commerce Layer?

[Commerce Layer](https://commercelayer.io) is a multi-market commerce API and order management system that lets you add global shopping capabilities to any website, mobile app, chatbot, wearable, voice, or IoT device, with ease. Compose your stack with the best-of-breed tools you already mastered and love. Make any experience shoppable, anywhere, through a blazing-fast, enterprise-grade, and secure API.

## Table of contents

- [Starter features](#starter-features)
- [Getting started](#getting-started)
  - [⚙️ Installation guide](#%EF%B8%8F-installation-guide)
  - [⬇️ Import test studio content](#%EF%B8%8F-import-test-studio-content)
  - [⬇️ Seed Commerce Layer data](#%EF%B8%8F-seed-commerce-layer-data)
- [Contributors guide](#contributors-guide)
- [Need help?](#need-help)
- [License](#license)

## Starter features

- An ecommerce storefront built with Nextjs, [Commerce Layer react components library](https://github.com/commercelayer/commercelayer-react-components), and Tailwind CSS.
- International shopping capabilities powered by [Commerce Layer](https://commercelayer.io) APIs.
- [Micro CLI seeder](https://github.com/commercelayer/commercelayer-seeder-cli) to import Commerce Layer data.
- Structured content on Sanity CMS.
- Localization support.
- Deployment configuration to Netlify.

## Getting started

The quickest way to get up and running is to go to https://www.sanity.io/create?template=commercelayer/sanity-template-commercelayer and create a new project by following the instructions on Sanity.

Alternatively, you can clone this repository, configure the starter, import the dataset into your Sanity studio, import some test data into your Commerce Layer organization, and deploy your application.

![](https://raw.githubusercontent.com/commercelayer/sanity-template-commercelayer/main/.sanity-template/assets/sanity.png 'A screenshot of Commerce Layer Starter in sanity.io')

### ⚙️ Installation guide

1. Clone this repository ([learn how to do this](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository)).

2. Rename the `/env.example` file to `.env` and add the following:

- Your project ID, dataset, and token from [manage.sanity.io](https://manage.sanity.io).
- Your client ID and client endpoint from [Commerce Layer](https://core.commercelayer.io/users/sign_up).

3. Run the command below to install the necessary dependencies of your project:

```bash
npm install && cd /studio && sanity install
```

4. Add your `projectTitle`, `projectId,` and `dataset` in `/studio/sanity.json`.

5. Run the command below to start the development server:

```bash
npm run dev
```

This will run the frontend at http://localhost:3000 



and Sanity studio at http://localhost:3333/desk

![image](https://user-images.githubusercontent.com/3156358/147373463-f6973e9e-de32-41df-b6c5-1a7443b70860.png)

### ⬇️ Import test studio content (ignore if you created via Sanity dataset creation)

> If you set up your project from the starters page on Sanity, you should skip this step as Sanity will automatically add the dataset's content.

1. Extract the `production.tar.gz` file in `/.sanity-template/data` directory using the command below:

```bash
tar -xf production.tar.gz
```

The extracted folder name should look like `production-export-2021-02-26t14-15-56-557z`.

2. Run the command below in `/studio` to import the `data.ndjson` file in the extracted folder.

```bash
sanity dataset import ../.sanity-template/data/<name of extracted folder>/data.ndjson <your_dataset>
```

3. Check the frontend and studio now to preview the imported content.

### ⬇️ Seed Commerce Layer data

1. Create a [Commerce Layer account](https://core.commercelayer.io/users/sign_up).

Also, general info here: https://docs.commercelayer.io/developers/v/how-tos/

2. Create a new organization.

3. Create a new application in **Settings > Applications** with **Kind** set to `integration`, and **Role** set to `admin`.

4. In your newly created application, copy your Client ID and Client Secret.

5. Install the Commerce Layer Seeder which is available as an [npm package](https://www.npmjs.com/package/@commercelayer/commercelayer-seeder-cli):

```
// npm
npm install -g @commercelayer/commercelayer-seeder-cli

// yarn
yarn global add @commercelayer/commercelayer-seeder-cli
```

Output
```java
✓ Importing the seed in Commerce Layer... 21.3 secs
🎉The seed has been imported with success.
```

https://dashboard.commercelayer.io/

6. Run the command below to import a [set of products](https://data.commercelayer.app/seed/skus.json), related [prices](https://data.commercelayer.app/seed/prices.json), and [inventory](https://data.commercelayer.app/seed/stock_items.json) into your organization.

```bash
commercelayer-seeder -i <your-client-id> -s <your-client-secret> -e https://<yourdomain>.commercelayer.io
```

7. To see the commands for other seeder options, type the command below:

```bash
commercelayer-seeder --help
```

Output
```java
Usage: commercelayer-seeder [options]

Import a Commerce Layer seeder in your organization

Options:
  -v, --version                        output the current version
  -V, --version                        output the version number
  -i, --clientId <clientId>            your Commerce Layer application client ID
  -s, --clientSecret <clientSecret>    your Commerce Layer application client secret
  -e, --endpoint <endpoint>            your Commerce Layer application endpoint
  -b, --businessModel <businessModel>  the kind of business model you want to import
  -m, --maxItems <maxItems>            the maximum number of SKUs that will be imported
  -u, --resourcesUrl <resourcesUrl>    the resources URL or local path
  -h, --help                           display help for command
```

## Contributors guide

1. Fork [this repository](https://github.com/commercelayer/sanity-template-commercelayer) (learn how to do this [here](https://help.github.com/articles/fork-a-repo)).

2. Clone the forked repository like so:

```bash
git clone https://github.com/<your username>/sanity-template-commercelayer.git && cd sanity-template-commercelayer
```

3. Make your changes and create a pull request ([learn how to do this](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)).

4. Someone will attend to your pull request and provide some feedback.

## Need help?

1. Request an invite to join [Commerce Layer's Slack community](https://commercelayer.io/developers) (kindly scroll down to the bottom of the page).

2. Create an [issue](https://github.com/commercelayer/sanity-template-commercelayer/issues) in this repository.

3. Ping us [on Twitter](https://twitter.com/commercelayer).

## License

This repository is published under the [MIT](LICENSE) license.

---

Want to learn more about how we built this starter and how you can build yours? Sign up for our [newsletter](https://commercelayer.io) to get notified once we publish the article.
