dotinstall-grunt
================

## 1. グローバル環境構築

グローバルにgruntコマンドをインストールする。<br>
lessの自動コンパイルも行うので入れてなければインストール。

<pre>
npm install -g grunt-cli
npm install -g less
</pre>

## 2. 開発環境構築

package.jsonのひな形を作る。

<pre>
npm init
<pre>

gruntインストール。package.jsonに追記する場合は

<pre>
npm install grunt --save-dev
</pre>

既存プロジェクトを他のマシンで動かす場合は下記で良い。

<pre>
npm install
</pre>

## 3. Gruntfile.jsを作って編集する

gruntのプラグインは[gruntjs.com/plugins](http://gruntjs.com/plugins)に揃っている。
まずはgruntが公式にメンテナンスしているcontribから使ってみる。

<pre>
npm install grunt-contrib --save-dev
</pre>

config, pluginLoad, taskで構成されている。

<pre>
module.exports = function(grunt){
  // config
  grunt.initConfig({
    task:{
      target:{
        config
      }
    }
    .
    .
    .
  });

  // plugin
  grunt.loadNpmTasks('grunt-contrib');

  // task
  grunt.registerTask('default', 'task');
};
</pre>

* less: lessコンパイル
* csslint: css構文チェック
* cssmin: css圧縮
* watch: ファイル更新検知
* connect: 簡易サーバー(+livereload)

の設定に関しては[こちら](https://github.com/Mrk1869/dotinstall-grunt/blob/master/Gruntfile.js)を参考。

livereloadにはブラウザ拡張(Chromeだと[ここから](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei))の事前インストールが必要