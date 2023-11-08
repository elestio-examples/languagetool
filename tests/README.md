<a href="https://elest.io">
  <img src="https://elest.io/images/elestio.svg" alt="elest.io" width="150" height="75">
</a>

[![Discord](https://img.shields.io/static/v1.svg?logo=discord&color=f78A38&labelColor=083468&logoColor=ffffff&style=for-the-badge&label=Discord&message=community)](https://discord.gg/4T4JGaMYrD "Get instant assistance and engage in live discussions with both the community and team through our chat feature.")
[![Elestio examples](https://img.shields.io/static/v1.svg?logo=github&color=f78A38&labelColor=083468&logoColor=ffffff&style=for-the-badge&label=github&message=open%20source)](https://github.com/elestio-examples "Access the source code for all our repositories by viewing them.")
[![Blog](https://img.shields.io/static/v1.svg?color=f78A38&labelColor=083468&logoColor=ffffff&style=for-the-badge&label=elest.io&message=Blog)](https://blog.elest.io "Latest news about elestio, open source software, and DevOps techniques.")

# Languagetool, verified and packaged by Elestio

A better community platform for the modern web.

[Languagetool](https://github.com/languagetool-org/languagetool/) is an Open Source proofreading software for English, Spanish, French, German, Portuguese, Polish, Dutch, and more than 20 other languages. It finds many errors that a simple spell checker cannot detect.is an Open Source proofreading software for English, Spanish, French, German, Portuguese, Polish, Dutch, and more than 20 other languages. It finds many errors that a simple spell checker cannot detect.

<img src="https://github.com/elestio-examples/languagetool/raw/main/languagetool.png" alt="Languagetool" width="800">


# API usage

You can now use LanguageTool REST API like this:

    curl -X POST --header 'Content-Type: application/x-www-form-urlencoded' --header 'Accept: application/json' -d 'text=hey%20whats%20up&language=auto&enabledOnly=false' 'https://[CI_CD_DOMAIN]/v2/check'

# Integrations and plugins

## Step 1.

Go to the <a target="_blank" href="https://languagetool.org/">LangagueTool website</a> and choose the app or Add-on of your choice.
In our case, we will choose Chrome

<img src="https://github.com/elestio-examples/languagetool/raw/main/step-01.png" style='width: 600px; max-width:100%;'/>

## Step 2.

In google chrome, go to the extensions tab and choose Grammar & Spell Checker.

<img src="https://github.com/elestio-examples/languagetool/raw/main/step-02.png" style='width: 600px; max-width:100%;'/>
<img src="https://github.com/elestio-examples/languagetool/raw/main/step-03.png" style='width: 600px; max-width:100%;'/>

## Step 3.

Click on the cog wheel at the bottom right of the tab

<img src="https://github.com/elestio-examples/languagetool/raw/main/step-04.png" style='width: 600px; max-width:100%;'/>

## Step 4.

Go to the very bottom of the page and choose Advanced settings

<img src="https://github.com/elestio-examples/languagetool/raw/main/step-05.png" style='width: 600px; max-width:100%;'/>

## Step 5.

In the drop-down menu choose the button Other server.
And type your server address.
For you, it will be:
https://[CI_CD_DOMAIN]/v2
Save

<img src="https://github.com/elestio-examples/languagetool/raw/main/step-06.png" style='width: 600px; max-width:100%;'/>

That's all. Now you can go in Gmail for example, and type a mail.
LanguageTool will do the job!

<img src="https://github.com/elestio-examples/languagetool/raw/main/step-07.png" style='width: 600px; max-width:100%;'/>
<img src="https://github.com/elestio-examples/languagetool/raw/main/step-08.png" style='width: 600px; max-width:100%;'/>


Deploy a <a target="_blank" href="https://elest.io/open-source/languagetool">fully managed languagetool</a> on <a target="_blank" href="https://elest.io/">elest.io</a> Free & Source Available Messaging Platform for Marketing, Support & Sales .

[![deploy](https://github.com/elestio-examples/languagetool/raw/main/deploy-on-elestio.png)](https://dash.elest.io/deploy?source=cicd&social=dockerCompose&url=https://github.com/elestio-examples/languagetool)

# Why use Elestio images?

- Elestio stays in sync with updates from the original source and quickly releases new versions of this image through our automated processes.
- Elestio images provide timely access to the most recent bug fixes and features.
- Our team performs quality control checks to ensure the products we release meet our high standards.

# Usage

## Git clone

You can deploy it easily with the following command:

    git clone https://github.com/elestio-examples/languagetool.git

Copy the .env file from tests folder to the project directory

    cp ./tests/.env ./.env

Edit the .env file with your own values.

    mkdir -p ./datastorage
    chown -R 1000:1000 ./datastorage

Run the project with the following command

    docker-compose up -d

You can access the Web UI at: `http://your-domain:8010`

## Docker-compose

Here are some example snippets to help you get started creating a container.

      
        version: "3"

        services:
        languagetool:
            image: elestio4test/languagetool:${SOFTWARE_VERSION_TAG}
            ports:
            - 172.17.0.1:8010:8010
            environment:
            - langtool_languageModel=/ngrams
            - Java_Xms=512m
            - Java_Xmx=1g
            volumes:
            - ./data:/ngrams


### Environment variables

|       Variable       | Value (example) |
| :------------------: | :-------------: |
| SOFTWARE_VERSION_TAG |     latest      |


# Maintenance

## Logging

The Elestio Languagetool Docker image sends the container logs to stdout. To view the logs, you can use the following command:

    docker-compose logs -f

To stop the stack you can use the following command:

    docker-compose down

## Backup and Restore with Docker Compose

To make backup and restore operations easier, we are using folder volume mounts. You can simply stop your stack with docker-compose down, then backup all the files and subfolders in the folder near the docker-compose.yml file.

Creating a ZIP Archive
For example, if you want to create a ZIP archive, navigate to the folder where you have your docker-compose.yml file and use this command:

    zip -r myarchive.zip .

Restoring from ZIP Archive
To restore from a ZIP archive, unzip the archive into the original folder using the following command:

    unzip myarchive.zip -d /path/to/original/folder

Starting Your Stack
Once your backup is complete, you can start your stack again with the following command:

    docker-compose up -d

That's it! With these simple steps, you can easily backup and restore your data volumes using Docker Compose.

# Links

- <a target="_blank" href="https://languagetool.org/http-api/swagger-ui/#!/default/post_check">Languagetool documentation</a>

- <a target="_blank" href="https://github.com/languagetool-org/languagetool/">Languagetool Github repository</a>

- <a target="_blank" href="https://github.com/elestio-examples/languagetool">Elestio/Languagetool Github repository</a>
