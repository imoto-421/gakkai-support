# 学会運営支援システム 配布ページ

GitHub Pages で公開している配布ページです：https://imoto-421.github.io/gakkai-support/

アプリ本体のソースは非公開のリポジトリ（member-management）にあります。

## ファイル

| ファイル | 中身 | 直す場所 |
|---|---|---|
| `index.html` | トップ（紹介・ダウンロード・料金・よくある質問） | ここで直接 |
| `purchase.html` | ライセンスの購入の案内（Stripe の支払いへ進む） | ここで直接 |
| `privacy.html` | プライバシーポリシー | ここで直接 |
| `tokushoho.html` | 特定商取引法に基づく表記 | ここで直接 |
| `style.css` | 見た目 | ここで直接 |
| `terms.html` | 利用規約（アプリと同じ文面） | member-management の `src/core/terms.ts` |
| `manual.pdf`・`security.pdf`・`img/` | 説明書・画面写真 | member-management |

`terms.html`・PDF・画面写真は、member-management で `npm run site:assets` を実行し、
できた `site-assets/` の中身をこのリポジトリにそのまま上書きします。

## 新しい版を出すとき

1. member-management で zip を作り、このリポジトリの Releases に新しいリリース（例：`v1.0.1`）を作って zip を添付する
2. `index.html` のダウンロードのリンク（`releases/download/v…/GakkaiSupport-…-win.zip`）と、版・サイズの表示を書き換える
3. 利用規約や説明書が変わったときは、`npm run site:assets` の中身を上書きする

## アプリが開く URL（変えないこと）

アプリの中に書いてあるので、ファイル名を変えるとアプリのボタンが開けなくなります。

- `index.html`（配布ページ）
- `purchase.html`（購入のページ）
- `terms.html`（利用規約）
