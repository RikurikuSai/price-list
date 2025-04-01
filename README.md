<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>動画制作ご依頼フォーム - リアルタイム見積もり</title>
    <style>
        :root {
            --primary-color: #1868b7; /* より鮮やかな青 */
            --secondary-color: #003d7a; /* ダークブルー */
            --accent-color: #5dadf7; /* ライトブルー */
            --light-bg: #ebf5ff; /* 青みがかった薄い背景色 */
            --dark-text: #1a3451; /* 青みがかった濃いテキスト色 */
            --light-text: #6a85a0; /* 青みがかった薄いテキスト色 */
            --border-color: #cbe3ff; /* 青みがかったボーダー色 */
            --highlight-color: #ffb547; /* アクセント（オレンジ）*/
            --section-space: 40px;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "SF Pro Text", "SF Pro Icons", "Helvetica Neue", Helvetica, Arial, sans-serif;
        }
        
        body {
            background-color: #f8faff; /* 薄い青色の背景 */
            color: var(--dark-text);
            line-height: 1.5;
            font-size: 16px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            text-align: center;
            padding: 40px 0;
            background: linear-gradient(135deg, var(--secondary-color), var(--primary-color));
            border-radius: 10px;
            margin-bottom: 30px;
            color: white;
        }
        
        h1 {
            font-size: 36px;
            font-weight: 600;
            margin-bottom: 15px;
            color: white;
            text-shadow: 0 1px 2px rgba(0,0,0,0.2);
        }
        
        .subtitle {
            font-size: 18px;
            color: rgba(255, 255, 255, 0.9);
            max-width: 600px;
            margin: 0 auto 40px;
        }
        
        .form-container {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            margin-bottom: var(--section-space);
        }
        
        .form-section {
            flex: 1 1 600px;
            background-color: white;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(24, 104, 183, 0.08);
            padding: 20px;
            max-height: 800px; /* スクロールできるよう高さを制限 */
            overflow-y: auto;
        }
        
        .price-section {
            flex: 1 1 300px;
            position: sticky;
            top: 20px;
            align-self: flex-start;
            height: fit-content; /* 内容に合わせて高さを調整 */
        }
        
        .section {
            margin-bottom: var(--section-space);
            padding-bottom: var(--section-space);
            border-bottom: 1px solid var(--border-color);
        }
        
        .section:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }
        
        h2 {
            font-size: 24px;
            font-weight: 600;
            margin-bottom: 20px;
            color: var(--primary-color);
            border-left: 4px solid var(--accent-color);
            padding-left: 10px;
        }
        
        h3 {
            font-size: 20px;
            font-weight: 500;
            margin-bottom: 15px;
            color: var(--primary-color);
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        label {
            display: block;
            font-size: 16px;
            font-weight: 500;
            margin-bottom: 8px;
            color: var(--secondary-color);
        }
        
        .helper-text {
            display: block;
            font-size: 14px;
            color: var(--light-text);
            margin-bottom: 8px;
        }
        
        input[type="text"],
        input[type="email"],
        input[type="tel"],
        select,
        textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
            background-color: #f8faff;
        }
        
        input:focus,
        select:focus,
        textarea:focus {
            outline: none;
            border-color: var(--accent-color);
            box-shadow: 0 0 0 2px rgba(93, 173, 247, 0.2);
        }
        
        .radio-group,
        .checkbox-group {
            margin-top: 10px;
        }
        
        .radio-item,
        .checkbox-item {
            position: relative;
            padding: 15px;
            margin-bottom: 10px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            background-color: white;
        }
        
        .radio-item:hover,
        .checkbox-item:hover {
            background-color: rgba(93, 173, 247, 0.05);
            border-color: rgba(93, 173, 247, 0.5);
        }
        
        .radio-item.selected,
        .checkbox-item.selected {
            background-color: rgba(93, 173, 247, 0.1);
            border-color: var(--primary-color);
        }
        
        .checkbox-title {
            font-weight: 500;
            display: block;
            padding-left: 30px;
            color: var(--dark-text);
        }
        
        .option-desc {
            display: block;
            font-size: 14px;
            color: var(--light-text);
            margin-top: 5px;
            padding-left: 30px;
        }
        
        .custom-radio,
        .custom-checkbox {
            position: absolute;
            left: 15px;
            top: 15px;
            width: 20px;
            height: 20px;
            border: 2px solid var(--border-color);
            border-radius: 50%;
            transition: all 0.3s;
        }
        
        .custom-checkbox {
            border-radius: 4px;
        }
        
        .radio-item.selected .custom-radio {
            border-color: var(--primary-color);
            background-color: white;
        }
        
        .radio-item.selected .custom-radio::after {
            content: "";
            position: absolute;
            top: 4px;
            left: 4px;
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background-color: var(--primary-color);
        }
        
        .checkbox-item.selected .custom-checkbox {
            border-color: var(--primary-color);
            background-color: var(--primary-color);
        }
        
        .checkbox-item.selected .custom-checkbox::after {
            content: "✓";
            position: absolute;
            top: -5px;
            left: 3px;
            color: white;
            font-size: 16px;
        }
        
        .tab-container {
            display: flex;
            margin-bottom: 30px;
            border-bottom: 1px solid var(--border-color);
            background-color: white;
            border-radius: 12px 12px 0 0;
            padding: 0 10px;
            box-shadow: 0 2px 8px rgba(24, 104, 183, 0.08);
        }
        
        .tab {
            padding: 15px 25px;
            cursor: pointer;
            font-weight: 500;
            position: relative;
            color: var(--light-text);
            transition: all 0.3s;
        }
        
        .tab:hover {
            color: var(--primary-color);
        }
        
        .tab.active {
            color: var(--primary-color);
            font-weight: 600;
        }
        
        .tab.active::after {
            content: "";
            position: absolute;
            bottom: -1px;
            left: 0;
            width: 100%;
            height: 3px;
            background-color: var(--primary-color);
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .price-card {
            background: linear-gradient(135deg, #ffffff, var(--light-bg));
            border-radius: 12px;
            padding: 25px;
            box-shadow: 0 4px 15px rgba(24, 104, 183, 0.1);
            border: 1px solid var(--border-color);
            position: sticky;
            top: 20px;
        }
        
        .price-card h3 {
            text-align: center;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }
        
        .price-row {
            display: flex;
            justify-content: space-between;
            padding: 12px 0;
            border-bottom: 1px solid var(--border-color);
        }
        
        .price-row:last-of-type {
            border-bottom: none;
            margin-top: 20px;
            padding-top: 15px;
            font-weight: 600;
            font-size: 18px;
            color: var(--secondary-color);
        }
        
        .price-label {
            max-width: 70%;
        }
        
        .price-value {
            font-weight: 500;
            color: var(--primary-color);
        }
        
        .discount {
            color: #29ad5d;
        }
        
        .submit-btn {
            display: block;
            width: 100%;
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            border: none;
            border-radius: 8px;
            padding: 15px;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            margin-top: 30px;
            transition: all 0.3s;
            text-shadow: 0 1px 1px rgba(0,0,0,0.2);
            box-shadow: 0 4px 6px rgba(0, 61, 122, 0.2);
        }
        
        .submit-btn:hover {
            background: linear-gradient(135deg, #1c73c7, #004a94);
            box-shadow: 0 6px 12px rgba(0, 61, 122, 0.3);
            transform: translateY(-2px);
        }
        
        .range-container {
            padding: 10px 0;
        }
        
        .range-slider {
            width: 100%;
            -webkit-appearance: none;
            height: 6px;
            border-radius: 3px;
            background: var(--border-color);
            outline: none;
            margin: 15px 0;
        }
        
        .range-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--primary-color);
            cursor: pointer;
            box-shadow: 0 1px 3px rgba(0,0,0,0.3);
        }
        
        .range-slider::-moz-range-thumb {
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--primary-color);
            cursor: pointer;
            border: none;
            box-shadow: 0 1px 3px rgba(0,0,0,0.3);
        }
        
        .range-value {
            text-align: center;
            font-weight: 500;
            font-size: 18px;
            margin-bottom: 10px;
            color: var(--primary-color);
        }
        
        .range-labels {
            display: flex;
            justify-content: space-between;
            font-size: 14px;
            color: var(--light-text);
        }
        
        .special-offer {
            background: linear-gradient(to right, #fff8ef, #ffeed0);
            border: 1px dashed var(--highlight-color);
            border-radius: 8px;
            padding: 15px;
            margin-top: 20px;
            text-align: center;
        }
        
        .special-offer h4 {
            color: #e67600;
            margin-bottom: 10px;
        }
        
        @media (max-width: 768px) {
            .form-container {
                flex-direction: column;
            }
            
            .price-section {
                position: static;
                order: -1;
                margin-bottom: 30px;
            }
            
            .form-section {
                max-height: none;
                overflow-y: visible;
            }
            
            h1 {
                font-size: 28px;
            }
            
            h2 {
                font-size: 22px;
            }
            
            h3 {
                font-size: 18px;
            }
            
            .tab {
                padding: 12px 15px;
                font-size: 15px;
            }
        }
        
        /* 料金表のスタイル追加 */
        .price-table-container {
            background-color: white;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(24, 104, 183, 0.08);
            margin-bottom: 20px;
            overflow: hidden;
        }
        
        .price-table-container h3 {
            font-size: 18px;
            padding: 15px;
            margin: 0;
            border-bottom: 1px solid var(--border-color);
            background-color: var(--light-bg);
        }
        
        .price-table {
            width: 100%;
            border-collapse: collapse;
        }
        
        .price-table th, .price-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid var(--border-color);
        }
        
        .price-table th {
            background-color: var(--light-bg);
            font-weight: 500;
            color: var(--secondary-color);
        }
        
        .price-table tr:nth-child(even) {
            background-color: #f8faff;
        }
        
        .price-table tr:hover {
            background-color: rgba(93, 173, 247, 0.05);
        }
        
        .price-tables-wrapper {
            max-height: 400px;
            overflow-y: auto;
            padding: 0 15px;
        }
        
        .current-estimate {
            background-color: var(--light-bg);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
        }
        
        .current-estimate-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px;
        }
        
        .current-estimate-total {
            grid-column: span 2;
            font-size: 18px;
            font-weight: 600;
            text-align: center;
            padding: 10px 0;
            margin-top: 10px;
            border-top: 1px solid var(--border-color);
            color: var(--primary-color);
        }
    </style>
    <!-- React と ReactDOM の読み込み -->
    <script src="https://unpkg.com/react@17/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>動画制作ご依頼フォーム</h1>
            <p class="subtitle">ご希望に合わせてチェックするだけで見積もりが自動計算されます。<br>専門知識がなくても、簡単に動画制作の依頼ができます。</p>
        </div>
        
        <div class="tab-container">
            <div class="tab active" onclick="showTab('youtube')">YouTube動画</div>
            <div class="tab" onclick="showTab('instagram')">Instagram・TikTok</div>
            <div class="tab" onclick="showTab('manual')">マニュアル動画</div>
            <div class="tab" onclick="showTab('company')">会社紹介動画</div>
        </div>
        
        <div class="form-container">
            <div class="form-section">
                <!-- YouTube動画タブ -->
                <div id="youtube" class="tab-content active">
                    <div class="section">
                        <h2>どんな動画を作りたいですか？</h2>
                        
                        <div class="form-group">
                            <label>動画の目的</label>
                            <span class="helper-text">どのような目的で動画を制作されますか？</span>
                            <div class="radio-group" id="youtube-purpose">
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="product">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">商品・サービスのご紹介</span>
                                    <span class="option-desc">自社の商品やサービスの特徴をわかりやすく説明する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="howto">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">使い方・ハウツー</span>
                                    <span class="option-desc">商品の使い方や知識を解説する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="interview">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">インタビュー・対談</span>
                                    <span class="option-desc">社員や専門家へのインタビューを中心とした動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="event">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">イベント・セミナー</span>
                                    <span class="option-desc">イベントやセミナーの様子を記録・配信する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="vlog">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">Vlog・日常記録</span>
                                    <span class="option-desc">日常業務や活動の様子を記録する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="educational">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">教育・研修</span>
                                    <span class="option-desc">従業員教育や顧客向け研修用の動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="testimonial">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様の声・体験談</span>
                                    <span class="option-desc">顧客の体験談やレビューを紹介する動画</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>動画の長さ</label>
                            <span class="helper-text">動画の長さはどのくらいをお考えですか？</span>
                            <div class="range-container">
                                <div class="range-value" id="youtube-length-value">5分</div>
                                <input type="range" min="1" max="20" value="5" class="range-slider" id="youtube-length" oninput="updateRangeValue('youtube-length')">
                                <div class="range-labels">
                                    <span>1分</span>
                                    <span>5分</span>
                                    <span>10分</span>
                                    <span>15分</span>
                                    <span>20分</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>動画に入れたい要素</h2>
                        
                        <div class="form-group">
                            <label>基本の構成要素</label>
                            <span class="helper-text">動画に含めたい基本的な要素をお選びください</span>
                            <div class="checkbox-group" id="youtube-basic-elements">
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'youtube-basic-elements')" data-value="opening">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">オープニング映像＋ダイジェスト</span>
                                    <span class="option-desc">動画冒頭に会社名・タイトルとダイジェストを表示（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'youtube-basic-elements')" data-value="ending">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">エンディング映像</span>
                                    <span class="option-desc">動画の最後に問い合わせ先などを表示（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'youtube-basic-elements')" data-value="bgm">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">BGM（音楽）</span>
                                    <span class="option-desc">動画全体に流れる背景音楽（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'youtube-basic-elements')" data-value="captions">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">テロップ（文字）</span>
                                    <span class="option-desc">話している内容や補足を文字で表示（標準装備）</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>追加したい要素</label>
                            <span class="helper-text">動画をより充実させるオプション要素をお選びください</span>
                            <div class="checkbox-group" id="youtube-additional-elements">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-additional-elements')" data-value="narration" data-price="15000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">プロナレーション</span>
                                    <span class="option-desc">プロのナレーターによる音声案内（+15,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-additional-elements')" data-value="ai-narration" data-price="10000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">AI音声ナレーション</span>
                                    <span class="option-desc">AI技術による自然な音声読み上げ（+10,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-additional-elements')" data-value="animation" data-price="20000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">アニメーション・図解</span>
                                    <span class="option-desc">内容を視覚的に説明するアニメーション（+20,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-additional-elements')" data-value="subtitles" data-price="10000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">字幕（日本語）</span>
                                    <span class="option-desc">音声内容をテキストで画面下部に表示（+10,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-additional-elements')" data-value="foreign-subtitles" data-price="15000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">外国語字幕</span>
                                    <span class="option-desc">英語・中国語など外国語の字幕（+15,000円/言語）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-additional-elements')" data-value="thumbnail" data-price="6000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">サムネイル画像</span>
                                    <span class="option-desc">再生前に表示される画像のデザイン（+6,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>素材について</h2>
                        
                        <div class="form-group">
                            <label>素材の準備方法</label>
                            <span class="helper-text">撮影素材や原稿などはどのように準備しますか？</span>
                            <div class="radio-group" id="youtube-materials">
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-materials')" data-value="client">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様がご用意</span>
                                    <span class="option-desc">写真・動画・原稿などをお客様側でご準備いただきます</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-materials')" data-value="mixed">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">一部お客様・一部制作会社</span>
                                    <span class="option-desc">基本素材はお客様が用意し、足りない部分は当社で補完します</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-materials')" data-value="producer" data-price="15000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">制作会社におまかせ</span>
                                    <span class="option-desc">素材探しからすべて当社が行います（+15,000円）</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>台本制作</label>
                            <span class="helper-text">動画の台本（シナリオ）はどうしますか？</span>
                            <div class="radio-group" id="youtube-script">
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-script')" data-value="client">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様がご用意</span>
                                    <span class="option-desc">台本はお客様側でご準備いただきます</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-script')" data-value="outline" data-price="10000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様の構想をもとに作成</span>
                                    <span class="option-desc">お客様の要望をもとに台本を作成します（+10,000円）</span>
                                    </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-script')" data-value="full" data-price="20000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">完全におまかせ</span>
                                    <span class="option-desc">打ち合わせ内容をもとにゼロから台本を作成（+20,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>修正・納品について</h2>
                        
                        <div class="form-group">
                            <label>修正回数</label>
                            <span class="helper-text">完成までに内容の修正を何回希望されますか？</span>
                            <div class="radio-group" id="youtube-revisions">
                                <div class="radio-item selected" onclick="selectRadio(this, 'youtube-revisions')" data-value="2">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">2回まで</span>
                                    <span class="option-desc">標準プラン（基本料金に含まれています）</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-revisions')" data-value="3" data-price="5000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">3回まで</span>
                                    <span class="option-desc">少し多めに修正したい方向け（+5,000円）</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'youtube-revisions')" data-value="5" data-price="10000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">5回まで</span>
                                    <span class="option-desc">念入りに修正したい方向け（+10,000円）</span>
                                </div>
                            </div></div>
                        
                        <div class="form-group">
                            <label>アップロードサポート</label>
                            <span class="helper-text">YouTubeへのアップロードをサポートしますか？</span>
                            <div class="checkbox-group" id="youtube-upload">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-upload')" data-value="support" data-price="5000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">アップロードサポート</span>
                                    <span class="option-desc">YouTubeへの投稿をお手伝いします（+5,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>特典オプション</h2>
                        
                        <div class="form-group">
                            <label>割引オプション</label>
                            <span class="helper-text">お得な割引をご利用いただけます</span>
                            <div class="checkbox-group" id="youtube-discount">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-discount')" data-value="first-time" data-discount="0.15">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">初回ご利用割引</span>
                                    <span class="option-desc">初めてのお客様は15%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-discount')" data-value="multiple" data-discount="0.1">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">複数本割引</span>
                                    <span class="option-desc">3本以上のご注文で10%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'youtube-discount', showContractOptions)" data-value="contract">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">継続契約割引</span>
                                    <span class="option-desc">定期的に動画制作をご検討の方向け</span>
                                </div>
                            </div>
                        </div>
                        
                        <!-- 継続契約オプション（初期状態では非表示） -->
                        <div class="form-group" id="contract-options" style="display: none;">
                            <label>継続契約の詳細</label>
                            <span class="helper-text">継続期間によって割引率が変わります</span>
                            <div class="radio-group" id="contract-duration">
                                <div class="radio-item" onclick="selectRadio(this, 'contract-duration')" data-value="3" data-discount="0.05">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">3ヶ月契約</span>
                                    <span class="option-desc">5%割引</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'contract-duration')" data-value="6" data-discount="0.1">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">6ヶ月契約</span>
                                    <span class="option-desc">10%割引</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'contract-duration')" data-value="12" data-discount="0.15">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">12ヶ月契約</span>
                                    <span class="option-desc">15%割引</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Instagram・TikTok動画タブ -->
                <div id="instagram" class="tab-content">
                    <div class="section">
                        <h2>Instagram・TikTok用動画制作（1分以内）</h2>
                        
                        <div class="form-group">
                            <label>動画の目的</label>
                            <span class="helper-text">どのような目的で動画を制作されますか？</span>
                            <div class="radio-group" id="instagram-purpose">
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-purpose')" data-value="product">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">商品・サービスのご紹介</span>
                                    <span class="option-desc">自社の商品やサービスを短くアピールする動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-purpose')" data-value="branding">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">ブランディング</span>
                                    <span class="option-desc">企業・ブランドのイメージ向上のための動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-purpose')" data-value="trend">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">トレンド活用</span>
                                    <span class="option-desc">流行のスタイル・音楽を取り入れた動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-purpose')" data-value="campaign">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">キャンペーン告知</span>
                                    <span class="option-desc">セールやイベントの告知動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-purpose')" data-value="behind">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">舞台裏・日常</span>
                                    <span class="option-desc">会社や製品の舞台裏を見せる動画</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>動画の長さ</label>
                            <span class="helper-text">動画の長さはどのくらいをお考えですか？</span>
                            <div class="range-container">
                                <div class="range-value" id="instagram-length-value">30秒</div>
                                <input type="range" min="10" max="60" value="30" class="range-slider" id="instagram-length" oninput="updateRangeValue('instagram-length', '秒')">
                                <div class="range-labels">
                                    <span>10秒</span>
                                    <span>30秒</span>
                                    <span>60秒</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>動画に入れたい要素</h2>
                        
                        <div class="form-group">
                            <label>基本の構成要素</label>
                            <span class="helper-text">動画に含めたい基本的な要素をお選びください</span>
                            <div class="checkbox-group" id="instagram-basic-elements">
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'instagram-basic-elements')" data-value="captions">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">テロップ（文字）</span>
                                    <span class="option-desc">重要なメッセージを文字で表示（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'instagram-basic-elements')" data-value="bgm">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">BGM（音楽）</span>
                                    <span class="option-desc">トレンドや商品イメージに合った音楽（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'instagram-basic-elements')" data-value="effects">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">トランジション効果</span>
                                    <span class="option-desc">場面転換時の視覚効果（標準装備）</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>追加したい要素</label>
                            <span class="helper-text">動画をより効果的にするオプション要素をお選びください</span>
                            <div class="checkbox-group" id="instagram-additional-elements">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'instagram-additional-elements')" data-value="beauty" data-price="5000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">美肌補正</span>
                                    <span class="option-desc">人物の肌をきれいに見せる補正処理（+5,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'instagram-additional-elements')" data-value="animation" data-price="15000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">簡易アニメーション</span>
                                    <span class="option-desc">ロゴやテキストのアニメーション効果（+15,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'instagram-additional-elements')" data-value="subtitles" data-price="8000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">字幕（日本語）</span>
                                    <span class="option-desc">音声内容をテキストで表示（+8,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'instagram-additional-elements')" data-value="cta" data-price="5000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">行動喚起画面</span>
                                    <span class="option-desc">「詳細はプロフィールから」などの案内（+5,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>素材について</h2>
                        
                        <div class="form-group">
                            <label>素材の準備方法</label>
                            <span class="helper-text">撮影素材などはどのように準備しますか？</span>
                            <div class="radio-group" id="instagram-materials">
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-materials')" data-value="client">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様がご用意</span>
                                    <span class="option-desc">写真・動画などをお客様側でご準備いただきます</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-materials')" data-value="mixed">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">一部お客様・一部制作会社</span>
                                    <span class="option-desc">基本素材はお客様が用意し、足りない部分は当社で補完します</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-materials')" data-value="producer" data-price="10000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">制作会社におまかせ</span>
                                    <span class="option-desc">素材探しからすべて当社が行います（+10,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>修正・納品について</h2>
                        
                        <div class="form-group">
                            <label>修正回数</label>
                            <span class="helper-text">完成までに内容の修正を何回希望されますか？</span>
                            <div class="radio-group" id="instagram-revisions">
                                <div class="radio-item selected" onclick="selectRadio(this, 'instagram-revisions')" data-value="2">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">2回まで</span>
                                    <span class="option-desc">標準プラン（基本料金に含まれています）</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-revisions')" data-value="3" data-price="3000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">3回まで</span>
                                    <span class="option-desc">少し多めに修正したい方向け（+3,000円）</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'instagram-revisions')" data-value="5" data-price="8000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">5回まで</span>
                                    <span class="option-desc">念入りに修正したい方向け（+8,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div><div class="section">
                        <h2>特典オプション</h2>
                        
                        <div class="form-group">
                            <label>割引オプション</label>
                            <span class="helper-text">お得な割引をご利用いただけます</span>
                            <div class="checkbox-group" id="instagram-discount">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'instagram-discount')" data-value="first-time" data-discount="0.15">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">初回ご利用割引</span>
                                    <span class="option-desc">初めてのお客様は15%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'instagram-discount')" data-value="multiple" data-discount="0.1">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">複数本割引</span>
                                    <span class="option-desc">3本以上のご注文で10%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'instagram-discount', showContractOptions)" data-value="contract">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">継続契約割引</span>
                                    <span class="option-desc">定期的に動画制作をご検討の方向け</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- マニュアル動画タブ -->
                <div id="manual" class="tab-content">
                    <div class="section">
                        <h2>マニュアル動画制作</h2>
                        
                        <div class="form-group">
                            <label>動画の種類</label>
                            <span class="helper-text">どのような種類のマニュアル動画が必要ですか？</span>
                            <div class="radio-group" id="manual-type">
                                <div class="radio-item" onclick="selectRadio(this, 'manual-type')" data-value="product">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">製品の使い方</span>
                                    <span class="option-desc">商品やサービスの使用方法を解説する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-type')" data-value="software">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">ソフトウェア操作</span>
                                    <span class="option-desc">アプリやシステムの操作方法を解説する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-type')" data-value="process">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">業務手順</span>
                                    <span class="option-desc">社内作業や手続きの手順を解説する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-type')" data-value="safety">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">安全・注意事項</span>
                                    <span class="option-desc">安全対策や注意点を説明する動画</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-type')" data-value="training">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">研修・教育</span>
                                    <span class="option-desc">新人教育や技術研修のための動画</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>動画の長さ</label>
                            <span class="helper-text">動画の長さはどのくらいをお考えですか？</span>
                            <div class="range-container">
                                <div class="range-value" id="manual-length-value">5分</div>
                                <input type="range" min="1" max="15" value="5" class="range-slider" id="manual-length" oninput="updateRangeValue('manual-length')">
                                <div class="range-labels">
                                    <span>1分</span>
                                    <span>5分</span>
                                    <span>10分</span>
                                    <span>15分</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="section">
                        <h2>動画の要素</h2>
                        
                        <div class="form-group">
                            <label>基本の構成要素</label>
                            <div class="checkbox-group" id="manual-basic-elements">
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'manual-basic-elements')" data-value="title">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">タイトル・見出し</span>
                                    <span class="option-desc">セクションごとの見出しを表示（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'manual-basic-elements')" data-value="captions">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">テロップ（解説文字）</span>
                                    <span class="option-desc">操作手順や説明を文字で表示（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'manual-basic-elements')" data-value="bgm">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">BGM（音楽）</span>
                                    <span class="option-desc">集中しやすい背景音楽（標準装備）</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>追加したい要素</label>
                            <div class="checkbox-group" id="manual-additional-elements">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-additional-elements')" data-value="narration" data-price="15000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">プロナレーション</span>
                                    <span class="option-desc">プロのナレーターによる音声解説（+15,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-additional-elements')" data-value="ai-narration" data-price="10000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">AI音声ナレーション</span>
                                    <span class="option-desc">AI技術による自然な音声解説（+10,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-additional-elements')" data-value="pointer" data-price="8000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">ポインター表示</span>
                                    <span class="option-desc">マウスポインターの強調表示（+8,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-additional-elements')" data-value="zoom" data-price="12000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">ズーム・強調効果</span>
                                    <span class="option-desc">重要部分を拡大・強調する効果（+12,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-additional-elements')" data-value="chapters" data-price="8000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">チャプター設定</span>
                                    <span class="option-desc">項目ごとに頭出しできる設定（+8,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>素材について</h2>
                        
                        <div class="form-group">
                            <label>素材の準備方法</label>
                            <div class="radio-group" id="manual-materials">
                                <div class="radio-item" onclick="selectRadio(this, 'manual-materials')" data-value="client">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様がご用意</span>
                                    <span class="option-desc">画面録画や手順資料はお客様側でご準備いただきます</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-materials')" data-value="mixed">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様から素材をお預かりして撮影</span>
                                    <span class="option-desc">製品や操作画面をお預かりして当社で撮影します</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-materials')" data-value="remote" data-price="15000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">リモート画面共有で撮影</span>
                                    <span class="option-desc">オンライン会議ツールで画面共有して録画（+15,000円）</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>台本制作</label>
                            <div class="radio-group" id="manual-script">
                                <div class="radio-item" onclick="selectRadio(this, 'manual-script')" data-value="client">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様がご用意</span>
                                    <span class="option-desc">手順書や台本はお客様側でご準備いただきます</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-script')" data-value="outline" data-price="10000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様の手順書をもとに作成</span>
                                    <span class="option-desc">お客様の資料をもとに台本を作成（+10,000円）</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'manual-script')" data-value="full" data-price="25000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">一から作成</span>
                                    <span class="option-desc">製品の分析から始め、台本を作成（+25,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>特典オプション</h2>
                        
                        <div class="form-group">
                            <label>割引オプション</label>
                            <div class="checkbox-group" id="manual-discount">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-discount')" data-value="first-time" data-discount="0.15">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">初回ご利用割引</span>
                                    <span class="option-desc">初めてのお客様は15%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-discount')" data-value="multiple" data-discount="0.1">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">複数本割引</span>
                                    <span class="option-desc">3本以上のご注文で10%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'manual-discount', showContractOptions)" data-value="contract">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">継続契約割引</span>
                                    <span class="option-desc">定期的に動画制作をご検討の方向け</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- 会社紹介動画タブ -->
                <div id="company" class="tab-content">
                    <div class="section">
                        <h2>会社紹介動画制作</h2>
                        
                        <div class="form-group">
                            <label>動画の目的</label>
                            <div class="radio-group" id="company-purpose">
                                <div class="radio-item" onclick="selectRadio(this, 'company-purpose')" data-value="general">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">総合的な会社紹介</span>
                                    <span class="option-desc">企業理念・事業内容・強みなどを総合的に紹介</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'company-purpose')" data-value="recruit">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">採用向け</span>
                                    <span class="option-desc">就職希望者向けの職場環境や社風の紹介</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'company-purpose')" data-value="investor">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">投資家・取引先向け</span>
                                    <span class="option-desc">事業の強みや実績を重視した内容</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'company-purpose')" data-value="anniversary">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">周年記念</span>
                                    <span class="option-desc">会社の歴史や成長の軌跡を紹介</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>動画の長さ</label>
                            <div class="range-container">
                                <div class="range-value" id="company-length-value">3分</div>
                                <input type="range" min="1" max="10" value="3" class="range-slider" id="company-length" oninput="updateRangeValue('company-length')">
                                <div class="range-labels">
                                    <span>1分</span>
                                    <span>3分</span>
                                    <span>5分</span>
                                    <span>10分</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>動画の要素</h2>
                        
                        <div class="form-group">
                            <label>基本の構成要素</label>
                            <div class="checkbox-group" id="company-basic-elements">
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'company-basic-elements')" data-value="logo">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">ロゴアニメーション</span>
                                    <span class="option-desc">会社ロゴを動きのあるデザインで表示（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'company-basic-elements')" data-value="bgm">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">BGM（音楽）</span>
                                    <span class="option-desc">会社イメージに合った背景音楽（標準装備）</span>
                                </div>
                                <div class="checkbox-item selected" onclick="toggleCheckbox(this, 'company-basic-elements')" data-value="captions">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">テロップ（文字）</span>
                                    <span class="option-desc">重要なメッセージを文字で表示（標準装備）</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>追加したい要素</label>
                            <div class="checkbox-group" id="company-additional-elements">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'company-additional-elements')" data-value="narration" data-price="15000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">プロナレーション</span>
                                    <span class="option-desc">プロのナレーターによる音声案内（+15,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'company-additional-elements')" data-value="animation" data-price="25000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">グラフィックアニメーション</span>
                                    <span class="option-desc">データやイメージを視覚的に表現（+25,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'company-additional-elements')" data-value="subtitle" data-price="10000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">英語字幕</span>
                                    <span class="option-desc">海外向けの英語字幕を追加（+10,000円）</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'company-additional-elements')" data-value="aerial" data-price="30000">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">資料映像制作</span>
                                    <span class="option-desc">既存素材を活用したモーショングラフィックス（+30,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>素材について</h2>
                        
                        <div class="form-group">
                            <label>素材の準備方法</label>
                            <div class="radio-group" id="company-materials">
                                <div class="radio-item" onclick="selectRadio(this, 'company-materials')" data-value="client">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様がご用意</span>
                                    <span class="option-desc">写真・動画・ロゴなどをお客様側でご準備いただきます</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'company-materials')" data-value="mixed">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">一部既存素材の加工</span>
                                    <span class="option-desc">お客様の素材に加えて一部新規作成・加工します</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'company-materials')" data-value="full" data-price="20000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">全て新規作成</span>
                                    <span class="option-desc">既存素材をもとに全て新規制作します（+20,000円）</span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label>台本制作</label>
                            <div class="radio-group" id="company-script">
                                <div class="radio-item" onclick="selectRadio(this, 'company-script')" data-value="client">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様がご用意</span>
                                    <span class="option-desc">台本・シナリオはお客様側でご準備いただきます</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'company-script')" data-value="outline" data-price="15000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">お客様の資料をもとに作成</span>
                                    <span class="option-desc">会社案内やサイトをもとに台本作成（+15,000円）</span>
                                </div>
                                <div class="radio-item" onclick="selectRadio(this, 'company-script')" data-value="interview" data-price="30000">
                                    <div class="custom-radio"></div>
                                    <span class="checkbox-title">インタビューをもとに作成</span>
                                    <span class="option-desc">経営者へのヒアリングをもとに台本作成（+30,000円）</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="section">
                        <h2>特典オプション</h2>
                        
                        <div class="form-group">
                            <label>割引オプション</label>
                            <div class="checkbox-group" id="company-discount">
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'company-discount')" data-value="first-time" data-discount="0.15">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">初回ご利用割引</span>
                                    <span class="option-desc">初めてのお客様は15%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'company-discount')" data-value="referral" data-discount="0.1">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">ご紹介割引</span>
                                    <span class="option-desc">お知り合いからのご紹介で10%オフ</span>
                                </div>
                                <div class="checkbox-item" onclick="toggleCheckbox(this, 'company-discount')" data-value="social" data-discount="0.05">
                                    <div class="custom-checkbox"></div>
                                    <span class="checkbox-title">SNS投稿割引</span>
                                    <span class="option-desc">完成動画をSNSで紹介いただくと5%オフ</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- 価格表示セクション -->
            <div class="price-section">
                <!-- 価格表コンポーネントを表示するためのdiv -->
                <div id="price-table-container"></div>
                
                <div class="price-card">
                    <h3>お見積り金額</h3>
                    
                    <div class="price-row">
                        <div class="price-label">基本料金</div>
                        <div class="price-value" id="base-price">38,000円</div>
                    </div>
                    
                    <div class="price-row">
                        <div class="price-label">オプション料金</div>
                        <div class="price-value" id="options-price">0円</div>
                    </div>
                    
                    <div class="price-row" id="discount-row" style="display: none;">
                        <div class="price-label">割引</div>
                        <div class="price-value discount" id="discount-amount">- 0円</div>
                    </div>
                    
                    <div class="price-row">
                        <div class="price-label">合計金額</div>
                        <div class="price-value" id="total-price">38,000円</div>
                    </div>
                    
                    <div class="special-offer">
                        <h4>初回限定特別オファー</h4>
                        <p>制作した動画を弊社の実績として<br>公開OKで5,000円割引！</p>
                    </div>
                    
                    <button class="submit-btn">この内容でお問い合わせ</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // タブ切り替え関数
        function showTab(tabId) {
            // すべてのタブコンテンツを非表示
            const tabContents = document.querySelectorAll('.tab-content');
            tabContents.forEach(content => {
                content.classList.remove('active');
            });
            
            // すべてのタブボタンを非アクティブ化
            const tabs = document.querySelectorAll('.tab');
            tabs.forEach(tab => {
                tab.classList.remove('active');
            });
            
            // 選択したタブとコンテンツをアクティブ化
            document.getElementById(tabId).classList.add('active');
            document.querySelector(`.tab[onclick="showTab('${tabId}')"]`).classList.add('active');
            
            // 見積もりを更新
            calculateEstimate();
        }
        
        // ラジオボタン選択関数
        function selectRadio(element, groupName) {
            // 同じグループの全ラジオボタンから選択状態を解除
            const radioItems = document.querySelectorAll(`#${groupName} .radio-item`);
            radioItems.forEach(item => {
                item.classList.remove('selected');
            });
            
            // クリックされた要素を選択状態にする
            element.classList.add('selected');
            
            // 見積もりを更新
            calculateEstimate();
        }
        
        // チェックボックス切り替え関数
        function toggleCheckbox(element, groupName, callback) {
            // クリックされた要素の選択状態を切り替え
            element.classList.toggle('selected');
            
            // 追加のコールバック関数がある場合は実行
            if(callback) {
                callback();
            }
            
            // 見積もりを更新
            calculateEstimate();
        }
        
        // スライダー値更新関数
        function updateRangeValue(elementId, unit = '分') {
            const slider = document.getElementById(elementId);
            const valueDisplay = document.getElementById(`${elementId}-value`);
            if (slider && valueDisplay) {
                valueDisplay.textContent = `${slider.value}${unit}`;
            }
            
            // 見積もりを更新
            calculateEstimate();
        }
        
        // 継続契約オプション表示関数
        function showContractOptions() {
            const contractOptions = document.getElementById('contract-options');
            const contractCheckbox = document.querySelector('#youtube-discount .checkbox-item[data-value="contract"].selected, #instagram-discount .checkbox-item[data-value="contract"].selected, #manual-discount .checkbox-item[data-value="contract"].selected');
            
            if(contractCheckbox && contractOptions) {
                contractOptions.style.display = 'block';
            } else if(contractOptions) {
                contractOptions.style.display = 'none';
                
                // 継続契約が選択解除された場合、期間選択も解除
                const durationRadios = document.querySelectorAll('#contract-duration .radio-item');
                durationRadios.forEach(item => {
                    item.classList.remove('selected');
                });
            }
            
            // 見積もりを更新
            calculateEstimate();
        }
        
        // 見積もり計算関数
        function calculateEstimate() {
            // アクティブなタブを取得
            const activeTabElement = document.querySelector('.tab.active');
            if (!activeTabElement) return; // タブが見つからない場合は処理を中止
            
            const activeTab = activeTabElement.textContent.toLowerCase();
            let basePrice = 0;
            let optionPrice = 0;
            let discount = 0;
            
            // YouTube動画の場合
            if(activeTab.includes('youtube')) {
                // 動画の長さに基づく基本料金計算
                const lengthElement = document.getElementById('youtube-length');
                if (!lengthElement) return;
                
                const length = parseInt(lengthElement.value);
                if(length <= 3) {
                    basePrice = 38000;
                } else if(length <= 5) {
                    basePrice = 58000;
                } else if(length <= 10) {
                    basePrice = 98000;
                } else if(length <= 15) {
                    basePrice = 150000;
                } else {
                    basePrice = 200000;
                }
                
                // 追加要素の料金を加算
                const additionalElements = document.querySelectorAll('#youtube-additional-elements .checkbox-item.selected');
                additionalElements.forEach(element => {
                    if(element.dataset.price) {
                        optionPrice += parseInt(element.dataset.price);
                    }
                });
                
                // 素材準備オプション
                const materialOption = document.querySelector('#youtube-materials .radio-item.selected');
                if(materialOption && materialOption.dataset.price) {
                    optionPrice += parseInt(materialOption.dataset.price);
                }
                
                // 台本制作オプション
                const scriptOption = document.querySelector('#youtube-script .radio-item.selected');
                if(scriptOption && scriptOption.dataset.price) {
                    optionPrice += parseInt(scriptOption.dataset.price);
                }
                
                // 修正回数オプション
                const revisionOption = document.querySelector('#youtube-revisions .radio-item.selected');
                if(revisionOption && revisionOption.dataset.price) {
                    optionPrice += parseInt(revisionOption.dataset.price);
                }
                
                // アップロードサポートオプション
                const uploadOptions = document.querySelectorAll('#youtube-upload .checkbox-item.selected');
                uploadOptions.forEach(option => {
                    if(option.dataset.price) {
                        optionPrice += parseInt(option.dataset.price);
                    }
                });
                
                // 割引計算
                const discountOptions = document.querySelectorAll('#youtube-discount .checkbox-item.selected');
                discountOptions.forEach(option => {
                    if(option.dataset.discount) {
                        discount += parseFloat(option.dataset.discount);
                    }
                });
                
                // 継続契約の割引
                if(document.querySelector('#youtube-discount .checkbox-item[data-value="contract"].selected')) {
                    const contractDuration = document.querySelector('#contract-duration .radio-item.selected');
                    if(contractDuration && contractDuration.dataset.discount) {
                        discount += parseFloat(contractDuration.dataset.discount);
                    }
                }
            }
            // Instagram・TikTok動画の場合
            else if(activeTab.includes('instagram') || activeTab.includes('tiktok')) {
                // 基本料金設定
                basePrice = 25000;
                
                // 動画の長さに応じた追加料金
                const lengthElement = document.getElementById('instagram-length');
                if (lengthElement) {
                    const length = parseInt(lengthElement.value);
                    if(length > 30) {
                        basePrice += 5000;
                    }
                    if(length > 45) {
                        basePrice += 5000;
                    }
                }
                
                // 追加要素の料金を加算
                const additionalElements = document.querySelectorAll('#instagram-additional-elements .checkbox-item.selected');
                additionalElements.forEach(element => {
                    if(element.dataset.price) {
                        optionPrice += parseInt(element.dataset.price);
                    }
                });
                
                // 素材準備オプション
                const materialOption = document.querySelector('#instagram-materials .radio-item.selected');
                if(materialOption && materialOption.dataset.price) {
                    optionPrice += parseInt(materialOption.dataset.price);
                }
                
                // 修正回数オプション
                const revisionOption = document.querySelector('#instagram-revisions .radio-item.selected');
                if(revisionOption && revisionOption.dataset.price) {
                    optionPrice += parseInt(revisionOption.dataset.price);
                }
                
                // 割引計算
                const discountOptions = document.querySelectorAll('#instagram-discount .checkbox-item.selected');
                discountOptions.forEach(option => {
                    if(option.dataset.discount) {
                        discount += parseFloat(option.dataset.discount);
                    }
                });
                
                // 継続契約の割引
                if(document.querySelector('#instagram-discount .checkbox-item[data-value="contract"].selected')) {
                    const contractDuration = document.querySelector('#contract-duration .radio-item.selected');
                    if(contractDuration && contractDuration.dataset.discount) {
                        discount += parseFloat(contractDuration.dataset.discount);
                    }
                }
            }
            // マニュアル動画の場合
            else if(activeTab.includes('manual')) {
       // 基本料金設定（長さに基づく）
                const lengthElement = document.getElementById('manual-length');
                if (lengthElement) {
                    const length = parseInt(lengthElement.value);
                    if(length <= 3) {
                        basePrice = 45000;
                    } else if(length <= 7) {
                        basePrice = 65000;
                    } else if(length <= 10) {
                        basePrice = 85000;
                    } else {
                        basePrice = 110000;
                    }
                }
                
                // 追加要素の料金を加算
                const additionalElements = document.querySelectorAll('#manual-additional-elements .checkbox-item.selected');
                additionalElements.forEach(element => {
                    if(element.dataset.price) {
                        optionPrice += parseInt(element.dataset.price);
                    }
                });
                
                // 素材準備オプション
                const materialOption = document.querySelector('#manual-materials .radio-item.selected');
                if(materialOption && materialOption.dataset.price) {
                    optionPrice += parseInt(materialOption.dataset.price);
                }
                
                // 台本制作オプション
                const scriptOption = document.querySelector('#manual-script .radio-item.selected');
                if(scriptOption && scriptOption.dataset.price) {
                    optionPrice += parseInt(scriptOption.dataset.price);
                }
                
                // 割引計算
                const discountOptions = document.querySelectorAll('#manual-discount .checkbox-item.selected');
                discountOptions.forEach(option => {
                    if(option.dataset.discount) {
                        discount += parseFloat(option.dataset.discount);
                    }
                });
                
                // 継続契約の割引
                if(document.querySelector('#manual-discount .checkbox-item[data-value="contract"].selected')) {
                    const contractDuration = document.querySelector('#contract-duration .radio-item.selected');
                    if(contractDuration && contractDuration.dataset.discount) {
                        discount += parseFloat(contractDuration.dataset.discount);
                    }
                }
            }
            // 会社紹介動画の場合
            else if(activeTab.includes('company')) {
                // 基本料金設定（長さに基づく）
                const lengthElement = document.getElementById('company-length');
                if (lengthElement) {
                    const length = parseInt(lengthElement.value);
                    if(length <= 2) {
                        basePrice = 80000;
                    } else if(length <= 5) {
                        basePrice = 120000;
                    } else if(length <= 7) {
                        basePrice = 160000;
                    } else {
                        basePrice = 200000;
                    }
                }
                
                // 追加要素の料金を加算
                const additionalElements = document.querySelectorAll('#company-additional-elements .checkbox-item.selected');
                additionalElements.forEach(element => {
                    if(element.dataset.price) {
                        optionPrice += parseInt(element.dataset.price);
                    }
                });
                
                // 素材準備オプション
                const materialOption = document.querySelector('#company-materials .radio-item.selected');
                if(materialOption && materialOption.dataset.price) {
                    optionPrice += parseInt(materialOption.dataset.price);
                }
                
                // 台本制作オプション
                const scriptOption = document.querySelector('#company-script .radio-item.selected');
                if(scriptOption && scriptOption.dataset.price) {
                    optionPrice += parseInt(scriptOption.dataset.price);
                }
                
                // 割引計算
                const discountOptions = document.querySelectorAll('#company-discount .checkbox-item.selected');
                discountOptions.forEach(option => {
                    if(option.dataset.discount) {
                        discount += parseFloat(option.dataset.discount);
                    }
                });
            }
            
            // 割引金額計算
            const totalBeforeDiscount = basePrice + optionPrice;
            const discountAmount = totalBeforeDiscount * discount;
            const finalTotal = totalBeforeDiscount - discountAmount;
            
            // 価格表示を更新
            const basePriceElement = document.getElementById('base-price');
            const optionsPriceElement = document.getElementById('options-price');
            const discountRowElement = document.getElementById('discount-row');
            const discountAmountElement = document.getElementById('discount-amount');
            const totalPriceElement = document.getElementById('total-price');
            
            if (basePriceElement) basePriceElement.textContent = basePrice.toLocaleString() + '円';
            if (optionsPriceElement) optionsPriceElement.textContent = optionPrice.toLocaleString() + '円';
            
            if(discountAmount > 0 && discountRowElement && discountAmountElement) {
                discountRowElement.style.display = 'flex';
                discountAmountElement.textContent = '- ' + discountAmount.toLocaleString() + '円';
            } else if (discountRowElement) {
                discountRowElement.style.display = 'none';
            }
            
            if (totalPriceElement) totalPriceElement.textContent = finalTotal.toLocaleString() + '円';
        }
        
        // ページ読み込み時に初期計算を実行
        document.addEventListener('DOMContentLoaded', function() {
            // タブの初期設定
            showTab('youtube');
            
            // 初期計算
            calculateEstimate();
        });
    </script>

    <!-- Reactコンポーネントのスクリプト -->
    <script type="text/babel">
        // 料金表コンポーネント
        const PriceTable = () => {
          // 各タブの基本料金テーブルデータ
          const priceTables = {
            youtube: {
              title: "YouTube動画 基本料金表",
              headers: ["動画の長さ", "料金"],
              rows: [
                ["3分以内", "38,000円"],
                ["5分以内", "58,000円"],
                ["10分以内", "98,000円"],
                ["15分以内", "150,000円"],
                ["20分以内", "200,000円"]
              ]
            },
            instagram: {
              title: "Instagram・TikTok動画 基本料金表",
              headers: ["動画の長さ", "料金"],
              rows: [
                ["30秒以内", "25,000円"],
                ["45秒以内", "30,000円"],
                ["60秒以内", "35,000円"]
              ]
            },
            manual: {
              title: "マニュアル動画 基本料金表",
              headers: ["動画の長さ", "料金"],
              rows: [
                ["3分以内", "45,000円"],
                ["7分以内", "65,000円"],
                ["10分以内", "85,000円"],
                ["15分以内", "110,000円"]
              ]
            },
            company: {
              title: "会社紹介動画 基本料金表",
              headers: ["動画の長さ", "料金"],
              rows: [
                ["2分以内", "80,000円"],
                ["5分以内", "120,000円"],
                ["7分以内", "160,000円"],
                ["10分以内", "200,000円"]
              ]
            }
          };

          // 各タブのオプション料金テーブルデータ
          const optionTables = {
            youtube: {
              title: "YouTube動画 オプション料金表",
              headers: ["オプション項目", "料金"],
              rows: [
                ["プロナレーション", "+15,000円"],
                ["AI音声ナレーション", "+10,000円"],
                ["アニメーション・図解", "+20,000円"],
                ["字幕（日本語）", "+10,000円"],
                ["外国語字幕", "+15,000円/言語"],
                ["サムネイル画像", "+6,000円"],
                ["制作会社におまかせ（素材）", "+15,000円"],
                ["お客様の構想をもとに作成（台本）", "+10,000円"],
                ["完全におまかせ（台本）", "+20,000円"],
                ["修正回数 3回まで", "+5,000円"],
                ["修正回数 5回まで", "+10,000円"],
                ["アップロードサポート", "+5,000円"]
              ]
            },
            instagram: {
              title: "Instagram・TikTok動画 オプション料金表",
              headers: ["オプション項目", "料金"],
              rows: [
                ["美肌補正", "+5,000円"],
                ["簡易アニメーション", "+15,000円"],
                ["字幕（日本語）", "+8,000円"],
                ["行動喚起画面", "+5,000円"],
                ["制作会社におまかせ（素材）", "+10,000円"],
                ["修正回数 3回まで", "+3,000円"],
                ["修正回数 5回まで", "+8,000円"]
              ]
            },
            manual: {
              title: "マニュアル動画 オプション料金表",
              headers: ["オプション項目", "料金"],
              rows: [
                ["プロナレーション", "+15,000円"],
                ["AI音声ナレーション", "+10,000円"],
                ["ポインター表示", "+8,000円"],
                ["ズーム・強調効果", "+12,000円"],
                ["チャプター設定", "+8,000円"],
                ["リモート画面共有で撮影", "+15,000円"],
                ["お客様の手順書をもとに作成（台本）", "+10,000円"],
                ["一から作成（台本）", "+25,000円"]
              ]
            },
            company: {
              title: "会社紹介動画 オプション料金表",
              headers: ["オプション項目", "料金"],
              rows: [
                ["プロナレーション", "+15,000円"],
                ["グラフィックアニメーション", "+25,000円"],
                ["英語字幕", "+10,000円"],
                ["資料映像制作", "+30,000円"],
                ["全て新規作成（素材）", "+20,000円"],
                ["お客様の資料をもとに作成（台本）", "+15,000円"],
                ["インタビューをもとに作成（台本）", "+30,000円"]
              ]
            }
          };

          // 割引テーブルデータ
          const discountTable = {
            title: "適用可能な割引",
            headers: ["割引項目", "割引率"],
            rows: [
              ["初回ご利用割引", "15%"],
              ["複数本割引（3本以上）", "10%"],
              ["3ヶ月契約", "5%"],
              ["6ヶ月契約", "10%"],
              ["12ヶ月契約", "15%"],
              ["ご紹介割引", "10%"],
              ["SNS投稿割引", "5%"]
            ]
          };

          // 現在表示中のタブを追跡
          const [activeTab, setActiveTab] = React.useState('youtube');
          // 現在の見積もり金額を追跡
          const [currentEstimate, setCurrentEstimate] = React.useState({
            basePrice: '38,000円',
            optionsPrice: '0円',
            discount: '0円',
            totalPrice: '38,000円'
          });

          // タブの変更を監視する関数
          const observeTabChanges = () => {
            const tabElements = document.querySelectorAll('.tab');
            
            // タブ要素が存在する場合
            if (tabElements.length > 0) {
              // アクティブなタブを見つける
              const activeTabElement = document.querySelector('.tab.active');
              if (activeTabElement) {
                const tabText = activeTabElement.textContent.toLowerCase();
                if (tabText.includes('youtube')) {
                  setActiveTab('youtube');
                } else if (tabText.includes('instagram') || tabText.includes('tiktok')) {
                  setActiveTab('instagram');
                } else if (tabText.includes('manual')) {
                  setActiveTab('manual');
                } else if (tabText.includes('company')) {
                  setActiveTab('company');
                }
              }
            }
          };

          // 料金の変更を監視する関数
          const observePriceChanges = () => {
            const basePriceElement = document.getElementById('base-price');
            const optionsPriceElement = document.getElementById('options-price');
            const discountAmountElement = document.getElementById('discount-amount');
            const totalPriceElement = document.getElementById('total-price');
            
            if (basePriceElement && optionsPriceElement && totalPriceElement) {
              const basePrice = basePriceElement.textContent;
              const optionsPrice = optionsPriceElement.textContent;
              const discount = discountAmountElement ? discountAmountElement.textContent.replace('- ', '') : '0円';
              const totalPrice = totalPriceElement.textContent;
              
              setCurrentEstimate({
                basePrice,
                optionsPrice, 
                discount,
                totalPrice
              });
            }
          };

          // 初期化と監視設定
          React.useEffect(() => {
            // 初期タブの設定
            observeTabChanges();
            observePriceChanges();
            
            // MutationObserverで変更を監視
            const tabObserver = new MutationObserver(() => {
              observeTabChanges();
            });
            
            const priceObserver = new MutationObserver(() => {
              observePriceChanges();
            });
            
            // タブの変更を監視
            const tabContainer = document.querySelector('.tab-container');
            if (tabContainer) {
              tabObserver.observe(tabContainer, { 
                attributes: true, 
                childList: true, 
                subtree: true 
              });
            }
            
            // 価格の変更を監視
            const priceCard = document.querySelector('.price-card');
            if (priceCard) {
              priceObserver.observe(priceCard, { 
                childList: true, 
                subtree: true,
                characterData: true
              });
            }
            
            // クリーンアップ
            return () => {
              tabObserver.disconnect();
              priceObserver.disconnect();
            };
          }, []);

          return (
            <div className="price-table-container">
              {/* 現在の見積もり概要 */}
              <div className="current-estimate">
                <h3>現在の見積もり</h3>
                <div className="current-estimate-grid">
                  <div>基本料金:</div>
                  <div style={{textAlign: 'right'}}>{currentEstimate.basePrice}</div>
                  
                  <div>オプション料金:</div>
                  <div style={{textAlign: 'right'}}>{currentEstimate.optionsPrice}</div>
                  
                  {currentEstimate.discount !== '0円' && (
                    <>
                      <div>割引:</div>
                      <div style={{textAlign: 'right', color: '#29ad5d'}}>- {currentEstimate.discount}</div>
                    </>
                  )}
                  
                  <div className="current-estimate-total">
                    合計: {currentEstimate.totalPrice}
                  </div>
                </div>
              </div>
              
              {/* 基本料金表 */}
              <div className="price-table-container">
                <h3>{priceTables[activeTab].title}</h3>
                <div className="price-tables-wrapper">
                  <table className="price-table">
                    <thead>
                      <tr>
                        {priceTables[activeTab].headers.map((header, index) => (
                          <th key={index}>{header}</th>
                        ))}
                      </tr>
                    </thead>
                    <tbody>
                      {priceTables[activeTab].rows.map((row, rowIndex) => (
                        <tr key={rowIndex}>
                          {row.map((cell, cellIndex) => (
                            <td key={cellIndex}>{cell}</td>
                          ))}
                        </tr>
                      ))}
                    </tbody>
                  </table>
                </div>
              </div>
              
              {/* オプション料金表 */}
              <div className="price-table-container">
                <h3>{optionTables[activeTab].title}</h3>
                <div className="price-tables-wrapper">
                  <table className="price-table">
                    <thead>
                      <tr>
                        {optionTables[activeTab].headers.map((header, index) => (
                          <th key={index}>{header}</th>
                        ))}
                      </tr>
                    </thead>
                    <tbody>
                      {optionTables[activeTab].rows.map((row, rowIndex) => (
                        <tr key={rowIndex}>
                          {row.map((cell, cellIndex) => (
                            <td key={cellIndex}>{cell}</td>
                          ))}
                        </tr>
                      ))}
                    </tbody>
                  </table>
                </div>
              </div>
              
              {/* 割引情報 */}
              <div className="price-table-container">
                <h3>{discountTable.title}</h3>
                <div className="price-tables-wrapper">
                  <table className="price-table">
                    <thead>
                      <tr>
                        {discountTable.headers.map((header, index) => (
                          <th key={index}>{header}</th>
                        ))}
                      </tr>
                    </thead>
                    <tbody>
                      {discountTable.rows.map((row, rowIndex) => (
                        <tr key={rowIndex}>
                          {row.map((cell, cellIndex) => (
                            <td key={cellIndex}>{cell}</td>
                          ))}
                        </tr>
                      ))}
                    </tbody>
                  </table>
                </div>
              </div>
              
              <div style={{margin: '20px 0', fontSize: '14px', color: '#6a85a0'}}>
                <p>※ 表示されている金額は全て税抜きです</p>
                <p>※ 料金は選択内容によって変動します</p>
              </div>
            </div>
          );
        };

        // コンポーネントをレンダリング
        ReactDOM.render(
          <PriceTable />,
          document.getElementById('price-table-container')
        );
    </script>
</body>
</html>
