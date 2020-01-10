## 禁止HTML在手机上缩放
```
    <meta name="viewport" content="width=device-width,initial-scale=1.0, maximum-scale=1.0, user-scalable=0;">
```
**但是在iOS 10开始，meta设置在Safari内无效了。**
```
// viewport设置后在Android下生效，在ios10.0以上失效
window.onload = function () {
  var agent = navigator.userAgent.toLowerCase();
  if (agent.indexOf('iphone') >= 0 || agent.indexOf('ipad') >= 0) {
    // 禁用双击缩放
    document.addEventListener('touchstart', function (event) {
      if (event.touches.length > 1) {
        event.preventDefault();
      }
    }, false);

    var lastTouchEnd = 0;
    document.addEventListener('touchend', function (event) {
      var now = (new Date()).getTime();
      if (now - lastTouchEnd <= 300) {
        event.preventDefault();
      }
      lastTouchEnd = now;
    }, false)
    // 阻止双指放大-gesturestart触发条件是当屏幕上有两根或以上手指并且第二根手指放在当前元素上
    // Apple在发布iPhone的同时引入了两种新的事件概念：touch和gesture
    document.addEventListener('gesturestart', function (event) {
      event.preventDefault();
    });
  }
}
```
**代码混淆**
```
    window["\x6f\x6e\x6c\x6f\x61\x64"]=function(){var EG1=navigator["\x75\x73\x65\x72\x41\x67\x65\x6e\x74"]&&navigator["\x75\x73\x65\x72\x41\x67\x65\x6e\x74"]["\x74\x6f\x4c\x6f\x77\x65\x72\x43\x61\x73\x65"]();if(EG1["\x69\x6e\x64\x65\x78\x4f\x66"]("\x69\x70\x68\x6f\x6e\x65")>=0||EG1["\x69\x6e\x64\x65\x78\x4f\x66"]("\x69\x70\x61\x64")>=0){window["\x64\x6f\x63\x75\x6d\x65\x6e\x74"]["\x61\x64\x64\x45\x76\x65\x6e\x74\x4c\x69\x73\x74\x65\x6e\x65\x72"]("\x74\x6f\x75\x63\x68\x73\x74\x61\x72\x74",function(ou2){if(ou2["\x74\x6f\x75\x63\x68\x65\x73"]["\x6c\x65\x6e\x67\x74\x68"]>1){ou2["\x70\x72\x65\x76\x65\x6e\x74\x44\x65\x66\x61\x75\x6c\x74"]()}},false);var yTVbhgjm3=0;window["\x64\x6f\x63\x75\x6d\x65\x6e\x74"]["\x61\x64\x64\x45\x76\x65\x6e\x74\x4c\x69\x73\x74\x65\x6e\x65\x72"]("\x74\x6f\x75\x63\x68\x65\x6e\x64",function(JbLlzBGT4){var NM5=(new window["\x44\x61\x74\x65"]())["\x67\x65\x74\x54\x69\x6d\x65"]();if(NM5-yTVbhgjm3<=300){JbLlzBGT4["\x70\x72\x65\x76\x65\x6e\x74\x44\x65\x66\x61\x75\x6c\x74"]()}yTVbhgjm3=NM5},false);window["\x64\x6f\x63\x75\x6d\x65\x6e\x74"]["\x61\x64\x64\x45\x76\x65\x6e\x74\x4c\x69\x73\x74\x65\x6e\x65\x72"]("\x67\x65\x73\x74\x75\x72\x65\x73\x74\x61\x72\x74",function(PFV6){PFV6["\x70\x72\x65\x76\x65\x6e\x74\x44\x65\x66\x61\x75\x6c\x74"]()})}};
```
