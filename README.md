# Youtube-Auto-Upload
 
 ### Auto upload video from url and post to Youtube using Google colab and Youtube Api v3
 
 ## Installation:
 
 
 1. go to https://console.cloud.google.com/projectselector2/apis/dashboard and search YouTube Data API v3 then click enable
 2. go to Credentials > Create OAuth client ID > CONFIGURE CONSENT SCREEN > choose External > fill all require form
 3. in stage 'Scopes' click ADD OR REMOVE SCOPES, search upload then tick to Youtube Data API v3 > SAVE AND CONTINUE
 4. in stage 'Test Users' add your email address then continue
 5. go back Credentials and create new OAuth client ID, application type choose Desktop App then create
 6. copy and save your Client ID and Client Secret
 7. go to colab and run
 ```
!git clone https://github.com/zcrossoverz/Youtube-Auto-Upload
%cd Youtube-Auto-Upload
!pip install -r requirements.txt
```
8. config your client_secret.josn

## Example Usage:

1. Example download file form url
```
import requests 
file_url = "https://domain.com/video.mp4"
	
r = requests.get(file_url, stream = True) 

with open("video.mp4", "wb") as file: 
	for block in r.iter_content(chunk_size = 1024): 
		if block: 
			file.write(block) 
```

2. Example upload file on colab to youtube

```
!python youtube.py --file="../video.mp4" --title="Test api upload" --description="Nhan dep trai" --keywords="crossover" --privacyStatus="private"
```


