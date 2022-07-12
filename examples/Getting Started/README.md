
# Using Xooa NFT Image Asset 

Once XooaSDK-x.x.x.unitypackage is imported in Unity Project and configure authentication token.

    Login to [Xooa Design Console](https://xooa.com/blockchain)

    Click on Design button of App from App List section

    Go to API > Identities and then click Add New

    Enter an identity name and under API Access Permission, select Read.

    Click Create. You’ll get a message that the identity has been enrolled and the API token generated.

    Before you dismiss the message, click Copy, The token is now in the clipboard.



Open ExampleImageLoadScene.scene from Assets > Xooa > Examples folder.

ExampleImageLoadController Game object script loads NFT from app and display it within Unity.

Modify below code from ExampleImageLoadController.cs as per requirement. 

```
 RequestFilters filters = new RequestFilters();
            filters.AddFilter("type", "ERC-721 Token", "eq");
            NFTItemsCollection collections = await XooaNFTRequest.BuildRequest().AddRequestFilters(filters).SetLimit(100).Execute();

            Debug.Log("Loading Textures....");
            await collections.LoadItemsTextures("asset");
```            

Refer to Xooa [API Documentation](https://api.xooa.com/explorer/#!/NFT/NFT_GetAllTokens) for additional fiters.