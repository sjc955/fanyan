<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>城市全能裝修租賃報價系統</title>
    <style>
        body { font-family: "Microsoft JhengHei", sans-serif; background: #f4f7f6; padding: 10px; margin: 0; color: #333; }
        .container { max-width: 900px; margin: 20px auto; background: #fff; padding: 25px; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1); }
        h1 { text-align: center; color: #1a508b; border-bottom: 3px solid #1a508b; padding-bottom: 10px; margin-bottom: 5px; }
        .subtitle { text-align: center; color: #666; font-size: 14px; margin-bottom: 25px; }
        .info-box { background: #eef2ff; padding: 15px; border-radius: 8px; margin-bottom: 20px; border: 1px solid #d1d5db; }
        .category-header { background: #1a508b; color: white; padding: 10px 15px; margin-top: 30px; border-radius: 5px; font-size: 1.1em; font-weight: bold; }
        table { width: 100%; border-collapse: collapse; margin-top: 5px; background: #fff; }
        th, td { padding: 12px 10px; border-bottom: 1px solid #eee; text-align: left; }
        th { background: #f9fafb; font-size: 0.9em; color: #6b7280; }
        input[type="number"] { width: 75px; padding: 6px; border: 1px solid #cbd5e1; border-radius: 4px; text-align: center; font-size: 16px; }
        .price-text { color: #d97706; font-weight: bold; font-size: 0.95em; }
        .item-name { width: 50%; font-weight: 500; }
        .sticky-footer { position: sticky; bottom: 0; background: rgba(255,255,255,0.95); padding: 15px; border-top: 2px solid #1a508b; text-align: center; z-index: 100; }
        .calc-btn { background: #1a508b; color: white; padding: 15px; border: none; border-radius: 8px; font-size: 1.3em; cursor: pointer; width: 100%; font-weight: bold; transition: 0.3s; }
        .calc-btn:hover { background: #133e6d; }
        #result-area { display: none; margin-top: 30px; padding: 25px; background: #fffbeb; border: 2px dashed #f59e0b; border-radius: 12px; }
        .total-row { font-size: 2em; color: #b91c1c; font-weight: bold; text-align: right; margin-top: 15px; border-top: 1px solid #f59e0b; padding-top: 10px; }
        .line-btn { display: flex; align-items: center; justify-content: center; background: #06C755; color: white; text-align: center; padding: 18px; border-radius: 10px; font-size: 1.4em; text-decoration: none; font-weight: bold; margin-top: 25px; transition: 0.3s; }
        .line-btn:hover { background: #05a346; transform: translateY(-2px); }
        .note-text { color: #d35400; font-weight: bold; text-align: center; font-size: 1.2em; margin-top: 20px; }
    </style>
</head>
<body>

<div class="container">
    <h1>🏠 城市全能裝修報價系統</h1>
    <div class="subtitle">專業工法 · 價格透明 · 50項全能服務</div>

    <div class="info-box">
        <label><b>📍 施工地址 / 聯絡人資訊：</b></label>
        <input type="text" id="user_info" placeholder="例如：新北市板橋區王先生 0912-345xxx" style="width: 100%; padding: 10px; margin-top: 8px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box;">
    </div>

    <!-- 1. 保護與拆除 (7項) -->
    <div class="category-header">一、保護與拆除工程</div>
    <table>
        <tr><th class="item-name">品項</th><th>單價</th><th>數量</th></tr>
        <tr><td>全屋地面防潮防護 (坪)</td><td class="price-text">$300</td><td><input type="number" class="p" data-l="地面防護" data-h="300"></td></tr>
        <tr><td>木作天花板拆除 (坪)</td><td class="price-text">$650</td><td><input type="number" class="p" data-l="天花板拆除" data-h="650"></td></tr>
        <tr><td>隔間牆拆除 (坪)</td><td class="price-text">$1,200</td><td><input type="number" class="p" data-l="隔間牆拆除" data-h="1200"></td></tr>
        <tr><td>地磚/地板拆除 (坪)</td><td class="price-text">$850</td><td><input type="number" class="p" data-l="地磚拆除" data-h="850"></td></tr>
        <tr><td>浴室整間拆除 (間)</td><td class="price-text">$12,000</td><td><input type="number" class="p" data-l="浴室拆除" data-h="12000"></td></tr>
        <tr><td>廚具/大型櫃體拆除 (組)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="廚具拆除" data-h="3500"></td></tr>
        <tr><td>廢棄物清運 (3.5噸車)</td><td class="price-text">$3,800</td><td><input type="number" class="p" data-l="廢棄物清運" data-h="3800"></td></tr>
    </table>

    <!-- 2. 水電工程 (8項) -->
    <div class="category-header">二、基礎水電工程</div>
    <table>
        <tr><td>全屋電線更新 (坪)</td><td class="price-text">$2,800</td><td><input type="number" class="p" data-l="電線更新" data-h="2800"></td></tr>
        <tr><td>新增插座/電燈開關 (個)</td><td class="price-text">$650</td><td><input type="number" class="p" data-l="新增插座" data-h="650"></td></tr>
        <tr><td>冷熱水管更新 (間)</td><td class="price-text">$18,000</td><td><input type="number" class="p" data-l="水管更新" data-h="18000"></td></tr>
        <tr><td>衛浴設備安裝工費 (組)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="衛浴安裝" data-h="3500"></td></tr>
        <tr><td>開關面板更新 (組)</td><td class="price-text">$450</td><td><input type="number" class="p" data-l="開關更新" data-h="450"></td></tr>
        <tr><td>燈具/嵌燈安裝 (盞)</td><td class="price-text">$300</td><td><input type="number" class="p" data-l="燈具安裝" data-h="300"></td></tr>
        <tr><td>浴室排風扇/暖風機 (組)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="暖風機安裝" data-h="2500"></td></tr>
        <tr><td>電話/網路線路配置 (處)</td><td class="price-text">$1,200</td><td><input type="number" class="p" data-l="網路線配置" data-h="1200"></td></tr>
    </table>

    <!-- 3. 泥作工程 (8項) -->
    <div class="category-header">三、專業泥作工程</div>
    <table>
        <tr><td>牆面水泥粉光 (坪)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="水泥粉光" data-h="2500"></td></tr>
        <tr><td>浴室防水/貼磚 (間)</td><td class="price-text">$45,000</td><td><input type="number" class="p" data-l="浴室防水貼磚" data-h="45000"></td></tr>
        <tr><td>拋光石英磚鋪設 (坪)</td><td class="price-text">$4,200</td><td><input type="number" class="p" data-l="拋光磚" data-h="4200"></td></tr>
        <tr><td>室內地磚鋪設 (坪)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="地磚鋪設" data-h="3500"></td></tr>
        <tr><td>紅磚牆砌磚 (坪)</td><td class="price-text">$5,000</td><td><input type="number" class="p" data-l="砌磚牆" data-h="5000"></td></tr>
        <tr><td>大理石門檻安裝 (條)</td><td class="price-text">$1,500</td><td><input type="number" class="p" data-l="門檻" data-h="1500"></td></tr>
        <tr><td>牆面瓷磚修補 (次)</td><td class="price-text">$3,000</td><td><input type="number" class="p" data-l="瓷磚修補" data-h="3000"></td></tr>
        <tr><td>洩水坡度調整 (處)</td><td class="price-text">$2,000</td><td><input type="number" class="p" data-l="洩水調整" data-h="2000"></td></tr>
    </table>

    <!-- 4. 木作工程 (7項) -->
    <div class="category-header">四、精緻木作工程</div>
    <table>
        <tr><td>平釘矽酸鈣天花板 (坪)</td><td class="price-text">$2,800</td><td><input type="number" class="p" data-l="平釘天花" data-h="2800"></td></tr>
        <tr><td>間接照明造型天花 (坪)</td><td class="price-text">$3,800</td><td><input type="number" class="p" data-l="造型天花" data-h="3800"></td></tr>
        <tr><td>木作隔間牆-雙面 (坪)</td><td class="price-text">$3,200</td><td><input type="number" class="p" data-l="木作隔間" data-h="3200"></td></tr>
        <tr><td>窗簾盒製作 (尺)</td><td class="price-text">$500</td><td><input type="number" class="p" data-l="窗簾盒" data-h="500"></td></tr>
        <tr><td>實木房門組更換 (樘)</td><td class="price-text">$6,500</td><td><input type="number" class="p" data-l="房門更換" data-h="6500"></td></tr>
        <tr><td>隱藏門造型製作 (樘)</td><td class="price-text">$12,000</td><td><input type="number" class="p" data-l="隱藏門" data-h="12000"></td></tr>
        <tr><td>電視牆造型板 (坪)</td><td class="price-text">$6,000</td><td><input type="number" class="p" data-l="電視牆造型" data-h="6000"></td></tr>
    </table>

    <!-- 5. 系統櫃與地板 (7項) -->
    <div class="category-header">五、系統櫃與地面工程</div>
    <table>
        <tr><td>系統衣櫃自選色 (尺)</td><td class="price-text">$2,400</td><td><input type="number" class="p" data-l="系統衣櫃" data-h="2400"></td></tr>
        <tr><td>系統鞋櫃/玄關櫃 (尺)</td><td class="price-text">$1,800</td><td><input type="number" class="p" data-l="系統鞋櫃" data-h="1800"></td></tr>
        <tr><td>系統展示/書櫃 (尺)</td><td class="price-text">$2,200</td><td><input type="number" class="p" data-l="系統書櫃" data-h="2200"></td></tr>
        <tr><td>廚具下櫃含檯面 (尺)</td><td class="price-text">$3,200</td><td><input type="number" class="p" data-l="廚具下櫃" data-h="3200"></td></tr>
        <tr><td>SPC石塑防水地板 (坪)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="SPC地板" data-h="2500"></td></tr>
        <tr><td>超耐磨木地板 (坪)</td><td class="price-text">$3,200</td><td><input type="number" class="p" data-l="超耐磨地板" data-h="3200"></td></tr>
        <tr><td>樓梯木踏板鋪設 (階)</td><td class="price-text">$1,500</td><td><input type="number" class="p" data-l="樓梯踏板" data-h="1500"></td></tr>
    </table>

    <!-- 6. 油漆與鋁窗 (7項) -->
    <div class="category-header">六、油漆與鋁窗工程</div>
    <table>
        <tr><td>全屋油漆/水泥漆 (坪)</td><td class="price-text">$800</td><td><input type="number" class="p" data-l="水泥漆工程" data-h="800"></td></tr>
        <tr><td>乳膠漆精緻施工 (坪)</td><td class="price-text">$1,200</td><td><input type="number" class="p" data-l="乳膠漆工程" data-h="1200"></td></tr>
        <tr><td>室內壁紙鋪設 (坪)</td><td class="price-text">$1,200</td><td><input type="number" class="p" data-l="壁紙鋪設" data-h="1200"></td></tr>
        <tr><td>鋁窗換新/氣密窗 (才)</td><td class="price-text">$750</td><td><input type="number" class="p" data-l="鋁窗氣密窗" data-h="750"></td></tr>
        <tr><td>後陽台三合一門 (樘)</td><td class="price-text">$15,000</td><td><input type="number" class="p" data-l="三合一門" data-h="15000"></td></tr>
        <tr><td>紗窗手工更換 (片)</td><td class="price-text">$450</td><td><input type="number" class="p" data-l="紗窗更換" data-h="450"></td></tr>
        <tr><td>矽利康更新工程 (公尺)</td><td class="price-text">$150</td><td><input type="number" class="p" data-l="矽利康更新" data-h="150"></td></tr>
    </table>

    <!-- 7. 其他與清潔 (5項) -->
    <div class="category-header">七、雜項與專業清潔</div>
    <table>
        <tr><td>裝修後細部清潔 (坪)</td><td class="price-text">$650</td><td><input type="number" class="p" data-l="細部清潔" data-h="650"></td></tr>
        <tr><td>粗清/廢棄物搬運 (次)</td><td class="price-text">$2,500</td><td><input type="number" class="p" data-l="粗清服務" data-h="2500"></td></tr>
        <tr><td>不鏽鋼水塔清洗 (座)</td><td class="price-text">$2,000</td><td><input type="number" class="p" data-l="水塔清洗" data-h="2000"></td></tr>
        <tr><td>冷氣內外機清洗 (組)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="冷氣清洗" data-h="3500"></td></tr>
        <tr><td>全屋防水補漏工費 (處)</td><td class="price-text">$3,500</td><td><input type="number" class="p" data-l="防水補漏" data-h="3500"></td></tr>
    </table>

    <div class="sticky-footer">
        <button class="calc-btn" onclick="calculateTotal()">🛠️ 生成即時報價單</button>
    </div>

    <div id="result-area">
        <h2 id="final-addr"></h2>
        <div id="final-list" style="background: #fff; padding: 15px; border-radius: 8px; border: 1px solid #ddd;"></div>
        <div class="total-row" id="final-total"></div>
        
        <p class="note-text">※ 以上為初步估價 ※</p>

        <p style="text-align:center; color:#555; margin-top: 15px;">請加入官方 LINE，我們將安排師傅與您聯繫並確認細節：</p>
        
        <a href="https://line.me" target="_blank" class="line-btn">
             💬 加入官方 LINE 聯繫我們 (@fanyan)
        </a>

        <p style="color: #888; font-size: 0.85em; margin-top: 20px; text-align: center;">
            * 最終報價視材料選用、施工難易度及現場測量為準。<br>
            * 服務區域：全台主要城市（細節請洽詢 LINE 專員）。
        </p>
    </div>
</div>

<script>
function calculateTotal() {
    let items = document.querySelectorAll('.p');
    let total = 0;
    let listHtml = "<ul style='list-style:none; padding:0; margin:0;'>";
    let addr = document.getElementById('user_info').value || "未提供聯絡資訊";
    let hasValue = false;

    items.forEach(i => {
        let qty = parseFloat(i.value) || 0;
        if (qty > 0) {
            hasValue = true;
            let subtotal = qty * parseFloat(i.dataset.h);
            total += subtotal;
            listHtml += `<li style='padding: 8px 0; border-bottom: 1px dashed #eee;'><b>${i.dataset.l}</b> x ${qty} <span style='float:right; color:#1a508b;'>$${subtotal.toLocaleString()}</span></li>`;
        }
    });

    if (!hasValue) {
        alert("請至少填入一個項目的數量唷！");
        return;
    }

    document.getElementById('final-addr').innerText = "📋 報價資訊：" + addr;
    document.getElementById('final-list').innerHTML = listHtml + "</ul>";
    document.getElementById('final-total').innerText = "預估總計：$" + total.toLocaleString();
    document.getElementById('result-area').style.display = "block";
    
    // 平滑滾動到結果區
    window.scrollTo({ top: document.getElementById('result-area').offsetTop - 20, behavior: 'smooth' });
}
</script>

</body>
</html>
