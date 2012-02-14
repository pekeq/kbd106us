Windowsの日本語106キーボードをUS-ASCII風配列にする
==================================================

日本語キーボードを英語配列で使う場合、
窓使いの憂鬱(http://mayu.sourceforge.net/)や、
のどか(http://www.appletkan.com/nodoka.htm)、
USJP(http://www.trinityworks.co.jp/software/)などを利用してキーマップを
変更するやり方は結構メジャーですが、ここで紹介する方法は、キーボード配列の
定義をしているDLLを入れ替えてしまうというものです。


使い方
------

### Windows 2000/XP/Vista/7 (32bit)の場合

- コントロールパネル → キーボード → ハードウェアを開き、デバイスが「日本語 PS/2　キーボード（106/109キー Ctrl+英数）」に設定されていることを確認する。設定されていない場合は、プロパティ → ドライバ → ドライバの更新で、キーボードのデバイスを変更してください。
- Windows7の場合は、コントロールパネル → コンピューターの簡単操作 → コンピューターの簡単操作センター → キーボードを使いやすくします → キーボード設定（一番下の関連項目のところ） → ハードウェアを開くと確認できます。変更する場合は、プロパティ → 設定の変更 → ドライバー → ドライバーの更新で変更できます。
- ダウンロードしたDLLファイルを、"kbd106us.dll"にリネームする。
- kbd106us.dllを、%SystemRoot%\System32（C:\WINNT\System32, C:\Windows\System32など）にコピー。
- HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\i8042prt\parametersの"LayerDriver JPN"を"kbd106us.dll"に変更する。
- キーボードのデバイスを変更したりすると内容が戻ってしまう場合があります。その際は再度レジストリを書き換えてください。
- 再起動


そのほか
--------

* サービスパック適用後など、レジストリ設定が元に戻ってしまう場合がありますので、その際は上記のレジストリ設定を再度行ってください。
* CtrlキーとCapsLockキーを入れ替えたい場合は、ScanCode Mapの変更をすると便利です。


参考リンク
----------

* Scan Code Mapper for Windows(http://msdn.microsoft.com/en-us/windows/hardware/gg463447.aspx)
