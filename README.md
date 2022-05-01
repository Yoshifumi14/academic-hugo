# https://takeshima14.netlify.app

## Hugoプロジェクト

### Hugo コマンド

Webサーバー立ち上げ

```
$ hugo server
```

ビルド

```
$ hogo -D
```

## Academic

### AcademicをNetlifyにデプロイ

ここからスタート:https://wowchemy.com/templates/
- Create Siteをクリック
- GitHubの認証
- GitHubリポジトリ名を決める
- ここでもう環境、あとはローカルで開発&pushするだけ
- DomainSettingで{}.netlify.app以下のドメイン変更
- Setie SettingsのBuilt&Deployからターゲットブランチ変更

管理: https://app.netlify.com/
成果物: https://takeshima14.netlify.app/

## Tips

#### hugo serverでエラーその1
```
$ hugo server
Error: from config: failed to resolve output format "WebAppManifest" from site config
```
これを試す:https://wowchemy.com/docs/guide/troubleshooting/#error-failed-to-resolve-output-format

#### `git clone`後のHoguのビルドエラー

`git clone`後にHugoのテーマとして使用しているsubmoduleも更新する必要がある。
```
$ git submodule update --init --recursive
```
- 参考: https://infraya.work/posts/hugo_mypage_git_clone_error/

#### submoduleの追加

```
$ git submodule add ${サブモジュール化するリポジトリurl} ${パス/名前指定}
```

#### submoduleの削除

```
$ git submodule deinit -f ${追加したサブモジュール}
$ git rm -f ${追加したサブモジュール}
$ rm -rf .git/modules/${追加したサブモジュール}
```

### Golang
Academicテーマを使うときはGoのインストールが必要
```
$ brew install go
```

#### AcademicはGitHubPagesではなくNetflyを推奨している

>If you prefer easy automated deployments whenever you make a change to your site, we recommend deploying with Netlify (see above) rather than Github Pages.

引用元:https://wowchemy.com/docs/guide/deployment/#automating-deployment

### Academicのicon追加

assets/images/icon-packにおく
https://gauger.io/fonticon/

公式の記述:https://wowchemy.com/docs/getting-started/page-builder/#icons

### themeの配色のカスタマイズ

https://wowchemy.com/docs/getting-started/customization/#custom-theme

## Docs

- Hugo: https://gohugo.io/documentation/
- GitHub Pages: https://docs.github.com/ja/github/working-with-github-pages
- wowchemy: https://wowchemy.com/docs/