---
layout: page
title: Contact
permalink: /contact/
---

<!--  -->
<!-- Adopted from http://www.grall.name/posts/1/onlineTools_obfuscation.html -->
<!--  -->
<script language="Javascript" type="text/Javascript">
    function decrypt(origin, size, key, word) {
      var s = 0
      for (var i = 0; i < key.length; i++) {
        s = s + key.charCodeAt(i)
      }
      var pos = 0
      var first = s % word.length
      var prefix = ''
      var suffix = ''
      for (var i = 0; i < word.length - first; i++) {
        suffix = suffix + String.fromCharCode((word.charCodeAt(i) + size - key.charCodeAt(pos)) % size+ origin)
        pos = (pos + 1) % key.length
      }
      for (var i = word.length - first; i < word.length; i++) {
        prefix = prefix + String.fromCharCode((word.charCodeAt(i) + size - key.charCodeAt(pos)) % size + origin)
        pos = (pos + 1) % key.length
      }
      var d = prefix + suffix
      return d;
    };

    var orig1 = 38, orig2 = 44;
    var size1 = 84, size2 = 83;
    var key1 = "mone" + "yint" + "heba" + "nana" + "stand";
    var key2 = "par" + "esh" + "aan";
    var word1 = "[^hm" + "oPf_" + "YS(L" + "mLb\\" + "d(Jc" + "Wa^g";
    var word2 = "ZU[y[" + "VCK[r" + "EbSdJ" + "TGZYP";

    document.write("For official purposes, please use: " + decrypt(orig1,size1,key1,word1) + "<br>" +
                   "For personal purposes, please use: " + decrypt(orig2,size2,key2,word2))

</script>

My public key can be accessed <a href="../public.asc">here</a>.