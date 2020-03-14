# QitzAngleForceUtill
角度や引っ張る力を取得できます！

# 使い方

Unityのプロジェクトは、パッケージからインスコする
https://github.com/QitzPub/QitzAngleForceUtill/raw/master/QitzAngleForceUtill.unitypackage


## コード

ネームスペースで Qitz.AngleForceUtilを指定する。
```C#
using Qitz.AngleForceUtil;
```


### 使い方

![図](https://i.gyazo.com/1ab3de2c2957a64731ca7b7d949a3a20.png "図")<br>
<br>
こんな感じにプレイヤーとカーソルのゲームオブジェクトを配置<br>
<br>

```C#

        [SerializeField]
        GameObject target;
        [SerializeField]
        GameObject curserTarget;

        QitzAngleForceUtil qitzAngleForceUtil;

        // Start is called before the first frame update
        void Start()
        {
            //アングルツールを作成
            this.qitzAngleForceUtil = new QitzAngleForceUtil(target.transform.position);
        }

        // Update is called once per frame
        void Update()
        {
            //現在の角度と引っ張る力を取得
            var angleAndForce = qitzAngleForceUtil.GetAngleAndForce();

            //引っ張る大きさに応じてカーソルの大きさを変える
            curserTarget.transform.localScale = new Vector3(angleAndForce.PullForce, angleAndForce.PullForce);

            //カーソルの向きをAngleに合わせる
            curserTarget.transform.eulerAngles = new Vector3(0, 0, angleAndForce.Angle);

            //カーソル位置をカーソルポジションに合わせる
            curserTarget.transform.position = angleAndForce.CursorPostion;

        }
    

```
こんな感じで、引っ張る大きさや、角度が取得できます！<br>
<br>
![図](https://i.gyazo.com/bd7764a86c9dce24fbe6925f975cb244.gif "図")<br>



