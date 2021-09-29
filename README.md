# install after init
npm install -g mbt
cf install-plugin multiapps
npm install ui5-middleware-simpleproxy
npm install -g @sap/ux-ui5-tooling
npm install -g @sap/generator-fiori

# Test apps local
cds watch
ui5 serve


# Build project and Deploy
mbt build -t ./
cf deploy cpapp_1.0.0.mtar


# Delete apps and associations
cf undeploy cpapp --delete-service-keys --delete-services


# List to apps
cf services
cf apps


# Getting Started

Welcome to your new project.

It contains these folders and files, following our recommended project layout:

File or Folder | Purpose
---------|----------
`app/` | content for UI frontends goes here
`db/` | your domain models and data go here
`srv/` | your service models and code go here
`package.json` | project metadata and configuration
`readme.md` | this getting started guide


## Next Steps

- Open a new terminal and run `cds watch` 
- (in VS Code simply choose _**Terminal** > Run Task > cds watch_)
- Start adding content, for example, a [db/schema.cds](db/schema.cds).


## Learn More

Learn more at https://cap.cloud.sap/docs/get-started/.
