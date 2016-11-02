# Facebook bot python wrapper
Python Wrapper for [Facebook Messenger](https://developers.facebook.com/products/messenger/) Bot Platform.

[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/hyperium/hyper/master/LICENSE)
[![PyPI](https://img.shields.io/pypi/v/fbbotw.svg)](https://pypi.python.org/pypi?name=fbbotw&version=0.1.dev1&:action=display)

## Install

```
pip install fbbotw
```

## Using with Django

1 - In your global settings define the variable `PAGE_ACCESS_TOKEN` that is
your access token generated on the app configuration from facebook.

```py
#settings.py
PAGE_ACCESS_TOKEN = "<your access token>"
```

2 - To use the functions of this wrapper do:

```py
from fbbotw import fbbotw

fbbotw.typing(fbid, "typing_on"):

```

## If you want to use this package without Django

1. Download the .zip of this directory.

2. Copy the `fbbotw` directory to your project root.

3. Change the variable `PAGE_ACCESS_TOKEN` at the line 8 in `fbbotw/fbbotw.py` adding your facebook page access token:

```py
    PAGE_ACCESS_TOKEN = "<Set the page access token here>"
```

# Available functions (+facebook documentation):

- **post_settings(welcometext):**  Sets the START button and welcome text
  - https://developers.facebook.com/docs/messenger-platform/thread-settings/greeting-text
  - https://developers.facebook.com/docs/messenger-platform/thread-settings/get-started-button

- **typing(fbid, sender_action):** Displays the typing gif on facebook chat
  - sender_action: "typing_on", "typing_off"
  - https://developers.facebook.com/docs/messenger-platform/send-api-reference/sender-actions

- **get_user_information(fbid):** Gets user information: first_name, last_name, gender, profile_pic.
  - https://developers.facebook.com/docs/messenger-platform/user-profile

- **post_text_message(fbid, message):** Sends a common text message
  - https://developers.facebook.com/docs/messenger-platform/send-api-reference

- **post_image_attch(fbid, imgurl):** ''' Sends an image attachment. '''
  - https://developers.facebook.com/docs/messenger-platform/send-api-reference/image-attachment

- **post_text_w_quickreplies(fbid, message, quick_replies):** Sends text with quick replies buttons
  - quick_replies format:
  ```
      quick_replies = [
          {
              "content_type" : "text",
              "title" : "Yes!",
              "payload": "USER_SAY_YES"
          },
          {
              "content_type" : "text",
              "title" : "Nope",
              "payload": "USER_SAY_NOT"
          }
      ]
  ```
  - https://developers.facebook.com/docs/messenger-platform/send-api-reference/quick-replies
