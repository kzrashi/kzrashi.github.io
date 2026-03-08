## NXP ソフトリンク
- NotebookLM登録おすすめURL（優先度順・ソフトウェア理解に特化）i.MX Linux User's Guide（最重要：全体のソフトウェアアーキテクチャとBSP構築のバイブル）  
https://www.nxp.com/docs/en/user-guide/UG10163.pdf  
→ BSPのビルド手順、ブートフロー（U-Boot → Kernel → Rootfs）、デバイスツリー、フラッシュ方法、特殊機能（GPU/NPU統合含む）の詳細が178ページにわたって網羅。まずこれを入れて「i.MX 95のLinux BSP構成を説明して」と聞くと全体像がつかめます。

- i.MX Yocto Project User's Guide（Yoctoビルドの核心）  
https://www.nxp.com/docs/en/user-guide/UG10164.pdf    
→ Yoctoを使ったBSPイメージビルド手順、レイヤー構成（meta-imxなど）、imx95-19x19-lpddr5-evk向けのMACHINE設定、追加パッケージ（eIQ含む）のカスタマイズ方法を詳述。i.MX 95のBSPは完全にYocto依存なので必須。  

- i.MX Machine Learning User's Guide（eIQ Neutron NPUのソフトウェアスタック理解に最適）  
https://www.nxp.com/docs/en/user-guide/UG10166.pdf  
→ TensorFlow Lite / ONNX Runtime / PyTorch / OpenCVの統合、Neutron Delegateの使い方、NPUアクセラレーションの詳細、モデルデプロイ手順。i.MX 95のEdge AIソフト構成の肝。ここを入れると「Neutron NPUのソフトウェアフローは？」が深く理解できます。

- Embedded Linux for i.MX Applications Processors（公式Linuxページ・BSPダウンロード入口）  
https://www.nxp.com/design/design-center/software/embedded-software/i-mx-software/embedded-linux-for-i-mx-applications-processors:IMXLINUX  
→ 最新BSPリリース情報、ソース取得（GitHub: nxp-imx/imx-manifest）、Release Notesへのリンク。Yocto manifestのブランチ（例: imx-6.12.49-2.2.0.xml）もここから追える。

- i.MX 95 EVK Quick Start Guide（実機でのソフトウェア立ち上げ手順）  
https://www.nxp.com/docs/en/quick-reference-guide/IMX95LPD5EVK-19CM.pdf  
→ 工場出荷イメージのブート、ソフトウェアダウンロード場所（nxp.com/imxsw）、eMMC/SDへの書き込み。ハードとソフトのつなぎ目がわかる。

- How to Run Application on M7 Core of i.MX 95（M7コアのRTOS/BareMetal構成理解）  
https://www.nxp.com/docs/en/application-note/AN14748.pdf  
→ MCUXpresso SDKを使ったM7アプリビルド、imx-mkimageとの連携、ITCM/DDR実行、FreeRTOS例。異種コア（Aコア + M7）のソフト構成が具体的にわかる。

- i.MX Software and Development Tools（全体ソフトウェアエコシステムの概要）  
https://www.nxp.com/design/design-center/software/embedded-software/i-mx-software:IMX-SW  
→ Linux/Android/FreeRTOS/QNX/GHSなどのOSサポート一覧、eIQ、Real-time Edge Softwareへのリンク。i.MX 95のマルチOS対応が俯瞰できる。

## 学習ルート
学習の進め方Tips（NotebookLM活用）まず1・2・3を登録 →  
「i.MX 95のLinuxソフトウェアスタック全体をブロック図風にまとめて」「YoctoでeIQを有効にする方法は？」からスタート    
NPU/AIに興味 → 3を深掘り（Neutron Delegateの章が秀逸）    
M7/M33のリアルタイム部分 → 6を追加    
最新BSPバージョン確認 → 4のページを定期的にブラウズ（GitHubリポジトリも併用可：https://github.com/nxp-imx/meta-imx）  
Androidも興味あれば → Android User's Guide（UG10156）やAndroidページ（https://www.nxp.com/design/design-center/software/embedded-software/i-mx-software/android-os-for-i-mx-applications-processors:IMXANDROID）も追加  


