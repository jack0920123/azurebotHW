# Computer Vision Line Chat Bot

Date: 2021/01/17

## On Azure

### Resource

- Azure App Service: B1

### App service setting

- TLS/SSL setting: 
    - HTTPS only: on 

### Prepare 

1. Install azure cli

2. Turn on Azure app service

3. Open SSH session in browser

4. Edit `/home/config.json`
```
{
    "line":{
            "line_secret":...,
            "line_token":...
    },
    "azure":{
            "subscription_key":...,
            "endpoint":"https://<your name of Azure Cognitive Services>.cognitiveservices.azure.com/",
            "face_key":...,
            "face_end":"https://<your name of Azure Face Detection>.cognitiveservices.azure.com/"
    },
    "imgur":{
            "client_id":...,
            "client_secret":...,
            "access_token":...,
            "refresh_token":...
    }
}
```
5. Set username and password: `az webapp deployment user set --user-name <usrname> --password <password>`

6. Get git url:
`az webapp deployment source config-local-git --name <app_name> --resource-group <resource_name>`

7. Add remote: 
```
cd cv_tutorial
git remote add azure <your_git_url>
```

8. `git push azure master`
9. demo
face api
![image](https://github.com/jack0920123/azurebotHW/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202021-08-19%20224355.png)
ocr
![image](https://github.com/jack0920123/azurebotHW/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202021-08-19%20224432.png)
object detect
![image](https://github.com/jack0920123/azurebotHW/blob/main/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202021-08-19%20224519.png)

