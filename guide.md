```
<document> := <root>
<root> := <paragraph>\n*
<paragraph> := {<block> | <inline>}.
<block> := {<code> | <inline>.}
<code> := @@<attr>\n<inline>.@@
<inline> := <plain> | <emphasize>
<emphasize> := <heading> | <hr> | <list> | <bold> | <italic> | <underline> | <quote> | <link>
<heading> := #[1-3]\  <plain>
<attr> := pop
```
受け取った文字列に対して以下の操作を行う。

1. `\n`で分割して各行の内容を要素としたイテレータオブジェクトに分割する。
2. 分割された要素の文字列を上記の正規表現にてマッチするかどうかを判定、マッチしたのちはそれ以外の要素を切り出す。


```ts
type token {
	kind: T;

}
```
