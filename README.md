# tesseract-vis

テッセラクト／4次元直方体（Orthotope）の可視化Webアプリです。HTMLファイル1つ（Three.js はCDN）で動作します。

**デモ: https://sasekazu.github.io/tesseract-vis/**

## 機能

- **Slice**: 4次元回転後の物体を超平面 `w = w₀` で切った3次元断面（凸多面体）を、ポリゴンメッシュとして厳密に計算して表示
- **Projection**: 16頂点・32辺の4D→3D投影（透視／直交）
- **Comparison**: 投影と断面を左右に並べ、切断位置を半透明メッシュで可視化
- 4次元回転（XW・YW・ZW）、Orthotope の各半幅（a, b, c, d）、`w` の自動往復、4D回転の自動アニメーション
- 3Dカメラの透視／正射影の切替、OrbitControls、CAD風の軸ギズモ（ViewHelper）
- 3Dプリント用の水密STL出力（Slice は断面ソリッド、Projection は球＋ロッドの模型）と、出力前のメッシュ検証

## ローカルで動かす

`index.html` をブラウザで開くだけです（Three.js の読み込みにネットワーク接続が必要）。

## 補足

- 4次元回転の合成順序は `R = R_ZW · R_YW · R_XW` です。
- 3Dカメラの視点操作は、4次元回転とは独立です。
