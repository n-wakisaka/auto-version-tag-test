# auto-version-tag-test
milibで使うバージョンファイルから自動でgit tagを付けるテスト

# 使い方
* .github/ 以下のファイルを導入したいrepositoryに配置

# workflow説明
## Build Version Tag
config.orgかlibinfoファイルからバージョンを取得しgit tagをつけます。

最も新しいtagがつけられたバージョンを現在のバージョンを比較し、更新されている場合はtagをつけ、更新されていない場合はtagはつけません。

これまでに一つもバージョンtagがつけられていない場合、commitを遡ってバージョンが変更されたcommitにtagをつけていきます。

mainブランチpush時に自動的に実行されます。

## Check Version Updated
config.orgかlibinfoファイルから取得したバージョンが、最も新しいtagより新しいかチェックします。

mainブランチへのpull requestに対して実行されます。

## Delete Version Tags
バージョンtagをすべて削除します。

自動では実行されず、tag付けが失敗していた場合など用。Actionsから手動で実行できます。
