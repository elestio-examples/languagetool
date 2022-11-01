# LanguageTool CI/CD pipeline

<a href="https://dash.elest.io/deploy?source=cicd&social=dockerCompose&url=https://github.com/elestio-examples/languagetool"><img src="deploy-on-elestio.png" alt="Deploy on Elest.io" width="180px" /></a>

Deploy LanguageTool server with CI/CD on Elestio

<img src="languagetool.png" style='width: 100%;'/>
<br/>
<br/>

# API usage

Youy can now use LanguageTool REST API like this:

    curl -X POST --header 'Content-Type: application/x-www-form-urlencoded' --header 'Accept: application/json' -d 'text=hey%20whats%20up&language=auto&enabledOnly=false' 'https://[CI_CD_DOMAIN]/v2/check'

# Integrations and plugins

## Step 1.

Go to the <a target="_blank" href="https://languagetool.org/">LangagueTool website</a> and choose the app or Add-on of your choice.
In our case, we will choose Chrome

<img src="step-01.png" style='width: 600px; max-width:100%;'/>

## Step 2.

In google chrome, go to the extensions tab and choose Grammar & Spell Checker.

<img src="step-02.png" style='width: 600px; max-width:100%;'/>
<img src="step-03.png" style='width: 600px; max-width:100%;'/>

## Step 3.

Click on the cog wheel at the bottom right of the tab

<img src="step-04.png" style='width: 600px; max-width:100%;'/>

## Step 4.

Go to the very bottom of the page and choose Advanced settings

<img src="step-05.png" style='width: 600px; max-width:100%;'/>

## Step 5.

In the drop-down menu choose the button Other server.
And type your server address.
For you, it will be:
https://[CI_CD_DOMAIN]/v2
Save

<img src="step-06.png" style='width: 600px; max-width:100%;'/>

That's all. Now you can go in Gmail for example, and type a mail.
LanguageTool will do the job!

<img src="step-07.png" style='width: 600px; max-width:100%;'/>
<img src="step-08.png" style='width: 600px; max-width:100%;'/>
