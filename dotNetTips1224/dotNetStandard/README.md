'dotNetStandard' ディレクトリ

　記事では言及しなかったが、Xamarin.Forms での手法 (画像データを SKBitmap に変換してから ZXing.NET に渡す方法) は .NET Standard 1.3 に収まっている。 ならば、その部分を .NET Standard の PCL に切り出すこともできるだろう。 そのように作ってみたのが、 StdLib プロジェクトである。

このやり方のメリット:  
・ 使う側のプロジェクトは、'StdLib' の NuGet パッケージを 1 つインストールするだけ  
・ ともかく画像ファイルのデータをバイト配列にして渡せばよい

デメリット:  
・ プラットフォームによっては無駄な処理が入る (=遅くなる)  
・ プラットフォームによってはバイナリのサイズが大きくなる  
