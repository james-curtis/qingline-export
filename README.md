# qingline-export
清览题目导出


# 代码
```js
function markRightAns() {
  let right = document.querySelectorAll(".option_box.right_answer");
  for (let item of right) {
    item.append("✔");
  }
}

function getQue(el) {
  if (!el.querySelector) return;
  let title = el.querySelector(".stem_con").innerText;
  let ops = [];
  for (let op of el.querySelectorAll(".option_box")) {
    ops.push(op.textContent);
  }
  return `${title}\n${ops.join("\n")}`;
}

(function () {
  markRightAns();
  let ques = document.querySelectorAll(".ques_part");
  let res = [];
  let logText = [];
  for (let idx of [...Array.from({ length: ques.length }).keys()]) {
    console.log(ques[idx]);
    let resp = getQue(ques[idx]);
    res.push(resp);
    logText.push(`${Number(idx) + 1}. ${resp}`);
    logText.push("");
  }
  console.log(logText.join("\n"));
})();
``

# 执行
在浏览器控制台执行之后即可得到结果

![image](https://user-images.githubusercontent.com/49338067/220844625-26424921-25ad-463c-b97d-ed9a43a889ec.png)
