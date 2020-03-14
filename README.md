# QitzAdPlagins 
QitzのAdプラグインのラッパーです！

# 使い方

Unityのプロジェクトは、パッケージからインスコする
https://github.com/QitzPub/QitzAdPlagins/raw/master/QitzAdPlagins/Archives/QitzAdModule.unitypackage


## コード

ネームスペースで Qitz.AdModulesを指定する。
```C#
using Qitz.AdModules;
```

## プレファブの設定

![プレファブ](https://i.gyazo.com/2dcb081926a37f0e0eb4629a5808f9c6.png "プレファブ")<br>
<br>
Assets/QitzAdModule/Resources/QitzAdModule.prefab<br>
を開く<br>
<br>
![プレファブ](https://i.gyazo.com/d60eae06d0e98890fff1839f51bd0ce7.png"プレファブ")<br>
<br>
GoogleのAdmobの各種AdIDを入れる

### 使い方
```C#

    public class DemoLoadAds : MonoBehaviour, IAdModuleReceiver
    {
    

```
こんな感じで「IAdModuleReceiver」を実装します


### 使い方続き
```C#

    public class DemoLoadAds : MonoBehaviour, IAdModuleReceiver
    {
        public bool IsLoadedInterstitial => this.GetQitzAdModule().IsLoadedInterstitial;

        public bool IsLoadedReward => this.GetQitzAdModule().IsLoadedReward;

        public void DestroyBanner()
        {
            this.GetQitzAdModule().DestroyBanner();
        }

        public void SetRewardedCallBack(Action rewardedCallBack)
        {
            this.GetQitzAdModule().SetRewardedCallBack(rewardedCallBack);
        }

        public void ShowBanner()
        {
            this.GetQitzAdModule().ShowBanner();
        }

        public void ShowInterstitial()
        {
            this.GetQitzAdModule().ShowInterstitial();
        }

        public void ShowReword()
        {
            this.GetQitzAdModule().ShowReword();
        }
    }

```
こんな感じでバナーを読み込んだり、インタースティシャル広告やリワード広告を表示できます。
