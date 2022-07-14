
# Using Xooa NFT Image Asset 

Once XooaSDK-x.x.x.unitypackage is imported into the Unity Project and the authentication token has been configured, follow the steps below

    Login to [Xooa Design Console](https://xooa.com/blockchain)

    Click on Design button of the App from the App List section

    Go to API > Identities and click Add New

    Enter an identity name and under API Access Permission, select Read.

    Click Create. You’ll get a message that the identity has been enrolled and the API token generated.

    Before you dismiss the message, click Copy. The API token will be copied to the clipboard.



Open ExampleImageLoadScene.scene from Assets > Xooa > Examples folder.

ExampleImageLoadController Game object script loads NFT from the app and displays it within the Unity Project.

Modify below code from ExampleImageLoadController.cs as per the requirement. 

```
 RequestFilters filters = new RequestFilters();
            filters.AddFilter("type", "ERC-721 Token", "eq");
            NFTItemsCollection collections = await XooaNFTRequest.BuildRequest().AddRequestFilters(filters).SetLimit(100).Execute();

            Debug.Log("Loading Textures....");
            await collections.LoadItemsTextures("asset");
```            

Refer to Xooa [API Documentation](https://api.xooa.com/explorer/#!/NFT/NFT_GetAllTokens) for additional fiters.
