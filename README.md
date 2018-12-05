# Welcome to a hands-on workshop for **Building a Web App Bot in 10 Minutes** using Azure Portal, QnA Maker, the Bot service, and Microsoft Teams

![steps](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/steps.png)


## Prerequisites

To deploy the Azure resources required for this lab, you will need:

1. An [Azure account](https://portal.azure.com)
   
   `Note:` If you don't have an account you can create your free Azure account [here](https://azure.microsoft.com/en-us/free/)

2. Clone this GitHub repository using Git and the following commands: 

`git clone https://github.com/DataSnowman/BotInTen.git`

## Create an Azure Resource group
![createResourceGroup](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/createResourceGroup.png)

## Create an Azure QnA Maker Cognitive Service in the Resource group created earlier using the Azure Portal

1. Search for `QnA` in the Azure Portal

![createQnAmaker](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/createQnAmaker.png)

2. Click `Create`

## Create Knowledge Base

1. Sign in to the [QnA Maker](https://www.qnamaker.ai/) portal.

2. Select `Create a knowledge base` from the top menu.

3. Skip Step 1 becasue we already created a QnA service, but complete steps 2-5.

    In step 4 enter a URL of your choice to an online FAQ like this on on [Slavic Languages](https://slavic.ucla.edu/languages/russian/faq/)

4. Click `Create your KB`

![createKB](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/createKB.png)

5. To test the Knowledge base click the `Test` button and enter a question that was imported by the FAQ to that you entered manually and Saved and Trained

![testKB](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/testKB.png)

6. Click `Publish` to publish the Knowledge base

![publishKB](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/publishKB.png)

For more details check out [Tutorial: Create a knowledge base then answer question via the QnA Maker portal](https://docs.microsoft.com/en-us/azure/cognitive-services/qnamaker/tutorials/create-publish-query-in-portal)

## Create Azure Web App Bot in the Resource group created earlier using the Azure Portal

1. Search for `Bot` in the Azure Portal and select `Web App Bot`

![createWebAppBot](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/createWebAppBot.png)

2. Click `Create`

For more details check out [Tutorial: Create a QnA Bot with Azure Bot Service v3](https://docs.microsoft.com/en-us/azure/cognitive-services/qnamaker/tutorials/create-qna-bot)

## Test and Configure Bot to use Knowledge base

1. In the Azure Portal open the `Web App Bot` and select `Test in Web Chat`

![testInWebChat](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/testInWebChat.png)

For more details on how to do this [Get the App Setting](https://aka.ms/qnaabssetup) from QnA Maker.

## Connect your QnA Maker knowledge base to the bot

1. Open **Application Settings** and edit the **QnAKnowledgebaseId**, **QnAAuthKey**, and the **QnAEndpointHostName** fields to contain the values of your QnA Maker knowledge base.

    ![app settings](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/application-settings.png)

2. Click `Save`

3. Get your knowledge base ID, host url, and the endpoint key from the settings tab of your knowledge base in the QnA Maker portal.

    - Sign in to [QnA Maker](https://qnamaker.ai)
    - Go to `My knowledge bases` and select your Knowledge base name
    - Select the **Settings** tab
    - **Publish** your knowledge base, if not already done so

    ![QnA Maker values](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/qnamaker-settings-kbid-key.png)

    Note: Be careful to put the `QnAAuthKey` (which is the last key in the deployment details) and the `QnAKnowledgebaseId` (which is the first ID in the deployment details) in the correct place in the Application settings.  If your bot is not working in `Test in Web Chat` it could be because you have these in the wrong place. 

## Test the bot

In the Azure portal, select **Test in Web Chat** to test the bot.

Type in something like `What languages are related to Russian?`

![QnA Maker bot](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/qna-bot-web-chat-response.png)

The first time it might be a bit slow.  If it does not return an answer double check your values in `Application Settings` per the Note above.

Your QnA Bot answers from your knowledge base.

## Connect the bot to the Teams Channel

1. Click on Channels and click Teams.  Click `Save` and `Agree` to Terms of Service

![channels](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/channels.png)

2. Click on the `Microsoft Teams` Channel and `Open Microsoft Teams`

![connectToTeamsChannel](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/connectToTeamsChannel.png)

3. Ask the bot a question in teams like `What are the Slavic languages?`

![botInTeams](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/botInTeams.png)

## Deploy the bot into Teams

1. Click on Store > Bots > App Studio

![store](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/store.png)

2. Click on `Available`

![available](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/available.png)

3. Click on `Open` next to `Bot`

![appOpen](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/appOpen.png)

4. Click on `Manifest editor` and select `Create a new app`

![manifestEditor](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/manifestEditor.png)

5. Enter details into the Manifest.  Click `Generate` to generate an App ID

![manifestDetails1](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/manifestDetails1.png)

![manifestDetails2](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/manifestDetails2.png)

6. Click on Bots under the Capabilities section on the left navigation and click `Set up`

![setupBots](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/setupBots.png)

7. Choose `Existing bot` and provide a name for the bot, for the Bot ID choose `Select from one of my existing bots` and select the correct bot, and select the Scope in Teams and click `Create bot`

![nameScope](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/nameScope.png)

8. Click on `Test and distribute` and then click on `Install`

![testAndDistribute](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/testAndDistribute.png)

9. Choose the team you want the bot to be part of in `Add to a team` and select `Install`

![installBot](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/installBot.png)

10. Pick the channel where you want to use the app and click `Setup`

![pickChannel](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/pickChannel.png)

11. Click on the bot link, type a question, and click on the Conversation bubble icon

![conversation](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/conversation.png)

12. It works

![itWorks](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/itWorks.png)

If you would like to see a video on this check out Larry Jin and Mark Rackley's Ignite Theatre Session from Microsoft Ingite [THR2040 - Build a bot in five minutes](https://myignite.techcommunity.microsoft.com/sessions/65554?source=sessions#ignite-html-anchor)