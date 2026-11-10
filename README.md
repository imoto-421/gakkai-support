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
| `intro.pdf` | 紹介資料（A4 2枚）。学会の役員会などに配る用 | ここの `print/intro.html` |

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

## 紹介資料を作り直すとき

`print/intro.html` を直してから、Chrome で PDF にします（Git Bash で、このフォルダから）。

```bash
"/c/Program Files/Google/Chrome/Application/chrome.exe" --headless=new --no-pdf-header-footer --virtual-time-budget=15000 --print-to-pdf="$(pwd -W)/intro.pdf" "file:///$(pwd -W)/print/intro.html"
```

- できた `intro.pdf` が **ちょうど2ページ** で、どのページも下の帯（QRコード）が切れていないことを確かめる
- 書体は Google Fonts から読み込むので、インターネットにつないだ状態で作る
- 料金・規約・機能が変わったら、配布ページ（`index.html`）と同じ中身にそろえる
- QRコード（`print/qr-site.svg`）は配布ページの URL。URL が変わらないかぎり作り直さなくてよい
