[🇬🇧 English](README.md) | [🇰🇷 한국어](README.ko.md)

# VRM Chat Room

**VRMモデルベースのマルチアバター3Dチャットルーム — WebSocketリアルタイムメッセージング、吹き出し、Mixamoアニメーションリターゲティング。**

> [NVatar](https://github.com/nskit-io/nvatar)プロジェクトより — ローカルハードウェアで完全に動作するAIアバターチャットシステム。

---

## なぜ作ったのか

Ready Player Meがサービスを終了しました。VRMエコシステムには、モダンウェブでの**3Dアバターチャットルーム**のシンプルなデモがありません。重いメタバースフレームワークは存在しますが、以下の4つを軽量に統合した実装はありません：

1. **VRMアバター** — three-vrmでレンダリング
2. **WebSocket** — リアルタイムマルチユーザーチャット
3. **吹き出し** — 3Dアバターの頭上に浮かぶ
4. **Mixamo FBX** — VRMスケルトンへのアニメーションリターゲティング

## 主な機能

### 3Dアバターシステム
- **VRM 1.0**モデル、@pixiv/three-vrm 3.3.3
- **自動まばたき**: ランダムな自然なまばたき間隔
- **アイドル呼吸**: 微細な背骨と体のマイクロムーブメント
- **視線追跡**: スムーズな補間視線追跡

### 感情ポーズ
VRM表情 + ボーン回転のブレンド：

| 感情 | 体 | 表情 |
|------|-----|------|
| 喜び | 腕後ろ、背骨後ろ | スマイルブレンドシェイプ |
| 悲しみ | 肩前、背骨前傾、頭下げ | 悲しみブレンドシェイプ |
| 怒り | 拳握り、背骨後ろ | 怒りブレンドシェイプ |
| 驚き | 腕上げ、後ろ反り | 驚きブレンドシェイプ |

### Mixamo FBXリターゲティング
- Mixamo FBX読込 → 位置トラック除去（回転のみ）
- 正確なボーンマッピングのためのカスタムレストポーズ補正アルゴリズム
- 同梱モーション：Idle、Walking

### 吹き出しシステム
- 3D頭部位置 → `camera.project()` → 2Dスクリーン座標
- バブルキュー：時間制限表示とフェードトランジション

### バーチャルルーム
- 3D環境：壁（3面）、木製床、窓 + PointLight、家具
- ダブルクリック移動：レイキャスター → 3Dターゲット → 歩行アニメーション → 到着時アイドル

## 関連プロジェクト

- [**avatar-chat**](https://github.com/nskit-io/avatar-chat) — GemmaキャラクターAIプロンプトエンジニアリング
- [**chat-like-human-memory**](https://github.com/nskit-io/chat-like-human-memory) — 9D感情トラッキング + 性格進化 + 3層記憶
- [**customize-local-llm**](https://github.com/nskit-io/customize-local-llm) — 性格はローカルGemma、ファクトはクラウドClaude
- [**CSW**](https://github.com/nskit-io/csw) — クラウドレイヤーを動かすClaude Subscription Worker
- [**portable-ai-companion**](https://github.com/nskit-io/portable-ai-companion) — クロスアプリフランチャイズアーキテクチャ

## ライセンス

MIT License - [LICENSE](LICENSE)参照

---

## このプロジェクトをサポートしてください

NVatarは、AIアバターインタラクションの次世代を構築する独立R&Dプロジェクトです。個人創業者が外部資金なしで進めています。

**寄付・投資のお問い合わせ**
- Email: [nskit@nskit.io](mailto:nskit@nskit.io)
- Organization: [NSKit](https://nskit.io) by Neoulsoft Inc.

<p align="center">
  <a href="https://github.com/nskit-io">github.com/nskit-io</a>
</p>
