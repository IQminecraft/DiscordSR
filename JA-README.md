# Discord Self Request (DiscordSR) ライブラリ Ver0.1.0

`DiscordSR` ライブラリは、DiscordのAPIを楽に叩くために作られたPythonパッケージです。ユーザーがDiscord上で様々なアクションを自動化することを可能にします。例えば、ニックネームの変更、ステータスの管理、リアクションの管理、webhookの管理などです。
## 更新機能

- `tts_send` を追加
- `dissoku` を追加
- `sticker_send` を追加
- `all_reaction_delete` を追加
- sendの説明を修正
- readmeを更新

## 機能

- `guild_mynick` でギルド内の自分のニックネームを変更。
- `guild_IDnick` でギルド内の他ユーザーのニックネームを変更。
- `status` でDiscordステータスを更新。
- `timeout` でギルド内のユーザーをタイムアウト。
- `untimeout` でユーザーのタイムアウトを解除。
- `kick` でユーザーをギルドからキック。
- `ban` でユーザーをギルドからバン。
- `report` でユーザーを報告。
- `token_check` でDiscordトークンが有効かチェック。
- `nitro_check` でDiscord Nitroコードが有効かチェック。
- `send` でチャンネルにメッセージを送信。
- `sticker_send` でチャンネルにステッカーを送信。
- `tts_send` でチャンネルにTTS（テキスト読み上げ）メッセージを送信。
- `bump` でサーバーをサーバーリストで上位表示。
- `dissoku` でサーバーをサーバーリストで上位表示。
- `normal_reaction` でメッセージに通常のリアクションを追加。
- `custom_reaction` でメッセージにカスタム絵文字リアクションを追加。
- `all_reaction_delete` でメッセージの全てのリアクションの絵文字を削除。
- `webhook_send` でDiscordウェブフックを通じてメッセージを送信。
- `webhook_delete` でDiscordウェブフックを削除。

## インストール
> *このライブラリは* **requests** *を使用しています。*

`requests` と `DiscordSR` ライブラリをインストールするには、pipを使用します:
### bash
```bash
pip install requests
```
```bash
pip install DiscordSR
```
## 戻り値
応答はJSON形式またはステータスコードで返されます。
## 使用上の注意
他人のニックネームを変更する機能などは、`permission`を所有していない限り変更できず、エラーが返されます。
## 機能

### guild_mynick

**説明**: 特定のサーバーで自分のニックネームを変更する

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): ニックネームを変更するサーバーのID
- `nick` (str): ユーザーに設定する新しいニックネーム

---

### guild_IDnick

**説明**: 特定のサーバーで他のユーザーのニックネームを変更する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): ニックネームを変更するサーバーのID
- `user_id` (int): ニックネームを変更するユーザーのID
- `nick` (str): ユーザーに設定する新しいニックネーム

---

### status

**説明**: ユーザーのDiscordステータスを更新する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `msg` (str): 表示される新しいステータスメッセージ

---

### timeout

**説明**: ユーザーをタイムアウトさせる。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): ユーザーがタイムアウトされるサーバーのID
- `user_id` (int): タイムアウトされるユーザーのID
- `mode` (int): 定義済みモード（1から6）でのタイムアウトの期間

    - **1** : 60秒
    - **2** : 5分
    - **3** : 10分
    - **4** : 1時間
    - **5** : 1日
    - **6** : 1週間

---

### untimeout

**説明**: ユーザーのタイムアウトを解除する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): ユーザーのタイムアウトを解除するサーバーのID
- `user_id` (int): タイムアウトを解除するユーザーのID

---

### kick

**説明**: ユーザーをキックする。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): ユーザーがキックされるサーバーのID
- `user_id` (int): キックされるユーザーのID

---

### ban

**説明**: ユーザーをサーバーからバンし、オプションで過去のメッセージを削除する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): ユーザーがバンされるサーバーのID
- `user_id` (int): バンされるユーザーのID
- `deletemsg_time` (int): ユーザーのメッセージを削除する秒数

---

### report

**説明**: サーバー内での違反行為を報告する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): ユーザーを報告するサーバーのID
- `user_id` (int): 報告されるユーザーのID

---

### token_check

**説明**: Discordトークンが有効かどうかをチェックする。

**パラメータ**:
- `token` (str): 検証するDiscordトークン

---

### nitro_check

**説明**: Discord Nitroコード(16)が有効かどうかをチェックする。

**パラメータ**:
- `code` (str): 検証するDiscord Nitroコード

---

### send

**説明**: 指定されたチャンネルにメッセージを送信する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `channel_id` (int): メッセージが送信されるチャンネルのID
- `msg` (str): 送信されるメッセージ

**カスタム絵文字について**: <:emoji_name:emoji_id>

- 使用したい絵文字が存在するサーバーで"\{emoji_name}"と入力してemoji_idを取得してください。{emoji_name}には絵文字の名前を入力してください。

---

### sticker_send

**説明**: 指定されたチャンネルにステッカーを送信する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `channel_id` (int): メッセージが送信されるチャンネルのID
- `sticker_id` (str): 送信するステッカー

**カスタム絵文字について**: <:emoji_name:emoji_id>

- 使用したい絵文字が存在するサーバーで"\{emoji_name}"と入力してemoji_idを取得してください。{emoji_name}には絵文字の名前を入力してください。

---

### tts_send

**説明**: DiscordチャンネルでTTSメッセージを送信する。

**パラメータ**:
- `token` (str): リクエストを認証するユーザートークン
- `channel_id` (int): TTSメッセージが送信されるチャンネルのID
- `msg` (str): TTSとして送信されるメッセージ

---

### bump
#### <font color="DeepPink">※この機能はテスト中です。</font>
**説明**: サーバーの可視性を高めるためにサーバーリストでサーバーをバンプする。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): バンプされるサーバーのID
- `channel_id` (int): バンプコマンドが実行されるチャンネルのID

---

### dissoku
#### <font color="DeepPink">※この機能はテスト中です。</font>
**説明**: サーバーの可視性を高めるためにサーバーリストでサーバーをdissoku_upする。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `server_id` (int): バンプされるサーバーのID
- `channel_id` (int): バンプコマンドが実行されるチャンネルのID

---

### normal_reaction

**説明**: メッセージに通常の絵文字リアクションを追加する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `channel_id` (int): メッセージが含まれるチャンネルのID
- `msg_id` (str): リアクションを追加するメッセージのID
- `emoji` (str): リアクションに使用する絵文字

---

### custom_reaction

**説明**: メッセージにカスタム絵文字リアクションを追加する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `channel_id` (int): メッセージが含まれるチャンネルのID
- `msg_id` (str): リアクションが追加されるメッセージのID
- `emoji_name` (str): カスタム絵文字の名前
- `emoji_id` (str): カスタム絵文字のID

> 絵文字IDの取得方法
> - 使用したい絵文字が存在するサーバーで"\{emoji_name}"と入力してemoji_idを取得してください。{emoji_name}には絵文字の名前を入力してください。

---

### all_reaction_delete

**説明**: メッセージについたすべての絵文字リアクションを削除する。

**パラメータ**:
- `token` (str): 使用するユーザートークン
- `channel_id` (int): メッセージが含まれるチャンネルのID
- `msg_id` (str): リアクションを削除するメッセージのID

---

### webhook_send

**説明**: DiscordのWebhookを通じてメッセージを送信する。

**パラメータ**:
- `webhook_url` (str): メッセージを送信するWebhookのURL
- `name` (int): 送信者として表示される名前
- `avatar` (str): 送信者として表示されるアバター画像のURL

---

### webhook_delete

**説明**: DiscordのWebhookを削除する。認証に関わらず削除可能。

**パラメータ**:
- `webhook_url` (str): 削除するWebhookのURL
