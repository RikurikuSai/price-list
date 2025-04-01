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
        
        /* その他のCSSは省略（長くなるため） */
    </style>
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
            <!-- フォームの本体部分は別パートに分けます -->
        </div>
    </div>
</body>
</html>
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
                <div class="radio-item" onclick="selectRadio(this, 'youtube-purpose')" data-value="other">
                    <div class="custom-radio"></div>
                    <span class="checkbox-title">その他の目的</span>
                    <span class="option-desc">上記に当てはまらない特別な目的の動画</span>
                </div>
            </div>
        </div>
        
        <div class="form-group">
            <label>動画の長さ</label>
            <span class="helper-text">動画の長さはどのくらいをお考えですか？</span>
            <div class="range-container">
                <div class="range-value" id="youtube-length-value">5分</div>
                <input type="range" min="1" max="20" value="5" class="range-slider" id="youtube-length" onInput="updateRangeValue('youtube-length')">
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
    
    <!-- YouTubeタブのその他の部分は省略 -->
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
                <input type="range" min="10" max="60" value="30" class="range-slider" id="instagram-length" onInput="updateRangeValue('instagram-length', '秒')">
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
            <label>追加したい要素</label>
            <span class="helper-text">動画をより効果的にするオプション要素をお選びください</span>
            <div class="checkbox-group" id="instagram-additional-elements">
                <!-- ここに美肌補正オプションが含まれています -->
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
    
    <!-- Instagramタブのその他の部分は省略 -->
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
                <input type="range" min="1" max="10" value="3" class="range-slider" id="company-length" onInput="updateRangeValue('company-length')">
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
                    <span class="option-desc">お客様の素材に加えて一部新規作成・加工します</span
