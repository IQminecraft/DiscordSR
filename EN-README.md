# Discord Self Request (DiscordSR) Library Ver0.1.0

The `DiscordSR` library is a Python package designed to interact with Discord's API. It enables users to automate various actions on Discord, such as changing nicknames, managing statuses, moderating users, and more.
## Update Feature

- added `tts_send`
- added `dissoku`
- added `sticker_send`
- added `all_reaction_delete`
- fixed send's description.
- update readme

## Features

- Change your nickname in a guild with `guild_mynick`.
- Change another user's nickname in a guild with `guild_IDnick`.
- Update your Discord status with `status`.
- Timeout a user in a guild with `timeout`.
- Remove a timeout from a user with `untimeout`.
- Kick a user from a guild with `kick`.
- Ban a user from a guild with `ban`.
- Report a user with `report`.
- Check if a Discord token is valid with `token_check`.
- Check if a Discord Nitro code is valid with `nitro_check`.
- Send a message to a channel with `send`.
- Send a sticker to a channel with `sticker_send`.
- Send a TTS (Text-to-Speech) message in a channel with `tts_send`.
- Bump a server in server listings with `bump`.
- dissoku_up a server in server listings with `dissoku`.
- Add a normal reaction to a message with `normal_reaction`.
- Add a custom emoji reaction to a message with `custom_reaction`.
- Delete all emojis of reactions to a message with `all_reaction_delete`.
- Send a message through a Discord webhook with `webhook_send`.
- Delete a Discord webhook with `webhook_delete`.

## Installation
> *This library using* **requests** *.*

To install the `requests` and `DiscordSR` library, use pip:
### bash
```bash
pip install requests
```
```bash
pip install DiscordSR
```
## Return
The response in json format or status code is returned.
## Cautions for use
Functions that change other people's nicknames, etc., cannot be changed unless you own the `permission`, and an error will be returned.
## Function

### guild_mynick

**Description**: Change your nickname on a specific server

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server where the nickname will be changed.
- `nick` (str): A new nickname to be set for the user.

---

### guild_IDnick

**Description**: Changes the nickname of another user on a specific server.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server where the nickname will be changed.
- `user_id` (int): The ID of the user whose nickname will be changed.
- `nick` (str): The new nickname to be set for the user.

---

### status

**Description**: Update the user's Discord status.

**Parameters**:
- `token` (str): user token to be used
- `msg` (str): The new status message to be displayed.

---

### timeout

**Description**: Time out user.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server where the user will be timed out.
- `user_id` (int): The ID of the user to be timed out.
- `mode` (int): The duration of the timeout in predefined modes (1 to 6).

    - **1** : 60seconds
    - **2** : 5minutes
    - **3** : 10minutes
    - **4** : 1hour
    - **5** : 1day
    - **6** : 1weak

---

### untimeout

**Description**: Remove user timeout.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server where the user will be untimeout.
- `user_id` (int): The ID of the user to have the timeout removed.

---

### kick

**Description**: Kick a user.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server from which the user will be kicked.
- `user_id` (int): The ID of the user to be kicked.

---

### ban

**Description**: Bans a user from a server and optionally deletes their previous messages.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server where the user will be banned.
- `user_id` (int): The ID of the user to be banned.
- `deletemsg_time` (int): The time in seconds to delete messages from the user.

---

### report

**Description**: Reports a user for violations within a server.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server where the user is to be reported.
- `user_id` (int): The ID of the user to be reported.

---

### token_check

**Description**: Checks if a Discord token is valid.

**Parameters**:
- `token` (str): The Discord token to be validated.

---

### nitro_check

**Description**: Checks if a Discord Nitro code(16) is valid.

**Parameters**:
- `code` (str): The Discord Nitro code to be validated.

---

### send

**Description**: Sends a message to a specified channel.

**Parameters**:
- `token` (str): user token to be used
- `channel_id` (int): The ID of the channel where the message will be sent.
- `msg` (str): The message to be sent.

**about custom emoji**: <:emoji_name:emoji_id>

- Type "\{emoji_name}" on the server where the emoji you want to use exists to get the emoji_id. Please enter the name of the emoji in {emoji_name}.

---

### sticker_send

**Description**: Sends a sticker to a specified channel.

**Parameters**:
- `token` (str): user token to be used
- `channel_id` (int): The ID of the channel where the message will be sent.
- `sticker_id` (str): sticker to send.

**about custom emoji**: <:emoji_name:emoji_id>

- Type "\{emoji_name}" on the server where the emoji you want to use exists to get the emoji_id. Please enter the name of the emoji in {emoji_name}.

---

### tts_send

Send a TTS message in a Discord channel.

**Parameters**:
- `token` (str): The user token to authenticate the request.
- `channel_id` (int): The ID of the channel where the TTS message will be sent.
- `msg` (str): The message to be sent as TTS.

---

### bump
#### <font color="DeepPink">※This function is Test.</font>
**Description**: Bumps a server in server listings to increase its visibility.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server to be bumped.
- `channel_id` (int): The ID of the channel where the bump command is executed.

---

### dissoku
#### <font color="DeepPink">※This function is Test.</font>
**Description**: dissoku_up a server in server listings to increase its visibility.

**Parameters**:
- `token` (str): user token to be used
- `server_id` (int): The ID of the server to be bumped.
- `channel_id` (int): The ID of the channel where the bump command is executed.

---

### normal_reaction

**Description**: Adds a normal emoji reaction to a message.

**Parameters**:
- `token` (str): user token to be used
- `channel_id` (int): The ID of the channel containing the message.
- `msg_id` (str): The ID of the message to react to.
- `emoji` (str): The emoji to be used for the reaction.

---

### custom_reaction

**Description**: Adds a custom emoji reaction to a message.

**Parameters**:
- `token` (str): user token to be used
- `channel_id` (int): The ID of the channel containing the message.
- `msg_id` (str): The ID of the message to which the reaction will be added.
- `emoji_name` (str): The name of the custom emoji.
- `emoji_id` (str): The ID of the custom emoji.

> how to get emoji id
>- Type "\{emoji_name}" on the server where the emoji you want to use exists to get the emoji_id. Please enter the name of the emoji in {emoji_name}.
---

### all_reaction_delete

**Description**: Delete all emojis of reactions to a message.

**Parameters**:
- `token` (str): user token to be used
- `channel_id` (int): The ID of the channel containing the message.
- `msg_id` (str): The ID of the message to react to.

---

### webhook_send

Send a message through a Discord webhook.

**Parameters**:
- `webhook_url` (str): The webhook URL to send the message to.
- `name` (int): The name to be displayed as the sender.
- `avatar` (str): The URL of the avatar image to be displayed as the sender.

---

### webhook_delete

Delete a Discord webhook.Can be deleted regardless of authorization.

**Parameters**:
- `webhook_url` (str): The webhook URL to be deleted.
