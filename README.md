<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>城市全能裝修報價系統</title>
    <style>
        body { font-family: "Microsoft JhengHei", sans-serif; background: #f4f7f6; padding: 20px; }
        .container { max-width: 600px; margin: auto; background: white; padding: 25px; border-radius: 12px; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        h2 { text-align: center; color: #2c3e50; }
        .item-row { display: flex; justify-content: space-between; align-items: center; padding: 10px 0; border-bottom: 1px solid #eee; }
        input { width: 100px; padding: 5px; text-align: right; }
        button { width: 100%; padding: 15px; background: #3498db; color: white; border: none; border-radius: 5px; font-size: 18px; cursor: pointer; margin-top: 20px; }
        #result { display: none; margin-top: 20px; padding: 15px; background: #fffbe6; border: 1px solid #ffe58f; }
        .line-btn { display: block; text-align: center; background: #00c300; color: white; padding: 15px; text-decoration: none; border-radius: 5px; margin-top: 15px; font-weight: bold; }
    </style>
</head>
<body>
<div class="container">
    <h2>🏠 城市全能裝修報價系統</h2>
    <p>施工地址：<input type="text" id="addr" style="width: 200px;" placeholder="請輸入地址"></p>
    <div class="item-row"><span>卡扣地板 (坪)</span><input type="number" class="calc" data-l="2800" data-h="4500"></div>
    <div class="item-row"><span>橡木地板 (坪)</span><input type="number" class="calc" data-l="9000" data-h="16000"></div>
    <div class="item-row"><span>浴室翻新 (間)</span><input type="number" class="calc" data-l="135000" data-h="220000"></div>
    <div class="item-row"><span>全屋電線重拉 (坪)</span><input type="number" class="calc" data-l="3500" data-h="6000"></div>
    <div class="item-row"><span>天花板拆除 (坪)</span><input type="number" class="calc" data-l="800" data-h="1200"></div>
    <button onclick="calculate()">🔥 產出即時報價單</button>
    <div id="result">
        <div id="details"></div>
        <p><strong>⚠️ 以上為初估價錢</strong></p>
        <input type="text" placeholder="您的姓名" style="width: 100%; margin-bottom: 10px;"><br>
        <input type="text" placeholder="您的電話" style="width: 100%;"><br>
        <a href="https://line.me" class="line-btn">🟢 加入 LINE 官方：＠fanyan</a>
    </div>
</div>
<script>
function calculate() {
    let items = document.querySelectorAll('.calc'), lowSum = 0, highSum = 0, txt = "";
    items.forEach(el => {
        let v = parseFloat(el.value) || 0;
        if(v > 0) {
            let l = v * parseFloat(el.dataset.l), h = v * parseFloat(el.dataset.h);
            lowSum += l; highSum += h;
            txt += "✅ " + el.parentElement.querySelector('span').innerText + ": $" + l.toLocaleString() + " ~ $" + h.toLocaleString() + "<br>";
        }
    });
    if(lowSum === 0) return alert("請輸入數量！");
    document.getElementById('details').innerHTML = txt + "<hr><h3>總計：$" + lowSum.toLocaleString() + " ~ $" + highSum.toLocaleString() + "</h3>";
    document.getElementById('result').style.display = 'block';
}
</script>
</body>
</html>
