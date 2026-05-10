<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>城市全能裝修租賃報價系統</title>
    <style>
        body { font-family: "Microsoft JhengHei", sans-serif; padding: 20px; background: #f0f2f5; color: #333; }
        .container { max-width: 800px; margin: auto; background: #fff; padding: 30px; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
        h1 { text-align: center; color: #2c3e50; border-bottom: 2px solid #3498db; padding-bottom: 10px; }
        .category { margin-top: 20px; font-weight: bold; color: #3498db; background: #e8f4fd; padding: 5px 10px; border-left: 4px solid #3498db; }
        .item-row { display: flex; align-items: center; padding: 10px 0; border-bottom: 1px inset #eee; }
        .item-name { flex: 2; font-size: 15px; }
        .item-price { flex: 1; color: #888; font-size: 13px; text-align: right; margin-right: 15px; }
        .item-input { flex: 1; }
        input[type="number"] { width: 100%; padding: 8px; border: 1px solid #ddd; border-radius: 4px; }
        button { width: 100%; padding: 15px; background: #27ae60; color: #fff; border: none; cursor: pointer; border-radius: 6px; font-size: 18px; margin-top: 25px; transition: 0.3s; }
        button:hover { background: #219150; }
        #result { margin-top: 25px; padding: 20px; background: #fffbe6; border: 1px solid #ffe58f; border-radius: 8px; display: none; }
        .total-amount { font-size: 24px; color: #e74c3c; font-weight: bold; text-align: right; border-top: 2px solid #ccc; margin-top: 10px; padding-top: 10px; }
    </style>
</head>
<body>

<div class="container">
    <h1>🏠 城市全能裝修報價</h1>
    <p style="text-align: center; color: #666;">（中等偏下優惠價位 · 線上初步估算）</p>

    <!-- 基礎工程 -->
    <div class="category">一、拆除與基礎工程</div>
    <div class="item-row">
        <span class="item-name">牆面/地面拆除 (坪)</span>
        <span class="item-price">$1,200起</span>
        <div class="item-input"><input type="number" class="p" data-l="牆面拆除" data-h="1200" placeholder="0"></div>
    </div>
    <div class="item-row">
        <span class="item-name">廢棄物清運 (車)</span>
        <span class="item-price">$3,500起</span>
        <div class="item-input"><input type="number" class="p" data-l="廢棄物清運" data-h="3500" placeholder="0"></div>
    </div>

    <!-- 泥作工程 -->
    <div class="category">二、泥作工程</div>
    <div class="item-row">
        <span class="item-name">浴室整修 (間) - 基本款</span>
        <span class="item-price">$45,000起</span>
        <div class="item-input"><input type="number" class="p" data-l="浴室整修" data-h="45000" placeholder="0"></div>
    </div>
    <div class="item-row">
        <span class="item-name">地磚鋪設 (坪) - 工帶料</span>
        <span class="item-price">$3,800起</span>
        <div class="item-input"><input type="number" class="p" data-l="地磚鋪設" data-h="3800" placeholder="0"></div>
    </div>

    <!-- 水電工程 -->
    <div class="category">三、水電配管</div>
    <div class="item-row">
        <span class="item-name">全屋電線更新 (坪)</span>
        <span class="item-price">$2,500起</span>
        <div class="item-input"><input type="number" class="p" data-l="全屋電線更新" data-h="2500" placeholder="0"></div>
    </div>

    <!-- 木作/天花板 -->
    <div class="category">四、木作與天花板</div>
    <div class="item-row">
        <span class="item-name">平釘天花板 (坪)</span>
        <span class="item-price">$2,800起</span>
        <div class="item-input"><input type="number" class="p" data-l="平釘天花板" data-h="2800" placeholder="0"></div>
    </div>
    <div class="item-row">
        <span class="item-name">系統高櫃 (尺)</span>
        <span class="item-price">$2,200起</span>
        <div class="item-input"><input type="number" class="p" data-l="系統高櫃" data-h="2200" placeholder="0"></div>
    </div>

    <!-- 地板工程 -->
    <div class="category">五、地板/油漆工程</div>
    <div class="item-row">
        <span class="item-name">超耐磨/SPC地板 (坪)</span>
        <span class="item-price">$2,600起</span>
        <div class="item-input"><input type="number" class="p" data-l="SPC地板" data-h="2600" placeholder="0"></div>
    </div>
    <div class="item-row">
        <span class="item-name">全屋油漆 (坪) - 跳色另計</span>
        <span class="item-price">$800起</span>
        <div class="item-input"><input type="number" class="p" data-l="全屋油漆" data-h="800" placeholder="0"></div>
    </div>

    <button onclick="calculate()">立即計算初步報價</button>

    <div id="result">
        <div id="detail-list"></div>
        <div class="total-amount" id="total-display"></div>
        <p style="font-size: 12px; color: #999; margin-top: 15px;">* 此報價僅供參考，實際價格依現場勘查為準。</p>
    </div>
</div>

<script>
function calculate() {
    let items = document.querySelectorAll('.p');
    let total = 0;
    let detailHtml = "<h3>報價清單：</h3>";
    let hasValue = false;

    items.forEach(item => {
        let qty = parseFloat(item.value) || 0;
        if (qty > 0) {
            hasValue = true;
            let unitPrice = parseFloat(item.dataset.h);
            let subtotal = qty * unitPrice;
            total += subtotal;
            detailHtml += `<div style="display:flex; justify-content:space-between; margin-bottom:5px;">
                <span>${item.dataset.l} x ${qty}</span>
                <span>$${subtotal.toLocaleString()}</span>
            </div>`;
        }
    });

    if (!hasValue) {
        alert("請至少輸入一個品項的數量！");
        return;
    }

    document.getElementById('detail-list').innerHTML = detailHtml;
    document.getElementById('total-display').innerText = "預估總金額：$" + total.toLocaleString();
    document.getElementById('result').style.display = "block";
    
    // 自動滾動到結果畫面
    document.getElementById('result').scrollIntoView({ behavior: 'smooth' });
}
</script>

</body>
</html>
