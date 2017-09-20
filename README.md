# 积累每一点小知识，汇聚成汪洋大海

## CSS 篇

* writing-mode（文字竖排）
* unicode-bidi: bidi-override; + direction: rtl; 文本从右向左
* direction:rtl 下 inline 右对齐不换顺序，inline-block 换序不对齐（兼容很好，但效果不同，有点鸡肋）
* all:inherit（所有样式重置为 body 的样式，除了 unicode-bidi 和 direction）
* background-blend-mode（类似PS的混合模式）
* background-clip:text（图片只作文字背景）
* counter-reset & counter-increment 让 content:counter() 自定义序号
* 动画元素添加 z-index:1 （既创建层叠上下文）可以减少对上下文的影响，减少卡顿
* :in-range 和 :out-of-range 伪类选择器，对拥有 min 和 max 属性的表单添加范围内外不同样式
* object-fit & object-position 资源在元素中的位置，类似于让 img 的 src 拥有 background 的特性
* font-display: swap; 让字体加载时不显示为空白，尚未兼容
* width 相关的新属性值：fill-available（撑满可用空间）、fit-contemt（收缩为内容宽度）、min-content（父级之下除了本元素的最小宽度）、max-content（文本不换行的宽度）
* currentColor 让子级继承父级的 color，如 background/fill等，兼容性很棒
* text-decoration 的拓展，text-decoration-line 线条位置（上中下），text-decoration-style 线条样式（点线/虚线/双线/波浪线），兼容一般。
* -webkit-user-select: none;user-select: none; 可以阻止微信选择文本，selectstart 方法不行
* background-origin: content-box; 背景图以什么盒子模式为准
* touch-action: none; 可禁用浏览器的触摸交互，比如拖拽的时候禁用滚动的CSS解决方案
* background 多图形态下，最先的为最上层
* shape-outside 改变盒子形状，不再只能是方形。shape-margin 与其他盒子的空隙，shape-image-threshold 根据颜色（比如渐变）来改变盒子形状。兼容较差。
* text-align-last 让最后一行也能进行对齐，ios 不兼容
* tab-size 对 tab 键打出的空隙进行设置，1代表（1个中文字/2个英文字），兼容一般。

## HTML 篇
* 不对图片限定尺寸会造成页面布局重绘，影响加载性能
* `<meta name="format-detection" content="telephone=no" /` 禁止自动识别为电话
* 微信标题能容纳数量为13字，否则将出现省略号
* MathML 即 `<math>` 标签，用来展示数学公式的，仅 Firefox 和 Safari 支持
* HTML 的 ID 可以用中文
* `accept="image/*"` 可兼容所有手机拥有拍照选项
* autocapitalize="off" autocorrect="off" 取消IOS输入英文默认首字母大写
* `http://www.placehold.it/100x200/bgcolor/textcolor&text=hello+world` 生成占位图
* `<meta name="vieport" content=""width=device-width,viewport-fit="cover">` 应对像 iPhoneX 那样的全面屏
 
## SVG 篇
* SVG SMIL animation（SVG动画）
* SVG 的 viewBox 和 preserveAspectRatio
* svg 标签 <text> 的 textLength 等效于宽度，lengthAdjust 设置自动字间距(spacing)或自动词间距(spacingAndGlyphs)
* svg 最好加上 `xmlns="http://www.w3.org/2000/svg"`，因为加的话直接打开是渲染后的结果，否则只显示代码
* svg 的 <foreignObject> 嵌套 <body> 解决文本换行的需求

## 小玩具
* JSFuck（字符改乱码）
* $.velocity 号称更快的动画操作方法
* jsfiddle RunJS codepen runmars // 线上编辑器

## JavaScript 篇
* (num + 0.5) | 0 也可以获得整数
* 用 a = ++a % 5 替代 if (++a > 5) a = 0
* canvas 使用整数比使用小数会更清晰
* preventDefault 能解决移动端拖拽时滚动条也跟着动的情况
* 事件代理，事件绑在父级比绑在很多 li 上好
* pushState/replaceState 无刷新网页地址更换
* typeof arr;("object") / arr instanceof Array;(true) / arr.constructor();([])
* function clone(object) {function x(){};x.prototype = object;return new x();} 克隆
* DOMActivate，DOMFocusin,DOMAttrModified，DOMCharacterDataModified，DOMNodeInserted，DOMNodeInsertedIntoDocument，DOMNodeRemoved，DOMNodeRemovedFromDocument，DOMSubtreeModified，DOMContentLoaded，众多 DOM 相关事件
* eval(strJSON); | strJSON.parseJSON(); | JSON.parse(strJSON) 的区别
* $.cssHooks 和 $.cssNumber 拓展 css 属性
* $.queue 队列，很棒
* visibilitychange 事件监听从当前浏览器标签移出，对应 document.hidden 的值
* unref 和 ref （setTimeout 的暂停和重启）
* canvas 的 bezierCurveTo（贝塞尔曲线）
* canvas 的 globalCompositeOperation 属性
* setTimeout(arguments.callee, 130); 130ms为周期重复调用本方法，但无法传参
* querySelector() / $().get(0) / $()[0] 三者相比，后者更快
* onpageshow 时如果拥有 e.persisted 属性能判断该页是否缓存
* document.execCommand 使用浏览器权限，如复制粘贴
* elem.matchesSelector('.xx') 相当于 $.is('.xx')，但需要兼容
* navigator.onLine 判断是否联网
* requestIdleCallback 空闲时间运行，与 requestAnimationFrame 合用，当前帧有空闲时间则运行，没有则推迟到下一帧
* visibilitychange / pointerlockchange / requestPointerLock
* MSPointer 是 IE10 特有的事件处理，合并了 mouse 和 touch
* createEvent / dispatchEvent 自定义事件及其触发
* new FormData() 对象可传入 form 元素，或 append(key, value) 来生成数据字符串
* xhr 还有 upload 属性，可以绑定 load progress abort 等事件
* 将 debugtbs.qq.com 输入微信对话框发送，并打开此链接，可强制使用 webview 而不是 X5
* WeakMap 生成弱引用对象，使用 get 和 set 对其他对象进行拿取和赋值，不计入垃圾回收
* ctx.setLineDash([lineWidth, lineGap]) | canvas 画虚线
* Object.getOwnPropertyDescriptor(obj, prop)
* btoa 转码 / atob 解码（base64 形态的码）
* performance.now() // 网页性能
* document.referrer(必须放在服务器，否则为"")
* localeCompare 比较字母大小
* appendHTML，insertAdjacentHTML，createDocumentFragment 文档片段，及其性能差异

## 面试题套路
* new Boolean(false) 是一个对象，所以 if (new Boolean(false)) 是会继续运行的
