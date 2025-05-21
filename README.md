# Studdyflow
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>...</title>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no"/>
    <meta name="robots" content="noindex, nofollow">
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
    <!--<link rel="manifest" href="/site.webmanifest">-->
    <meta name="msapplication-TileColor" content="#da532c">
    <meta name="theme-color" content="#ffffff">
    <!-- Hotjar Tracking Code -->
    <script>
      (function(h,o,t,j,a,r){
          h.hj=h.hj||function(){(h.hj.q=h.hj.q||[]).push(arguments)};
          h._hjSettings={hjid:689640,hjsv:6};
          a=o.getElementsByTagName('head')[0];
          r=o.createElement('script');r.async=1;
          r.src=t+h._hjSettings.hjid+j+h._hjSettings.hjsv;
          a.appendChild(r);
      })(window,document,'https://static.hotjar.com/c/hotjar-','.js?sv=');
    </script>
  <link href="/style.490bf0b6cad937f463fd.css" rel="stylesheet"></head>
  <body>
    <div id="app"></div>
    <div id="vendor-scripts">
      <script src="https://cdnjs.cloudflare.com/ajax/libs/react/16.8.5/umd/react.production.min.js"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/react-dom/16.8.5/umd/react-dom.production.min.js"></script>
      <script src="https://cdn.jsdelivr.net/g/lodash@4(lodash.min.js+lodash.fp.min.js)"></script>
      <script src="https://cdnjs.cloudflare.com/ajax/libs/rxjs/5.4.3/Rx.min.js"></script>
    </div>
    <script type="text/javascript"> (function(){var t=document.createElement("script");t.type="text/javascript",t.async=!0,t.src='https://cdn.firstpromoter.com/fprom.js',t.onload=t.onreadystatechange=function(){var t=this.readyState;if(!t||"complete"==t||"loaded"==t)try{$FPROM.init("4d7zgogz",".app.weblium.com")}catch(t){}};var e=document.getElementsByTagName("script")[0];e.parentNode.insertBefore(t,e)})(); </script>

    <!-- GA -->
    <script>
      (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
      (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
      m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
      })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
      "serviceWorker" in navigator && navigator.serviceWorker.register('/sw.js');
      fetch(self.location.origin.replace("//app.", "//api.") + "/api/host/replacer")
        .then(function(res) {return res.json()}).then(function(replacer) {
          replacer = replacer ? replacer.data : {}
          if(!Object.keys(replacer).length) return
          var replacing, Observer = window.MutationObserver || window.WebKitMutationObserver
          function replace(node) {
            if(node === document.documentElement || !node.attributes) return
            try {
              function r(node) {
                for(var i  = node.attributes.length - 1; i >= 0; i--) {
                  var o = node.attributes[i].value
                  var n = o
                  replacing = true
                  for(var key in replacer)
                    n = n.replaceAll ? n.replaceAll("//" + key, "//" + replacer[key])
                      : n.replace(new RegExp("\\\\/\\\\/" + key.replace(/\\./g, "\\\\."), "g"), "//" + replacer[key])
                  replacing = false
                  if(o != n) node.setAttribute(node.attributes[i].name, n)
                }
                for(var i = node.childNodes.length-1; i >= 0; i--) r(node.childNodes[i])
              }
              r(node)
            } catch(e) {e}
          }
          replace(document.body)
          if(Observer) {
            window.__replacer__ = new Observer(function(mutationRecords) {
              replacing || setTimeout(function() {mutationRecords.forEach(function(data) {replace(data.target)})}, 100)
            })
            window.__replacer__.observe(document.documentElement, {subtree: true, childList: true, attributes: true})
          }
        }).catch(function(error) {console.error(error)});
    </script>
<script type="text/javascript" src="/main.490bf0b6cad937f463fd.js"></script></body>
</html>
