mlterm-fbを使ってみる
---------------------
リソースの限られたマシンでは、Xを起動させるだけでリソースを使いきってしまう場合があります。
mlterm (pkgsrc/x11/mlterm) [mlterm]_ は、X上で動作する多言語ターミナルエミュレータですが、mlterm-fbを有効にしてコンパイルすると、フレームバッファ上で動作する多言語ターミナルエミュレータとして利用できます。

.. image:: ../Picture/2013/08/02/DSC_2283.jpg
 :width: 800

mlterm-fb向けオプション設定
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
/etc/mk.confに、mltermに与えるオプションを指定しておきます。pkgsrc/x11/mlterm以下を利用して、mltermをインストールします。

::

 % grep mlterm /etc/mk.conf
 PKG_OPTIONS.mlterm=xft2 mlterm-fb
 # cd /usr/pkgsrc/x11/mlterm
 # make package-install
 # which mlterm-fb
 /usr/pkg/bin/mlterm-fb

起動
~~~~
 コンソール画面からmlterm-fbを起動します。

::

 % mlterm-fb

PCでのmlterm-fb起動
""""""""""""""""""""""
NetBSD/i386,amd64でmlterm-fbを利用する場合、起動時にVESAを指定します。

#. 起動オプションで5を選択
#. > プロンプトでvesa を指定
#. boot
#. 起動
#. ログイン
#. mlterm-fb起動

テスト画像表示
~~~~~~~~~~~~~~
 mlterm-fbを起動した状態で、catを利用して、画像イメージを表示します。

::

 % ftp http://mlterm.sourceforge.net/vimperator.six
 % cat vimperator.six

mltermについて
~~~~~~~~~~~~~~~
 *http://mlterm.sourceforge.net/* に、より詳しい情報があります。

mlterm-fb上でtwを動かしてみる
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

mlterm-fb上で日本語が表示できたら、tw [tw]_ を利用してツイッターのタイムラインを表示してみましょう。

twのインストール
""""""""""""""""
pkgsrcからtwをインストールします。

::

 # cd /usr/pkgsrc/net/ruby-tw
 # make package-install 

.. rubic:: 

.. [mlterm] mlterm http://mlterm.sourceforge.net/
.. [tw] tw http://shokai.github.io/tw/
.. [はよーん] http://jnug.net/msg012914ja.html

