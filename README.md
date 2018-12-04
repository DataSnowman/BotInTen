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

1. In the Azure Portal open `Web App Bot` and select `Test in Web Chat`

![testInWebChat](https://raw.githubusercontent.com/DataSnowman/BotInTen/master/images/testInWebChat.png)