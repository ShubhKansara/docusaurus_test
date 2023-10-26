---
sidebar_position: 2
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Audio To Video

In this section, we'll demonstrate how to use the Audio-to-Video API to generate a video from an audio file and an avatar image.

## Overview

The Audio-to-Video API allows you to create a video by combining an audio track and an avatar image. This is a powerful tool for generating engaging content with ease.

## API Endpoint

- **URL**: `admin.homoaction.ai/api/audio-to-video`
- **Method**: POST

## Request Parameters

- `token` (String, required): An API token for authentication.
- `title` (String, required): The title for the generated video.
- `avatar` (File, required): An image file that will be used as an avatar in the video.
- `audio` (File, required): An audio file that will be used as the audio track for the video.
- `email` (String, optional): An email address associated with the generated video.

## Example Request

Below is an example of making a POST request to the Audio-to-Video API. This example includes the required parameters.

<!-- ```javascript
var formdata = new FormData();
formdata.append("token", "8d4507576faead2d1e5fe286fb4b3789");
formdata.append("title", "Test video");
formdata.append(
  "avatar",
  fileInput.files[0],
  "/C:/Users/shubh/Downloads/homo action/Agnes.png"
);
formdata.append(
  "audio",
  fileInput.files[0],
  "/C:/Users/shubh/Downloads/homo action/RD_Radio31_000.wav"
);
formdata.append("email", "shubh.k.kansara@gmail.com");

var requestOptions = {
  method: "POST",
  body: formdata,
  redirect: "follow",
};

fetch("admin.homoaction.ai/api/audio-to-video", requestOptions)
  .then((response) => response.text())
  .then((result) => console.log(result))
  .catch((error) => console.log("error", error));
``` -->



<Tabs>
  <TabItem value="javascript" label="JavaScript" default>

```javascript

var formdata = new FormData();
formdata.append("token", "8d4507576faead2d1e5fe286fb4b3789");
formdata.append("title", "Test video");
formdata.append("avatar", fileInput.files[0], "/C:/Users/shubh/Downloads/homo action/Agnes.png");
formdata.append("audio", fileInput.files[0], "/C:/Users/shubh/Downloads/homo action/RD_Radio31_000.wav");
formdata.append("email", "shubh.k.kansara@gmail.com");

var requestOptions = {
  method: 'POST',
  body: formdata,
  redirect: 'follow'
};

fetch("http://127.0.0.1:8000/api/audio-to-video", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));

```

</TabItem>
<TabItem value="python" label="Python" default>

```python

import requests

url = "http://127.0.0.1:8000/api/audio-to-video"

payload = {'token': '8d4507576faead2d1e5fe286fb4b3789',
'title': 'Test video',
'email': 'shubh.k.kansara@gmail.com'}
files=[
  ('avatar',('Agnes.png',open('/C:/Users/shubh/Downloads/homo action/Agnes.png','rb'),'image/png')),
  ('audio',('RD_Radio31_000.wav',open('/C:/Users/shubh/Downloads/homo action/RD_Radio31_000.wav','rb'),'audio/wav'))
]
headers = {}

response = requests.request("POST", url, headers=headers, data=payload, files=files)

print(response.text)


```

  </TabItem>

<TabItem value="php" label="PHP">

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'http://127.0.0.1:8000/api/audio-to-video',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('token' => '8d4507576faead2d1e5fe286fb4b3789','title' => 'Test video','avatar'=> new CURLFILE('/C:/Users/shubh/Downloads/homo action/Agnes.png'),'audio'=> new CURLFILE('/C:/Users/shubh/Downloads/homo action/RD_Radio31_000.wav'),'email' => 'shubh.k.kansara@gmail.com'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;


```

</TabItem>
</Tabs>


---

For any questions or assistance, please contact our support team at [support@homoaction.com](mailto:support@homoaction.com).