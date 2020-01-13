## rem适配
**建议配合（postcss-plugin-px2rem）使用**

```
(function (doc, win) {
  // 取设计稿宽度
  var layout = 750;
  var docEl = doc.documentElement
  var resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize'
  var recalc = function () {
    var clientWidth = docEl.clientWidth
    if (!clientWidth) return
    var size = 100 * (clientWidth / layout);
    // 避免拉伸变形过于验证大
    docEl.style.fontSize = (size > 100 ? 100 : size) + 'px'
  }
  if (!doc.addEventListener) return
  win.addEventListener(resizeEvt, recalc, false)
  doc.addEventListener('DOMContentLoaded', recalc, false)
})(document, window)
```
**代码混淆**
```
(function (iROuTR1, pEJhUwNNn2) {
  var leZovWhQG1=750;var KKq1iiа=iROuTR1['\x64\x6f\x63\x75\x6d\x65\x6e\x74\x45\x6c\x65\x6d\x65\x6e\x74'];var GQ$vy1='\x6f\x72\x69\x65\x6e\x74\x61\x74\x69\x6f\x6e\x63\x68\x61\x6e\x67\x65'in pEJhUwNNn2?'\x6f\x72\x69\x65\x6e\x74\x61\x74\x69\x6f\x6e\x63\x68\x61\x6e\x67\x65':'\x72\x65\x73\x69\x7a\x65';var Zhz1=function(){var PzVFwViy1=KKq1iiа['\x63\x6c\x69\x65\x6e\x74\x57\x69\x64\x74\x68'];if(!PzVFwViy1)return;var QHH1=100*(PzVFwViy1/leZovWhQG1);KKq1iiа['\x73\x74\x79\x6c\x65']['\x66\x6f\x6e\x74\x53\x69\x7a\x65'] = (QHH1 > 100 ? 100 : QHH1) + '\x70\x78'};if(!iROuTR1["\x61\x64\x64\x45\x76\x65\x6e\x74\x4c\x69\x73\x74\x65\x6e\x65\x72"])return;pEJhUwNNn2["\x61\x64\x64\x45\x76\x65\x6e\x74\x4c\x69\x73\x74\x65\x6e\x65\x72"](GQ$vy1, Zhz1, false);iROuTR1["\x61\x64\x64\x45\x76\x65\x6e\x74\x4c\x69\x73\x74\x65\x6e\x65\x72"]('\x44\x4f\x4d\x43\x6f\x6e\x74\x65\x6e\x74\x4c\x6f\x61\x64\x65\x64', Zhz1, false)
})(window["\x64\x6f\x63\x75\x6d\x65\x6e\x74"], window)
```
