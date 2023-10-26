---
sidebar_position: 3
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';


# Text To Audio

In this section, we'll demonstrate how to use the Text-to-Video API to generate a audio from an text.

## Overview

The Text-to-Audio API allows you to convert text into audio using Azure Text-to-Speech services. This documentation provides details on how to use the API and its endpoints.

## API Endpoint

- **URL**: `admin.homoaction.ai/api/text-to-audio`
- **Method**: POST

## Request Parameters

The API accepts the following parameters in the request:

- `token` (String, required): An API token for authentication.
- `title` (String, required): The title for the generated audio.
- `script` (String, required): The text content you want to convert to audio.
- `language` (String, required): The language for the generated audio (e.g., "en-US" for English).
- `speaker_name` (String, required): The name of the speaker (e.g., "en-US-JasonNeural").
- `speech_tone` (String, required): The desired speech tone (e.g., "shouting").
- `email` (String, optional): An email address to associate with the generated audio.

## Example Request

Below is an example of making a POST request to the Text-to-Audio API using Fatch API in JavaScript. This example includes the required parameters.

<!-- ```javascript
var formdata = new FormData();
formdata.append("token", "8d4507576faead2d1e5fe286fb4b3789");
formdata.append("title", "Test video");
formdata.append(
  "script",
  "This is test of text to speech by azure with different languages."
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

fetch("admin.homoaction.ai/api/text-to-audio", requestOptions)
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

fetch("http://127.0.0.1:8000/api/text-to-audio", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

</TabItem>
<TabItem value="python" label="Python" default>

```python
import requests
url = "http://127.0.0.1:8000/api/text-to-audio"

payload = {
    'token': '8d4507576faead2d1e5fe286fb4b3789',
    'title': 'Test video',
    'script': 'This is a test of text to speech by azure with different languages.',
    'language': 'en-US',
    'speaker_name': 'en-US-JasonNeural',
    'speech_tone': 'shouting',
    'email': 'shubh.k.kansara@gmail.com'
}
files = []

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
  CURLOPT_URL => 'http://127.0.0.1:8000/api/text-to-audio',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('token' => '8d4507576faead2d1e5fe286fb4b3789','title' => 'Test video','script' => 'This is test of text to speech by azure with different languages.','language' => 'en-US','speaker_name' => 'en-US-JasonNeural','speech_tone' => 'shouting','email' => 'shubh.k.kansara@gmail.com'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```

</TabItem>
</Tabs>



---

For any questions or assistance, please contact our support team at [support@homoaction.com](mailto:support@homoaction.com).
