
# Using Xooa NFT scriptable object Asset

Login to [Xooa Design Console](https://xooa.com/blockchain) and Deploy Platform minted marketplace app from solution templates, if the app is not deployed yet

Once the app is ready, click Design > Forms > Import

Download sample inventory form [here](./Mint%20Game%20Object.json) then browse or drag & drop to file section and click Import

Setup the Page action and Roles permissions to mint Game object

In Unity Project, create Game Object Asset Bundle by clicking on Main Menu > Xooa > Build Asset Bundles. This action will generate Asset bundles in Assets > Xooa > GeneratedAssetBundles folder

Go to Xooa app runtime console and mint game object with generated asset. Refer to the below screenshot

![Screenshot4](../../Screenshots/Screenshot4.png)

Open ExampleScriptObjectController file in unity and replace <USER EMAIL> with user's actual email id with which the token was minted

```
NFTItemsCollection collections = await XooaNFTRequest.BuildRequest()
            .AddEmail("<USER EMAIL>")
            .AddRequestFilters(filters).SetLimit(10).Execute();
```

Run the ExampleScriptObjectScene scene.

Refer to Xooa [API Documentation](https://api.xooa.com/explorer/#!/NFT/NFT_GetAllTokens) for additional filters
