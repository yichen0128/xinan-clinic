<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>信安診所 - 嘉義肝膽腸胃、心臟血管專科與體重管理</title>
    <style>
        /* 基礎樣式與全域字型美化設定 */
        :root {
            --primary-color: #2c7a7b; /* 醫療藍綠色調 */
            --secondary-color: #4a5568;
            --accent-color: #dd6b20; /* 亮眼標示橘色 */
            --bg-color: #f7fafc;
            --text-color: #2d3748;
            --highlight-bg: #e6fffa;
        }

        /* 放大與美化字型 */
        html {
            font-size: 18px; /* 全域基礎字體大小放大 */
            scroll-behavior: smooth; /* 平滑滾動效果 */
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Microsoft JhengHei", "Noto Sans TC", sans-serif;
            line-height: 1.75;
            letter-spacing: 0.3px;
            color: var(--text-color);
            background-color: var(--bg-color);
            margin: 0;
            padding: 0;
            -webkit-font-smoothing: antialiased;
        }

        /* 頁首標題區 */
        header {
            background: linear-gradient(135deg, #2c7a7b 0%, #205a5b 100%);
            color: white;
            text-align: center;
            padding: 3rem 1.5rem;
        }
        header h1 {
            margin: 0;
            font-size: 2.6rem;
            letter-spacing: 2px;
            font-weight: 700;
        }
        header p {
            margin: 0.8rem 0 0 0;
            opacity: 0.95;
            font-size: 1.15rem;
        }

        /* 區塊通用樣式 */
        .container {
            max-width: 980px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }
        
        section {
            background: white;
            padding: 2.2rem;
            margin-bottom: 2rem;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.04);
        }

        h2 {
            color: var(--primary-color);
            border-bottom: 3px solid var(--primary-color);
            padding-bottom: 0.6rem;
            margin-top: 0;
            font-size: 1.6rem;
            letter-spacing: 0.5px;
        }

        /* 醫療團隊樣式 */
        .doctor-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
        }
        @media (max-width: 768px) {
            .doctor-grid { grid-template-columns: 1fr; }
        }
        .doctor-card {
            background: #fafbfd;
            padding: 1.8rem;
            border-left: 5px solid var(--primary-color);
            border-radius: 0 10px 10px 0;
        }
        .doctor-name {
            font-size: 1.45rem;
            font-weight: bold;
            margin-bottom: 0.4rem;
            color: #1a202c;
        }
        .doctor-title {
            color: var(--primary-color);
            font-weight: 700;
            font-size: 1.1rem;
            margin-bottom: 1rem;
        }
        .doctor-specialty {
            margin: 0;
            padding-left: 1.2rem;
            font-size: 1.05rem;
        }
        .doctor-specialty li {
            margin-bottom: 0.4rem;
        }

        /* 點擊跳轉服務卡片按鈕樣式 */
        .service-click-card {
            display: block;
            background: #ffffff;
            border: 2px solid #e2e8f0;
            border-radius: 12px;
            padding: 1.8rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.02);
            transition: all 0.25s ease;
            cursor: pointer;
        }
        .service-click-card:hover {
            border-color: var(--primary-color);
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(44, 122, 123, 0.12);
        }
        .service-click-card h3 {
            color: var(--primary-color);
            margin-top: 0;
            margin-bottom: 0.8rem;
            font-size: 1.4rem;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        .service-click-card p {
            margin: 0;
            color: #4a5568;
            font-size: 1.05rem;
        }
        .badge {
            background-color: var(--highlight-bg);
            color: var(--primary-color);
            font-size: 0.85rem;
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-weight: bold;
            border: 1px solid #b2f5ea;
        }
        .arrow-btn {
            display: inline-block;
            margin-top: 1rem;
            font-weight: bold;
            color: var(--primary-color);
            font-size: 1.05rem;
        }

        /* 詳細內容彈窗 Modal 樣式 */
        .info-modal {
            display: none;
            position: fixed;
            z-index: 9999;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(4px);
            overflow-y: auto;
        }
        .info-modal-content {
            background-color: #ffffff;
            margin: 5% auto;
            padding: 2.2rem;
            border-radius: 14px;
            max-width: 800px;
            width: 88%;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            position: relative;
            animation: fadeIn 0.3s ease;
        }
        .close-info {
            position: absolute;
            right: 20px;
            top: 15px;
            font-size: 32px;
            font-weight: bold;
            color: #a0aec0;
            cursor: pointer;
        }
        .close-info:hover { color: #2d3748; }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* 彈窗圖片樣式 */
        .modal-img {
            width: 100%;
            height: auto;
            border-radius: 8px;
            margin: 1rem 0;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            border: 1px solid #e2e8f0;
            display: block;
        }

        /* 專屬技術與注意事項框 */
        .tech-box {
            background-color: #f0fff4;
            border: 1px solid #c6f6d5;
            border-radius: 8px;
            padding: 1.2rem;
            margin: 1.2rem 0;
            font-size: 1.02rem;
        }
        .tech-box-title {
            font-weight: bold;
            color: #22543d;
            margin-bottom: 0.6rem;
            font-size: 1.1rem;
        }
        .notice-box {
            background-color: #fffaf0;
            border-left: 5px solid #ed8936;
            padding: 1.2rem;
            border-radius: 6px;
            margin-top: 1.2rem;
            font-size: 1.02rem;
        }
        .notice-title {
            font-weight: bold;
            color: #c05621;
            margin-bottom: 0.6rem;
            font-size: 1.15rem;
        }

        /* 瘦瘦針專屬預約門診區塊 */
        .weight-loss-section {
            background: linear-gradient(135deg, #f0fdf4 0%, #e6fffa 100%);
            border: 2px solid #319795;
            border-radius: 14px;
            padding: 2.2rem;
            margin-bottom: 2rem;
        }
        .weight-loss-section h2 {
            color: #234e52;
            border-bottom: 3px solid #319795;
        }
        .step-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1.2rem;
            margin: 1.8rem 0;
            text-align: center;
        }
        @media (max-width: 768px) {
            .step-grid { grid-template-columns: repeat(2, 1fr); }
        }
        .step-item {
            background: white;
            padding: 1.2rem;
            border-radius: 10px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.05);
        }
        .step-number {
            background-color: #319795;
            color: white;
            width: 32px;
            height: 32px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-bottom: 0.6rem;
            font-size: 1.1rem;
        }
        .step-title {
            font-weight: bold;
            color: #2d3748;
            font-size: 1.05rem;
        }

        .cta-container {
            text-align: center;
            margin-top: 1.8rem;
        }
        .btn-cta {
            display: inline-block;
            background-color: #319795;
            color: white;
            text-decoration: none;
            padding: 0.9rem 2.2rem;
            font-size: 1.2rem;
            border-radius: 35px;
            font-weight: bold;
            box-shadow: 0 4px 12px rgba(49, 151, 149, 0.35);
            transition: all 0.2s ease;
        }
        .btn-cta:hover {
            background-color: #2c7a7b;
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(49, 151, 149, 0.45);
        }

        /* 門診時間表樣式 */
        .table-responsive {
            overflow-x: auto;
            margin-top: 1.2rem;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 650px;
            text-align: center;
            font-size: 1.05rem;
        }
        th, td {
            border: 1px solid #e2e8f0;
            padding: 0.85rem;
        }
        th {
            background-color: #edf2f7;
            color: #2d3748;
            font-size: 1.1rem;
        }
        tr:nth-child(even) {
            background-color: #f7fafc;
        }
        .status-open {
            color: var(--primary-color);
            font-weight: bold;
            font-size: 1.2rem;
        }
        .status-close {
            color: #a0aec0;
        }

        /* 聯絡資訊樣式 */
        .info-list {
            list-style: none;
            padding: 0;
            font-size: 1.1rem;
        }
        .info-list li {
            margin-bottom: 1rem;
        }
        .info-label {
            font-weight: bold;
            color: var(--primary-color);
            display: inline-block;
            width: 105px;
        }
        .btn-call {
            display: inline-block;
            background-color: var(--primary-color);
            color: white;
            text-decoration: none;
            padding: 0.6rem 1.2rem;
            border-radius: 6px;
            margin-top: 0.6rem;
            font-weight: bold;
            font-size: 1.05rem;
        }

        footer {
            text-align: center;
            padding: 1.8rem;
            color: #a0aec0;
            font-size: 1rem;
            background-color: #1a202c;
            margin-top: 4rem;
        }
    </style>
</head>
<body>

    <!-- 頁首區塊 -->
    <header>
        <h1>信安診所</h1>
        <p>信心、安全、專業｜肝膽腸胃、心臟血管專科與體重管理團隊</p>
    </header>

    <div class="container">
        
        <!-- 關於診所 -->
        <section id="about">
            <h2>關於信安診所</h2>
            <p>信安診所座落於嘉義市中心，由前醫學中心主治醫師團隊親自坐鎮。我們秉持「信心、安全、專業」的理念，結合肝膽腸胃、心臟血管兩大專科與現代醫學體重管理，引進日本最新頂級 Fujifilm ELUXEO 6000 高解析度內視鏡系統與高解析度腹部超音波等醫療設備，為在地鄉親提供最精準的診斷與最溫馨的照護。</p>
        </section>

        <!-- 醫療團隊 -->
        <section id="team">
            <h2>醫療團隊介紹</h2>
            <div class="doctor-grid">
                <!-- 醫師 1 -->
                <div class="doctor-card">
                    <div class="doctor-name">陳奕成 院長</div>
                    <div class="doctor-title">肝膽腸胃專科醫師</div>
                    <p><strong>主治專長：</strong></p>
                    <ul class="doctor-specialty">
                        <li>Fujifilm E-6000 早期癌與息肉精準篩檢</li>
                        <li>無痛胃鏡與大腸鏡檢查、大腸息肉即時切除</li>
                        <li>腹部超音波（脂肪肝、膽結石、肝臟病變）</li>
                        <li>胃食道逆流、幽門桿菌根除與潰瘍治療</li>
                        <li>腸泌素機轉減重與體重管理門診</li>
                    </ul>
                </div>
                <!-- 醫師 2 -->
                <div class="doctor-card">
                    <div class="doctor-name">陳浩光 醫師</div>
                    <div class="doctor-title">心臟血管專科醫師</div>
                    <p><strong>主治專長：</strong></p>
                    <ul class="doctor-specialty">
                        <li>三高慢性病（糖尿病、高血壓、高血脂）</li>
                        <li>心血管疾病（心絞痛、心律不整）</li>
                        <li>代謝症候群與健康評估</li>
                        <li>骨關節炎治療</li>
                        <li>一般感冒與常見內科疾病</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- 特色醫療服務 (點擊彈窗展開卡片) -->
        <section id="services">
            <h2>特色醫療服務與檢查</h2>
            <p style="margin-bottom: 1.5rem; color: #718096;">點擊下方卡片即可展開完整的詳細介紹與說明：</p>
            
            <!-- 卡片 1：腸胃鏡與超音波 -->
            <div class="service-click-card" onclick="openModal('endoModal')">
                <h3>
                    <span>🔍 旗艦級 Fujifilm ELUXEO 6000 無痛腸胃鏡與腹部超音波</span>
                    <span class="badge">頂級醫學中心設備</span>
                </h3>
                <p>引進日本最新 Fujifilm E-6000 內視鏡系統，具備 LCI/BLI 先進光學顯影技術，提供精準息肉篩檢與無痛腸胃鏡檢查服務。</p>
                <div class="arrow-btn">點擊閱讀完整內容與注意事項 ➔</div>
            </div>

            <!-- 卡片 2：瘦瘦針 -->
            <div class="service-click-card" onclick="openModal('weightModal')">
                <h3>
                    <span>💉 注射式腸泌素體重管理與代謝調節</span>
                    <span class="badge">科學減重</span>
                </h3>
                <p>衛福部核准之瘦瘦針（GLP-1 受體促效劑），由專科醫師評估，透過調控食慾與延緩胃排空達到安全有效的體重管理。</p>
                <div class="arrow-btn">點擊閱讀詳細作用機轉說明 ➔</div>
            </div>
        </section>

        <!-- 體重管理預約門診專屬區塊 -->
        <section id="weight-loss-appointment" class="weight-loss-section">
            <h2>✨ 體重管理與代謝門診 - 專屬預約諮詢</h2>
            <p>想要開啟科學減重之旅？信安診所提供一站式的客製化體重管理服務，由肝膽腸胃專科醫師親自把關，讓您安心瘦身、健康不打折！</p>
            
            <div class="step-grid">
                <div class="step-item">
                    <div class="step-number">1</div>
                    <div class="step-title">預約專屬諮詢</div>
                    <p style="font-size:0.9rem; color: #718096; margin-top:0.3rem;">電話或現場預約門診時段</p>
                </div>
                <div class="step-item">
                    <div class="step-number">2</div>
                    <div class="step-title">醫師評估與檢測</div>
                    <p style="font-size:0.9rem; color: #718096; margin-top:0.3rem;">評估 BMI、慢性病史與抽血檢測</p>
                </div>
                <div class="step-item">
                    <div class="step-number">3</div>
                    <div class="step-title">訂製個人化處方</div>
                    <p style="font-size:0.9rem; color: #718096; margin-top:0.3rem;">依體質調配腸泌素機轉方案</p>
                </div>
                <div class="step-item">
                    <div class="step-number">4</div>
                    <div class="step-title">施打衛教與追蹤</div>
                    <p style="font-size:0.9rem; color: #718096; margin-top:0.3rem;">專業護理師注射教學與定期回診</p>
                </div>
            </div>

            <div class="cta-container">
                <p style="font-weight: bold; color: #2c7a7b; margin-bottom: 0.9rem; font-size: 1.15rem;">跨出健康減重第一步！歡迎來電預約專屬評估時間</p>
                <a href="tel:05-27857681" class="btn-cta">📞 立即撥打預約專線 (05) 278-57681</a>
            </div>
        </section>

        <!-- 門診時間表 -->
        <section id="timetable">
            <h2>門診時間表</h2>
            <div class="table-responsive">
                <table>
                    <thead>
                        <tr>
                            <th>時段</th>
                            <th>星期一</th>
                            <th>星期二</th>
                            <th>星期三</th>
                            <th>星期四</th>
                            <th>星期五</th>
                            <th>星期六</th>
                            <th>星期日</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>早班</strong><br>08:30–12:00</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-close">休診</td>
                        </tr>
                        <tr>
                            <td><strong>午班</strong><br>16:00–18:00</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-close">休診</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-close">休診</td>
                        </tr>
                        <tr>
                            <td><strong>晚班</strong><br>19:00–21:00</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-open">●</td>
                            <td class="status-close">休診</td>
                            <td class="status-close">休診</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- 聯絡與交通資訊 -->
        <section id="contact">
            <h2>聯絡與交通資訊</h2>
            <ul class="info-list">
                <li><span class="info-label">診所地址：</span>嘉義市民權路278號</li>
                <li>
                    <span class="info-label">聯絡電話：</span>05-27857681 
                    <br><a href="tel:05-27857681" class="btn-call">📞 點擊撥打電話諮詢／預約</a>
                </li>
                <li><span class="info-label">交通指引：</span>鄰近嘉義中央廣場與地方法院舊址，周邊設有路邊停車格與收費停車場，方便您就醫停車。</li>
            </ul>
        </section>

    </div>

    <!-- 彈窗 1：腸胃鏡詳細內容 (包含新加入的圖片) -->
        <div id="endoModal" class="info-modal">
        <div class="info-modal-content">
            <span class="close-info" onclick="closeModal('endoModal')">&times;</span>
            <h2 style="margin-top:0;">🔍 旗艦級 Fujifilm ELUXEO 6000 無痛腸胃鏡與腹部超音波</h2>
            <p>腸胃道與肝膽胰臟疾病早期往往無明顯症狀，診所引進日本最新 <strong>Fujifilm ELUXEO 6000 (E-6000)</strong> 頂級內視鏡系統，由專科醫師親自操作：</p>
            
            <!-- 如果您使用本地圖片檔，請確認檔名與這行一致；或改用相對／絕對路徑 -->
            <img src="fuji-endo.jpg" > 
            <div class="tech-box">
                <div class="tech-box-title">🌟 Fujifilm ELUXEO 6000 核心技術：</div>
                <ul>
                    <li><strong>LCI (Linked Color Imaging) 聯動彩色影像：</strong>大幅提升黏膜顏色對比度，精準捕捉微小發炎、幽門桿菌與早期癌變。</li>
                    <li><strong>BLI (Blue Light Imaging) 藍光成像：</strong>突出微血管與坑紋結構，協助醫師即時判斷息肉性質。</li>
                    <li><strong>Multi-Light 4-LED 多光源：</strong>提供高亮度高解析視野，顯著降低盲點。</li>
                </ul>
            </div>

            <div class="notice-box">
                <div class="notice-title">⚠️ 腸胃鏡檢查事前注意事項</div>
                <ul style="margin:0; padding-left:1.2rem;">
                    <li><strong>低渣飲食準備：</strong>大腸鏡檢查前 2～3 天請配合執行低渣飲食並服用瀉劑。</li>
                    <li><strong>禁食禁水：</strong>受檢前一晚午夜 12 點起須嚴格禁食禁水。</li>
                    <li><strong>慢性病用藥：</strong>有服用抗凝血劑或血糖藥者請預先告知醫師。</li>
                    <li><strong>麻醉陪同：</strong>無痛檢查當日請務必由一名成年家屬陪同。</li>
                </ul>
            </div>
        </div>
    </div>
   

    <!-- 彈窗 2：瘦瘦針詳細內容 -->
    <div id="weightModal" class="info-modal">
        <div class="info-modal-content">
            <span class="close-info" onclick="closeModal('weightModal')">&times;</span>
            <h2 style="margin-top:0;">💉 注射式腸泌素體重管理與代謝調節</h2>
            <p>肥胖是多種慢性疾病與代謝症候群的關鍵誘因。信安診所引進衛生福利部核准之「瘦瘦針（GLP-1 受體促效劑）」，透過仿照人體天然腸道荷爾蒙運作，以科學原理輔助體重管理：</p>
            
            <ul>
                <li><strong>腦部調控增加飽足感：</strong>作用於大腦中樞，減少飢餓感、降低食慾。</li>
                <li><strong>胃部延緩胃排空：</strong>減緩胃部食物排空速度，有效延長飽足感。</li>
                <li><strong>胰臟調節血糖代謝：</strong>刺激胰島素分泌，達到穩定血糖的作用。</li>
                <li><strong>長期健康效益：</strong>幫助體重減輕與減少脂肪組織，改善代謝健康。</li>
            </ul>
        </div>
    </div>

    <!-- 頁尾 -->
    <footer>
        <p>&copy; 2026 信安診所 版權所有｜信心・安全・專業</p>
    </footer>

    <!-- JavaScript 彈窗控制邏輯 -->
    <script>
        function openModal(id) {
            document.getElementById(id).style.display = "block";
            document.body.style.overflow = "hidden"; // 禁止背景滾動
        }

        function closeModal(id) {
            document.getElementById(id).style.display = "none";
            document.body.style.overflow = "auto"; // 恢復背景滾動
        }

        // 點擊 Modal 外部空白處自動關閉
        window.onclick = function(event) {
            if (event.target.classList.contains('info-modal')) {
                event.target.style.display = "none";
                document.body.style.overflow = "auto";
            }
        }
    </script>

</body>
</html>
