字多得眼花，每十个进行划分，无其他意义

# 积累每一点小知识，汇聚成汪洋大海

* writing-mode（文字竖排）
* JSFuck（字符改乱码）
* $.velocity 更快的动画操作方法
* SVG SMIL animation（SVG动画）
* CSS all:inherit;（还没怎么试，好像很好用的样子）
* direction:rtl 下 inline 右对齐不换顺序，inline-block 换序不对齐（兼容很好，但效果不同，有点鸡肋）
* background-clip:text（图片只作文字背景）
* 不对图片限定尺寸会造成页面布局重绘，影响加载性能
* background-blend-mode（如PS的混合模式）
* counter-reset & counter-increment 让 content:counter() 自定义序号

-----

* 动画元素添加 z-index:1 可以减少对上下文的影响，减少卡顿
* <meta name="format-detection" content="telephone=no" /> 真的有效
* pushState/replaceState 无刷新网页地址更换
* ['cube', 'coverflow', 'flip'].indexOf(string) 字符串中检索是否存在前者
* typeof arr;("object") / arr instanceof Array;(true) / arr.constructor();([])
* Array.prototype.push.apply(array1, array2); 合并两个数组
* function clone(object) {function x(){};x.prototype = object;return new x();} 克隆
* DOMActivate，DOMFocusin,DOMAttrModified，DOMCharacterDataModified，DOMNodeInserted，DOMNodeInsertedIntoDocument，DOMNodeRemoved，DOMNodeRemovedFromDocument，DOMSubtreeModified，DOMContentLoaded
* eval(strJSON); | strJSON.parseJSON(); | JSON.parse(strJSON) 的区别
* unicode-bidi: bidi-override; + direction: rtl; 文本从右向左

-----

* $.cssHooks 和 $.cssNumber 拓展 css 属性
* $.queue 可将函数放入队列，产生回调的感觉，个人认为就是为了代码优美
* 事件代理，时间绑在父级比绑在很多 li 上好
* SVG 的 viewBox 和 preserveAspectRatio
* CSS 的 clip-path 和 SVG 的 clip-path 完爆 clip: rect 这弃子
* visibilitychange 事件： 从当前浏览器标签移出 对应 document.hidden
* http://www.placehold.it/widthxheight/bgcolor/textcolor[&text=hello+world] 生成占位图
* unref 和 ref （setTimeout 的暂停和重启）
* canvas  的 bezierCurveTo（贝塞尔曲线）
* canvas 的 globalCompositeOperation 属性
* :in-range 和 :out-of-range 伪类选择器，对拥有 min 和 max 属性的表单添加范围内外不同样式

-----

* setTimeout(arguments.callee, 130); 130ms为周期重复调用本方法（但传参会消失，可以用 xx.call(this, arguments);）
* object-fit & object-position 资源在元素中的位置，类似于让 img 的 src 拥有 background 的特性
* querySelector() / $().get(0) / $()[0] 三者相比，后者更快
* onpageshow 拥有 e.persisted 属性能判断该页是否缓存
* MathML 即 <math> 标签，用来写数学表达式的，仅 Firefox 和 Safari 支持
* 微信标题能容纳数量为13字，否则将出现省略号
* svg 标签 <text> 的 textLength 等效于宽度，lengthAdjust 设置自动字间距(spacing)或自动词间距(spacingAndGlyphs)
* svg 最好加上 xmlns="http://www.w3.org/2000/svg"，因为加的话直接打开是渲染后的结果，否则只显示代码
* svg 的 <foreignObject> 嵌套 <body> 解决文本换行的需求
* width 相关的新属性：fill-available（撑满可用空间）、fit-contemt（收缩为内容宽度）、min-content（父级之下除了本元素的最小宽度）、max-content（文本不换行的宽度）

-----

* 用 a = ++a % 5 替代 if (++a > 5) a = 0
* document.execCommand 使用浏览器权限，如复制粘贴
* elem.matchesSelector('.xx') 相当于 $.is('.xx') 需要兼容
* font-display: swap; 让字体加载时不显示为空白，尚未兼容
* navigator.onLine 判断是否联网
* requestIdleCallback 空闲时间运行，与 requestAnimationFrame 合用，当前帧有空闲时间则运行，没有则推迟到下一帧
* HTML 的 ID 可以用中文
* visibilitychange / pointerlockchange / requestPointerLock
* MSPointer 是 IE10 特有的事件处理，合并了 mouse 和 touch
* touch-action: none; 可禁用浏览器的触摸交互，比如拖拽的时候禁用滚动的CSS解决方案

-----

* createEvent / dispatchEvent 自定义事件及其触发
* background 多图形态下，最先的为最上层
* new FormData() 对象可传入 form 元素，或 append(key, value) 来生成数据字符串
* xhr 还有 upload 属性，可以绑定 load progress abort 等事件
* 将 debugtbs.qq.com 输入微信对话框发送，并打开此链接，可强制使用 webview 而不是 X5
* WeakMap 生成弱引用对象，使用 get 和 set 对其他对象进行拿取和赋值，不计入垃圾回收
* currentColor 让子级继承父级的 color，如 background/fill等，兼容性很棒
* shape-outside 改变盒子形状，不再只能是方形。shape-margin 与其他盒子的空隙，shape-image-threshold 根据颜色（比如渐变）来改变盒子形状。兼容较差。
* text-align-last 让最后一行也能进行对齐，ios 不兼容
* tab-size 对 tab 键打出的空隙进行设置，1代表（1个中文字/2个英文字），兼容一般。

-----

* text-decoration 的拓展，text-decoration-line 线条位置（上中下），text-decoration-style 线条样式（点线/虚线/双线/波浪线），兼容一般。
* ctx.setLineDash([lineWidth, lineGap]) | canvas 画虚线
* canvas 使用整数比使用小数会更清晰
* (num + 0.5) | 0 这样来获得整数比较好
* Object.getOwnPropertyDescriptor(obj, prop)
* btoa 转码 / atob 解码（base64 形态的码）
* preventDefault 能解决移动端拖拽时滚动条也跟着动的情况
* jsfiddle RunJS codepen runmars // 线上编辑器
* Date 支持的五种传值 new Date("month dd,yyyy hh:mm:ss"); new Date("month dd,yyyy"); new Date(yyyy,mth,dd,hh,mm,ss); new Date(yyyy,mth,dd); new Date(ms);

-----

* performance.now() // 网页性能
* document.referrer(必须放在服务器，否则为"")
* localeCompare 比较字母大小
* -webkit-user-select: none;user-select: none; 可以阻止微信选择文本，selectstart 方法不行
* accept="image/*" 可兼容所有手机拥有拍照选项
* appendHTML，insertAdjacentHTML，createDocumentFragment 文档片段
* autocapitalize="off" autocorrect="off" 取消IOS输入英文默认首字母大写
* background-origin: content-box; 背景图以什么盒子模式为准
* new Boolean(false) 是一个对象，所以 if (new Boolean(false)) 是会继续运行的
