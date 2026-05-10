<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>城市全能裝修租賃報價系統 - 旗艦版</title>
    <style>
        body { font-family: "Microsoft JhengHei", sans-serif; background: #f0f4f8; padding: 10px; margin: 0; }
        .container { max-width: 900px; margin: 20px auto; background: #fff; padding: 25px; border-radius: 12px; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        h1 { text-align: center; color: #1e3a8a; border-bottom: 3px solid #1e3a8a; padding-bottom: 10px; }
        .info-box { background: #eef2ff; padding: 15px; border-radius: 8px; margin-bottom: 20px; }
        .category-header { background: #1e3a8a; color: white; padding: 8px 15px; margin-top: 25px; border-radius: 4px; font-size: 1.1em; }
        table { width: 100%; border-collapse: collapse; margin-top: 5px; }
        th, td { padding: 10px; border-bottom: 1px solid #ddd; text-align: left; }
        th { background: #f8fafc; font-size: 0.9em; color: #64748b; }
        input[type="number"] { width: 70px; padding: 5px; border: 1px solid #cbd5e1; border-radius: 4px; text-align: center; }
        .price-text { color: #d97706; font-weight: bold; }
        .sticky-footer { position: sticky; bottom: 0; background: rgba(255,255,255,0.95); padding: 15px; border-top: 2px solid #1e3a8a; text-align: center; }
        button { background: #059669; color: white; padding: 12px 40px; border: none; border-radius: 6px; font-size: 1.2em; cursor: pointer; transition: 0.3s; width: 100%; }
        button:hover { background: #047857; }
        #result-area { display: none; margin-top: 20px; padding: 20px; background: #fffbeb; border: 2px dashed #f59e0b; border-radius: 10px; }
        .total-row { font-size: 1.8em; color: #b91c1c; font-weight: bold; text-align: right; margin-top: 15px; }
        .item-name { width: 50%; }
    </style>
</head>
<body>

<div class="container">
    <h1>🏠 城市全能裝修報價系統</h1>
    <p style="text-align:center; color:#666;">（50項全能服務 · 中等偏下優惠報價）</p>

    <div class="info-box">
        <label><b>施工地址：</b></label>
        <input type="text" id="addr" placeholder="請輸入地址" style="width: 70%; padding: 5px;">
    </div>

    <!-- 1. 保護與拆除 (7項) -->
    <div class="category-header">一、保護與拆除工程</div>
    <table>
        <tr><th class="item-name">品項</th><th>單價</th><th>數量</th></tr>
        <tr><td>地面防潮防護 (坪)</td><td class="price-text">$300</td><td><input type="number" class="p" data-l="地面防護" data-h="300"></td></tr>
        <tr><td>天花板拆除 (坪)</td><td class="price-text">$650</td><td><input type="number" class="p" data-l="天花板拆除" data-h="650"></td></tr>
        <tr><td>隔間牆拆除 (坪)</td><td class="price-text">$1,200</td><td><input type="number" class="p" data-l="隔間牆拆除" data-h="1200"></td></tr>
        <tr><td>地磚/地板拆除 (坪)</td><td class="price-text">$850</td><td><input type="number" class="p" data-l="地磚拆除" data-h="850"></td></tr>
        <tr><td>浴室整間拆除 (間)</td><td class="price-text">$12,000</td><td><input type="number" class="p" data-l="浴室拆除" data-h="12000"></td></tr>
        <tr><td>廚具/櫃體拆除 (組)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="廚具拆除" data-h="3500"></td></tr>
        <tr><td>廢棄物清運 (車)</td><td class="price-text">$3,800</td><td><input type="number" class="p" data-l="廢棄物清運" data-h="3800"></td></tr>
    </table>

    <!-- 2. 泥作工程 (8項) -->
    <div class="category-header">二、基礎泥作工程</div>
    <table>
        <tr><td>牆面水泥粉光 (坪)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="水泥粉光" data-h="2500"></td></tr>
        <tr><td>浴室防水/貼磚 (間)</td><td class="price-text">$45,000</td><td><input type="number" class="p" data-l="浴室貼磚" data-h="45000"></td></tr>
        <tr><td>拋光石英磚 (坪)</td><td class="price-text">$4,200</td><td><input type="number" class="p" data-l="拋光磚" data-h="4200"></td></tr>
        <tr><td>地磚鋪設 (坪)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="地磚鋪設" data-h="3500"></td></tr>
        <tr><td>文化石/造型磚 (坪)</td><td class="price-text">$5,500</td><td><input type="number" class="p" data-l="文化石" data-h="5500"></td></tr>
        <tr><td>砌磚牆 (坪)</td><td class="price-text">$5,000</td><td><input type="number" class="p" data-l="砌磚牆" data-h="5000"></td></tr>
        <tr><td>門檻/大理石 (條)</td><td class="price-text">$1,500</td><td><input type="number" class="p" data-l="門檻" data-h="1500"></td></tr>
        <tr><td>填縫處理 (坪)</td><td class="price-text">$400</td><td><input type="number" class="p" data-l="填縫" data-h="400"></td></tr>
    </table>

    <!-- 3. 水電工程 (8項) -->
    <div class="category-header">三、水電配置工程</div>
    <table>
        <tr><td>全屋電線更新 (坪)</td><td class="price-text">$2,800</td><td><input type="number" class="p" data-l="電線更新" data-h="2800"></td></tr>
        <tr><td>新增插座/移位 (個)</td><td class="price-text">$650</td><td><input type="number" class="p" data-l="新增插座" data-h="650"></td></tr>
        <tr><td>冷熱水管更新 (間)</td><td class="price-text">$18,000</td><td><input type="number" class="p" data-l="水管更新" data-h="18000"></td></tr>
        <tr><td>開關面板更新 (組)</td><td class="price-text">$450</td><td><input type="number" class="p" data-l="開關更新" data-h="450"></td></tr>
        <tr><td>燈具安裝工費 (盞)</td><td class="price-text">$300</td><td><input type="number" class="p" data-l="燈具安裝" data-h="300"></td></tr>
        <tr><td>衛浴設備安裝 (組)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="衛浴安裝" data-h="3500"></td></tr>
        <tr><td>排風扇/暖風機 (組)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="暖風機安裝" data-h="2500"></td></tr>
        <tr><td>對講機系統更新 (組)</td><td class="price-text">$3,800</td><td><input type="number" class="p" data-l="對講機" data-h="3800"></td></tr>
    </table>

    <!-- 4. 木作工程 (7項) -->
    <div class="category-header">四、精緻木作/天花</div>
    <table>
        <tr><td>平釘矽酸鈣板 (坪)</td><td class="price-text">$2,800</td><td><input type="number" class="p" data-l="平釘天花" data-h="2800"></td></tr>
        <tr><td>造型/間接天花 (坪)</td><td class="price-text">$3,800</td><td><input type="number" class="p" data-l="造型天花" data-h="3800"></td></tr>
        <tr><td>木作隔間牆-雙面 (坪)</td><td class="price-text">$3,200</td><td><input type="number" class="p" data-l="木作隔間" data-h="3200"></td></tr>
        <tr><td>實木房門更換 (樘)</td><td class="price-text">$6,500</td><td><input type="number" class="p" data-l="房門更換" data-h="6500"></td></tr>
        <tr><td>隱藏門製作 (樘)</td><td class="price-text">$12,000</td><td><input type="number" class="p" data-l="隱藏門" data-h="12000"></td></tr>
        <tr><td>包樑/窗簾盒 (尺)</td><td class="price-text">$500</td><td><input type="number" class="p" data-l="包樑窗簾盒" data-h="500"></td></tr>
        <tr><td>電視牆面造型 (坪)</td><td class="price-text">$6,000</td><td><input type="number" class="p" data-l="電視牆" data-h="6000"></td></tr>
    </table>

    <!-- 5. 系統與地板 (7項) -->
    <div class="category-header">五、系統櫃與地板工程</div>
    <table>
        <tr><td>系統衣櫃 (尺)</td><td class="price-text">$2,400</td><td><input type="number" class="p" data-l="系統衣櫃" data-h="2400"></td></tr>
        <tr><td>系統鞋櫃/矮櫃 (尺)</td><td class="price-text">$1,800</td><td><input type="number" class="p" data-l="系統鞋櫃" data-h="1800"></td></tr>
        <tr><td>系統書櫃/展示櫃 (尺)</td><td class="price-text">$2,200</td><td><input type="number" class="p" data-l="系統書櫃" data-h="2200"></td></tr>
        <tr><td>廚具下櫃 (尺)</td><td class="price-text">$3,200</td><td><input type="number" class="p" data-l="廚具下櫃" data-h="3200"></td></tr>
        <tr><td>SPC石塑地板 (坪)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="SPC地板" data-h="2500"></td></tr>
        <tr><td>超耐磨木地板 (坪)</td><td class="price-text">$3,200</td><td><input type="number" class="p" data-l="超耐磨地板" data-h="3200"></td></tr>
        <tr><td>樓梯踏板鋪設 (階)</td><td class="price-text">$1,500</td><td><input type="number" class="p" data-l="樓梯踏板" data-h="1500"></td></tr>
    </table>

    <!-- 6. 油漆與鋁窗 (7項) -->
    <div class="category-header">六、油漆與鋁窗工程</div>
    <table>
        <tr><td>全屋油漆/水泥漆 (坪)</td><td class="price-text">$800</td><td><input type="number" class="p" data-l="水泥漆" data-h="800"></td></tr>
        <tr><td>乳膠漆/跳色 (坪)</td><td class="price-text">$1,200</td><td><input type="number" class="p" data-l="乳膠漆" data-h="1200"></td></tr>
        <tr><td>壁紙施工 (坪)</td><td class="price-text">$1,200</td><td><input type="number" class="p" data-l="壁紙施工" data-h="1200"></td></tr>
        <tr><td>鋁窗更新 (才)</td><td class="price-text">$650</td><td><input type="number" class="p" data-l="鋁窗更新" data-h="650"></td></tr>
        <tr><td>氣密窗/隔音窗 (才)</td><td class="price-text">$850</td><td><input type="number" class="p" data-l="氣密窗" data-h="850"></td></tr>
        <tr><td>紗窗更換 (片)</td><td class="price-text">$400</td><td><input type="number" class="p" data-l="紗窗更換" data-h="400"></td></tr>
        <tr><td>後陽台三合一門 (樘)</td><td class="price-text">$15,000</td><td><input type="number" class="p" data-l="三合一門" data-h="15000"></td></tr>
    </table>

    <!-- 7. 其他與清潔 (6項) -->
    <div class="category-header">七、雜項與專業清潔</div>
    <table>
        <tr><td>冷氣安裝/清洗 (組)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="冷氣服務" data-h="3500"></td></tr>
        <tr><td>全屋細部清潔 (坪)</td><td class="price-text">$650</td><td><input type="number" class="p" data-l="細部清潔" data-h="650"></td></tr>
        <tr><td>粗清/清運 (次)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="粗清" data-h="2500"></td></tr>
        <tr><td>水塔清洗 (座)</td><td class="price-text">$2,000</td><td><input type="number" class="p" data-l="水塔清洗" data-h="2000"></td></tr>
        <tr><td>五金掛件安裝 (組)</td><td class="price-text">$500</td><td><input type="number" class="p" data-l="五金安裝" data-h="500"></td></tr>
        <tr><td>防水修補工程 (次)</td><td class="price-text">$3,000</td><td><input type="number" class="p" data-l="防水修補" data-h="3000"></td></tr>
    </table>

    <div class="sticky-footer">
        <button onclick="calculateTotal()">生成專業報價單</button>
    </div>

    <div id="result-area">
        <h2 id="final-addr"></h2>
        <div id="final-list"></div>
        <div class="total-row" id="final-total"></div>
        <p style="color: #666; font-size: 0.8em; margin-top: 20px;">
            * 備註：以上報價為初步估算值，最終報價視材料等級與現場困難度而定。<br>
            * 若有未盡事宜，請與服務專員聯繫。
        </p>
    </div>
</div>

<script>
function calculateTotal() {
    let items = document.querySelectorAll('.p');
    let total = 0;
    let listHtml = "<ul>";
    let addr = document.getElementById('addr').value;
    let hasValue = false;

    items.forEach(i => {
        let qty = parseFloat(i.value) || 0;
        if (qty > 0) {
            hasValue = true;
            let subtotal = qty * parseFloat(i.dataset.h);
            total += subtotal;
            listHtml += `<li><b>${i.dataset.l}</b>: ${qty} 單位 × $${parseInt(i.dataset.h).toLocaleString()} = <span style="float:right;">$${subtotal.toLocaleString()}</span></li>`;
        }
    });

    if (!hasValue) {
        alert("還沒填入任何項目喔！");
        return;
    }

    document.getElementById('final-addr').innerText = "📍 施工地點：" + (addr || "未註記");
    document.getElementById('final-list').innerHTML = listHtml + "</ul>";
    document.getElementById('final-total').innerText = "預估總金額：$" + total.toLocaleString();
    document.getElementById('result-area').style.display = "block";
    window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
}
</script>

</body>
</html>
