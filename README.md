# Color Bloom Composite Pack

Blenderの**コンポジット用テンプレート/アセット**です。  
以下の4つのノードグループを含み、Asset Browser からドラッグ＆ドロップするだけで映像/静止画の仕上げを行えます。

- **Vignette**：周辺減光。サイズとブラー量でエッジの柔らかさを調整。  
- **Color Bloom**：ハイライトを拡散したうえで色味を重ね、雰囲気を演出。  
- **Bloom**：明るい部分を抽出して拡散・合成するシンプルなブルーム。  
- **Overlay_Color_Grading**：オーバーレイ合成で色味・明度を一括調整。

---

## フォルダ構成（配布物）

```
Color_Bloom_Composite_pack/
  demo/
    after_composite.mkv
    before_composite.mkv
    compare.mkv
  Color_Bloom_Composite_Library/
    composite_example.blend
    composite_example.blend1
  README.md
  README_EN.md
  SIMPLE_TUTORIAL_JA.md
  SIMPLE_TUTORIAL_EN.md
  LICENSE.txt
  CHANGELOG.md
```

> **ライセンスの概要**  
> - `Color_Bloom_Composite_Library/` 配下（.blend 等のアセット）は **CC0**（パブリックドメイン相当）  
> - `demo/` 配下（動画・静止画）は **CC BY 4.0**（クレジット表示必須）  
> 詳細は `LICENSE.txt` を参照してください。

---

## 対応環境

- **Blender**：4.5 LTS で動作確認済み  
- 追加アドオン：不要（標準ノードのみ）

---

## インストール（Asset Library として使用）

1. `Edit > Preferences > File Paths > Asset Libraries` を開く。  
2. **Add** をクリックし、`Color_Bloom_Composite_pack/Color_Bloom_Composite_Library` フォルダを追加。  
3. Asset Browser を開き、左の **Catalogs** で登録フォルダを選択（作成したカタログ名に分類されます）。各アセットをドラッグ＆ドロップ。

> `.blend` から直接アペンドする場合：  
> `File > Append` → `composite_example.blend` → `NodeTree/` → 必要なノードグループ（**Vignette**, **Color Bloom**, **Bloom**, **Overlay_Color_Grading**）を選択。

---

## 使い方（クイックスタート）

1. `Compositor` で **Use Nodes** をON。結果確認用に `Viewer` ノードを接続。  
2. Asset Browser から必要なアセットを追加してチェイン（推奨順）：  
   `Exposure（任意） → Color Bloom → Vignette → Overlay_Color_Grading → (Brightness/Contrast) → Composite`  
   ※ 静止画は **Image**、動画は **Movie Clip** ノードで読み込み、チェインの先頭へ接続します。  
3. `Color_Bloom_Composite_Library/composite_example.blend` にサンプルセットアップを同梱。

### 主なパラメータ
> ※ 入力ソケット名は環境によりUI表示順が異なる場合があります。以下は機能の目安です。

- **Color Bloom**  
  - **Image**：元画像入力  
  - **Value（Blur Size）**：拡散（ぼかし）量  
  - **Factor（Bloom Mix）**：ブルームの混合量（Lighten合成の強さ）  
  - **Image（Shadow Tint）**：暗部の着色（青・赤・緑など）  
  - **Image（Highlight Tint）**：ハイライトの着色（白など明るい色が推奨）  
  - **Value（Recolor Strength）**：リカラーの強度  
  - **Factor（Recolor Overlay）**：リカラー画像を元画像にどれくらい重ねるか  

- **Vignette**  
  - **Image**：元画像入力  
  - **Image（Vignette Color）**：ビネットカラー  
  - **Factor**：強さ（0–1）  
  - **Size（Blur）**：エッジのぼけ量  
  - **Size（Radius）**：円の大きさ  

- **Bloom（補助）**  
  - **Image**：元画像入力  
  - **Value（Blur Size）**：拡散量  
  - **Factor**：ブルームの混合量  

- **Overlay_Color_Grading（補助）**  
  - **A（Base Image）**：元画像  
  - **Vector（Tint Color）**：リカラー用の色  
  - **Value（Strength）**：リカラー強度  
  - **Factor（Overlay Mix）**：オーバーレイ合成の混合量  

4. 最終出力は `Composite` ノードへ、確認は `Viewer` ノードへ。

---

## 再現用ファイル

- `Color_Bloom_Composite_Library/composite_example.blend` に4アセットを組み合わせた例を同梱。  
- `demo/` には **Before / After / 比較** 動画が入っています（CC BY 4.0）。

---

## よくある質問（FAQ）

- **Q. Missing Files と出ます**  
  A. `File > External Data > Report Missing Files` で欠損を確認し、必要に応じて `Make All Paths Relative` を実行してください。

- **Q. 商用利用は可能？**  
  A. アセット（`Color_Bloom_Composite_Library/`）は CC0 のため自由に利用・再配布可能です。デモ（`demo/`）は CC BY 4.0 で、再配布の際はクレジット表記が必要です。

---

## クレジット / 連絡先

- **LinkAster**  
- 連絡先: linkaster71@gmail.com

---

## 変更履歴
詳細は `CHANGELOG.md` を参照。
