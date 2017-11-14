---
id: version-0.49-alertios
original_id: alertios
title: alertios
---
<a id="content"></a><h1><a class="anchor" name="alertios"></a>AlertIOS <a class="hash-link" href="docs/alertios.html#alertios">#</a></h1><div><div><p><code>AlertIOS</code> provides functionality to create an iOS alert dialog with a
message or create a prompt for user input.</p><p>Creating an iOS alert:</p><div class="prism language-javascript">AlertIOS<span class="token punctuation">.</span><span class="token function">alert</span><span class="token punctuation">(</span>
 <span class="token string">'Sync Complete'</span><span class="token punctuation">,</span>
 <span class="token string">'All your data are belong to us.'</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span></div><p>Creating an iOS prompt:</p><div class="prism language-javascript">AlertIOS<span class="token punctuation">.</span><span class="token function">prompt</span><span class="token punctuation">(</span>
  <span class="token string">'Enter a value'</span><span class="token punctuation">,</span>
  <span class="token keyword">null</span><span class="token punctuation">,</span>
  text <span class="token operator">=&gt;</span> console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"You entered "</span><span class="token operator">+</span>text<span class="token punctuation">)</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span></div><p>We recommend using the <a href="docs/alert.html" target="_blank"><code>Alert.alert</code></a> method for
cross-platform support if you don't need to create iOS-only prompts.</p></div><span><h3><a class="anchor" name="methods"></a>Methods <a class="hash-link" href="docs/alertios.html#methods">#</a></h3><div class="props"><div class="prop"><h4 class="methodTitle"><a class="anchor" name="alert"></a><span class="methodType">static </span>alert<span class="methodType">(title: string, message?: string, callbackOrButtons?: ?(() =&gt; void), ButtonsArray, type?: AlertType)</span> <a class="hash-link" href="docs/alertios.html#alert">#</a></h4><div><p>Create and display a popup alert.</p></div><div><strong>Parameters:</strong><table class="params"><thead><tr><th>Name and Type</th><th>Description</th></tr></thead><tbody><tr><td>title<br><br><div><span>string</span></div></td><td class="description"><div><p>The dialog's title.</p><p>   An empty string hides the title.</p></div></td></tr><tr><td>[message]<br><br><div><span>string</span></div></td><td class="description"><div><p>An optional message that appears below
    the dialog's title.</p></div></td></tr><tr><td>[callbackOrButtons]<br><br><div><span>?(() =&gt; void) | </span><span><a href="docs/alertios.html#buttonsarray">ButtonsArray</a></span></div></td><td class="description"><div><p>This optional argument should
   be either a single-argument function or an array of buttons. If passed
   a function, it will be called when the user taps 'OK'.</p><p>   If passed an array of button configurations, each button should include
   a <code>text</code> key, as well as optional <code>onPress</code> and <code>style</code> keys. <code>style</code>
   should be one of 'default', 'cancel' or 'destructive'.</p></div></td></tr><tr><td>[type]<br><br><div><span><a href="docs/alertios.html#alerttype">AlertType</a></span></div></td><td class="description"><div><p>Deprecated, do not use.</p></div></td></tr></tbody></table></div><div><br>Example with custom buttons:<div class="prism language-javascript">AlertIOS<span class="token punctuation">.</span><span class="token function">alert</span><span class="token punctuation">(</span>
 <span class="token string">'Update available'</span><span class="token punctuation">,</span>
 <span class="token string">'Keep your app up to date to enjoy the latest features'</span><span class="token punctuation">,</span>
 <span class="token punctuation">[</span>
   <span class="token punctuation">{</span>text<span class="token punctuation">:</span> <span class="token string">'Cancel'</span><span class="token punctuation">,</span> onPress<span class="token punctuation">:</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'Cancel Pressed'</span><span class="token punctuation">)</span><span class="token punctuation">,</span> style<span class="token punctuation">:</span> <span class="token string">'cancel'</span><span class="token punctuation">}</span><span class="token punctuation">,</span>
   <span class="token punctuation">{</span>text<span class="token punctuation">:</span> <span class="token string">'Install'</span><span class="token punctuation">,</span> onPress<span class="token punctuation">:</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'Install Pressed'</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token punctuation">,</span>
 <span class="token punctuation">]</span><span class="token punctuation">,</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span></div></div></div><div class="prop"><h4 class="methodTitle"><a class="anchor" name="prompt"></a><span class="methodType">static </span>prompt<span class="methodType">(title: string, message?: string, callbackOrButtons?: ?((text: string) =&gt; void), ButtonsArray, type?: AlertType, defaultValue?: string, keyboardType?: string)</span> <a class="hash-link" href="docs/alertios.html#prompt">#</a></h4><div><p>Create and display a prompt to enter some text.</p></div><div><strong>Parameters:</strong><table class="params"><thead><tr><th>Name and Type</th><th>Description</th></tr></thead><tbody><tr><td>title<br><br><div><span>string</span></div></td><td class="description"><div><p>The dialog's title.</p></div></td></tr><tr><td>[message]<br><br><div><span>string</span></div></td><td class="description"><div><p>An optional message that appears above the text
   input.</p></div></td></tr><tr><td>[callbackOrButtons]<br><br><div><span>?((text: string) =&gt; void) | </span><span><a href="docs/alertios.html#buttonsarray">ButtonsArray</a></span></div></td><td class="description"><div><p>This optional argument should
   be either a single-argument function or an array of buttons. If passed
   a function, it will be called with the prompt's value when the user
   taps 'OK'.</p><p>   If passed an array of button configurations, each button should include
   a <code>text</code> key, as well as optional <code>onPress</code> and <code>style</code> keys (see
   example). <code>style</code> should be one of 'default', 'cancel' or 'destructive'.</p></div></td></tr><tr><td>[type]<br><br><div><span><a href="docs/alertios.html#alerttype">AlertType</a></span></div></td><td class="description"><div><p>This configures the text input. One of 'plain-text',
   'secure-text' or 'login-password'.</p></div></td></tr><tr><td>[defaultValue]<br><br><div><span>string</span></div></td><td class="description"><div><p>The default text in text input.</p></div></td></tr><tr><td>[keyboardType]<br><br><div><span>string</span></div></td><td class="description"><div><p>The keyboard type of first text field(if exists).
   One of 'default', 'email-address', 'numeric', 'phone-pad',
   'ascii-capable', 'numbers-and-punctuation', 'url', 'number-pad',
   'name-phone-pad', 'decimal-pad', 'twitter' or 'web-search'.</p></div></td></tr></tbody></table></div><div><br>Example with custom buttons:<div class="prism language-javascript">AlertIOS<span class="token punctuation">.</span><span class="token function">prompt</span><span class="token punctuation">(</span>
  <span class="token string">'Enter password'</span><span class="token punctuation">,</span>
  <span class="token string">'Enter your password to claim your $1.5B in lottery winnings'</span><span class="token punctuation">,</span>
  <span class="token punctuation">[</span>
    <span class="token punctuation">{</span>text<span class="token punctuation">:</span> <span class="token string">'Cancel'</span><span class="token punctuation">,</span> onPress<span class="token punctuation">:</span> <span class="token punctuation">(</span><span class="token punctuation">)</span> <span class="token operator">=&gt;</span> console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'Cancel Pressed'</span><span class="token punctuation">)</span><span class="token punctuation">,</span> style<span class="token punctuation">:</span> <span class="token string">'cancel'</span><span class="token punctuation">}</span><span class="token punctuation">,</span>
    <span class="token punctuation">{</span>text<span class="token punctuation">:</span> <span class="token string">'OK'</span><span class="token punctuation">,</span> onPress<span class="token punctuation">:</span> password <span class="token operator">=&gt;</span> console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">'OK Pressed, password: '</span> <span class="token operator">+</span> password<span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">]</span><span class="token punctuation">,</span>
  <span class="token string">'secure-text'</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span></div></div><div><br>Example with the default button and a custom callback:<div class="prism language-javascript">AlertIOS<span class="token punctuation">.</span><span class="token function">prompt</span><span class="token punctuation">(</span>
  <span class="token string">'Update username'</span><span class="token punctuation">,</span>
  <span class="token keyword">null</span><span class="token punctuation">,</span>
  text <span class="token operator">=&gt;</span> console<span class="token punctuation">.</span><span class="token function">log</span><span class="token punctuation">(</span><span class="token string">"Your username is "</span><span class="token operator">+</span>text<span class="token punctuation">)</span><span class="token punctuation">,</span>
  <span class="token keyword">null</span><span class="token punctuation">,</span>
  <span class="token string">'default'</span>
<span class="token punctuation">)</span><span class="token punctuation">;</span></div></div></div></div></span><span><h3><a class="anchor" name="type-definitions"></a>Type Definitions <a class="hash-link" href="docs/alertios.html#type-definitions">#</a></h3><div class="props"><div class="prop"><h4 class="propTitle"><a class="anchor" name="alerttype"></a>AlertType <a class="hash-link" href="docs/alertios.html#alerttype">#</a></h4><div><p>An Alert button type</p></div><strong>Type:</strong><br>$Enum<div><br><strong>Constants:</strong><table class="params"><thead><tr><th>Value</th><th>Description</th></tr></thead><tbody><tr><td>default</td><td class="description"><div><p>Default alert with no inputs</p></div></td></tr><tr><td>plain-text</td><td class="description"><div><p>Plain text input alert</p></div></td></tr><tr><td>secure-text</td><td class="description"><div><p>Secure text input alert</p></div></td></tr><tr><td>login-password</td><td class="description"><div><p>Login and password alert</p></div></td></tr></tbody></table></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="alertbuttonstyle"></a>AlertButtonStyle <a class="hash-link" href="docs/alertios.html#alertbuttonstyle">#</a></h4><div><p>An Alert button style</p></div><strong>Type:</strong><br>$Enum<div><br><strong>Constants:</strong><table class="params"><thead><tr><th>Value</th><th>Description</th></tr></thead><tbody><tr><td>default</td><td class="description"><div><p>Default button style</p></div></td></tr><tr><td>cancel</td><td class="description"><div><p>Cancel button style</p></div></td></tr><tr><td>destructive</td><td class="description"><div><p>Destructive button style</p></div></td></tr></tbody></table></div></div><div class="prop"><h4 class="propTitle"><a class="anchor" name="buttonsarray"></a>ButtonsArray <a class="hash-link" href="docs/alertios.html#buttonsarray">#</a></h4><div><p>Array or buttons</p></div><strong>Type:</strong><br>Array<div><br><strong>Properties:</strong><table class="params"><thead><tr><th>Name and Type</th><th>Description</th></tr></thead><tbody><tr><td>[text]<br><br><div><span>string</span></div></td><td class="description"><div><p>Button label</p></div></td></tr><tr><td>[onPress]<br><br><div><span>function</span></div></td><td class="description"><div><p>Callback function when button pressed</p></div></td></tr><tr><td>[style]<br><br><div><span><a href="docs/alertios.html#alertbuttonstyle">AlertButtonStyle</a></span></div></td><td class="description"><div><p>Button style</p></div></td></tr></tbody></table></div><div><br><strong>Constants:</strong><table class="params"><thead><tr><th>Value</th><th>Description</th></tr></thead><tbody><tr><td>text</td><td class="description"><div><p>Button label</p></div></td></tr><tr><td>onPress</td><td class="description"><div><p>Callback function when button pressed</p></div></td></tr><tr><td>style</td><td class="description"><div><p>Button style</p></div></td></tr></tbody></table></div></div></div></span></div><p class="edit-page-block"><a target="_blank" href="https://github.com/facebook/react-native/blob/master/Libraries/Alert/AlertIOS.js">Improve this page</a> by sending a pull request!</p><div class="docs-prevnext"><a class="docs-prev" href="docs/alert.html#content">← Prev</a><a class="docs-next" href="docs/animated.html#content">Next →</a></div>