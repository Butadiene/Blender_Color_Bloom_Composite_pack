# はじめての仕上げ：素材を差し替えてレンダリング（超シンプル）
対象：Blender初心者（写真・動画） / 所要：**5〜10分**  
使用ファイル：`Color_Bloom_Composite_Library/composite_example.blend`（コンポジットノードが既に接続済み）

---

## ゴール
- 付属の `.blend` を開く
- 画像 or 動画ノードに自分の素材を差し替える
- 少しだけパラメータを触って雰囲気を見る
- 静止画 または 動画としてレンダリングする

---

## 1) `.blend` を開く
1. Blender 起動 → **File > Open** → `Color_Bloom_Composite_Library/composite_example.blend` を開く。
2. 上部タブから **Compositing** を選び、**Use Nodes** がONになっていることを確認。
   - 本シーンは **3Dオブジェクトは無く**、**コンポジットノードのみ**が接続済みです。

---

## 2) 素材を差し替える（画像 or 動画）
### 画像の場合
1. ノードエディタで **Shift+A > Input > Image** を追加して **Open** から写真を選択。
2. 既存の入力ノード（Movie clip）と差し替え、チェインの**最初**に接続する（他のノード接続は既存のまま）。

### 動画の場合
1. **Shift+A > Input > Movie Clip** を追加して **Open** から動画を選択。
2. 既存の入力ノード（Movie clip）と差し替え、Movie Clip ノードをチェインの**最初**に接続。
3. 右側 **Output Properties > Frame Range** で **Start/End** を動画の長さに合わせる。

> 画面確認用に **Shift+A > Output > Viewer** を追加し、チェインの最後を Viewer にも繋ぐと結果が見やすくなります。（最初から追加されているはずです。）

---

## 3) パラメータを少し触ってみる
- ノードの「Factor」「Color」など、**分かりやすい一つだけ**を少し上下して雰囲気を確認。  
- 迷ったら、変更前後を比べるために **Ctrl+Z**（一つ戻る）を活用しましょう。  
- パラメーターの説明はREADME.mdにあります。

---

## 4) レンダリングする
### 静止画として書き出し
1. **F12** でレンダー。
2. 画像エディタ上部 **Image > Save** から保存。形式は **PNG** か **JPEG** が一般的。

### 動画として書き出し
1. 右側 **Output Properties**：  
   - **File Format** → `FFmpeg video`  
   - **Container** → `MPEG-4`  
   - **Video Codec** → `H.264`
2. 出力先（**Output** 欄のフォルダアイコン）を任意のパスに指定。
3. 上部メニュー **Render > Render Animation** を実行。

---

## よくある質問
- **結果が真っ黒/真っ白**：入力ノードがチェインの最初に繋がっているか確認。Viewer にも繋いで確認。  
- **アニメーションが短い/長い**：**Output Properties > Frame Range** の Start/End を動画に合わせる。  