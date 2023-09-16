# 👋 Hi there, This is Lruihao

![views](https://komarev.com/ghpvc/?username=Lruihao&color=ff69b4)

- 👨‍💻 A front-end development engineer.
- 👨‍💼 The creator of [@hugo-fixit][hugo-fixit].
- 📝 I regularly write articles and docs on 菠菜眾長[^1] and FixIt[^2].
- 📫 How to reach me: [微博](https://weibo.com/liahao)

## Latest Blog Posts

<!-- BLOG-POST-LIST:START -->
 - 📝[JS 实现全屏和退出全屏 - Blog](https://lruihao.cn/posts/js-fullscreen/ &lt;h2 id=&quot;背景&quot;&gt;背景&lt;/h2&gt;
&lt;p&gt;在 Web 开发中，全屏模式可以提供更沉浸式的体验，特别适用于视频播放、游戏展示和演示等场景。通过 JavaScript 的 Fullscreen API，我们可以以编程方式控制元素的全屏状态。&lt;/p&gt;
&lt;p&gt;Fullscreen API 是一组用于控制全屏显示的方法和属性，它们允许我们将网页内容以全屏的方式展示给用户，并提供了相应的事件来监听全屏模式的变化。&lt;/p&gt;
&lt;p&gt;在本文中，我们将介绍如何判断浏览器是否支持全屏功能，如何实现进入全屏和退出全屏的功能，以及如何获取当前全屏元素和监听全屏模式的变化。&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;注意：Fullscreen API 在不同浏览器之间可能存在差异，请在使用时进行兼容性测试和处理。&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;全屏是否可用&quot;&gt;全屏是否可用&lt;/h2&gt;
&lt;p&gt;在使用 Fullscreen API 之前，我们需要先判断当前浏览器是否支持全屏功能。可以通过 &lt;code&gt;document.fullscreenEnabled&lt;/code&gt; 属性来检查。&lt;/p&gt;
&lt;p&gt;以下是一个示例：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-javascript&quot; data-lang=&quot;javascript&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;fullscreenEnabled&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mozFullScreenEnabled&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;webkitFullscreenEnabled&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;msFullscreenEnabled&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;log&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;浏览器支持全屏功能&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;log&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;浏览器不支持全屏功能&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;详细的 API 说明可以参考 &lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Fullscreen API - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;。&lt;/p&gt;
&lt;h2 id=&quot;实现全屏&quot;&gt;实现全屏&lt;/h2&gt;
&lt;p&gt;要实现全屏，我们可以使用 &lt;code&gt;requestFullscreen&lpar;&rpar;&lt;/code&gt; 方法。该方法可用于 DOM 元素，使其进入全屏模式。&lt;/p&gt;
&lt;p&gt;以下是一个示例：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-javascript&quot; data-lang=&quot;javascript&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;getElementById&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;my-element&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;requestFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;requestFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mozRequestFullScreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Firefox
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mozRequestFullScreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;webkitRequestFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Chrome, Safari and Opera
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;webkitRequestFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;msRequestFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Internet Explorer and Edge
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nx&quot;&gt;element&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;msRequestFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;详细的 API 说明可以参考 &lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullscreen&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Element.requestFullscreen&lpar;&rpar; - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;。&lt;/p&gt;
&lt;h2 id=&quot;退出全屏&quot;&gt;退出全屏&lt;/h2&gt;
&lt;p&gt;当我们需要退出全屏时，可以使用 &lt;code&gt;exitFullscreen&lpar;&rpar;&lt;/code&gt; 方法。该方法可用于当前处于全屏状态的元素。&lt;/p&gt;
&lt;p&gt;以下是一个示例：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;9
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-javascript&quot; data-lang=&quot;javascript&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;exitFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;exitFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mozCancelFullScreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Firefox
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mozCancelFullScreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;webkitExitFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Chrome, Safari and Opera
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;webkitExitFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;msExitFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Internet Explorer and Edge
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;msExitFullscreen&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;详细的 API 说明可以参考 &lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Document/exitFullscreen&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Document.exitFullscreen&lpar;&rpar; - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;。&lt;/p&gt;
&lt;h2 id=&quot;获取全屏元素&quot;&gt;获取全屏元素&lt;/h2&gt;
&lt;p&gt;在全屏模式下，我们可能需要获取当前处于全屏状态的元素。可以使用&lt;code&gt;document.fullscreenElement&lt;/code&gt;属性来获取。&lt;/p&gt;
&lt;p&gt;以下是一个示例：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-4&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;7
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-javascript&quot; data-lang=&quot;javascript&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;fullscreenElement&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;fullscreenElement&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mozFullScreenElement&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;webkitFullscreenElement&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;msFullscreenElement&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;fullscreenElement&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;log&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;当前全屏元素：&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;fullscreenElement&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;log&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;没有全屏元素&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;详细的 API 说明可以参考 &lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Document.fullscreenElement - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;。&lt;/p&gt;
&lt;h2 id=&quot;监听全屏模式变化&quot;&gt;监听全屏模式变化&lt;/h2&gt;
&lt;p&gt;如果我们希望在全屏模式发生变化时得到通知，可以使用 Fullscreen API 提供的事件。&lt;/p&gt;
&lt;p&gt;以下是一个示例：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-5&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-javascript&quot; data-lang=&quot;javascript&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;addEventListener&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;fullscreenchange&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;handleFullscreenChange&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;addEventListener&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;mozfullscreenchange&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;handleFullscreenChange&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Firefox
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;addEventListener&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;webkitfullscreenchange&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;handleFullscreenChange&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Chrome, Safari and Opera
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;addEventListener&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;MSFullscreenChange&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;handleFullscreenChange&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// Internet Explorer and Edge
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kd&quot;&gt;function&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;handleFullscreenChange&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;fullscreenElement&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mozFullScreenElement&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;webkitFullscreenElement&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;||&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;msFullscreenElement&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;log&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;进入全屏模式&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;else&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;log&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;退出全屏模式&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;通过添加相应的事件监听器，可以在全屏模式变化时执行自定义的处理函数。&lt;/p&gt;
&lt;h2 id=&quot;相关插件&quot;&gt;相关插件&lt;/h2&gt;
&lt;p&gt;了解以上 API 后本来已经准备开始写插件了，不过秉承不重复造轮子的思想，找到了以下两个库，基本满足开发需求了。&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/sindresorhus/screenfull&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;screenfull&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/mirari/vue-fullscreen&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;vue-fullscreen&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;h2 id=&quot;小插曲&quot;&gt;小插曲&lt;/h2&gt;
&lt;p&gt;&lt;code&gt;document.fullscreen&lt;/code&gt;、&lt;code&gt;document.fullscreenElement&lt;/code&gt;、&lt;code&gt;document.fullscreenEnabled&lt;/code&gt; 的 MDN 文档中文翻译已过时，然后顺手提了一个 PR &lt;a href=&quot;https://github.com/mdn/translated-content/pull/15859&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;mdn/translated-content#15859&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/p&gt;
&lt;h2 id=&quot;参考链接&quot;&gt;参考链接&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Fullscreen API - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullscreen&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Element.requestFullscreen&lpar;&rpar; - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Document/exitFullscreen&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Document.exitFullscreen&lpar;&rpar; - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Document.fullscreenElement - MDN Web Docs&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
)
 - 🔥[中文翻译的常见问题 - Blog](https://lruihao.cn/posts/translation-guide/ &lt;blockquote&gt;
&lt;p&gt;以下内容截取自 &lt;a href=&quot;https://github.com/mdn/translated-content/blob/main/docs/zh-cn/translation-guide.md&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;针对 MDN 文档的本地化指南&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 的中文翻译的常见问题小节。&lt;/p&gt;
&lt;p&gt;其中翻译的规范也是中文写作的规范，更多详见之前写的 &lt;a href=&quot;/posts/document-style-guide/&quot;&gt;中文技术文档的写作规范&lt;/a&gt;。&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;为保证简体中文文档格式的一致性，翻译指南列出了部分规范。&lt;/p&gt;
&lt;h2 id=&quot;标点符号&quot;&gt;标点符号&lt;/h2&gt;
&lt;p&gt;除了代码中使用的符号以及一些特殊情况外，请将英文（半角）符号替换成中文（大部分为全角）符号。&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;但请注意，请不要使用&lt;strong&gt;全角数字&lt;/strong&gt;（特殊情况除外）。&lt;/p&gt;
&lt;/blockquote&gt;
&lt;p&gt;示例如下：&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;正确：&lt;code&gt;我们可以学习 JavaScript——一种很酷的语言&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;我们可以学习 JavaScript--一种很酷的语言&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;正确：&lt;code&gt;以下示例是“可交互的”&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;以下示例是&amp;quot;可交互的&amp;quot;&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;另外，请注意并列的词语间应使用顿号而非逗号：&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;原文：&lt;code&gt;a, b, and c&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;宜：&lt;code&gt;a、b 和 c&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;不宜：&lt;code&gt;a，b，和 c&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;h3 id=&quot;常见中英文标点&quot;&gt;常见中/英文标点&lt;/h3&gt;
&lt;!-- markdownlint-disable search-replace --&gt;
&lt;table&gt;
&lt;thead&gt;
&lt;tr&gt;
&lt;th&gt;名称&lt;/th&gt;
&lt;th&gt;中文&lt;/th&gt;
&lt;th&gt;英文&lt;/th&gt;
&lt;/tr&gt;
&lt;/thead&gt;
&lt;tbody&gt;
&lt;tr&gt;
&lt;td&gt;括号&lt;/td&gt;
&lt;td&gt;（）&lt;/td&gt;
&lt;td&gt;&lpar;&rpar;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;冒号&lt;/td&gt;
&lt;td&gt;：&lt;/td&gt;
&lt;td&gt;:&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;引号&lt;/td&gt;
&lt;td&gt;“”&lt;/td&gt;
&lt;td&gt;&amp;quot;&amp;quot;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;破折号&lt;/td&gt;
&lt;td&gt;——&lt;/td&gt;
&lt;td&gt;&amp;ndash; 、 —&lt;/td&gt;
&lt;/tr&gt;
&lt;/tbody&gt;
&lt;/table&gt;
&lt;!-- markdownlint-enable search-replace --&gt;
&lt;p&gt;简体中文标点符号参考资源：&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://www.moe.gov.cn/ewebeditor/uploadfile/2015/01/13/20150113091548267.pdf&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;教育部《标点符号用法》&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://zh.wikipedia.org/zh-cn/%e6%a0%87%e7%82%b9%e7%ac%a6%e5%8f%b7&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;维基百科：标点符号&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;h2 id=&quot;中文和拉丁语系文字间加空格&quot;&gt;中文和拉丁语系文字间加空格&lt;/h2&gt;
&lt;p&gt;对于简体中文文档，请在中文和拉丁语系文字之间保留&lt;strong&gt;一个空格&lt;/strong&gt;，但在拉丁语系文字和中文标点之间，则无需保留空格。&lt;/p&gt;
&lt;p&gt;示例如下：&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;正确：&lt;code&gt;学习 Web 开发&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;学习Web开发&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;正确：&lt;code&gt;学习 JavaScript、HTML、CSS 等&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;学习 JavaScript、 HTML、 CSS 等&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;正确：&lt;code&gt;应用程序接口（API）&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;应用程序接口（ API ）&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;对于链接文字和非链接文字部分，同样适用此规则：&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;正确：&lt;code&gt;它指向一个[示例]&lpar;#示例&rpar;&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;它指向一个 [示例]&lpar;#示例&rpar;&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;正确：&lt;code&gt;指向 [MDN 开发者文档]&lpar;https://developer.mozilla.org/&rpar;的链接&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;指向[MDN开发者文档]&lpar;https://developer.mozilla.org/&rpar;的链接&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;请注意，数字与中文之间也请保留空格：&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;正确：&lt;code&gt;需 10 个小时完成&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;错误：&lt;code&gt;需10个小时完成&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;h2 id=&quot;排版&quot;&gt;排版&lt;/h2&gt;
&lt;p&gt;英文文档中，对于较长的段落，会通过断行的形式截断，以方便维护文档。但在 Markdown 中，断行会引入空格，在简体中文翻译中，我们有如下约定：&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;在段落不是特别长的情况下（200 个字符以内），请不要断行。&lt;/li&gt;
&lt;li&gt;若段落过长，也请在中文与拉丁语系文字、数字之间，或是句子末尾断行。&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;例如：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-md&quot; data-lang=&quot;md&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;This is an example.
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;We usually write a paragraph into multiple lines.
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;Like this.&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;而在中文文档中，应该使它们在同一行内：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-md&quot; data-lang=&quot;md&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;这是一个示例。我们不应该断行写这一段话。就像这样。&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;词语翻译&quot;&gt;词语翻译&lt;/h2&gt;
&lt;h2 id=&quot;代名词&quot;&gt;代名词&lt;/h2&gt;
&lt;!-- markdownlint-disable search-replace --&gt;
&lt;p&gt;我们无需将“you”翻译为“您”，在文档正文部分的翻译中，请统一使用“你”。&lt;/p&gt;
&lt;!-- markdownlint-enable search-replace --&gt;
&lt;h2 id=&quot;复数形式&quot;&gt;复数形式&lt;/h2&gt;
&lt;p&gt;英文文档中，为了使语句的语法正确，会使用大量的复数形式。在中文翻译中，则无需保留这些复数的形式（未翻译的英文名词也同理）。&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;原文：&lt;code&gt;Application Programming Interfaces &lpar;APIs&rpar;&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;宜：&lt;code&gt;应用程序接口（API）&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;不宜：&lt;code&gt;应用程序接口（APIs）&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;不宜：&lt;code&gt;应用程序接口们（APIs）&lt;/code&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;h2 id=&quot;术语表&quot;&gt;术语表&lt;/h2&gt;
&lt;p&gt;我们在仓库中维护了一个&lt;a href=&quot;https://github.com/mdn/translated-content/blob/main/docs/zh-cn/glossary.md&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;术语表&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;，旨在统一目前还未有明确中文翻译的术语。在翻译文档时，请尽量使用术语表中的术语，以保证文档的一致性。&lt;/p&gt;
&lt;h2 id=&quot;常用标题&quot;&gt;常用标题&lt;/h2&gt;
&lt;p&gt;英文文档中使用了一些常见标题，为了保持简体中文文档的一致性，请在翻译时参考术语表中的&lt;a href=&quot;https://github.com/mdn/translated-content/blob/main/docs/zh-cn/glossary.md#%e6%a0%87%e9%a2%98%e8%a1%a8%e6%a0%bc&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;标题和表格的翻译&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;。&lt;/p&gt;)
 - 📝[在 Vue 项目中更优雅的使用 icon - Blog](https://lruihao.cn/posts/vue-svg-icon/ &lt;h2 id=&quot;前言&quot;&gt;前言&lt;/h2&gt;
&lt;p&gt;在 Web 开发中，我们经常会用到 icon，icon 的使用经历了从图片到字体，再到 svg 的演变过程，也产生出相应的 icon 库，如雪碧图、&lt;a href=&quot;https://fontawesome.com/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Font Awesome&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;、&lt;a href=&quot;https://www.iconfont.cn/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;Iconfont&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 等等。&lt;/p&gt;
&lt;p&gt;随着前端的发展，icon 使用方案落在了 svg 上，svg 有着矢量图的优势，可以无限放大而不失真，而且 svg 本身就是一种 XML 文件，可以直接在 HTML 中使用，也可以通过 CSS 进行样式控制，但是在 Vue 项目中使用 svg 时，我们会遇到一些问题，本文将介绍如何在 Vue 项目中更优雅的使用 svg icon。&lt;/p&gt;
&lt;h2 id=&quot;工具&quot;&gt;工具&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/JetBrains/svg-sprite-loader&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;svg-sprite-loader&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/svg/svgo-loader&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;svgo-loader&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
&lt;p&gt;&lt;code&gt;svg-sprite-loader&lt;/code&gt;用来打包 svg 图标，&lt;code&gt;svgo-loader&lt;/code&gt; 来精简我们的 svg 内容。&lt;/p&gt;
&lt;h2 id=&quot;封装组件&quot;&gt;封装组件&lt;/h2&gt;
&lt;p&gt;在 &lt;code&gt;src/components&lt;/code&gt; 目录下新建 &lt;code&gt;SvgIcon.vue&lt;/code&gt; 组件：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;19
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;20
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;21
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;22
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;23
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;24
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;25
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;26
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;27
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;28
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;29
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;30
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;31
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;32
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;33
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;34
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;35
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;36
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;37
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;38
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;39
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;40
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;41
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;42
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;43
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;44
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;45
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;46
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;47
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;48
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;49
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;50
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;51
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;52
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-vue&quot; data-lang=&quot;vue&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;v-if&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;=&amp;#34;isExternal&amp;#34; :style=&amp;#34;styleExternalIcon&amp;#34; class=&amp;#34;svg-external-icon svg-icon&amp;#34; v-on=&amp;#34;$listeners&amp;#34; /&amp;gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;s&quot;&gt;  &amp;lt;svg v-else class=&amp;#34;svg-icon&amp;#34; aria-hidden=&amp;#34;true&amp;#34; v-on=&amp;#34;$listeners&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;use&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;:href&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;=&amp;#34;iconName&amp;#34;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;svg&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;script&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;default&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;SvgIcon&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;props&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;iconClass&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;type&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;String&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;required&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;true&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;className&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;type&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;String&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;default&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;computed&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;isExternal&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;sr&quot;&gt;/^&lpar;https?:\/\/|data:image&rpar;/&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;test&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;iconClass&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;iconName&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;sb&quot;&gt;`#icon-&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;iconClass&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;styleExternalIcon&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;nx&quot;&gt;mask&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;sb&quot;&gt;`url&lpar;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;iconClass&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;&rpar; no-repeat 50% 50%`&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;s1&quot;&gt;&amp;#39;-webkit-mask&amp;#39;&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;sb&quot;&gt;`url&lpar;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;iconClass&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;&rpar; no-repeat 50% 50%`&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;script&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;style&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;scoped&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;svg&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;icon&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;width&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;1&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;em&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;height&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;1&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;em&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;vertical&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;align&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;mf&quot;&gt;0.15&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;em&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;fill&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;currentColor&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;overflow&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;hidden&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;svg&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;external&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;icon&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;background&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;color&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;currentColor&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;mask&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;size&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;cover&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;!&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;important&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;display&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;inline&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;-&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;block&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;style&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;安装&quot;&gt;安装&lt;/h2&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;npm install svg-sprite-loader svgo-loader -D
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# 或&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;yarn add svg-sprite-loader svgo-loader -D&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;配置&quot;&gt;配置&lt;/h2&gt;
&lt;p&gt;统一将所有的 icon 都以 svg 的形式都放在 &lt;code&gt;src/assets/icons&lt;/code&gt; 目录中。&lt;/p&gt;
&lt;p&gt;然后在 &lt;code&gt;vue.config.js&lt;/code&gt; 中添加如下配置：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;19
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;20
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;21
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;22
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;23
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;24
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;25
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;26
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;27
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;28
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;29
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;30
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;31
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;32
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;33
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;34
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;35
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;36
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;37
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;38
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;39
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-js&quot; data-lang=&quot;js&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;defineConfig&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;require&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;@vue/cli-service&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;path&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;require&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;path&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kd&quot;&gt;function&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;resolve&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;dir&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;path&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;join&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;__dirname&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;dir&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nx&quot;&gt;module&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;exports&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;defineConfig&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;c1&quot;&gt;// ...
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nx&quot;&gt;chainWebpack&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;config&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;=&amp;gt;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;c1&quot;&gt;// set svg-sprite-loader
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;    &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;svgPath&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;resolve&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;src/assets/icons&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;config&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;module&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;rule&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;svg&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;exclude&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;add&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;svgPath&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;end&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;config&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;module&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;rule&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;svg-icon&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;test&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;sr&quot;&gt;/.svg$/&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;include&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;add&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;svgPath&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;end&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;use&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;svg-sprite-loader&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;loader&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;svg-sprite-loader&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;options&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;nx&quot;&gt;symbolId&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;icon-[name]&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;}&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;end&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;c1&quot;&gt;// remove origin svg fill attr
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;use&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;svgo-loader&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;loader&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;svgo-loader&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;tap&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;options&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;=&amp;gt;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;...&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;options&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;c1&quot;&gt;// 删除 svg 中 fill 和 fill-rule
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;        &lt;span class=&quot;nx&quot;&gt;plugins&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[{&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;removeAttrs&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;params&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;attrs&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;fill|fill-rule&amp;#39;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;}],&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;}&rpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;end&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;c1&quot;&gt;// ...
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;}&rpar;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;自动引入&quot;&gt;自动引入&lt;/h2&gt;
&lt;p&gt;自动引入 &lt;code&gt;src/assets/icons&lt;/code&gt; 中的 icon，需要用到 webpack 中的 &lt;a href=&quot;https://webpack.docschina.org/guides/dependency-management/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;require.context&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;。&lt;/p&gt;
&lt;p&gt;在 &lt;code&gt;src/main.js&lt;/code&gt; 中引入所有的 svg 图标，之后可在文件夹自行添加或者删除图标，所以图标都会被自动导入，无需手动操作：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-4&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;9
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-js&quot; data-lang=&quot;js&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;Vue&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;from&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;vue&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;SvgIcon&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;from&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;@/components/SvgIcon&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;// register svg component globally 
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;Vue&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;component&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;SvgIcon&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;SvgIcon&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;// require all svg
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;requireAll&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;requireContext&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;=&amp;gt;&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;requireContext&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;keys&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;map&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;requireContext&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;req&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;require&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;context&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;@/assets/icons&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;false&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;sr&quot;&gt;/\.svg$/&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nx&quot;&gt;requireAll&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;req&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;使用-icon&quot;&gt;使用 icon&lt;/h2&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-5&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-html&quot; data-lang=&quot;html&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;svg-icon&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;icon-class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;fullscreen&amp;#34;&lt;/span&gt;  &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#39;custom-class&amp;#39;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h3 id=&quot;颜色&quot;&gt;颜色&lt;/h3&gt;
&lt;p&gt;&lt;code&gt;svg-icon&lt;/code&gt; 默认会读取其父级的 &lt;code&gt;color fill: currentColor;&lt;/code&gt;&lt;/p&gt;
&lt;p&gt;你可以改变父级的 &lt;code&gt;color&lt;/code&gt; 或者直接改变 &lt;code&gt;fill&lt;/code&gt; 的颜色即可。&lt;/p&gt;
&lt;h3 id=&quot;大小&quot;&gt;大小&lt;/h3&gt;
&lt;p&gt;图标可从 &lt;a href=&quot;https://www.iconfont.cn/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;iconfont&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 项目中下载或者由 UI 切图，同一个项目中使用的 Svg Icon 图标建议统一大小规格，比如 &lt;code&gt;128*128&lt;/code&gt;。&lt;/p&gt;
&lt;h2 id=&quot;示例&quot;&gt;示例&lt;/h2&gt;
&lt;p&gt;本文 &lt;a href=&quot;https://lruihao.github.io/vue-el-demo/#/icons&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;示例&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 代码已上传至 &lt;a href=&quot;https://github.com/Lruihao/vue-el-demo&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;vue-el-demo&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 项目中，可自行下载查看。&lt;/p&gt;
&lt;h2 id=&quot;参考资料&quot;&gt;参考资料&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://juejin.cn/post/6844903517564436493&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;手摸手，带你优雅的使用 icon&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://www.zhangxinxu.com/wordpress/2014/07/introduce-svg-sprite-technology/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;未来必热：SVG Sprites 技术介绍&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://www.zhangxinxu.com/wordpress/2016/02/svg-compress-tool-svgo-experience/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;SVG 精简压缩工具 svgo 简介和初体验&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/JetBrains/svg-sprite-loader&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;svg-sprite-loader&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/svg/svgo&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;svgo&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/svg/svgo-loader&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;svgo-loader&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;)
 - 📝[VSCode 添加用户代码片段，自定义用户代码片段 - Blog](https://lruihao.cn/posts/vscode-snippets/ &lt;p&gt;在使用 VScode 开发中经常会有一些重复使用的代码块，复制粘贴也很麻烦，这时可以在 VScode 中添加用户代码片段，输入简写即可快捷输入。&lt;/p&gt;
&lt;h2 id=&quot;新建代码片段&quot;&gt;新建代码片段&lt;/h2&gt;
&lt;p&gt;在 VScode 主界面-&amp;gt;点击左下角设置图标-&amp;gt;点击用户代码片段，可以建立全局代码片段，也可以建立单个项目的代码片段，也可以设置语言类型的代码片段。&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;h2 id=&quot;代码片段格式&quot;&gt;代码片段格式&lt;/h2&gt;
&lt;p&gt;代码片段格式如下：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-json&quot; data-lang=&quot;json&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;c1&quot;&gt;// Example:
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;// 在这里放置你的 JavaScript 代码片段。每个代码片段都有一个名称、前缀、代码块和描述。前缀用于触发代码片段，代码块将被展开并插入。可能使用的变量有：
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;// $1、$2 表示标签停止点，$0 表示最终光标位置，${1:label}、${2:another} 表示占位符。具有相同 id 的占位符是相互关联的。
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;// 示例：
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;// &amp;#34;Print to console&amp;#34;: {
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;//  &amp;#34;prefix&amp;#34;: &amp;#34;log&amp;#34;,
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;//  &amp;#34;body&amp;#34;: [
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;//   &amp;#34;console.log&lpar;&amp;#39;$1&amp;#39;&rpar;;&amp;#34;,
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;//   &amp;#34;$2&amp;#34;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;//  ],
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;//  &amp;#34;description&amp;#34;: &amp;#34;Log output to console&amp;#34;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;// }
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;可以使用工具 &lt;a href=&quot;https://snippet-generator.app/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;snippet-generator&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 生成代码片段。&lt;/p&gt;
&lt;h2 id=&quot;常用代码片段&quot;&gt;常用代码片段&lt;/h2&gt;
&lt;h3 id=&quot;javascript&quot;&gt;JavaScript&lt;/h3&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;9
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-json&quot; data-lang=&quot;json&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nt&quot;&gt;&amp;#34;Print to console&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;prefix&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;cl&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;body&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;console.log&lpar;&amp;#39;$1&amp;#39;&rpar;;&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;],&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;description&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;Log output to console&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h3 id=&quot;markdown&quot;&gt;Markdown&lt;/h3&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;19
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;20
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;21
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;22
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;23
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;24
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;25
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;26
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;27
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;28
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;29
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;30
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;31
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;32
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;33
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;34
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;35
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-json&quot; data-lang=&quot;json&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nt&quot;&gt;&amp;#34;Font Matter&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;prefix&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;fm&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;body&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;---&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;title: $1&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;date: $CURRENT_YEAR-$CURRENT_MONTH-$CURRENT_DATE$T$CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND+08:00&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;draft: true&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;categories: $2&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;tags: $3&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;description: $4&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;keywords: $5&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;---&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;],&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;description&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;Font Matter&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nt&quot;&gt;&amp;#34;Markdown Table&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;prefix&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;table&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;body&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;| $1 | $2 |&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;| --- | --- |&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;| $3 | $4 |&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;],&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;description&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;Markdown Table&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nt&quot;&gt;&amp;#34;FixIt Shortcode TypeIt&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;prefix&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;typeit&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;body&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;{{&amp;lt; typeit &amp;gt;}}&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;$1&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;s2&quot;&gt;&amp;#34;{{&amp;lt; /typeit &amp;gt;}}&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;],&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nt&quot;&gt;&amp;#34;description&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;FixIt Shortcode TypeIt&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;)
 - 📝[CSS 实现网格背景效果 - Blog](https://lruihao.cn/posts/grid-bg-image/ &lt;p&gt;本文将介绍如何使用 &lt;code&gt;linear-gradient&lt;/code&gt; 、&lt;code&gt;background-size&lt;/code&gt; 等属性来实现网格背景效果。&lt;/p&gt;
&lt;h2 id=&quot;前言&quot;&gt;前言&lt;/h2&gt;
&lt;p&gt;最近在开发一个拖拽式仪表盘时，需要在拖拽组件时添加网格辅助标线来帮助布局和对齐元素。&lt;/p&gt;
&lt;p&gt;最先想到的是使用 CSS 来实现这个效果，经过一番尝试，发现可以通过使用 CSS 的一些技术点，轻松实现不同类型的网格背景效果，包括实线网格和虚线网格。&lt;/p&gt;
&lt;h2 id=&quot;前驱知识&quot;&gt;前驱知识&lt;/h2&gt;
&lt;p&gt;在开始之前，我们需要了解一些必要的 CSS 属性和知识点。&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS/gradient/linear-gradient&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;&lt;code&gt;linear-gradient&lt;/code&gt;&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;：CSS &lt;strong&gt;&lt;code&gt;linear-gradient&lpar;&rpar;&lt;/code&gt;&lt;/strong&gt; 函数用于创建一个表示两种或多种颜色线性渐变的图片。其结果属于&lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS/gradient&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;&lt;code&gt;&amp;lt;gradient&amp;gt;&lt;/code&gt;&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;数据类型，是一种特别的&lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS/image&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;&lt;code&gt;&amp;lt;image&amp;gt;&lt;/code&gt;&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;数据类型。&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS/gradient/radial-gradient&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;&lt;code&gt;radial-gradient&lt;/code&gt;&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;：&lt;strong&gt;&lt;code&gt;radial-gradient&lpar;&rpar;&lt;/code&gt;&lt;/strong&gt; &lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;CSS&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; &lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Functions&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;函数&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;创建一个图像，该图像由从原点辐射的两种或多种颜色之间的渐进过渡组成。它的形状可以是圆形或椭圆形。函数的结果是 &lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS/gradient&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;&lt;code&gt;&amp;lt;gradient&amp;gt;&lt;/code&gt;&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 数据类型的对象。这是一种特别的 &lt;a href=&quot;https://developer.mozilla.org/zh-CN/docs/Web/CSS/image&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;&lt;code&gt;&amp;lt;image&amp;gt;&lt;/code&gt;&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;。&lt;/li&gt;
&lt;li&gt;&lt;code&gt;background-size&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;&lt;code&gt;background-repeat&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;&lt;code&gt;background-position&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;&lt;code&gt;::before&lt;/code&gt; 和 &lt;code&gt;::after&lt;/code&gt; 伪元素&lt;/li&gt;
&lt;/ul&gt;
&lt;h2 id=&quot;实线网格&quot;&gt;实线网格&lt;/h2&gt;
&lt;p&gt;这个效果，我最初是在刷掘金的时候发现的，掘金文章内容区的背景一个实线网格，呈现出的效果类似一页学生时代的记事本，当时觉得很有意思，于是扒下来当作了现在博客文章内容的背景。&lt;/p&gt;
&lt;p&gt;实线网格的实现思路是使用 &lt;code&gt;linear-gradient&lt;/code&gt; 来绘制横向和纵向的网格线，然后通过 &lt;code&gt;background-size&lt;/code&gt; 来控制网格线的间距。&lt;/p&gt;
&lt;p&gt;具体代码如下：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-css&quot; data-lang=&quot;css&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nc&quot;&gt;grid&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;background-image&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;linear-gradient&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;kc&quot;&gt;to&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;right&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;rgba&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;mi&quot;&gt;60&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;10&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;30&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;mf&quot;&gt;0.04&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;1&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;transparent&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nb&quot;&gt;linear-gradient&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;kc&quot;&gt;to&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;bottom&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;rgba&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;mi&quot;&gt;60&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;10&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;30&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;mf&quot;&gt;0.04&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;1&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;transparent&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;background-size&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;20&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;20&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;上面的代码中，&lt;code&gt;background-image&lt;/code&gt; 属性使用了两个 &lt;code&gt;linear-gradient&lt;/code&gt;，通过渐变颜色从 &lt;code&gt;rgba&lpar;60, 10, 30, 0.04&rpar;&lt;/code&gt; 到 &lt;code&gt;transparent&lt;/code&gt; 实现了横向和纵向的网格线。通过指定 &lt;code&gt;background-size&lt;/code&gt; 为 &lt;code&gt;20px 20px&lt;/code&gt;，设置了背景大小为 20px，由于 &lt;code&gt;background-repeat&lt;/code&gt; 默认为 &lt;code&gt;repeat&lt;/code&gt;，所以就实现了 20px 间距的网格线。&lt;/p&gt;
&lt;h2 id=&quot;虚线网格&quot;&gt;虚线网格&lt;/h2&gt;
&lt;p&gt;虚线网格的实现思路需要借助 &lt;code&gt;::before&lt;/code&gt; 和 &lt;code&gt;::after&lt;/code&gt; 伪元素，然后还是通过类似实线的思路实现网格线，然后两个伪元素叠加在一起，从而实现虚线网格。&lt;/p&gt;
&lt;blockquote&gt;
&lt;p&gt;未做实例&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;点阵网格&quot;&gt;点阵网格&lt;/h2&gt;
&lt;p&gt;这里把渐变修改为径向渐变就实现点点背景了，原理和前面说的都是一样的。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-css&quot; data-lang=&quot;css&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nc&quot;&gt;grid&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;background-image&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;radial-gradient&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;kc&quot;&gt;circle&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;mh&quot;&gt;#5a5a5a&lt;/span&gt; &lt;span class=&quot;mf&quot;&gt;.5&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;transparent&lt;/span&gt; &lt;span class=&quot;mf&quot;&gt;.5&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;background-size&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;20&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;20&lt;/span&gt;&lt;span class=&quot;kt&quot;&gt;px&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;总结&quot;&gt;总结&lt;/h2&gt;
&lt;p&gt;最后为了实现我在实际开发中的需求，我还需要控制网格宽度为容器的 1/24，这里就需要使用 &lt;code&gt;calc&lpar;&rpar;&lt;/code&gt; 函数来计算了。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-css&quot; data-lang=&quot;css&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c&quot;&gt;/* 背景显示网格辅助线（宽：1/24 高：40+8px） */&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nt&quot;&gt;background-image&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;linear-gradient&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;90deg&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;rgba&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;60&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;10&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;30&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nc&quot;&gt;04&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;1px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;transparent&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nt&quot;&gt;linear-gradient&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;1turn&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;rgba&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;60&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;10&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;30&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nc&quot;&gt;04&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;1px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;transparent&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nt&quot;&gt;background-size&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;calc&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&lpar;&lpar;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;100&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;%&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;-&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;8px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;/&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;24&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;48px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nt&quot;&gt;background-position&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;4px&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;4px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;div class=&quot;highlight&quot; id=&quot;id-4&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-css&quot; data-lang=&quot;css&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c&quot;&gt;/* 或者点阵网格辅助线（宽：1/24 高：40+8px） */&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nt&quot;&gt;background-image&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;radial-gradient&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;circle&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;#&lt;/span&gt;&lt;span class=&quot;nn&quot;&gt;5a5a5a&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nc&quot;&gt;5px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;transparent&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nc&quot;&gt;5px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nt&quot;&gt;background-size&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;calc&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&lpar;&lpar;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;100&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;%&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;-&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;8px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;/&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;24&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;48px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nt&quot;&gt;background-position&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;24px&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;24px&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;参考&quot;&gt;参考&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://zhuanlan.zhihu.com/p/345973110&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;CSS+HTML&amp;lt;网格背景效果&amp;gt;&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
)
 - 👨‍💻[将 Hugo 博客部署到亚马逊云服务器 - Blog](https://lruihao.cn/posts/aws-ec2/ &lt;p&gt;本文将介绍如何将 Hugo 博客打包并部署到亚马逊云服务器上，并附上亚马逊云服务器的配置过程。&lt;/p&gt;
&lt;h2 id=&quot;前言&quot;&gt;前言&lt;/h2&gt;
&lt;p&gt;最近很长一段时间都是使用 Hugo 在写博客，也花了很多精力在 &lt;a href=&quot;https://github.com/hugo-fixit/FixIt&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;hugo-fixit&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 这个主题的开发上。也听到很多使用 Hugo 写博客的网友们问我，如何部署博客？部署到哪里？&lt;/p&gt;
&lt;p&gt;今天就介绍一种方式：&lt;strong&gt;把博客部署到云服务器上&lt;/strong&gt;。&lt;/p&gt;
&lt;p&gt;但是国内的云服务器太贵了，而且还要备案，所以就想到了海外的云服务器，比如亚马逊云服务器，以下便是注册到部署的全过程。&lt;/p&gt;
&lt;h2 id=&quot;注册亚马逊云账户&quot;&gt;注册亚马逊云账户&lt;/h2&gt;
&lt;p&gt;打开 &lt;a href=&quot;https://aws.amazon.com/cn/free/?sc_channel=seo&amp;amp;sc_campaign=blog0805&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;亚马逊账号注册地址&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;，点击右上角创建 AWS 账户。&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;ol&gt;
&lt;li&gt;填写邮件地址和账号名称（支持使用国内的邮箱）
&lt;/li&gt;
&lt;li&gt;验证邮件
&lt;/li&gt;
&lt;li&gt;输入密码
&lt;/li&gt;
&lt;li&gt;联系人信息
&lt;/li&gt;
&lt;li&gt;付款信息（Visa）
&lt;/li&gt;
&lt;li&gt;验证手机号（支持中国地区国内手机号）
&lt;/li&gt;
&lt;li&gt;选择支持计划
&lt;/li&gt;
&lt;li&gt;完成注册
&lt;/li&gt;
&lt;li&gt;登录亚马逊云控制台，&lt;a href=&quot;https://console.aws.amazon.com/console/home&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;登录地址&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;，选择根用户输入电子邮件地址，点击下一步会让输入密码，输入密码后就可以完成登录了。&lt;/li&gt;
&lt;/ol&gt;
&lt;h2 id=&quot;创建-ec2-服务实例&quot;&gt;创建 EC2 服务实例&lt;/h2&gt;
&lt;p&gt;点击链接查看 &lt;a href=&quot;https://aws.amazon.com/cn/free/?sc_channel=seo&amp;amp;sc_campaign=blog0805&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;亚马逊免费套餐&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;，找到云服务器 EC2，点击立即开始 12 个月免费使用。&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;p&gt;进行 EC2 服务器主页后，点击页面&lt;strong&gt;创建实例&lt;/strong&gt;按钮。&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;p&gt;然后按照页面提示要求，依次填写或选择：&lt;/p&gt;
&lt;ol&gt;
&lt;li&gt;实例的名称：随便填&lt;/li&gt;
&lt;li&gt;应用程序和操作系统映像 &lpar;Amazon Machine Image&rpar;：Amazon Linux 和 Amazon Linux 2023 AMI 免费套餐&lt;/li&gt;
&lt;li&gt;实例类型：选择免费套餐&lt;/li&gt;
&lt;li&gt;密钥对（登录）：这里要点击创建密钥对，输入密钥对名称，选择 RSA 点击创建密钥对会下载文件到本地，要妥善保存，登录时会用到&lt;/li&gt;
&lt;li&gt;网络设置：安全组把允许来自于 http 和 https 得都勾选上&lt;/li&gt;
&lt;li&gt;配置存储：默认是 8G，但免费的最多可以 30G，可以手动改成 30G&lt;/li&gt;
&lt;li&gt;然后点击右侧侧边栏启动实例，等待片刻实例就创建好了&lt;/li&gt;
&lt;/ol&gt;
&lt;h2 id=&quot;连接实例&quot;&gt;连接实例&lt;/h2&gt;
&lt;p&gt;&lt;/p&gt;
&lt;p&gt;点击上面的实例 ID 进入实例的详情，再点击右上角的连接按钮。&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;p&gt;连接成功后，页面会新打开一个窗口，这个窗口就是我们服务器的终端，可以在这里对服务器进行操作。&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;h2 id=&quot;创建-root-用户角色&quot;&gt;创建 root 用户角色&lt;/h2&gt;
&lt;p&gt;在终端中输入以下命令，创建 root 用户角色。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# 切换到 root 用户&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;sudo -i
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# 修改 sshd 配置文件&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;vi /etc/ssh/sshd_config&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;修改如下两项&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-text&quot; data-lang=&quot;text&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;PermitRootLogin yes
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;PasswordAuthentication yes&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;设置 root 用户密码&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;passwd&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;会让输入两次密码，输入完成，重启一下 ssh 服务：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-4&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;service sshd restart&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;重启后在电脑命令行就可以通过 ssh 协议加上用户名称+密码连接远程服务器了。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-5&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;ssh root@3.85.xxx.xxx&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;blockquote&gt;
&lt;p&gt;后续操作尽量用 root 用户进行。&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;安装宝塔面板&quot;&gt;安装宝塔面板&lt;/h2&gt;
&lt;p&gt;宝塔面板是一个服务器管理面板，可以通过宝塔面板来管理服务器，比如安装 nginx、mysql、php 等等。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-6&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;yum install -y wget &lt;span class=&quot;o&quot;&gt;&amp;amp;&amp;amp;&lt;/span&gt; wget -O install.sh https://download.bt.cn/install/install_6.0.sh &lt;span class=&quot;o&quot;&gt;&amp;amp;&amp;amp;&lt;/span&gt; sh install.sh ed8484bec&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;ol&gt;
&lt;li&gt;在亚马逊服务器实例安全组中放行 TCP &lt;code&gt;19430&lt;/code&gt; 端口&lt;/li&gt;
&lt;li&gt;宝塔面板安装完后按照命令行提示打开宝塔面板，进入面板安装 &lt;code&gt;LAMP&lt;/code&gt; 环境，其中包含了我们需要的 &lt;code&gt;nginx&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;等待 &lt;code&gt;LAMP&lt;/code&gt; 环境安装完毕&lt;/li&gt;
&lt;/ol&gt;
&lt;h2 id=&quot;部署-hugo-博客&quot;&gt;部署 Hugo 博客&lt;/h2&gt;
&lt;p&gt;Hugo 博客打包&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-7&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;hugo -v --gc --minify&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;将打包好的 &lt;code&gt;public&lt;/code&gt; 文件夹上传到服务器的 &lt;code&gt;/www/wwwroot/hugo&lt;/code&gt; 目录下，输入以下命令，等待上传完成。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-8&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# 上传文件（需要输入 root 用户密码）&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;scp -r /path/to/public root@3.85.xxx.xxx:/www/wwwroot/hugo&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;在宝塔面板中选择网站，点击添加站点：&lt;/p&gt;
&lt;ol&gt;
&lt;li&gt;域名：填写你的公网 IP 或者域名&lt;/li&gt;
&lt;li&gt;网站目录：选择 &lt;code&gt;/www/wwwroot/hugo&lt;/code&gt;&lt;/li&gt;
&lt;li&gt;站点备注：随便填&lt;/li&gt;
&lt;li&gt;FTP、数据库选择不创建，PHP 选择纯静态&lt;/li&gt;
&lt;li&gt;点击提交&lt;/li&gt;
&lt;/ol&gt;
&lt;p&gt;在浏览器中输入服务器的公网 IP 地址，就可以看到 Hugo 博客了。&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;h2 id=&quot;注意事项&quot;&gt;注意事项&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;亚马逊的服务器每个月免费时长时 &lt;strong&gt;750&lt;/strong&gt; 小时，一个月 31 天 x 24 = 744 小时，正常使用是不会超出免费的份额的，但切记不要同时开两个服务器实例，使用时长会累加，不注意可能会超出套餐额度。&lt;/p&gt;
&lt;p&gt;到期后，如果不想继续使用，一定要记得删除实例，不然会一直扣费的。在控制台选中实例，点击实例状态-&amp;gt;终止实例。&lt;/p&gt;
&lt;/blockquote&gt;
&lt;h2 id=&quot;总结&quot;&gt;总结&lt;/h2&gt;
&lt;p&gt;有了一台海外服务器，我们还可以做很多事情，比如部署 chatgpt 等等，有了服务器一定要多去探索和学习，这么复杂的申请的流程，不要白白放着让过期了。&lt;/p&gt;
&lt;p&gt;保持探索欲，砥砺前行！&lt;/p&gt;)
 - 📝[用魔法打败魔法 - ElBacktop Fix - Blog](https://lruihao.cn/posts/el-backtop-fix/ &lt;p&gt;这篇文章主要是记录一下继承 &lt;a href=&quot;https://element.eleme.cn/#/zh-CN/component/backtop&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;ElBacktop&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt; 组件并修复了一些 bug 的过程。&lt;/p&gt;
&lt;h2 id=&quot;前言&quot;&gt;前言&lt;/h2&gt;
&lt;p&gt;由于某些原因，我希望在路由切换时给每个页面的总容器都加上一个共同的 class &lt;code&gt;page-container&lt;/code&gt;，然后我就在布局中里面加了这么一段代码：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-vue&quot; data-lang=&quot;vue&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;:class&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;=&amp;#34;classObj&amp;#34;&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;app-wrapper&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;app-container&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;topbar&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;header-container&amp;#34;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;el-container&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;main-container&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;sidebar&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;aside-container&amp;#34;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;el-container&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;is-vertical minor-container&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;breadcrumb&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;breadcrumb-container&amp;#34;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;c&quot;&gt;&amp;lt;!--&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;这一行&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;--&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;page-container&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;page-container&amp;#34;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;o&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;err&quot;&gt;/el-container&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;o&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;err&quot;&gt;/el-container&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;el-backtop&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;app-b2t&amp;#34;&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;.page-container&amp;#34;&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;:visibility-height&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;=&amp;#34;50&amp;#34;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;c&quot;&gt;&amp;lt;!--&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;back-to-top&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;app-b2t&amp;#34;&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;.page-container&amp;#34;&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;:visibility-height&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;=&amp;#34;50&amp;#34;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;--&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;7
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-Vue&quot; data-lang=&quot;Vue&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;transition&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;fade-transform&amp;#34;&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;mode&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;out-in&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;keep-alive&lt;/span&gt; &lt;span class=&quot;nt&quot;&gt;:include&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;=&amp;#34;cachedViews&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;router-view&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;/&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;o&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;err&quot;&gt;/keep-alive&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;transition&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;没错，相当于在 router-view 上直接加了一个 class &lt;code&gt;page-container&lt;/code&gt;。&lt;/p&gt;
&lt;h2 id=&quot;问题&quot;&gt;问题&lt;/h2&gt;
&lt;p&gt;那么问题就来了，此时 el-backtop 的 target 设置为 &lt;code&gt;.page-container&lt;/code&gt;，但是当我切换路由时，&lt;code&gt;.page-container&lt;/code&gt; 会被移除再添加为新的页面，此时 el-backtop 就会失效。&lt;/p&gt;
&lt;p&gt;原意是想让 el-backtop 指向每一个包含 &lt;code&gt;.page-container&lt;/code&gt; 的页面。&lt;/p&gt;
&lt;h2 id=&quot;解决&quot;&gt;解决&lt;/h2&gt;
&lt;p&gt;RTFSC，发现 el-backtop 的 target 属性只会在 mounted 时初始化一次，所以想办法在每次路由切换时重新初始化一下 el-backtop 的 target 属性就行了。&lt;/p&gt;
&lt;ol&gt;
&lt;li&gt;创建 MutationObserver 实例来观察 target 的父元素的子元素变化已解决上述 bug&lt;/li&gt;
&lt;li&gt;增加 target 的 data-target 属性，用于指定 target 的子元素作为滚动容器&lt;/li&gt;
&lt;/ol&gt;
&lt;p&gt;最后代码如下：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;19
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;20
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;21
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;22
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;23
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;24
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;25
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;26
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;27
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;28
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;29
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;30
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;31
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;32
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;33
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;34
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;35
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;36
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;37
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;38
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;39
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;40
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;41
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;42
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;43
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;44
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;45
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;46
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;47
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;48
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;49
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;50
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;51
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;52
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;53
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;54
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;55
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;56
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;57
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;58
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;59
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;60
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;61
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;62
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;63
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;64
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;65
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;66
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;67
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;68
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;69
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;70
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;71
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;72
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;73
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;74
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;75
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;76
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;77
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;78
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;79
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;80
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;81
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;82
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;83
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;84
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;85
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-Vue&quot; data-lang=&quot;Vue&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;script&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt;/**
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt; * BackToTop 继承 el-backtop
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt; * 1. 修复 el-backtop 在 target 被移除后，无法重新初始化的问题
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt; * 2. 增加 target 的 data-target 属性，用于指定 target 的子元素作为滚动容器。例如：&amp;lt;div data-target=&amp;#34;.list-pane&amp;#34;&amp;gt;&amp;lt;/div&amp;gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt; */&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;Backtop&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;from&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;element-ui&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;throttle&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;from&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;throttle-debounce/throttle&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;default&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;BackToTop&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;kr&quot;&gt;extends&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;Backtop&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;data&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;return&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;null&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;container&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;null&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;visible&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;false&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;observer&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;null&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;mounted&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;init&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;observeTarget&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;beforeDestroy&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;c1&quot;&gt;// 清除事件监听
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;    &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;container&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;removeEventListener&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;scroll&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;throttledScrollHandler&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;c1&quot;&gt;// 停止观察
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;    &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;observer&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;disconnect&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;methods&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;init&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;container&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;documentElement&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;querySelector&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;!&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;k&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;new&lt;/span&gt; &lt;span class=&quot;nb&quot;&gt;Error&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`target is not existed: &lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;c1&quot;&gt;// 如果 this.el 有 data-target 属性，就使用 data-target 属性的值作为 target
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;        &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;dataset&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;subEl&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;querySelector&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;dataset&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;nx&quot;&gt;subEl&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;&amp;amp;&amp;amp;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;subEl&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;container&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;el&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;throttledScrollHandler&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;throttle&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;mi&quot;&gt;300&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;onScroll&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;container&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;addEventListener&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;scroll&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;throttledScrollHandler&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;cm&quot;&gt;/**
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt;     * 观察 this.container 是否被移除或者新增
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt;     * 注意 router-view 切换页面步骤：1. 新增 router-view -&amp;gt; 2. 删除旧 router-view
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;cm&quot;&gt;     */&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;observeTarget&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;c1&quot;&gt;// 创建 MutationObserver 实例并传入回调函数
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;      &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;observer&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;new&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;MutationObserver&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mutationsList&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;=&amp;gt;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;k&quot;&gt;for&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;mutation&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;of&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;mutationsList&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mutation&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;type&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;===&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;childList&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;            &lt;span class=&quot;c1&quot;&gt;// 检测到删除节点
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;            &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;mutation&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;removedNodes&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;length&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;&amp;gt;&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;              &lt;span class=&quot;k&quot;&gt;for&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;node&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;of&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;mutation&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;removedNodes&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;                &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;node&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;===&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;container&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;                  &lt;span class=&quot;c1&quot;&gt;// 观察如果 this.container 从页面中被移除了，就清除事件监听
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;                  &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;container&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;removeEventListener&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;scroll&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;throttledScrollHandler&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;                  &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;visible&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;false&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;                  &lt;span class=&quot;k&quot;&gt;break&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;                &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;              &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;              &lt;span class=&quot;c1&quot;&gt;// 检测删除前是否有新增节点
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;              &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;querySelector&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;===&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;mutation&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;nextSibling&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;                &lt;span class=&quot;c1&quot;&gt;// 观察如果 this.container 被删除前的下一个兄弟节点是 this.target，就重新初始化
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;                &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;init&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;              &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;            &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;}&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;c1&quot;&gt;// 观察 this.container 父元素的子元素变化
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;      &lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;observer&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;observe&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nb&quot;&gt;document&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;querySelector&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;this&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;target&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;parentNode&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;nx&quot;&gt;childList&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;kc&quot;&gt;true&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;}&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;script&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;)
 - 👨‍💻[使用 Node.js 自动创建 Vue 的路由 - Blog](https://lruihao.cn/posts/gen-router/ &lt;p&gt;最近在写一个 Vue 插件，需要在项目中创建一些测试页面，由于都是些静态路由，就想到之前看到过的一个项目就是用 Node.js 来自动生成路由的，于是就借鉴过来改了一下。&lt;/p&gt;
&lt;h2 id=&quot;源码&quot;&gt;源码&lt;/h2&gt;
&lt;blockquote&gt;
&lt;p&gt;Gist: &lt;a href=&quot;https://gist.github.com/Lruihao/d8f2984525dc9e78dd6a49e15f49cf38&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;https://gist.github.com/Lruihao/d8f2984525dc9e78dd6a49e15f49cf38&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/p&gt;
&lt;/blockquote&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;19
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;20
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;21
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;22
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;23
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;24
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;25
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;26
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;27
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;28
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;29
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;30
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;31
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;32
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;33
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;34
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;35
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;36
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;37
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;38
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;39
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;40
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;41
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;42
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;43
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;44
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;45
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;46
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;47
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;48
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;49
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;50
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;51
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;52
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;53
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;54
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;55
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;56
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;57
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-js&quot; data-lang=&quot;js&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;fs&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;require&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;fs&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;os&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;require&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;os&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;vueDir&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;./src/views/&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;routerFile&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;./src/router.js&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nx&quot;&gt;fs&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;readdir&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;vueDir&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;kd&quot;&gt;function&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;err&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;files&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;err&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;error&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;❌ Could not list the directory.&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;err&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;return&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;routes&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[]&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;for&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;filename&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;of&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;files&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;filename&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;indexOf&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;.&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;&amp;lt;&lt;/span&gt; &lt;span class=&quot;mi&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;continue&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;ext&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;]&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;filename&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;split&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;s1&quot;&gt;&amp;#39;.&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;ext&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;!==&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;vue&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;k&quot;&gt;continue&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;routeName&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;replace&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;sr&quot;&gt;/-&lpar;[a-z]&rpar;/g&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;_&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;match&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;=&amp;gt;&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;match&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;toUpperCase&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;kd&quot;&gt;let&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;routeDescription&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;contentFull&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;fs&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;readFileSync&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;vueDir&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;filename&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;utf-8&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;c1&quot;&gt;// get route description from first line comment
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;    &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;match&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;sr&quot;&gt;/&amp;lt;!--\s*&lpar;.*&rpar;\s*--&amp;gt;/g&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;exec&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;contentFull&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;split&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;os&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;EOL&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;[&lt;/span&gt;&lt;span class=&quot;mi&quot;&gt;0&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;]&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;match&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;routeDescription&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;match&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;&lt;span class=&quot;mi&quot;&gt;1&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;].&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;trim&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;routes&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;push&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`  {
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;    path: &amp;#39;/&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;===&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;home&amp;#39;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;?&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;&amp;#39;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;&amp;#39;,
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;    name: &amp;#39;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;routeName&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;&amp;#39;,&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;routeDescription&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;?&lt;/span&gt; &lt;span class=&quot;sb&quot;&gt;`\n    meta: { description: &amp;#39;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;routeDescription&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;&amp;#39; },`&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;&amp;#39;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;    component: &lpar;&rpar; =&amp;gt; import&lpar;/* webpackChunkName: &amp;#34;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;routeName&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;&amp;#34; */ &amp;#39;@/views/&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;filename&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;&amp;#39;&rpar;,
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;  },`&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;result&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;`// This file is automatically generated by gen-router.js, please do not modify it manually！
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;import VueRouter from &amp;#39;vue-router&amp;#39;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;import Vue from &amp;#39;vue&amp;#39;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;Vue.use&lpar;VueRouter&rpar;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;const routes = [
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;routes&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;join&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;os&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;EOL&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;]
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;const router = new VueRouter&lpar;{
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;  mode: &amp;#39;hash&amp;#39;,
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;  routes,
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;}&rpar;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;export default router
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;sb&quot;&gt;`&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;fs&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;writeFile&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;routerFile&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;result&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;utf-8&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;err&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;=&amp;gt;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;err&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;throw&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;err&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;console&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;log&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`✅ Router generated successfully in &lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;routerFile&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;sb&quot;&gt;`&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;}&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&rpar;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;生成效果如下：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;19
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;20
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;21
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-js&quot; data-lang=&quot;js&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;// This file is automatically generated by gen-router.js, please do not modify it manually！
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;&lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;VueRouter&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;from&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;vue-router&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;Vue&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;from&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;vue&amp;#39;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nx&quot;&gt;Vue&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;use&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;VueRouter&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;routes&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;path&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;/&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;name&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;home&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;meta&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;description&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;Home&amp;#39;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;component&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;=&amp;gt;&lt;/span&gt; &lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;&lt;/span&gt;&lt;span class=&quot;cm&quot;&gt;/* webpackChunkName: &amp;#34;home&amp;#34; */&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;@/views/home.vue&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&rpar;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;]&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;const&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;router&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;new&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;VueRouter&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&lpar;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;mode&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;hash&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;routes&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;default&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;router&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;参考&quot;&gt;参考&lt;/h2&gt;
&lt;p&gt;&lt;a href=&quot;https://github.com/sunzsh/vue-el-demo/blob/f5e9a2a9934c7040f4fa72663eb8c24b1e3b20c1/gen-router.js&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;sunzsh/vue-el-demo&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/p&gt;)
 - 📝[解决 SourceTree 提交时候 husky 命令失败问题 - Blog](https://lruihao.cn/posts/sourcetree-husky/ &lt;h2 id=&quot;问题描述&quot;&gt;问题描述&lt;/h2&gt;
&lt;p&gt;在使用 SourceTree 提交代码的时候，会出现 husky 命令失败的问题（通过命令行提交代码没有问题），如下图所示：&lt;/p&gt;
&lt;p&gt;&lt;/p&gt;
&lt;p&gt;看错误，是一个 catch 参数的问题，在新版本的 Node 中，catch 参数是可以省略的，但是在旧版本中，catch 参数是必须的。&lt;/p&gt;
&lt;p&gt;由于使用了 nvm 管理 Node 版本，项目中的 Node 是正常的，但是 SourceTree 使用的是系统的 Node，所以会出现这个问题。&lt;/p&gt;
&lt;h2 id=&quot;解决方案&quot;&gt;解决方案&lt;/h2&gt;
&lt;p&gt;知道了问题的原因，解决起来就很简单了，只需要将 SourceTree husky hook 阶段的 Node 版本切换到项目中的 Node 版本即可。&lt;/p&gt;
&lt;p&gt;配置 &lt;code&gt;.huskyrc&lt;/code&gt; 文件，内容如下：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nb&quot;&gt;echo&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;export PATH=\&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;dirname &lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;which node&lt;span class=&quot;k&quot;&gt;&rpar;&rpar;&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;:\$PATH\&amp;#34;&amp;#34;&lt;/span&gt; &amp;gt; ~/.huskyrc&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;如果你使用了 &lt;code&gt;zsh&lt;/code&gt; 和 &lt;code&gt;nvm&lt;/code&gt;, 建议在 &lt;code&gt;$ZSH_CUSTOM&lt;/code&gt; 目录下添加一个自定义 zsh 脚本。
这个脚本会在你进入包含了 &lt;code&gt;.nvmrc&lt;/code&gt; 文件目录中自动切换 node 版本，切换版本后修正 &lt;code&gt;~/.huskyrc&lt;/code&gt; 的 path 内容。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;vim &lt;span class=&quot;nv&quot;&gt;$ZSH_CUSTOM&lt;/span&gt;/nvm_custom.zsh&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;17
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;18
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;19
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;20
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;21
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;22
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;23
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;24
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;25
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;26
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;27
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;28
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;29
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;30
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;31
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;32
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;33
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-zsh&quot; data-lang=&quot;zsh&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# https://github.com/nvm-sh/nvm#manual-install&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nb&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;nv&quot;&gt;NVM_DIR&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$HOME&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;/.nvm&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;o&quot;&gt;[&lt;/span&gt; -s &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$NVM_DIR&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;/nvm.sh&amp;#34;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;]&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;&amp;amp;&amp;amp;&lt;/span&gt; &lt;span class=&quot;se&quot;&gt;\.&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$NVM_DIR&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;/nvm.sh&amp;#34;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;# This loads nvm&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;o&quot;&gt;[&lt;/span&gt; -s &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$NVM_DIR&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;/bash_completion&amp;#34;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;]&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;&amp;amp;&amp;amp;&lt;/span&gt; &lt;span class=&quot;se&quot;&gt;\.&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$NVM_DIR&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;/bash_completion&amp;#34;&lt;/span&gt;  &lt;span class=&quot;c1&quot;&gt;# This loads nvm bash_completion&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# https://github.com/nvm-sh/nvm#deeper-shell-integration&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;autoload -U add-zsh-hook
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;load-nvmrc&lt;span class=&quot;o&quot;&gt;&lpar;&rpar;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nb&quot;&gt;local&lt;/span&gt; &lt;span class=&quot;nv&quot;&gt;node_version&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;nvm version&lt;span class=&quot;k&quot;&gt;&rpar;&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nb&quot;&gt;local&lt;/span&gt; &lt;span class=&quot;nv&quot;&gt;nvmrc_path&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;nvm_find_nvmrc&lt;span class=&quot;k&quot;&gt;&rpar;&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;[&lt;/span&gt; -n &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$nvmrc_path&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;]&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;then&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nb&quot;&gt;local&lt;/span&gt; &lt;span class=&quot;nv&quot;&gt;nvmrc_node_version&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;nvm version &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;cat &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;${&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;nvmrc_path&lt;/span&gt;&lt;span class=&quot;si&quot;&gt;}&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;&rpar;&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;&rpar;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;if&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;[&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$nvmrc_node_version&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;N/A&amp;#34;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;]&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;then&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      nvm install
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;elif&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;[&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$nvmrc_node_version&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt; !&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$node_version&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;]&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;then&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      nvm use
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;k&quot;&gt;fi&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;elif&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;[&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;nv&quot;&gt;$node_version&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt; !&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;nvm version default&lt;span class=&quot;k&quot;&gt;&rpar;&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;&amp;#34;&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;]&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;;&lt;/span&gt; &lt;span class=&quot;k&quot;&gt;then&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nb&quot;&gt;echo&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;Reverting to nvm default version&amp;#34;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    nvm use default
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;k&quot;&gt;fi&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;c1&quot;&gt;# fix husky hook&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;c1&quot;&gt;# ref: https://github.com/typicode/husky/issues/390#issuecomment-762213421&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nb&quot;&gt;echo&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;export PATH=\&amp;#34;&lt;/span&gt;&lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;dirname &lt;span class=&quot;k&quot;&gt;$descriptionlpar;&lt;/span&gt;which node&lt;span class=&quot;k&quot;&gt;&rpar;&rpar;&lt;/span&gt;&lt;span class=&quot;s2&quot;&gt;:\$PATH\&amp;#34;&amp;#34;&lt;/span&gt; &amp;gt; ~/.huskyrc
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;o&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;add-zsh-hook chpwd load-nvmrc
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;load-nvmrc
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# https://github.com/nvm-sh/nvm#use-a-mirror-of-node-binaries&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nb&quot;&gt;export&lt;/span&gt; &lt;span class=&quot;nv&quot;&gt;NVM_NODEJS_ORG_MIRROR&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;https://mirrors.ustc.edu.cn/node/&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;参考&quot;&gt;参考&lt;/h2&gt;
&lt;ul&gt;
&lt;li&gt;&lt;a href=&quot;https://wxhboy.cn/2022/04/12/%e8%a7%a3%e5%86%b3SourceTree%e6%8f%90%e4%ba%a4%e6%97%b6%e5%80%99husky%e5%91%bd%e4%bb%a4%e5%a4%b1%e8%b4%a5%e9%97%ae%e9%a2%98/&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;https://wxhboy.cn/2022/04/12/解决SourceTree提交时候husky命令失败问题/&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/typicode/husky/issues/390#issuecomment-762213421&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;https://github.com/typicode/husky/issues/390#issuecomment-762213421&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/typicode/husky/issues/904#issuecomment-862184954&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;https://github.com/typicode/husky/issues/904#issuecomment-862184954&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;li&gt;&lt;a href=&quot;https://github.com/nvm-sh/nvm#deeper-shell-integration&quot;target=&quot;_blank&quot; rel=&quot;external nofollow noopener noreferrer&quot;&gt;https://github.com/nvm-sh/nvm#deeper-shell-integration&lt;i class=&quot;fa-solid fa-external-link-alt fa-fw fa-xs ms-1 text-secondary&quot; aria-hidden=&quot;true&quot;&gt;&lt;/i&gt;&lt;/a&gt;&lt;/li&gt;
&lt;/ul&gt;
)
 - 📝[Vue2 + tailwindcss 初始化 - Blog](https://lruihao.cn/posts/v2-tailwind/ &lt;h2 id=&quot;新建-vue2-项目&quot;&gt;新建 Vue2 项目&lt;/h2&gt;
&lt;p&gt;通过 &lt;code&gt;vue-cli&lt;/code&gt; 创建一个叫 &lt;code&gt;v2-tailwind&lt;/code&gt; 的项目：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-1&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;vue create vue2-tailwind&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;根据需要选择其他的功能插件，例如：&lt;code&gt;Babel, Router, Vuex, CSS Pre-processors, Linter&lt;/code&gt;。&lt;/p&gt;
&lt;details&gt;
  &lt;summary&gt;关于 ESLint&lt;/summary&gt;
  当在 Vue 创建项目时，你可以根据自己的需求选择不同的 ESLint 配置。以下是一些常见的选项及其优缺点和注意事项：
&lt;ol&gt;
&lt;li&gt;
&lt;p&gt;&lt;strong&gt;ESLint with error prevention only&lt;/strong&gt;:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;优点：这个配置只会帮助你防止代码中的错误，它的规则相对宽松。适用于刚开始使用 ESLint 或者希望避免太多约束的开发者。&lt;/li&gt;
&lt;li&gt;缺点：由于规则相对宽松，可能无法完全确保代码风格的一致性。&lt;/li&gt;
&lt;li&gt;注意事项：如果你想要更严格的代码检查，可以考虑其他配置。&lt;/li&gt;
&lt;/ul&gt;
&lt;/li&gt;
&lt;li&gt;
&lt;p&gt;&lt;strong&gt;ESLint + Airbnb config&lt;/strong&gt;:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;优点：Airbnb 的配置非常严格，能够帮助你遵循最佳实践和编写高质量的代码。此外，它也包含了许多 ES6+ 的规则。&lt;/li&gt;
&lt;li&gt;缺点：由于其严格性，初学者可能需要花费更多时间来解决 ESLint 报告的问题。&lt;/li&gt;
&lt;li&gt;注意事项：在使用此配置时，请确保你理解并接受 Airbnb 的代码规范。&lt;/li&gt;
&lt;/ul&gt;
&lt;/li&gt;
&lt;li&gt;
&lt;p&gt;&lt;strong&gt;ESLint + Standard config&lt;/strong&gt;:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;优点：Standard 的配置旨在提供一个相对简单、一致的代码风格，适合那些喜欢“零配置”的开发者。&lt;/li&gt;
&lt;li&gt;缺点：这个配置可能不适用于所有项目，因为它有自己的代码风格要求。&lt;/li&gt;
&lt;li&gt;注意事项：如果你的团队或项目已经有自己的编码规范，使用 Standard 配置可能会导致不一致。&lt;/li&gt;
&lt;/ul&gt;
&lt;/li&gt;
&lt;li&gt;
&lt;p&gt;&lt;strong&gt;ESLint + Prettier&lt;/strong&gt;:&lt;/p&gt;
&lt;ul&gt;
&lt;li&gt;优点：Prettier 是一个自动格式化工具，可以与 ESLint 结合使用，以确保代码风格的一致性。这可以提高代码可读性，并减少在代码审查过程中关注格式问题的时间。&lt;/li&gt;
&lt;li&gt;缺点：Prettier 可能会覆盖某些 ESLint 规则，所以需要花一些时间确保配置正确。&lt;/li&gt;
&lt;li&gt;注意事项：为了避免冲突，请确保 ESLint 和 Prettier 的规则正确配置。&lt;/li&gt;
&lt;/ul&gt;
&lt;/li&gt;
&lt;/ol&gt;
&lt;p&gt;总之，在选择 ESLint 配置时，需要根据你的团队、项目需求和个人偏好来权衡。选择适当的配置可以帮助你提高代码质量并保持一致的代码风格。&lt;/p&gt;
&lt;/details&gt;
&lt;h2 id=&quot;安装-tailwindcss&quot;&gt;安装 tailwindcss&lt;/h2&gt;
&lt;p&gt;打开项目，安装 &lt;code&gt;tailwindcss&lt;/code&gt;：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-2&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nb&quot;&gt;cd&lt;/span&gt; vue2-tailwind
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# 安装 tailwindcss 低版本及相关插件&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;npm install tailwindcss@npm:@tailwindcss/postcss7-compat @tailwindcss/postcss7-compat postcss@^7 autoprefixer@^9&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;然后创建配置文件：&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-3&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;# 创建 postcss.config.js, tailwind.config.js&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;npx tailwindcss init -p&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;div class=&quot;highlight&quot; id=&quot;id-4&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;6
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-js&quot; data-lang=&quot;js&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nx&quot;&gt;module&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;exports&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;plugins&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;tailwindcss&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;nx&quot;&gt;autoprefixer&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;div class=&quot;highlight&quot; id=&quot;id-5&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;12
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;13
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;14
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;15
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;16
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-js&quot; data-lang=&quot;js&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;nx&quot;&gt;module&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;.&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;exports&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;=&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;purge&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;s2&quot;&gt;&amp;#34;./src/App.vue&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;s2&quot;&gt;&amp;#34;./src/views/**/*.{vue,js,ts,jsx,tsx}&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;s2&quot;&gt;&amp;#34;./src/components/**/*.{vue,js,ts,jsx,tsx}&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;],&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;darkMode&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;class&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// or &amp;#39;media&amp;#39; or &amp;#39;class&amp;#39;
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nx&quot;&gt;mode&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;s1&quot;&gt;&amp;#39;jit&amp;#39;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;,&lt;/span&gt; &lt;span class=&quot;c1&quot;&gt;// 是否开启 jit 模式，开启以后编译会更快，当然，tailwindcss 版本需要在 2.1 以上
&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;c1&quot;&gt;&lt;/span&gt;  &lt;span class=&quot;nx&quot;&gt;theme&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;extend&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;variants&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;nx&quot;&gt;extend&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;{},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;},&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;nx&quot;&gt;plugins&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;:&lt;/span&gt; &lt;span class=&quot;p&quot;&gt;[],&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;}&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;p&gt;最后在 &lt;code&gt;main.js&lt;/code&gt; 中引入 &lt;code&gt;tailwindcss&lt;/code&gt;&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-6&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-js&quot; data-lang=&quot;js&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;kr&quot;&gt;import&lt;/span&gt; &lt;span class=&quot;s2&quot;&gt;&amp;#34;tailwindcss/tailwind.css&amp;#34;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;h2 id=&quot;启动项目&quot;&gt;启动项目&lt;/h2&gt;
&lt;p&gt;启动项目，修改模板中的 class 进行测试。&lt;/p&gt;
&lt;div class=&quot;highlight&quot; id=&quot;id-7&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt;1
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-bash&quot; data-lang=&quot;bash&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;npm run serve&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;&lt;div class=&quot;highlight&quot; id=&quot;id-8&quot;&gt;&lt;div class=&quot;chroma&quot;&gt;
&lt;table class=&quot;lntable&quot;&gt;&lt;tr&gt;&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code&gt;&lt;span class=&quot;lnt&quot;&gt; 1
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 2
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 3
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 4
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 5
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 6
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 7
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 8
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt; 9
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;10
&lt;/span&gt;&lt;span class=&quot;lnt&quot;&gt;11
&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;
&lt;td class=&quot;lntd&quot;&gt;
&lt;pre tabindex=&quot;0&quot; class=&quot;chroma&quot;&gt;&lt;code class=&quot;language-vue&quot; data-lang=&quot;vue&quot;&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;id&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;app&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;bg-gray-100&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;container mx-auto&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;flex justify-center items-center h-screen&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;          &lt;span class=&quot;p&quot;&gt;&amp;lt;&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt; &lt;span class=&quot;na&quot;&gt;class&lt;/span&gt;&lt;span class=&quot;o&quot;&gt;=&lt;/span&gt;&lt;span class=&quot;s&quot;&gt;&amp;#34;text-4xl text-gray-700&amp;#34;&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;&lt;span class=&quot;nx&quot;&gt;Hello&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;Vue2&lt;/span&gt; &lt;span class=&quot;o&quot;&gt;+&lt;/span&gt; &lt;span class=&quot;nx&quot;&gt;tailwindcss&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;        &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;      &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;    &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;  &lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;div&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;
&lt;/span&gt;&lt;/span&gt;&lt;span class=&quot;line&quot;&gt;&lt;span class=&quot;cl&quot;&gt;&lt;span class=&quot;p&quot;&gt;&amp;lt;/&lt;/span&gt;&lt;span class=&quot;nt&quot;&gt;template&lt;/span&gt;&lt;span class=&quot;p&quot;&gt;&amp;gt;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;&lt;/code&gt;&lt;/pre&gt;&lt;/td&gt;&lt;/tr&gt;&lt;/table&gt;
&lt;/div&gt;
&lt;/div&gt;)<!-- BLOG-POST-LIST:END -->

<!-- link reference definition -->
[blog]: https://lruihao.cn
[blog-repo]: https://github.com/Lruihao/hugo-blog
[hugo-fixit]: https://github.com/hugo-fixit
[fixit]: https://fixit.lruihao.cn
[fixit-repo]: https://github.com/hugo-fixit/FixIt

<!-- footnote reference definition -->
[^1]: The source of [菠菜眾長][blog] is [Lruihao/hugo-blog][blog-repo].
[^2]: The source of [FixIt][fixit] is [hugo-fixit/FixIt][fixit-repo].
