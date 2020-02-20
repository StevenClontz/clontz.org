---
layout: page
title: "Signature"
description: ""
header-img: "img/puzzles-bg.png"
permalink: /puzzles/sign/
---

<input type="text" id="message">

<pre id="output"></pre>

<script type="text/javascript">
var message = document.getElementById("message");
var pre = document.getElementById("output");
var update = function(e) {
  var message = document.getElementById("message");
  pre.innerHTML = "";
  var sign =   "STEVENCLONTZ";
//  var messages = [
//    "ENJOYTHEBOOK",
//    "HAPPYSOLVING",
//    "HEYxxHAVEFUN",
//    "TOxxxHAVEFUN",
//    "HEYxxxxENJOY",
//    "xxxxxHAVEFUN",
//    "THANKSxxxxxx",
//    "ENJOYxxxxxxx",
//    "DEARxsxxxxxx",
//  ]
  var plain;
  switch(message.value.length) {
    case 1:
      plain = "ENJOYTHEBOOK";
      break;
    case 2:
      plain = "HEY"+message.value.toUpperCase()+"HAVEFUN";
      break;
    case 3:
      plain = "TO"+message.value.toUpperCase()+"HAVEFUN";
      break;
    case 4:
      plain = "HEY"+message.value.toUpperCase()+"ENJOY";
      break;
    case 5:
      plain = message.value.toUpperCase()+"HAVEFUN";
      break;
    case 6:
      plain = "THANKS"+message.value.toUpperCase();
      break;
    case 7:
      plain = "ENJOY"+message.value.toUpperCase();
      break;
    case 8:
      plain = "DEAR"+message.value.toUpperCase();
      break;
    default:
      plain = "HAPPYSOLVING";
      break;
  }
  pre.innerHTML += plain+"\n";
  for (var i = 0; i < 12; i++) {
    var diff = plain[i].charCodeAt(0)-sign[i].charCodeAt(0);
    pre.innerHTML += String(diff)+" ";
  }
  pre.innerHTML += "\n";
}
update();
message.addEventListener("input", update);
</script>
