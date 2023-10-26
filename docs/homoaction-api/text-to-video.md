---
sidebar_position: 1
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


# Text To Video

In this section, we'll demonstrate how to use the Audio-to-Video API to generate a video from an script and an avatar image.

## Overview

The Text-to-Video API allows you to convert text into a video with the provided parameters. This documentation provides details on how to use the API and its endpoints.

## API Endpoint

- **URL**: `admin.homoaction.ai/api/text-to-video`
- **Method**: POST

## Request Parameters

The API accepts the following parameters in the request:

- `token` (String, required): An API token for authentication.
- `title` (String, required): The title for the generated video.
- `avatar` (File, required): An image file that will be used as an avatar in the video.
- `script` (String, required): The text content you want to convert into speech and include in the video.
- `language` (String, required): The language in which the text will be spoken (e.g., "en-US" for English).
- `speaker_name` (String, required): The name of the speaker who will voice the text.
- `speech_tone` (String, required): The desired speech tone or style (e.g., "shouting").
- `email` (String, optional): An email address associated with the generated video.

Each parameter has a specific purpose in configuring the video generation. The `avatar` parameter, for example, is used to provide an image that will be used in the video. Make sure to set these parameters with the appropriate values to achieve the desired video output.

## Example Request

Below is an example of making a POST request to the Text-to-Video API using the Fetch API in JavaScript. This example includes the required parameters.

<!-- ```javascript
var formdata = new FormData();
formdata.append("token", "8d4507576faead2d1e5fe286fb4b3789");
formdata.append("title", "Test video");
formdata.append(
  "avatar",
  fileInput.files[0],
  "/C:/Users/shubh/Downloads/homo action/Alex_1.png"
);
formdata.append(
  "script",
  "This is a test of text to speech by Azure with different languages."
);
formdata.append("language", "en-US");
formdata.append("speaker_name", "en-US-JasonNeural");
formdata.append("speech_tone", "shouting");
formdata.append("email", "shubh.k.kansara@gmail.com");

var requestOptions = {
  method: "POST",
  body: formdata,
  redirect: "follow",
};

fetch("admin.homoaction.ai/api/text-to-video", requestOptions)
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
formdata.append("avatar", fileInput.files[0], "/C:/Users/shubh/Downloads/homo action/Alex_1.png");
formdata.append("script", "This is test of text to speech by azure with different languages.");
formdata.append("language", "en-US");
formdata.append("speaker_name", "en-US-JasonNeural");
formdata.append("speech_tone", "shouting");
formdata.append("email", "shubh.k.kansara@gmail.com");

var requestOptions = {
  method: 'POST',
  body: formdata,
  redirect: 'follow'
};

fetch("http://127.0.0.1:8000/api/text-to-video", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

</TabItem>
<TabItem value="python" label="Python" default>

```python
import requests

url = "http://127.0.0.1:8000/api/text-to-video"

payload = {'token': '8d4507576faead2d1e5fe286fb4b3789',
'title': 'Test video',
'script': 'This is test of text to speech by azure with different languages.',
'language': 'en-US',
'speaker_name': 'en-US-JasonNeural',
'speech_tone': 'shouting',
'email': 'shubh.k.kansara@gmail.com'}
files=[
  ('avatar',('Alex_1.png',open('/C:/Users/shubh/Downloads/homo action/Alex_1.png','rb'),'image/png'))
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
  CURLOPT_URL => 'http://127.0.0.1:8000/api/text-to-video',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('token' => '8d4507576faead2d1e5fe286fb4b3789','title' => 'Test video','avatar'=> new CURLFILE('/C:/Users/shubh/Downloads/homo action/Alex_1.png'),'script' => 'This is test of text to speech by azure with different languages.','language' => 'en-US','speaker_name' => 'en-US-JasonNeural','speech_tone' => 'shouting','email' => 'shubh.k.kansara@gmail.com'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```

</TabItem>
</Tabs>
---

For any questions or assistance, please contact our support team at [support@homoaction.com](mailto:support@homoaction.com).
