# 🛡️ Deep Focus Shield

サイト内の中毒性があるコンテンツだけを非表示にし、情報収集の跨げにならずに集中力を維持することを手助けするCherome拡張機能

## 機能

### 共通機能（すべてのサイトに適用）
- ✅ グレースケールモード（色彩による脳への報酬刺激をカット）
- ✅ 曜日・時間帯による制限（複数時間帯設定可能）
- ✅ 常時ON機能
- ✅ ダークモード対応

### YouTube
- ✅ Shortsの非表示
- ✅ ホーム画面を登録チャンネルへリダイレクト
- ✅ 関連動画の非表示（動画再生ページ右側）
- ✅ 動画終了時の関連動画の非表示
- ✅ コメントを非表示
- ✅ ミニプレイヤーを非表示

### Twitter/X
- ✅ デフォルトのTLを「フォロー中」に変更
- ✅ おすすめ（For you）タブの非表示
- ✅ トレンドの非表示（デフォルトON）
### TikTok
- ✅ サイト全体をブロック（デフォルトON）


## 📸 プレビュー / Preview

<p align="center">
  <img src="https://github.com/SKYMY-Workshop/Deep_Focus_Shield_-SK-/blob/main/popup-preview_v1.0.0.png?raw=true" width="480" alt="Deep Focus Shield UI Preview">
</p>


## 🔽 Install / ダウンロード

👉 最新版はこちら：
https://github.com/SKYMY-Workshop/Deep_Focus_Shield_-SK-/releases

## インストール方法

1. このリポジトリをダウンロード（上記ダウンロードページ内の **Assets → Source code.zip をダウンロード）して解凍する  
2. Chromeブラウザのアドレスバーに `chrome://extensions/` と入力して開く  
3. 右上の **デベロッパーモード** を ON にする  
4. 左上の **パッケージ化されていない拡張機能を読み込む** をクリックし、解凍したフォルダを選択  
   - ※指定したフォルダを後から移動すると動作しなくなるため、あらかじめ **マイドキュメント** や **Program Files** などの任意の固定場所に保存してから選択してください  
5. Chromeのアドレスバー右側にあるパズルピースをクリックし、 **Deep Focus Shield** の右にあるピン留め（📌）をクリック  
6. アドレスバー右側にアイコンが表示されるので、必要に応じて機能設定を行う  

---

## アンインストール方法

1. Chromeのアドレスバー右側にあるパズルピースをクリックし、一番下の **拡張機能を管理** を選択  
2. 拡張機能一覧から **🛡️ Deep Focus Shield** を探し、 **削除** をクリック  
3. インストール手順 4 で保存したフォルダを削除する  

---

## 🛠️ Support / サポート

不具合報告・機能提案はこちら：
https://github.com/SKYMY-Workshop/Deep_Focus_Shield_-SK-/issues

---

## 更新履歴
- v1.0.0-beta 初回プレリリース
- v1.0.3 再生終了画面の関連動画を非表示にする機能を追加
- v1.0.4 右下に表示されるミニプレイヤーの非表示機能を追加（自動再生された途中の映画が何度も表示され、邪魔な人向け）
- v1.0.5 パフォーマンス改善・バグ修正
  - Twitter/Xで動画があるページを閲覧中にフリーズする問題を修正
    - MutationObserverにデバウンス処理（200ms）を追加し、コールバックの過剰な発火を抑制
    - `stopAutoplay()` 内の `video.pause()` がObserverを再発火させる無限ループを修正
    - 2つあったMutationObserverを1つに統合（SPAナビゲーション検出を統合）
    - 処理済み動画の再走査をスキップするよう最適化
  - YouTubeでも同様のMutationObserverにデバウンス処理を追加
  - YouTube側のObserverが制限解除後も動き続ける問題を修正
  - background.jsの時間帯判定でプラットフォーム固有のtimeSlots設定が無視されていたバグを修正
  - CSSの無効なセレクタ（`:has-text()` 等）を削除・修正
- v1.0.6 X(Twitter)の動画が表示できない不具合を修正・機能整理
  - v1.0.5で無効なCSS（`:has-text()`）を削除した際に、広範囲なセレクタ（`[aria-label*="Live"]`等）が意図せず有効化され、動画プレイヤーが非表示になっていた問題を修正
  - 動画の自動再生停止機能を削除
  - 広告非表示の過剰なCSSルールを削除

## 📜 License

MIT License. 詳細は [LICENSE](./LICENSE) を参照してください。

本拡張は完全オープンソースです。
コードはすべて公開され、いつでも検証可能です。

---


