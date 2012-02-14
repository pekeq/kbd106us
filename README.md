Windowsの日本語106キーボードをUS-ASCII風配列にする
==================================================

日本語キーボードを英語配列で使う場合、窓使いの憂鬱や、のどか、USJPなどを
利用してキーマップを変更するやり方は結構メジャーですが、ここで紹介する方法は、
キーボード配列の定義をしているDLLを入れ替えてしまうというものです。


使い方
------

### Windows 2000/XP/Vista/7 (32bit)の場合

1.  コントロールパネル → キーボード → ハードウェアを開き、デバイスが「日本語 PS/2　キーボード（106/109キー Ctrl+英数）」に設定されていることを確認する。設定されていない場合は、プロパティ → ドライバ → ドライバの更新で、キーボードのデバイスを変更してください。
    Windows7の場合は、コントロールパネル → コンピューターの簡単操作 → コンピューターの簡単操作センター → キーボードを使いやすくします → キーボード設定（一番下の関連項目のところ） → ハードウェアを開くと確認できます。変更する場合は、プロパティ → 設定の変更 → ドライバー → ドライバーの更新で変更できます。
1.  ダウンロードしたDLLファイルを、"kbd106us.dll"にリネームする。
1.  kbd106us.dllを、%SystemRoot%\System32（C:\WINNT\System32, C:\Windows\System32など）にコピー。
1.  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\i8042prt\parametersの"LayerDriver JPN"を"kbd106us.dll"に変更する。
1.  キーボードのデバイスを変更したりすると内容が戻ってしまう場合があります。その際は再度レジストリを書き換えてください。
1.  再起動


そのほか
--------

* サービスパック適用後など、レジストリ設定が元に戻ってしまう場合がありますので、その際は上記のレジストリ設定を再度行ってください。
* CtrlキーとCapsLockキーを入れ替えたい場合は、ScanCode Mapの変更をすると便利です。


参考リンク
----------

* [Scan Code Mapper for Windows](http://msdn.microsoft.com/en-us/windows/hardware/gg463447.aspx)

* [窓使いの憂鬱](http://mayu.sourceforge.net/)
* [のどか](http://www.appletkan.com/nodoka.htm)
* [USJP](http://www.trinityworks.co.jp/software/)
