# adcmod

## これは何？

* Google Cloud SDK の複数の Application Default Credentials (ADC-profiles) を切り替えるためのツールです。

1. 環境変数 `GOOGLE_APPLICATION_CREDENTIALS` を設定します。
1. 現在の `$SHELL` を実行します。

### なぜこれが必要なのか

* [terraform-provider-google](https://www.terraform.io/docs/providers/google/) を使用して、あるプロジェクトで作業しているとします。
* 同時に別のプロジェクトでも terraform-provider-google を使用して作業する場合、同じマシン上で設定できる ADC は 1 つだけです。これは不便です。
  * そのため、簡単に切り替えられるようにしました。

## 特徴

* 複数の `application-default` 認証情報の切り替えが可能です。

## 使い方

* ログインシェルとして設定されていないシェルを使用する場合は、以下のように実行してください：

```bash
$ env SHELL=path/to/your/favorite-shell adcmod s PROFILE-NAME
```

### `adcmod`

* 現在アクティブな ADC (Application Default Credential) を表示します。
  * 環境変数が設定されている場合は、その値を表示します。
  * 環境変数が設定されていない場合は、Cloud SDK の ADC JSON ファイルの内容を表示 (`cat`) します。
  * それ以外の場合は `ADC not set` と表示します。

## `adcmod l`

* 登録されているプロファイルの一覧を表示します。

## `adcmod s PROFILE-NAME`

* 環境変数をセットし、`$SHELL` を実行します。

## セットアップ方法

### `adcmod` のインストール

1. このリポジトリをクローンします。
1. `$PATH` が通っている場所に `adcmod` へのシンボリックリンクを作成します。

### ADC の登録

1. `gcloud auth application-default login` を実行します。
1. `~/.config/gcloud/application_default_credentials.json` ファイルが生成されます。これが ADC の認証情報ファイルです。
1. この JSON ファイルの名前を `.json_PROFILE-NAME` というサフィックス（接尾辞）を付けてリネームします。
1. `adcmod l` を実行して確認します。
1. 完了です。別のプロファイルを登録したい場合は、この手順を繰り返してください。
