# Trimmed Karavan Designer for embedding

The dirigiblelabs/main contains the trimmed designer.

This branch was started out like this:
```
git checkout tags/3.20.1 -b 3.20.1-branch
// add changes
git checkout -b dirigiblelabs/main
```

## Setup
```
cd camel-karavan
git checkout -b dirigiblelabs/main
mvn clean compile exec:java -Dexec.mainClass="org.apache.camel.karavan.generator.KaravanGenerator" -f karavan-generator
cd karavan-core
yarn install
cd ../karavan-designer
yarn install
```

#### To build a designer page for dirigible:
```
yarn build
rm -rf /build/components/.gitignore
rm -rf /build/kamelets/.gitignore
```
Copy the files from `camel-karavan/karavan-designer/build` folder into `dirigible/components/ide-ui-integrations/src/main/resources/META-INF/dirigible/ide-integrations/designer`

#### To start the page locally without dirigible:

remove this line `"homepage": "/services/web/ide-integration/designer/”` from `camel-karavan/karavan-designer/package.json` at line 11
```
yarn start
```
