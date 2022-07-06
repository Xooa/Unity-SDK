
# Xooa Unity SDK

Xooa Unity SDK for integration with Xooa NFT Platform.




## Installation

Download [XooaSDK.unitypackage](./XooaSDK.unitypackage)

    1. Open Or Create Unity project .

    2. Click Assets > Import Package > Custom Package... in the Assets menu.

    3. Select downloaded XooaSDK.unitypackage and Import.

    4. Enter Xooa API token in settings wizard
       Authentication token can be obtained from Xooa Design console API Tab.


## Example Scenes

Navigate to Assets > Xooa > Example > Example Image Load Scene


![Screenshot1](./Screenshots/Screenshot1.png)

![Screenshot2](./Screenshots/Screenshot2.png)

![Screenshot3](./Screenshots/Screenshot3.png)

## Code
``` 
using Xooa;


RequestFilters filters = new RequestFilters();
filters.AddFilter("type", "ERC-721 Token", "eq");
NFTItemsCollection collections = await XooaNFTRequest.BuildRequest().AddRequestFilters(filters).SetLimit(100).Execute();


await collections.LoadItemsTextures("asset");


foreach (NFTItem item in collections.GetItems()){
    // Your Code Logic
} ```
