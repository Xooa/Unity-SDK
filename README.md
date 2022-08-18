
# Xooa Unity SDK

Xooa Unity SDK is designed to integrate Xooa NFT Platform with Unity Engine.

This SDK provides capability to fetch NFT Assets and their details from Xooa NFT platform. The NFT Assets can be used as in-game objects as Texture, Scriptable Object or Video link.


## Installation

Download [XooaSDK.unitypackage](./XooaSDK-1.0.0.unitypackage)

Open Or Create Unity project .

Click Assets > Import Package > Custom Package... in the Assets menu.

Select downloaded **XooaSDK.unitypackage ** and **Import**.

Enter the Xooa API token in settings wizard. The Authentication token can be obtained from Xooa Design console > API tab. Now follow the steps given below to generate new API token.
       
## Create API Token

Login to [Xooa Design Console](https://xooa.com/blockchain)

Click on **Design** of the App in  **My Apps** section

Go to **API > Identities** and then click **Add New**

Enter an identity name and under **API Access Permission**, select **Read**.

Click **Create**. You’ll get a message that the identity has been enrolled and the API token is generated.

Before you dismiss the message, click **Copy**. The API token will be copied 
to the clipboard..

## Get API Endpoint

Login to [Xooa Design Console](https://xooa.com/blockchain)

Click on **Design** of the App in  **My Apps** section

Go to **API > Sandbox** and then copy the link under **API Endpoint**

## Steps to import Xooa SDK in Unity Project

![Screenshot1](./Screenshots/Screenshot1.png)

![Screenshot2](./Screenshots/Screenshot2.png)

![Screenshot3](./Screenshots/Screenshot3.png)

## Integration Code
``` 
using Xooa;


RequestFilters filters = new RequestFilters();
filters.AddFilter("type", "ERC-721 Token", "eq");
NFTItemsCollection collections = await XooaNFTRequest.BuildRequest().AddRequestFilters(filters).SetLimit(100).Execute();


await collections.LoadItemsTextures("asset");


foreach (NFTItem item in collections.GetItems()){
    var name = item.GetPropertyKeyValue("name");
    var description =item.GetPropertyKeyValue("description");
    var tokenId = item.GetKeyValue("token_id");
    
    // Your Logic...
}
```

## Examples
Go to **Assets > Xooa > Examples** folder in Unity project where Xooa SDK is imported.

The examples show the capability to load Xooa NFT Asset (Image and Scriptable Object) into the Unity Game.

[Click here](./examples/) for detailed documentation about examples.

Refer to Xooa [API Documentation](https://api.xooa.com/explorer/#!/NFT/NFT_GetAllTokens) here.
