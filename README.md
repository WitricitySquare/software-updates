# TOMOMI RESEARCH Software Updates

Release information and installers of TOMOMI RESEARCH, INC. desktop applications.
TOMOMI RESEARCH, INC. のデスクトップアプリケーションの更新情報とインストーラです。

| Product / 製品 | Latest / 最新版 | Download / ダウンロード |
|---|---|---|
| TR CAD Viewer | see [`tr-cad-viewer.json`](tr-cad-viewer.json) | [Releases](https://github.com/WitricitySquare/software-updates/releases) (tag `tr-cad-viewer-v*`) |
| TR Camera Simulator | see [`tr-camera-simulator.json`](tr-camera-simulator.json) | [Releases](https://github.com/WitricitySquare/software-updates/releases) (tag `tr-camera-simulator-v*`; installer on request / インストーラはお問い合わせください) |

## How the applications use this repository / アプリとの関係

Each application reads `<product id>.json` from this repository over HTTPS (at most once a
day at startup, and from Help > Check for Updates). Only that file is read: no model, file
name or user data is sent, and nothing is downloaded or installed automatically. The check
can be turned off in Settings > Check for Updates at Startup.

各アプリは起動時（1 日 1 回まで）と Help > Check for Updates で、このリポジトリの
`<製品ID>.json` を HTTPS で読みます。読むのはそのファイルだけで、モデル・ファイル名・利用者の
情報は送信しません。自動でダウンロード・インストールすることもありません。
Settings > Check for Updates at Startup で止められます。

## Verifying a download / ダウンロードの確認

Each release includes `SHA256SUMS.txt`. Compare it with:
各リリースに `SHA256SUMS.txt` があります。次のコマンドの結果と比べてください。

```powershell
Get-FileHash .\<Setup file>.exe -Algorithm SHA256
```

## "Source code (zip / tar.gz)" / 「Source code」のファイル

GitHub adds "Source code (zip)" and "Source code (tar.gz)" to every release automatically;
they cannot be removed. They contain only this repository's files (`README.md` and `*.json`),
not the applications' source code, and are not needed for installation.

各リリースの「Source code (zip)」「Source code (tar.gz)」は GitHub が自動で付けるもので、
外すことはできません。中身はこのリポジトリのファイル（`README.md` と `*.json`）だけで、
アプリケーションのソースコードは含まれていません。インストールには使いません。

## For maintainers / 管理者向け

The format and the release procedure are in the internal skill `skills/update-check/SKILL.md`.
Publish the release (installer) first, then update the JSON.
書式と公開手順は社内スキル `skills/update-check/SKILL.md` を参照。Releases を先に作り、JSON は最後に更新する。
