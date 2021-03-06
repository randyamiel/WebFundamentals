project_path: /web/_project.yaml
book_path: /web/fundamentals/_book.yaml
description: alt 属性を使用して画像に代替テキストを提供する


{# wf_updated_on:2016-10-04 #}
{# wf_published_on:2016-10-04 #}

#  画像の代替テキスト {: .page-title }

{% include "web/_shared/contributors/megginkearney.html" %}
{% include "web/_shared/contributors/dgash.html" %}
{% include "web/_shared/contributors/aliceboxhall.html" %}



ほとんどのウェブページで画像は重要な要素ですが、当然のことながら、視覚に障がいがある方には特有の問題があります。
ページで画像が果たす役割を検討し、どのようなタイプの代替テキストを設定して機能させるのかを検討する必要があります。



    <article>
      <h2>研究によると、10 匹のうち 9 匹の猫が、飼い主の睡眠中、静かに飼い主のことを判断している</h2>
      <img src="imgs/160204193356-01-cat-500.jpg">
    </article>

<article>
  <h2>研究によると、10 匹のうち 9 匹の猫が、飼い主の睡眠中、静かに飼い主のことを判断している</h2>
  <img src="imgs/160204193356-01-cat-500.jpg">
</article>

猫の写真があるページでは、猫が飼い主を判断するという有名な習性に関する記事の説明をしています。
スクリーン リーダーは、この画像のリテラル名、`"/160204193356-01-cat-500.jpg"` を読み上げます。
正確とはいえ、まったく実用的ではありません。


`alt` 属性を使用すると、たとえば「疑わしそうに凝視する猫」など、この画像に有用な代替テキストを指定できます。


    <img src="/160204193356-01-cat-500.jpg" alt="疑わしそうに凝視する猫">

これで、スクリーン リーダーは画像の簡潔な説明を読み上げることができ（黒い VoiceOver バーを参照）、ユーザーは記事に移動するかどうかを選択できます。



![改善された alt テキスト付きの画像](imgs/funioncat2.png)

`alt` に関するコメント:

 - `alt` を使用すると、画像が使えなくても、いつでも使用できる単純な文字列を指定できます。たとえば、画像の読み込みに失敗したり、画像がウェブ クローラー ボットにアクセスされたり、またはスクリーン リーダーからアクセスしたときなどが考えられます。


 - `alt` は `title` やその他のタイプのキャプションとは異なり、画像が使用できない場合に*のみ*使用されます。


有用な alt テキストを記述するには少し工夫が必要です。文字列を使いやすい代替テキストにするには、画像と同じコンセプトを、同じコンテキストで伝える必要があります。



上の図のように、ページの先頭にあるリンク付きのロゴ画像で考えてみましょう。この画像を正確に表すと「Funion ロゴ」のように記述できます。


    <img class="logo" src="logo.jpg" alt="Funion ロゴ">

「ホーム」や「メインページ」といったさらにシンプルな代替テキストも考えられますが、これは視覚障がいの有無にかかわらずデメリットがあります。


ページの先頭のロゴを探しているスクリーン リーダーのユーザーの場合は、「ホーム」という alt 値を指定すると、さらに混乱する可能性があります。

視覚に障がいのないユーザーも、サイトのロゴをクリックすると何が起きるかを認識するという面で、スクリーン リーダーのユーザーと同じ課題に直面します。


一方、画像を説明することが必ずしも役立つとは限りません。たとえば、「検索」というテキスト付きの検索ボタン内に、虫メガネの画像があるとします。

テキストが存在しなかったとしたら、間違いなく画像に「検索」という alt 値を設定するところですが、
テキストが表示されているため、スクリーン リーダーは「検索」という単語を選んで読み上げます。そのため、画像に同一の `alt` 値を設定してしまうと、冗長になります。



ただし、`alt` テキストを書かなければ、代わりに画像ファイル名が読み上げられる可能性があり、意味がないうえに混乱を招きます。
このような場合、単に空の `alt` 属性を使用します。そうすれば、スクリーン リーダーは画像も一緒にスキップします。



    <img src="magnifying-glass.jpg" alt="">

まとめると、すべての画像に `alt` 属性を指定する必要がありますが、常にテキストが必要とは限りません。
重要な画像には画像の内容を説明する alt テキストを指定する必要がありますが、装飾的な画像には空の alt、つまり `alt=""` を指定する必要があります。




{# wf_devsite_translation #}
