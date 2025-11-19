# コンテンツ追加ガイド

このドキュメントでは、ウェブサイトに新しいコンテンツ（楽譜、数学ドキュメント、動画、その他資料）を追加する際の手順を説明します。

## 1. コンテンツ追加の基本構造

各コンテンツ項目は、`style.css` で定義された `content-item` クラスを持つ `div` 要素で構成されています。この構造を維持して追加してください。

```html
<div class="content-item">
  <div class="content-item-text">
    <h4>[ファイル名またはタイトル]</h4>
    <p>[説明のプレースホルダー | Description placeholder]</p>
  </div>
  <!-- ページに応じて以下のいずれか、または両方を配置します -->
  <!-- 閲覧ボタン (ブラウザで開く) -->
  <a href="[ファイルのパスまたは外部URL]" class="view-button" target="_blank">閲覧 | View</a>
  <!-- ダウンロードボタン (ファイルをダウンロード) -->
  <a href="[ファイルのパス]" download class="download-button" style="margin-left: 10px;">ダウンロード | Download</a>
</div>
```

-   `<h4>`: ファイル名またはコンテンツのタイトルを日本語と英語で記述します。
-   `<p>`: コンテンツの簡単な説明を日本語と英語で記述します。
-   `<a>` (閲覧ボタン):
    *   `href`: ファイルへのパス（例: `score/your_new_score.pdf`）または外部サイトのURLを指定します。
    *   `class="view-button"`: 閲覧ボタンとして表示するためのクラスです。
    *   `target="_blank"`: 新しいタブで開くようにします。
-   `<a>` (ダウンロードボタン):
    *   `href`: ファイルへのパス（例: `score/your_new_score.pdf`）を指定します。
    *   `download`: ファイルをダウンロードさせるための属性です。
    *   `class="download-button"`: ダウンロードボタンとして表示するためのクラスです。
    *   `style="margin-left: 10px;"`: 閲覧ボタンとの間にスペースを設ける場合に使用します。

## 2. 楽譜 (`scores.html`) および数学ドキュメント (`math.html`) の追加方法

コンテンツの種類によって、表示するボタンが異なります。

### 楽譜 (`scores.html`) の場合

楽譜ページでは、**ダウンロードボタンのみ**を配置します。

1.  **ファイルを配置する:**
    *   新しい楽譜のPDFファイルは `score/` ディレクトリに配置します。

2.  **HTMLファイルを編集する:**
    *   `scores.html` を開きます。
    *   適切なセクションに、以下の構造に従って新しい `div.content-item` ブロックを追加します。
    *   `href` 属性には、配置したファイルのパスを正確に記述します（例: `score/your_new_score.pdf`）。
    *   `<h4>` タグ内にファイル名を記述します。
    *   `<p>` タグ内に説明を記述します。

    **例 (scores.html):**
    ```html
    <div class="content-item">
      <div class="content-item-text">
        <h4>新しい楽譜.pdf | New Score.pdf</h4>
        <p>これは新しく追加された楽譜の説明です。 | This is a description of the newly added score.</p>
      </div>
      <a href="score/新しい楽譜.pdf" download class="download-button">ダウンロード | Download</a>
    </div>
    ```

### 数学ドキュメント (`math.html`) の場合

数学ドキュメントページでは、**閲覧ボタンのみ**を配置します。

1.  **ファイルを配置する:**
    *   新しい数学ドキュメントのPDFファイルは `math/questions_by_me/` または `math/study_output/` ディレクトリに配置します。

2.  **HTMLファイルを編集する:**
    *   `math.html` を開きます。
    *   適切なセクションに、以下の構造に従って新しい `div.content-item` ブロックを追加します。
    *   `href` 属性には、配置したファイルのパスを正確に記述します（例: `math/your_new_doc.pdf`）。
    *   `<h4>` タグ内にファイル名を記述します。
    *   `<p>` タグ内に説明を記述します。

    **例 (math.html):**
    ```html
    <div class="content-item">
      <div class="content-item-text">
        <h4>新しい数学ドキュメント.pdf | New Math Document.pdf</h4>
        <p>これは新しく追加された数学ドキュメントの説明です。 | This is a description of the newly added math document.</p>
      </div>
      <a href="math/新しい数学ドキュメント.pdf" class="view-button" target="_blank">閲覧 | View</a>
    </div>
    ```

## 3. 演奏動画 (`videos.html`) の追加方法

1.  **HTMLファイルを編集する:**
    *   `videos.html` を開きます。
    *   `main-content` 内に、上記の「基本構造」に従って新しい `div.content-item` ブロックを追加します。
    *   `href` 属性には、動画が公開されている外部サイトのURL（例: YouTube、ニコニコ動画など）を記述します。
    *   `download` 属性は不要です。
    *   リンクテキストは「詳細を見る | View Details」など、外部サイトへの誘導がわかるように記述します。

    **例 (videos.html):**
    ```html
    <div class="content-item">
      <div class="content-item-text">
        <h4>新しい演奏動画 | New Performance Video</h4>
        <p>YouTubeで公開されている新しい演奏動画です。 | This is a new performance video published on YouTube.</p>
      </div>
      <a href="https://www.youtube.com/watch?v=your_video_id" target="_blank" class="download-button">詳細を見る | View Details</a>
    </div>
    ```
    *`target="_blank"` を追加すると、新しいタブでリンクが開きます。

## 4. その他資料 (`misc.html`) の追加方法

1.  **HTMLファイルを編集する:**
    *   `misc.html` を開きます。
    *   `main-content` 内に、上記の「基本構造」に従って新しい `div.content-item` ブロックを追加します。
    *   `href` 属性には、資料へのパスまたは外部サイトのURLを記述します。
    *   必要に応じて `download` 属性を追加します。

    **例 (misc.html):**
    ```html
    <div class="content-item">
      <div class="content-item-text">
        <h4>新しい資料.pdf | New Document.pdf</h4>
        <p>これは新しく追加されたその他の資料です。 | This is a new miscellaneous document.</p>
      </div>
      <a href="misc/新しい資料.pdf" download class="download-button">ダウンロード | Download</a>
    </div>
    ```

## 5. CommentBoxの統合方法

コメント機能としてCommentBoxを導入する場合、以下の手順で設定してください。

1.  **CommentBoxアカウントの作成と設定:**
    *   CommentBoxのウェブサイトにアクセスし、アカウントを作成します。
    *   ご自身のウェブサイト（`kawawan.github.io`）をCommentBoxに登録し、コメントウィジェットの設定を行います。
    *   設定が完了すると、CommentBoxからウェブサイトに埋め込むためのJavaScriptコード（埋め込みコード）が提供されます。

2.  **埋め込みコードの貼り付け:**
    *   `scores.html` および `math.html` には、既にCommentBoxの埋め込みコードを貼り付けるためのプレースホルダーが用意されています。
    *   各ファイルの `main-content` セクションの最後に、以下の `div` 要素があります。
        ```html
        <div id="commentbox-comments" style="margin-top: 40px;">
          <h3>コメント | Comments</h3>
          <p>ここにCommentBoxの埋め込みコードを貼り付けてください。<br>Please paste your CommentBox embed code here.</p>
          <!-- CommentBox embed code will go here -->
        </div>
        ```
    *   `<!-- CommentBox embed code will go here -->` のコメント部分を削除し、CommentBoxから提供されたJavaScriptの埋め込みコードをそこに貼り付けてください。

    **例:**
    ```html
    <div id="commentbox-comments" style="margin-top: 40px;">
      <h3>コメント | Comments</h3>
      <p>ここにCommentBoxの埋め込みコードを貼り付けてください。<br>Please paste your CommentBox embed code here.</p>
      <script src="https://commentbox.io/static/js/widget.js?token=YOUR_COMMENTBOX_TOKEN" async></script>
    </div>
    ```
    *`YOUR_COMMENTBOX_TOKEN` はご自身のCommentBoxトークンに置き換えてください。

## 注意事項

*   **多言語対応:** タイトルや説明、リンクテキストは必ず日本語と英語の両方を併記してください。
*   **パスの正確性:** `href` 属性に指定するファイルのパスは、ウェブサイトのルートからの相対パスで正確に記述してください。
*   **HTMLの整合性:** 追加するHTMLコードが既存の構造と整合性が取れていることを確認してください。
*   **`_config.yml`:** GitHub PagesでJekyllを使用している場合、`_config.yml` の設定によっては、特定のファイルが処理されない場合があります。必要に応じて確認してください（現在の設定では特に問題ないはずです）。

このガイドを参考に、コンテンツの追加を行ってください。不明な点があれば、いつでも質問してください。
