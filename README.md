# Chrome-with-Secret-Mode-for-MacOSX
This application is for running Google Chrome with Secret mode on MacOSX or for running Google Chrome with Reduce Memory mode using Automator application (Mac OS standard application).

このアプリケーションは、MacOS標準アプリ「Automator」を使って作成された、Google Chrome と Google Chrome Canary（開発版）を、シークレットモードで起動したり、メモリ抑制モードで起動するためのツールです。

Therefore, if you don't install Google Chrome or Google Chrome Canary application, the application doesn't work.

したがって、Google ChromeやGoogle Chrome Canaryがインストールされていないと動作しません。

## Google Chrome with Secret mode
In case of Google Chrome with Secret mode, this application only carries out 'open -n -a "Google Chrome" --args --incognito' or 'open -n -a "Google Chrome Canary" --args --incognito'.

このモードは、起動時のオプションとして、 --incognito を追加します。

## Google Chrome with Reduce memory mode
In case of Google Chrome with Reduce memory mode, the application only carries out 'open -n -a "Google Chrome" --args --renderer-process-limit=1' or 'open -n -a "Google Chrome Canary" --args --renderer-process-limit=1'.

このモードは、起動時のオプションとして、 --renderer-process-limit=1 を追加します。

The reduce memory mode reduces the Chrome memory by controlling the rendering process (Google Chrome Helper). In the mode, when you open a lot of tabs, some tabs might not display until current tab displays. If you want to fix it, please increase the number of renderer-process-limit by opening the tool using Automator application in Application folder and change the value & save it.

このメモリ抑制モードは、レンダリングプロセス（Google Chrome Helper）を抑制することで使用メモリを減らします。このモードでは、沢山のタブを開いた場合、現在のタブが表示されるまでは、他のタブが表示されないかもしれません。このあたりを調整したければ、本ツールを、Automatorアプリ（アプリケーションフォルダ内）にて開いて、 renderer-process-limitの値を増やして保存してみてください。
