# Chrome-with-Secret-Mode-for-MacOSX
This application is for running Google Chrome with Secret mode on MacOSX or for running Google Chrome with Reduce Memory mode using Automator application (Mac OS standard application) and Apple Script.

このアプリケーションは、MacOS標準アプリ「Automator」（一部 Apple スクリプトバージョンあり）を使って作成された、Google Chrome と Google Chrome Canary（開発版）を、シークレットモードで起動したり、メモリ抑制モードで起動するためのツールです。

If you want to change the options, please open it by Automator or Apple Script.

もし、オプション変更したい場合には、Automator、Apple スクリプトなど、作成された各ツールで開いてください。

Therefore, if you don't install Google Chrome or Google Chrome Canary application, the application doesn't work.

したがって、Google ChromeやGoogle Chrome Canaryがインストールされていないと動作しません。

## Components 
Google Chrome with Reduce memory mode

Option --renderer-process-limit=1

- Google Chrome (process limication).app (Apple Script)
- Google Chrome Canary (process limication) (Apple Script)
- Google Chrome (Reduce Memory).app (Automator)
- Google Chrome Canary (Reduce Memory) (Automator)

Google Chrome with Secret mode

Option  --incognito

- Google Chrome (Run as Secret Mode).app (Automator)
- Google Chrome Canary (Run as Secret Mode) (Automator)

Option. --ssl-version-min="tls1.1"

Restriction tls mode

- Google Chrome (tls1.0 disabled).app  (Automator)
- Google Chrome (tls1.1 or prev disabled).app (Automator)
- Google Chrome Canary (tls1.0 disabled).app  (Automator)
- Google Chrome Canary (tls1.1 or prev disabled).app (Automator)


## Google Chrome with Secret mode
In case of Google Chrome with Secret mode, this application only carries out 'open -n -a "/Applications/Google Chrome.app" --args --incognito' or 'open -n -a "/Applications/Google Chrome Canary.app" --args --incognito'.

このモードは、起動時のオプションとして、 --incognito を追加します。

## Google Chrome with Reduce memory mode
In case of Google Chrome with Reduce memory mode, the application only carries out 'open -n -a "/Applications/Google Chrome.app" --args --renderer-process-limit=3' or 'open -n -a "/Applications/Google Chrome Canary.app" --args --renderer-process-limit=3'.

このモードは、起動時のオプションとして、 --renderer-process-limit=1 を追加します。

The reduce memory mode reduces the Chrome memory by controlling the rendering process (Google Chrome Helper). In the mode, when you open a lot of tabs, some tabs might not display until current tab displays. If you want to fix it, please increase the number of renderer-process-limit by opening the tool using Automator application in Application folder and change the value & save it.

このメモリ抑制モードは、レンダリングプロセス（Google Chrome Helper）を抑制することで使用メモリを減らします。このモードでは、沢山のタブを開いた場合、現在のタブが表示されるまでは、他のタブが表示されないかもしれません。このあたりを調整したければ、本ツールを、Automatorアプリ（アプリケーションフォルダ内）にて開いて、 renderer-process-limitの値を増やして保存してみてください。

Google Chrome (process limitation).app and Google Chrome Canary (process limitation).app are "Google Chrome with Reduce memory mode" tool used by "Apple Script".
You can use the number of process limitation on Apple Script Editor.
Please open the script file by "Apple Script Editor". Default limitation number is 3.

Google Chrome (process limitation).app と Google Chrome Canary (process limitation).appは、Apple Script で作成したメモリ抑制のためのツールです。
Appleスクリプトエディタでこのファイルを開くと簡単に値を変更できます。デフォルトは3にしています。

## Restriction tls mode
Chrome 81 (early 2020) will be disabled tls1.0 and 1.1, so we need to check our web sites using a web browser which disables tls1.0 and 1.1. Chrome can set tls restriction mode using option "--ssl-version-min".
Reference: https://www.chromestatus.com/feature/5654791610957824
https://peter.sh/experiments/chromium-command-line-switches/

Chrome 81 (2020年早期) に、tls1.0と1.1 がChromeから排除されます。その前に tls1.0と1.1を無効にしたブラウザでサイトをチェックしたいと思うかもしれません。Chromeでそれを実現するには、起動オプション「--ssl-version-min」を設定することで可能です。
参考：
https://www.chromestatus.com/feature/5654791610957824
https://peter.sh/experiments/chromium-command-line-switches/

