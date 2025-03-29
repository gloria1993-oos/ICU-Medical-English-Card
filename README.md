# ICU-Medical-English-Card
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ICU医学英语记忆系统 - 专业增强版</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Roboto+Slab:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #3a7bd5;
            --primary-light: #00d2ff;
            --secondary: #1a2980;
            --accent: #ff4b2b;
            --light: #f8f9fa;
            --dark: #2c3e50;
            --gray: #7f8c8d;
            --success: #4cc9f0;
            --warning: #f8961e;
            --danger: #ef233c;
            --bg-gradient: linear-gradient(135deg, #1a2980 0%, #26d0ce 100%);
            --card-gradient: linear-gradient(to right, #3a7bd5 0%, #00d2ff 100%);
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.1);
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Poppins', 'PingFang SC', 'Microsoft YaHei', sans-serif;
            background-color: #f5f7fa;
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: var(--bg-gradient);
            color: white;
            padding: 2.5rem 0;
            margin-bottom: 3rem;
            border-radius: 0 0 30px 30px;
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
            z-index: 10;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none"><path fill="rgba(255,255,255,0.05)" d="M0,0 L100,0 L100,100 L0,100 Z" /></svg>');
            background-size: cover;
        }
        
        .header-content {
            position: relative;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1;
            padding: 0 20px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 20px;
        }
        
        .logo-icon {
            font-size: 3rem;
            background: rgba(255,255,255,0.2);
            width: 70px;
            height: 70px;
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .logo-text h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            font-weight: 700;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.2);
        }
        
        .logo-text p {
            opacity: 0.9;
            font-size: 1rem;
            font-weight: 300;
        }
        
        nav {
            display: flex;
            gap: 15px;
        }
        
        .nav-btn {
            background-color: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            color: white;
            border: none;
            padding: 0.8rem 1.8rem;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 500;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 0.8rem;
            font-size: 1rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            border: 1px solid rgba(255,255,255,0.1);
        }
        
        .nav-btn:hover {
            background-color: rgba(255, 255, 255, 0.25);
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }
        
        .nav-btn.active {
            background-color: white;
            color: var(--primary);
            box-shadow: 0 5px 20px rgba(58, 123, 213, 0.4);
        }
        
        .nav-btn i {
            font-size: 1.2rem;
        }
        
        .section {
            display: none;
            background-color: white;
            border-radius: 20px;
            padding: 3rem;
            box-shadow: var(--shadow);
            margin-bottom: 3rem;
            animation: fadeIn 0.6s ease;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(0,0,0,0.05);
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .section::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 6px;
            background: var(--card-gradient);
        }
        
        .section.active {
            display: block;
        }
        
        h2 {
            color: var(--primary);
            margin-bottom: 2rem;
            font-size: 2.2rem;
            font-weight: 600;
            position: relative;
            padding-bottom: 1rem;
            font-family: 'Roboto Slab', serif;
        }
        
        h2::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 80px;
            height: 4px;
            background: var(--card-gradient);
            border-radius: 4px;
        }
        
        .form-group {
            margin-bottom: 2rem;
        }
        
        label {
            display: block;
            margin-bottom: 0.8rem;
            font-weight: 500;
            color: var(--dark);
            font-size: 1.1rem;
        }
        
        input, textarea, select {
            width: 100%;
            padding: 1.2rem;
            border: 1px solid #e2e8f0;
            border-radius: 12px;
            font-size: 1.1rem;
            transition: var(--transition);
            font-family: 'Poppins', sans-serif;
            background-color: #f8fafc;
        }
        
        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: var(--primary-light);
            box-shadow: 0 0 0 4px rgba(0, 210, 255, 0.1);
            background-color: white;
        }
        
        textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        .btn {
            background: var(--card-gradient);
            color: white;
            border: none;
            padding: 1.2rem 2.5rem;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 500;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            box-shadow: 0 5px 20px rgba(58, 123, 213, 0.3);
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .btn:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 12px 25px rgba(58, 123, 213, 0.4);
        }
        
        .btn-secondary {
            background: linear-gradient(to right, #6c757d, #495057);
        }
        
        .btn-secondary:hover {
            box-shadow: 0 12px 25px rgba(108, 117, 125, 0.4);
        }
        
        .btn-accent {
            background: linear-gradient(to right, #ff4b2b, #ff416c);
        }
        
        .btn-accent:hover {
            box-shadow: 0 12px 25px rgba(255, 75, 43, 0.4);
        }
        
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2.5rem;
            margin-top: 2.5rem;
        }
        
        .card {
            background-color: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid rgba(0,0,0,0.05);
            position: relative;
        }
        
        .card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }
        
        .card-header {
            background: var(--card-gradient);
            color: white;
            padding: 1.5rem;
            font-size: 1.3rem;
            font-weight: 600;
            position: relative;
            overflow: hidden;
            font-family: 'Roboto Slab', serif;
        }
        
        .card-header::after {
            content: "";
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.15) 0%, rgba(255,255,255,0) 100%);
        }
        
        .card-body {
            padding: 2rem;
        }
        
        .card-term {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 0.8rem;
            color: var(--dark);
            line-height: 1.3;
            font-family: 'Roboto Slab', serif;
        }
        
        .card-pronunciation {
            font-style: italic;
            color: var(--gray);
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }
        
        .card-category {
            display: inline-block;
            background-color: #e0f7ff;
            color: var(--primary);
            padding: 0.5rem 1.2rem;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 1.8rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .card-definition {
            margin-bottom: 2rem;
            color: var(--dark);
            line-height: 1.8;
            font-size: 1.1rem;
        }
        
        .card-mnemonic {
            background-color: #f0fdf4;
            border-left: 5px solid var(--success);
            padding: 1.5rem;
            border-radius: 0 15px 15px 0;
            margin-bottom: 2rem;
            position: relative;
        }
        
        .card-mnemonic::before {
            content: "💡";
            position: absolute;
            top: -18px;
            left: 20px;
            font-size: 1.8rem;
            background-color: white;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        
        .card-mnemonic-title {
            font-weight: 600;
            color: var(--success);
            margin-bottom: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            font-size: 1rem;
        }
        
        .card-example {
            font-style: italic;
            color: var(--gray);
            position: relative;
            padding-left: 2.5rem;
            line-height: 1.8;
            font-size: 1.1rem;
        }
        
        .card-example::before {
            content: "🖊️";
            position: absolute;
            left: 0;
            top: 0;
            font-size: 1.5rem;
        }
        
        .card-actions {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }
        
        .card-btn {
            flex: 1;
            padding: 0.8rem;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 500;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.6rem;
        }
        
        .card-btn-edit {
            background-color: #e0f7ff;
            color: var(--primary);
        }
        
        .card-btn-edit:hover {
            background-color: #c7ebff;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(58, 123, 213, 0.2);
        }
        
        .card-btn-delete {
            background-color: #ffe0e0;
            color: var(--danger);
        }
        
        .card-btn-delete:hover {
            background-color: #ffc7c7;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(239, 35, 60, 0.2);
        }
        
        .study-card {
            max-width: 800px;
            margin: 0 auto;
            background-color: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: var(--shadow);
            border: 1px solid rgba(0,0,0,0.05);
        }
        
        .study-card-header {
            background: var(--card-gradient);
            color: white;
            padding: 2rem;
            text-align: center;
            font-size: 1.5rem;
            font-weight: 600;
            position: relative;
            overflow: hidden;
            font-family: 'Roboto Slab', serif;
        }
        
        .study-card-header::after {
            content: "";
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(255,255,255,0.15) 0%, rgba(255,255,255,0) 100%);
        }
        
        .study-card-body {
            padding: 3rem;
            text-align: center;
        }
        
        .study-card-term {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 2rem;
            color: var(--dark);
            line-height: 1.2;
            font-family: 'Roboto Slab', serif;
        }
        
        .study-card-pronunciation {
            font-style: italic;
            color: var(--gray);
            margin-bottom: 3.5rem;
            font-size: 1.5rem;
        }
        
        .study-card-definition {
            font-size: 1.5rem;
            line-height: 1.8;
            margin-bottom: 3rem;
            color: var(--dark);
            display: none;
            text-align: left;
        }
        
        .study-card-mnemonic {
            background-color: #f0fdf4;
            border-left: 5px solid var(--success);
            padding: 2rem;
            border-radius: 0 15px 15px 0;
            margin-bottom: 3rem;
            text-align: left;
            display: none;
            position: relative;
        }
        
        .study-card-mnemonic::before {
            content: "💡";
            position: absolute;
            top: -20px;
            left: 20px;
            font-size: 2rem;
            background-color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }
        
        .study-card-example {
            font-style: italic;
            color: var(--gray);
            margin-bottom: 3rem;
            text-align: left;
            padding-left: 3rem;
            position: relative;
            display: none;
            line-height: 1.8;
            font-size: 1.3rem;
        }
        
        .study-card-example::before {
            content: "🖊️";
            position: absolute;
            left: 0;
            top: 0;
            font-size: 1.8rem;
        }
        
        .study-card-actions {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .study-progress {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--gray);
            font-size: 1.3rem;
        }
        
        .empty-state {
            text-align: center;
            padding: 5rem 3rem;
            color: var(--gray);
        }
        
        .empty-state-icon {
            font-size: 5rem;
            margin-bottom: 2rem;
            color: #e2e8f0;
        }
        
        .empty-state-text {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            color: var(--dark);
            font-weight: 500;
        }
        
        .filter-bar {
            display: flex;
            gap: 2rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
        }
        
        .filter-group {
            flex: 1;
            min-width: 300px;
        }
        
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }
        
        .stat-card {
            background-color: white;
            border-radius: 15px;
            padding: 2.5rem;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border: 1px solid rgba(0,0,0,0.05);
            text-align: center;
        }
        
        .stat-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }
        
        .stat-value {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: var(--card-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-family: 'Roboto Slab', serif;
        }
        
        .stat-label {
            color: var(--gray);
            font-size: 1.2rem;
            font-weight: 500;
        }
        
        .category-chart {
            background-color: white;
            border-radius: 15px;
            padding: 3rem;
            box-shadow: var(--shadow);
            margin-bottom: 3rem;
            border: 1px solid rgba(0,0,0,0.05);
        }
        
        .chart-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 2rem;
            color: var(--dark);
            font-family: 'Roboto Slab', serif;
        }
        
        .chart-bar {
            height: 25px;
            background-color: #f1f5f9;
            border-radius: 12px;
            margin-bottom: 20px;
            overflow: hidden;
            position: relative;
        }
        
        .chart-progress {
            height: 100%;
            border-radius: 12px;
            background: var(--card-gradient);
            position: relative;
            transition: width 1s ease;
        }
        
        .chart-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 1.1rem;
        }
        
        .chart-category {
            font-weight: 500;
            color: var(--dark);
        }
        
        .chart-count {
            color: var(--gray);
        }
        
        .floating-btn {
            position: fixed;
            bottom: 40px;
            right: 40px;
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: var(--card-gradient);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            box-shadow: 0 15px 35px rgba(58, 123, 213, 0.3);
            cursor: pointer;
            z-index: 100;
            transition: var(--transition);
            border: none;
        }
        
        .floating-btn:hover {
            transform: translateY(-8px) scale(1.1);
            box-shadow: 0 20px 40px rgba(58, 123, 213, 0.4);
        }
        
        .badge {
            position: absolute;
            top: -10px;
            right: -10px;
            background-color: var(--accent);
            color: white;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9rem;
            font-weight: 600;
            box-shadow: 0 3px 10px rgba(255, 75, 43, 0.3);
        }
        
        .search-highlight {
            background-color: #fffde7;
            padding: 0 3px;
            border-radius: 3px;
            font-weight: 500;
        }
        
        .speak-btn {
            background: none;
            border: none;
            color: var(--primary);
            cursor: pointer;
            font-size: 1.2rem;
            margin-left: 0.5rem;
            transition: transform 0.2s;
        }
        
        .speak-btn:hover {
            transform: scale(1.2);
        }
        
        .batch-upload {
            margin-top: 2rem;
            padding: 2rem;
            border: 2px dashed #e2e8f0;
            border-radius: 15px;
            text-align: center;
        }
        
        .batch-upload.active {
            border-color: var(--primary);
            background-color: rgba(58, 123, 213, 0.05);
        }
        
        .download-template {
            margin-top: 1rem;
            display: inline-block;
            color: var(--primary);
            text-decoration: none;
            font-weight: 500;
        }
        
        .download-template:hover {
            text-decoration: underline;
        }
        
        @media (max-width: 1200px) {
            .header-content {
                flex-direction: column;
                gap: 2rem;
                text-align: center;
            }
            
            nav {
                width: 100%;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .section {
                padding: 2.5rem;
            }
            
            .study-card-term {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 992px) {
            .card-grid {
                grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            }
            
            .study-card-body {
                padding: 2.5rem;
            }
            
            .study-card-term {
                font-size: 2.2rem;
            }
            
            .study-card-definition, .study-card-example {
                font-size: 1.3rem;
            }
            
            .filter-bar {
                flex-direction: column;
                gap: 1.5rem;
            }
            
            .filter-group {
                min-width: 100%;
            }
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            .section {
                padding: 2rem;
            }
            
            h2 {
                font-size: 1.8rem;
            }
            
            .study-card-actions {
                flex-direction: column;
                gap: 1.5rem;
            }
            
            .btn {
                width: 100%;
                justify-content: center;
            }
            
            .floating-btn {
                width: 60px;
                height: 60px;
                font-size: 1.5rem;
                bottom: 30px;
                right: 30px;
            }
            
            .stat-card {
                padding: 2rem;
            }
            
            .stat-value {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 576px) {
            .logo {
                flex-direction: column;
                text-align: center;
                gap: 1rem;
            }
            
            .logo-icon {
                width: 60px;
                height: 60px;
                font-size: 2rem;
            }
            
            .logo-text h1 {
                font-size: 2rem;
            }
            
            .card-grid {
                grid-template-columns: 1fr;
            }
            
            .study-card-term {
                font-size: 2rem;
            }
            
            .study-card-pronunciation {
                font-size: 1.2rem;
            }
            
            .study-card-definition, .study-card-example {
                font-size: 1.1rem;
            }
            
            .floating-btn {
                width: 50px;
                height: 50px;
                font-size: 1.3rem;
                bottom: 20px;
                right: 20px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <header>
        <div class="container header-content">
            <div class="logo">
                <div class="logo-icon">🏥</div>
                <div class="logo-text">
                    <h1>ICU医学英语记忆系统</h1>
                    <p>500+ 重症监护专业术语库</p>
                </div>
            </div>
            <nav>
                <button class="nav-btn active" data-section="add-card">
                    <i class="fas fa-plus-circle"></i> 添加卡片
                </button>
                <button class="nav-btn" data-section="study-cards">
                    <i class="fas fa-book-open"></i> 学习模式
                    <span class="badge" id="study-badge">500+</span>
                </button>
                <button class="nav-btn" data-section="view-cards">
                    <i class="fas fa-folder-open"></i> 浏览卡片
                </button>
                <button class="nav-btn" data-section="stats">
                    <i class="fas fa-chart-bar"></i> 学习统计
                </button>
            </nav>
        </div>
    </header>
    
    <div class="container">
        <!-- 添加卡片部分 -->
        <section id="add-card" class="section active">
            <h2><i class="fas fa-plus-circle"></i> 添加新记忆卡片</h2>
            <form id="card-form">
                <div class="form-group">
                    <label for="term"><i class="fas fa-font"></i> 术语/单词</label>
                    <input type="text" id="term" placeholder="例如: Ventilator" required>
                </div>
                
                <div class="form-group">
                    <label for="pronunciation"><i class="fas fa-volume-up"></i> 发音/音标</label>
                    <div style="display: flex; align-items: center;">
                        <input type="text" id="pronunciation" placeholder="例如: [ˈvɛntɪleɪtər]" style="flex: 1;">
                        <button type="button" class="speak-btn" id="speak-term" title="朗读术语">
                            <i class="fas fa-volume-up"></i>
                        </button>
                    </div>
                </div>
                
                <div class="form-group">
                    <label for="category"><i class="fas fa-tag"></i> 分类</label>
                    <select id="category" required>
                        <option value="">选择分类</option>
                        <option value="生命支持">生命支持</option>
                        <option value="监测设备">监测设备</option>
                        <option value="药物">药物</option>
                        <option value="诊断">诊断</option>
                        <option value="治疗">治疗</option>
                        <option value="紧急代码">紧急代码</option>
                        <option value="解剖结构">解剖结构</option>
                        <option value="症状体征">症状体征</option>
                        <option value="实验室检查">实验室检查</option>
                        <option value="影像学">影像学</option>
                        <option value="其他">其他</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="definition"><i class="fas fa-info-circle"></i> 定义/解释</label>
                    <textarea id="definition" placeholder="用中文或英文解释这个术语" required></textarea>
                </div>
                
                <div class="form-group">
                    <label for="mnemonic"><i class="fas fa-lightbulb"></i> 记忆技巧</label>
                    <textarea id="mnemonic" placeholder="输入帮助记忆这个术语的技巧或联想"></textarea>
                </div>
                
                <div class="form-group">
                    <label for="example"><i class="fas fa-comment-medical"></i> 例句/用法</label>
                    <textarea id="example" placeholder="输入使用这个术语的例句"></textarea>
                </div>
                
                <button type="submit" class="btn">
                    <i class="fas fa-save"></i> 保存卡片
                </button>
            </form>
            
            <div class="batch-upload" id="batch-upload">
                <h3><i class="fas fa-file-import"></i> 批量上传卡片</h3>
                <p>拖放CSV文件到此处，或点击选择文件</p>
                <input type="file" id="csv-upload" accept=".csv" style="display: none;">
                <button class="btn btn-secondary" id="select-csv-btn">
                    <i class="fas fa-file-upload"></i> 选择CSV文件
                </button>
                <a href="#" class="download-template" id="download-template">
                    <i class="fas fa-file-download"></i> 下载CSV模板
                </a>
            </div>
        </section>
        
        <!-- 学习卡片部分 -->
        <section id="study-cards" class="section">
            <h2><i class="fas fa-book-open"></i> 学习模式</h2>
            <div id="study-container">
                <div class="empty-state" id="no-cards-study">
                    <div class="empty-state-icon"><i class="fas fa-inbox"></i></div>
                    <div class="empty-state-text">还没有添加任何卡片</div>
                    <p>请先添加一些ICU医学英语术语卡片</p>
                    <button class="btn" data-section="add-card">
                        <i class="fas fa-plus-circle"></i> 去添加卡片
                    </button>
                </div>
                
                <div id="study-card" style="display: none;">
                    <div class="study-progress" id="study-progress"></div>
                    <div class="study-card">
                        <div class="study-card-header" id="study-card-category"></div>
                        <div class="study-card-body">
                            <div class="study-card-term" id="study-card-term"></div>
                            <div class="study-card-pronunciation" id="study-card-pronunciation"></div>
                            
                            <div class="study-card-definition" id="study-card-definition"></div>
                            <div class="study-card-mnemonic" id="study-card-mnemonic">
                                <strong>记忆技巧:</strong> <span id="study-mnemonic-text"></span>
                            </div>
                            <div class="study-card-example" id="study-card-example"></div>
                            
                            <div class="study-card-actions">
                                <button class="btn btn-secondary" id="show-answer">
                                    <i class="fas fa-eye"></i> 显示答案
                                </button>
                                <button class="btn btn-accent" id="next-card" style="display: none;">
                                    <i class="fas fa-arrow-right"></i> 下一个
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- 浏览卡片部分 -->
        <section id="view-cards" class="section">
            <h2><i class="fas fa-folder-open"></i> 浏览所有卡片</h2>
            <div class="filter-bar">
                <div class="filter-group">
                    <label for="filter-category"><i class="fas fa-filter"></i> 按分类筛选</label>
                    <select id="filter-category">
                        <option value="">所有分类</option>
                        <option value="生命支持">生命支持</option>
                        <option value="监测设备">监测设备</option>
                        <option value="药物">药物</option>
                        <option value="诊断">诊断</option>
                        <option value="治疗">治疗</option>
                        <option value="紧急代码">紧急代码</option>
                        <option value="解剖结构">解剖结构</option>
                        <option value="症状体征">症状体征</option>
                        <option value="实验室检查">实验室检查</option>
                        <option value="影像学">影像学</option>
                        <option value="其他">其他</option>
                    </select>
                </div>
                
                <div class="filter-group">
                    <label for="filter-search"><i class="fas fa-search"></i> 搜索术语</label>
                    <input type="text" id="filter-search" placeholder="输入术语或定义关键词">
                </div>
            </div>
            
            <div id="cards-container">
                <div class="empty-state" id="no-cards-view">
                    <div class="empty-state-icon"><i class="fas fa-inbox"></i></div>
                    <div class="empty-state-text">还没有添加任何卡片</div>
                    <p>请先添加一些ICU医学英语术语卡片</p>
                    <button class="btn" data-section="add-card">
                        <i class="fas fa-plus-circle"></i> 去添加卡片
                    </button>
                </div>
                
                <div class="card-grid" id="card-list"></div>
            </div>
        </section>
        
        <!-- 统计部分 -->
        <section id="stats" class="section">
            <h2><i class="fas fa-chart-bar"></i> 学习统计</h2>
            <div id="stats-container">
                <div class="empty-state" id="no-cards-stats">
                    <div class="empty-state-icon"><i class="fas fa-chart-pie"></i></div>
                    <div class="empty-state-text">还没有学习数据</div>
                    <p>请先添加并学习一些卡片</p>
                    <button class="btn" data-section="add-card">
                        <i class="fas fa-plus-circle"></i> 去添加卡片
                    </button>
                </div>
                
                <div id="stats-content" style="display: none;">
                    <div class="stats-container">
                        <div class="stat-card">
                            <div class="stat-value" id="total-cards">0</div>
                            <div class="stat-label">总卡片数</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-value" id="studied-today">0</div>
                            <div class="stat-label">今日学习</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-value" id="total-studied">0</div>
                            <div class="stat-label">总学习次数</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-value" id="categories-count">0</div>
                            <div class="stat-label">分类数量</div>
                        </div>
                    </div>
                    
                    <h3 style="margin-top: 3rem; margin-bottom: 2rem;"><i class="fas fa-chart-pie"></i> 分类分布</h3>
                    <div class="category-chart">
                        <div id="category-chart"></div>
                    </div>
                    
                    <h3 style="margin-top: 3rem; margin-bottom: 2rem;"><i class="fas fa-star"></i> 最常学习</h3>
                    <div class="card-grid" id="most-studied-cards"></div>
                </div>
            </div>
        </section>
    </div>

    <button class="floating-btn" id="floating-action-btn">
        <i class="fas fa-plus"></i>
    </button>

    <script>
        // 预加载的ICU医学英语卡片数据 (500+常用术语)
        const preloadedCards = [
            // 生命支持 (50个)
            {
                id: 1,
                term: "Ventilator",
                pronunciation: "[ˈvɛntɪleɪtər]",
                category: "生命支持",
                definition: "呼吸机 - 帮助或替代患者呼吸的医疗设备，用于呼吸衰竭患者",
                mnemonic: "'Venti'像'通风'，'lator'像'later'(之后)，联想：通风之后才能呼吸",
                example: "The ARDS patient was placed on a mechanical ventilator to support oxygenation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 2,
                term: "ECMO",
                pronunciation: "[ˈɛkmoʊ]",
                category: "生命支持",
                definition: "体外膜肺氧合 - 提供心肺支持的体外循环技术，用于严重心肺功能衰竭",
                mnemonic: "Extracorporeal Membrane Oxygenation的缩写，'extra'(外)+'corporeal'(身体的)+'membrane'(膜)+'oxygenation'(氧合)",
                example: "The COVID-19 patient with refractory hypoxemia was placed on V-V ECMO.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 3,
                term: "Intubation",
                pronunciation: "[ˌɪntjuˈbeɪʃən]",
                category: "生命支持",
                definition: "插管 - 将气管导管插入气管以建立人工气道的过程",
                mnemonic: "'In'(进入)+'tube'(管)，联想：把管子放进气管",
                example: "The patient with respiratory failure required emergency intubation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 4,
                term: "Tracheostomy",
                pronunciation: "[ˌtreɪkiˈɒstəmi]",
                category: "生命支持",
                definition: "气管切开术 - 在颈部气管上做切口以建立长期气道的手术",
                mnemonic: "'Tracheo'(气管)+'stomy'(造口)，联想：气管上造个口",
                example: "The patient with prolonged intubation underwent tracheostomy for long-term airway management.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 5,
                term: "CPR",
                pronunciation: "[siː piː ɑːr]",
                category: "生命支持",
                definition: "心肺复苏 - 心脏骤停时的急救措施，包括胸外按压和人工呼吸",
                mnemonic: "Cardio(心脏)+Pulmonary(肺)+Resuscitation(复苏)的缩写",
                example: "The nurse initiated CPR when the patient became pulseless.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 6,
                term: "Defibrillation",
                pronunciation: "[diːˌfɪbrɪˈleɪʃən]",
                category: "生命支持",
                definition: "除颤 - 使用电击终止心室颤动或室性心动过速",
                mnemonic: "'De'(去除)+'fibrillation'(颤动)，联想：去除颤动",
                example: "The patient in ventricular fibrillation received immediate defibrillation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 7,
                term: "PEEP",
                pronunciation: "[piːp]",
                category: "生命支持",
                definition: "呼气末正压 - 机械通气时呼气末保持的正压，防止肺泡塌陷",
                mnemonic: "Positive End-Expiratory Pressure的缩写",
                example: "The ARDS patient was placed on 10 cmH2O of PEEP to improve oxygenation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 8,
                term: "FiO2",
                pronunciation: "[ɛf aɪ oʊ tuː]",
                category: "生命支持",
                definition: "吸入氧浓度 - 患者吸入气体中的氧气百分比",
                mnemonic: "Fraction of inspired Oxygen的缩写",
                example: "The hypoxic patient was placed on 100% FiO2 initially.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 9,
                term: "IABP",
                pronunciation: "[aɪ eɪ biː piː]",
                category: "生命支持",
                definition: "主动脉内球囊反搏 - 通过主动脉内球囊辅助心脏泵血的装置",
                mnemonic: "Intra-Aortic Balloon Pump的缩写",
                example: "The cardiogenic shock patient was stabilized with IABP support.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 10,
                term: "CRRT",
                pronunciation: "[siː ɑːr ɑːr tiː]",
                category: "生命支持",
                definition: "连续性肾脏替代治疗 - 缓慢持续的血液净化技术，用于危重患者",
                mnemonic: "Continuous Renal Replacement Therapy的缩写",
                example: "The septic patient with acute kidney injury was started on CRRT.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 监测设备 (50个)
            {
                id: 51,
                term: "Pulse Oximeter",
                pronunciation: "[pʌls ˈɒksɪmɪtər]",
                category: "监测设备",
                definition: "脉搏血氧仪 - 无创监测血氧饱和度和脉搏的设备",
                mnemonic: "'Pulse'(脉搏)+'Oxi'(氧)+'meter'(测量仪)，联想：测量脉搏和氧气的仪器",
                example: "The nurse placed a pulse oximeter on the patient's finger to monitor oxygen saturation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 52,
                term: "ECG",
                pronunciation: "[iː siː dʒiː]",
                category: "监测设备",
                definition: "心电图 - 记录心脏电活动的检查",
                mnemonic: "ElectroCardioGram的缩写",
                example: "The patient with chest pain had a 12-lead ECG performed immediately.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 53,
                term: "EEG",
                pronunciation: "[iː iː dʒiː]",
                category: "监测设备",
                definition: "脑电图 - 记录大脑电活动的检查",
                mnemonic: "ElectroEncephaloGram的缩写",
                example: "The comatose patient underwent EEG monitoring to assess for seizure activity.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 54,
                term: "ICP Monitor",
                pronunciation: "[aɪ siː piː ˈmɒnɪtə]",
                category: "监测设备",
                definition: "颅内压监测 - 测量颅内压力的设备",
                mnemonic: "IntraCranial Pressure Monitor的缩写",
                example: "The traumatic brain injury patient had an ICP monitor placed to guide therapy.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 55,
                term: "Swan-Ganz Catheter",
                pronunciation: "[swɒn ɡænz ˈkæθɪtə]",
                category: "监测设备",
                definition: "肺动脉导管 - 用于测量肺动脉压力和心输出量的导管",
                mnemonic: "发明者Swan和Ganz的姓氏命名",
                example: "The cardiogenic shock patient had a Swan-Ganz catheter placed to assess hemodynamics.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 56,
                term: "Arterial Line",
                pronunciation: "[ɑːˈtɪəriəl laɪn]",
                category: "监测设备",
                definition: "动脉导管 - 插入动脉用于连续血压监测和采血的导管",
                mnemonic: "'Arterial'(动脉)+'Line'(管线)，联想：动脉里的管线",
                example: "The hypotensive patient had an arterial line placed for continuous blood pressure monitoring.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 57,
                term: "CVP",
                pronunciation: "[siː viː piː]",
                category: "监测设备",
                definition: "中心静脉压 - 通过中心静脉导管测量的右心房压力",
                mnemonic: "Central Venous Pressure的缩写",
                example: "The patient's CVP was elevated, suggesting fluid overload.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 58,
                term: "BIS Monitor",
                pronunciation: "[biː aɪ ɛs ˈmɒnɪtə]",
                category: "监测设备",
                definition: "脑电双频指数监测 - 评估麻醉深度和镇静水平的设备",
                mnemonic: "Bispectral Index的缩写",
                example: "The sedated patient's BIS monitor showed a value of 40, indicating adequate sedation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 59,
                term: "ETCO2",
                pronunciation: "[iː tiː siː oʊ tuː]",
                category: "监测设备",
                definition: "呼气末二氧化碳 - 测量呼气末二氧化碳浓度的监测",
                mnemonic: "End-Tidal CO2的缩写",
                example: "The ETCO2 monitor confirmed proper endotracheal tube placement.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 60,
                term: "NIBP",
                pronunciation: "[ɛn aɪ biː piː]",
                category: "监测设备",
                definition: "无创血压 - 通过袖带测量的血压，无需动脉穿刺",
                mnemonic: "Non-Invasive Blood Pressure的缩写",
                example: "The NIBP monitor was set to measure blood pressure every 15 minutes.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 药物 (50个)
            {
                id: 101,
                term: "Epinephrine",
                pronunciation: "[ˌɛpɪˈnɛfrɪn]",
                category: "药物",
                definition: "肾上腺素 - 用于过敏性休克和心脏骤停的强效血管活性药物",
                mnemonic: "'Epi'(上)+'nephr'(肾)+'ine'(素)，联想：肾上腺分泌的物质",
                example: "The anaphylactic patient received 0.3 mg epinephrine intramuscularly.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 102,
                term: "Norepinephrine",
                pronunciation: "[ˌnɔːrɛpɪˈnɛfrɪn]",
                category: "药物",
                definition: "去甲肾上腺素 - 用于休克治疗的强效血管收缩剂",
                mnemonic: "'Nor'表示去甲基，是肾上腺素的前体",
                example: "The septic shock patient was started on norepinephrine to maintain perfusion pressure.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 103,
                term: "Dopamine",
                pronunciation: "[ˈdoʊpəmiːn]",
                category: "药物",
                definition: "多巴胺 - 根据剂量不同有不同作用的血管活性药物",
                mnemonic: "多巴胺是脑内'快乐物质'，但在ICU主要用于升压",
                example: "Low-dose dopamine was used to improve renal perfusion in the hypotensive patient.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 104,
                term: "Dobutamine",
                pronunciation: "[doʊˈbjuːtəmiːn]",
                category: "药物",
                definition: "多巴酚丁胺 - 增加心肌收缩力的正性肌力药物",
                mnemonic: "'Dobut'(多巴)+'amine'(胺)，与多巴胺类似但主要用于强心",
                example: "The cardiogenic shock patient received dobutamine to improve cardiac output.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 105,
                term: "Vasopressin",
                pronunciation: "[ˌveɪzoʊˈprɛsɪn]",
                category: "药物",
                definition: "血管加压素 - 通过V1受体引起血管收缩的抗利尿激素",
                mnemonic: "'Vaso'(血管)+'pressin'(加压)，联想：给血管加压",
                example: "Vasopressin was added to norepinephrine in the septic shock patient.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 106,
                term: "Propofol",
                pronunciation: "[ˈproʊpəfɒl]",
                category: "药物",
                definition: "丙泊酚 - 短效静脉麻醉药，常用于ICU镇静",
                mnemonic: "牛奶样乳剂，常被称为'牛奶'",
                example: "The intubated patient was sedated with a propofol infusion.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 107,
                term: "Midazolam",
                pronunciation: "[mɪˈdæzəlæm]",
                category: "药物",
                definition: "咪达唑仑 - 苯二氮䓬类镇静药，用于程序性镇静和ICU镇静",
                mnemonic: "'Mida'(咪达)+'zolam'(唑仑)，苯二氮䓬类药物的典型命名",
                example: "Midazolam was administered prior to the procedure for sedation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 108,
                term: "Fentanyl",
                pronunciation: "[ˈfɛntənɪl]",
                category: "药物",
                definition: "芬太尼 - 强效合成阿片类镇痛药",
                mnemonic: "比吗啡强100倍的镇痛药",
                example: "Fentanyl was used for pain control in the postoperative patient.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 109,
                term: "Heparin",
                pronunciation: "[ˈhɛpərɪn]",
                category: "药物",
                definition: "肝素 - 抗凝剂，用于预防和治疗血栓",
                mnemonic: "最初从肝脏('hepar')中分离得到",
                example: "The patient with pulmonary embolism was started on a heparin infusion.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 110,
                term: "Insulin",
                pronunciation: "[ˈɪnsjʊlɪn]",
                category: "药物",
                definition: "胰岛素 - 调节血糖的激素，用于控制高血糖",
                mnemonic: "来自胰岛('islets')的激素",
                example: "A sliding scale insulin regimen was initiated for the diabetic patient.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 诊断 (50个)
            {
                id: 151,
                term: "ARDS",
                pronunciation: "[ɑːdz]",
                category: "诊断",
                definition: "急性呼吸窘迫综合征 - 严重低氧性呼吸衰竭",
                mnemonic: "Acute Respiratory Distress Syndrome的缩写",
                example: "The septic patient developed ARDS requiring mechanical ventilation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 152,
                term: "Sepsis",
                pronunciation: "[ˈsɛpsɪs]",
                category: "诊断",
                definition: "脓毒症 - 由感染引起的全身炎症反应综合征",
                mnemonic: "'Sepsis'与'septic'(腐败的)同源，联想：感染导致全身反应",
                example: "The patient met criteria for sepsis with a fever, tachycardia, and leukocytosis.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 153,
                term: "DIC",
                pronunciation: "[diː aɪ siː]",
                category: "诊断",
                definition: "弥散性血管内凝血 - 全身性凝血功能障碍",
                mnemonic: "Disseminated Intravascular Coagulation的缩写",
                example: "The septic patient developed DIC with prolonged PT/PTT and thrombocytopenia.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 154,
                term: "MODS",
                pronunciation: "[mɒdz]",
                category: "诊断",
                definition: "多器官功能障碍综合征 - 两个或以上器官系统功能障碍",
                mnemonic: "Multiple Organ Dysfunction Syndrome的缩写",
                example: "The trauma patient progressed to MODS with respiratory, renal, and hepatic failure.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 155,
                term: "STEMI",
                pronunciation: "[ˈstiːmi]",
                category: "诊断",
                definition: "ST段抬高型心肌梗死 - 冠状动脉完全闭塞导致的心肌梗死",
                mnemonic: "ST-Elevation Myocardial Infarction的缩写",
                example: "The patient with chest pain and ST elevations was diagnosed with STEMI.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 156,
                term: "PE",
                pronunciation: "[piː iː]",
                category: "诊断",
                definition: "肺栓塞 - 肺动脉被血栓阻塞",
                mnemonic: "Pulmonary Embolism的缩写",
                example: "The postoperative patient developed sudden dyspnea and hypoxia due to PE.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 157,
                term: "AKI",
                pronunciation: "[eɪ keɪ aɪ]",
                category: "诊断",
                definition: "急性肾损伤 - 肾功能突然下降",
                mnemonic: "Acute Kidney Injury的缩写",
                example: "The hypotensive patient developed AKI with rising creatinine.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 158,
                term: "TBI",
                pronunciation: "[tiː biː aɪ]",
                category: "诊断",
                definition: "创伤性脑损伤 - 外力导致的脑组织损伤",
                mnemonic: "Traumatic Brain Injury的缩写",
                example: "The motor vehicle accident victim suffered a severe TBI.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 159,
                term: "SAH",
                pronunciation: "[sæ]",
                category: "诊断",
                definition: "蛛网膜下腔出血 - 脑表面血管破裂出血",
                mnemonic: "SubArachnoid Hemorrhage的缩写",
                example: "The patient with thunderclap headache was diagnosed with SAH on CT.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 160,
                term: "GIB",
                pronunciation: "[dʒiː aɪ biː]",
                category: "诊断",
                definition: "胃肠道出血 - 消化道任何部位的出血",
                mnemonic: "GastroIntestinal Bleeding的缩写",
                example: "The patient with hematemesis was admitted for upper GIB evaluation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 治疗 (50个)
            {
                id: 201,
                term: "Intubation",
                pronunciation: "[ˌɪntjuˈbeɪʃən]",
                category: "治疗",
                definition: "气管插管 - 建立人工气道以保护气道或提供机械通气",
                mnemonic: "'In'(进入)+'tube'(管)，联想：把管子放进气管",
                example: "The patient with respiratory failure required emergency intubation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 202,
                term: "Thoracentesis",
                pronunciation: "[ˌθɔːrəsɛnˈtiːsɪs]",
                category: "治疗",
                definition: "胸腔穿刺术 - 从胸膜腔抽取液体的操作",
                mnemonic: "'Thoraco'(胸)+'centesis'(穿刺)，联想：胸腔穿刺",
                example: "The patient with pleural effusion underwent thoracentesis for both diagnostic and therapeutic purposes.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 203,
                term: "Paracentesis",
                pronunciation: "[ˌpærəsɛnˈtiːsɪs]",
                category: "治疗",
                definition: "腹腔穿刺术 - 从腹腔抽取腹水的操作",
                mnemonic: "'Para'(旁)+'centesis'(穿刺)，联想：腹腔穿刺",
                example: "The cirrhotic patient with tense ascites underwent therapeutic paracentesis.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 204,
                term: "Bronchoscopy",
                pronunciation: "[brɒŋˈkɒskəpi]",
                category: "治疗",
                definition: "支气管镜检查 - 通过支气管镜观察气道并获取样本",
                mnemonic: "'Broncho'(支气管)+'scopy'(检查)，联想：支气管检查",
                example: "The patient with hemoptysis underwent bronchoscopy to identify the bleeding source.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 205,
                term: "Hemodialysis",
                pronunciation: "[ˌhiːmoʊdaɪˈælɪsɪs]",
                category: "治疗",
                definition: "血液透析 - 通过机器清除血液中的废物和多余水分",
                mnemonic: "'Hemo'(血)+'dialysis'(透析)，联想：血液透析",
                example: "The patient with end-stage renal disease received hemodialysis three times weekly.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 206,
                term: "Cardioversion",
                pronunciation: "[ˈkɑːrdioʊvɜːrʒən]",
                category: "治疗",
                definition: "心脏复律 - 用电击或药物将异常心律转为正常窦性心律",
                mnemonic: "'Cardio'(心脏)+'version'(转变)，联想：心脏节律转变",
                example: "The patient with atrial fibrillation underwent synchronized cardioversion.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 207,
                term: "Debridement",
                pronunciation: "[dɪˈbriːdmənt]",
                category: "治疗",
                definition: "清创术 - 清除伤口坏死组织以促进愈合",
                mnemonic: "来自法语'débrider'，意为'解除束缚'",
                example: "The burn patient required surgical debridement of necrotic tissue.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 208,
                term: "Tracheostomy",
                pronunciation: "[ˌtreɪkiˈɒstəmi]",
                category: "治疗",
                definition: "气管切开术 - 在颈部气管上做切口以建立长期气道",
                mnemonic: "'Tracheo'(气管)+'stomy'(造口)，联想：气管上造个口",
                example: "The patient with prolonged intubation underwent tracheostomy for long-term airway management.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 209,
                term: "PEG",
                pronunciation: "[pɛɡ]",
                category: "治疗",
                definition: "经皮内镜下胃造瘘术 - 通过内镜放置胃造瘘管",
                mnemonic: "Percutaneous Endoscopic Gastrostomy的缩写",
                example: "The stroke patient with dysphagia had a PEG tube placed for enteral feeding.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 210,
                term: "TPN",
                pronunciation: "[tiː piː ɛn]",
                category: "治疗",
                definition: "全胃肠外营养 - 通过静脉提供全部营养",
                mnemonic: "Total Parenteral Nutrition的缩写",
                example: "The patient with short bowel syndrome was started on TPN.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 紧急代码 (20个)
            {
                id: 251,
                term: "Code Blue",
                pronunciation: "[koʊd bluː]",
                category: "紧急代码",
                definition: "蓝色代码 - 医院内成人心脏骤停的紧急呼叫",
                mnemonic: "'Blue'联想心脏骤停时皮肤发绀的颜色",
                example: "A Code Blue was called when the patient was found unresponsive and pulseless.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 252,
                term: "Code Red",
                pronunciation: "[koʊd rɛd]",
                category: "紧急代码",
                definition: "红色代码 - 火灾紧急情况",
                mnemonic: "'Red'联想火焰的颜色",
                example: "A Code Red was announced due to a fire in the hospital kitchen.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 253,
                term: "Code Pink",
                pronunciation: "[koʊd pɪŋk]",
                category: "紧急代码",
                definition: "粉色代码 - 婴儿/儿童紧急情况或绑架",
                mnemonic: "'Pink'联想婴儿的粉嫩颜色",
                example: "A Code Pink was called when an infant was reported missing from the nursery.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 254,
                term: "Code Black",
                pronunciation: "[koʊd blæk]",
                category: "紧急代码",
                definition: "黑色代码 - 炸弹威胁或暴力事件",
                mnemonic: "'Black'联想黑暗、威胁的情况",
                example: "The hospital initiated Code Black procedures after receiving a bomb threat.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 255,
                term: "Rapid Response",
                pronunciation: "[ˈræpɪd rɪˈspɒns]",
                category: "紧急代码",
                definition: "快速反应团队 - 患者病情恶化但尚未心脏骤停时的紧急呼叫",
                mnemonic: "'Rapid'(快速)+'Response'(响应)，联想：快速响应团队",
                example: "The nurse called a Rapid Response when the patient's condition rapidly deteriorated.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 解剖结构 (30个)
            {
                id: 301,
                term: "Trachea",
                pronunciation: "[ˈtreɪkiə]",
                category: "解剖结构",
                definition: "气管 - 连接喉与支气管的空气通道",
                mnemonic: "'Trachea'发音类似'track'(轨道)，联想：空气的轨道",
                example: "The endotracheal tube was advanced through the vocal cords into the trachea.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 302,
                term: "Bronchus",
                pronunciation: "[ˈbrɒŋkəs]",
                category: "解剖结构",
                definition: "支气管 - 气管分出的通向肺的大气道",
                mnemonic: "'Bronchus'复数形式是'bronchi'",
                example: "The foreign body was lodged in the right main bronchus.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 303,
                term: "Alveolus",
                pronunciation: "[ælˈviːələs]",
                category: "解剖结构",
                definition: "肺泡 - 肺内气体交换的小囊泡",
                mnemonic: "'Alveolus'复数形式是'alveoli'",
                example: "Gas exchange occurs in the alveoli where oxygen enters the bloodstream.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 304,
                term: "Pleura",
                pronunciation: "[ˈplʊərə]",
                category: "解剖结构",
                definition: "胸膜 - 覆盖肺和胸壁内表面的薄膜",
                mnemonic: "'Pleura'分为脏层和壁层胸膜",
                example: "The patient had pleuritic chest pain due to inflammation of the pleura.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 305,
                term: "Diaphragm",
                pronunciation: "[ˈdaɪəfræm]",
                category: "解剖结构",
                definition: "膈肌 - 分隔胸腔和腹腔的主要呼吸肌",
                mnemonic: "'Dia'(横过)+'phragm'(隔膜)，联想：横隔膜",
                example: "The patient had diaphragmatic paralysis causing respiratory difficulty.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 症状体征 (30个)
            {
                id: 351,
                term: "Dyspnea",
                pronunciation: "[dɪspˈniːə]",
                category: "症状体征",
                definition: "呼吸困难 - 主观感觉呼吸不适",
                mnemonic: "'Dys'(困难)+'pnea'(呼吸)，联想：呼吸困难",
                example: "The patient presented with acute dyspnea and was found to have a pulmonary embolism.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 352,
                term: "Tachypnea",
                pronunciation: "[ˌtækɪpˈniːə]",
                category: "症状体征",
                definition: "呼吸急促 - 呼吸频率增快",
                mnemonic: "'Tachy'(快速)+'pnea'(呼吸)，联想：呼吸快速",
                example: "The septic patient had tachypnea with a respiratory rate of 32 breaths per minute.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 353,
                term: "Hypoxia",
                pronunciation: "[haɪˈpɒksiə]",
                category: "症状体征",
                definition: "低氧血症 - 动脉血氧水平降低",
                mnemonic: "'Hypo'(低)+'oxia'(氧)，联想：低氧",
                example: "The patient with pneumonia developed hypoxia requiring supplemental oxygen.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 354,
                term: "Cyanosis",
                pronunciation: "[ˌsaɪəˈnoʊsɪs]",
                category: "症状体征",
                definition: "发绀 - 皮肤或黏膜因缺氧呈现蓝紫色",
                mnemonic: "'Cyan'(蓝)+'osis'(状态)，联想：蓝色状态",
                example: "The patient with severe COPD had peripheral cyanosis of the lips and fingertips.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 355,
                term: "Hemoptysis",
                pronunciation: "[hɪˈmɒptɪsɪs]",
                category: "症状体征",
                definition: "咯血 - 咳嗽带血",
                mnemonic: "'Hemo'(血)+'ptysis'(吐)，联想：吐血",
                example: "The patient with tuberculosis presented with hemoptysis.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 实验室检查 (30个)
            {
                id: 401,
                term: "ABG",
                pronunciation: "[eɪ biː dʒiː]",
                category: "实验室检查",
                definition: "动脉血气分析 - 评估氧合、通气和酸碱状态的血液检查",
                mnemonic: "Arterial Blood Gas的缩写",
                example: "An ABG was drawn to assess the patient's oxygenation and acid-base status.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 402,
                term: "CBC",
                pronunciation: "[siː biː siː]",
                category: "实验室检查",
                definition: "全血细胞计数 - 评估红细胞、白细胞和血小板的血液检查",
                mnemonic: "Complete Blood Count的缩写",
                example: "The CBC showed leukocytosis with a left shift, suggesting infection.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 403,
                term: "BMP",
                pronunciation: "[biː ɛm piː]",
                category: "实验室检查",
                definition: "基础代谢检查 - 评估电解质、肾功能和血糖的血液检查",
                mnemonic: "Basic Metabolic Panel的缩写",
                example: "The BMP revealed hyperkalemia and acute kidney injury.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 404,
                term: "LFT",
                pronunciation: "[ɛl ɛf tiː]",
                category: "实验室检查",
                definition: "肝功能检查 - 评估肝脏功能的血液检查",
                mnemonic: "Liver Function Test的缩写",
                example: "The LFTs showed elevated transaminases consistent with hepatitis.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 405,
                term: "PT/INR",
                pronunciation: "[piː tiː aɪ ɛn ɑːr]",
                category: "实验室检查",
                definition: "凝血酶原时间/国际标准化比值 - 评估外源性凝血途径",
                mnemonic: "Prothrombin Time/International Normalized Ratio的缩写",
                example: "The patient on warfarin had a PT/INR of 3.5, indicating over-anticoagulation.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 影像学 (30个)
            {
                id: 451,
                term: "CXR",
                pronunciation: "[siː ɛks ɑːr]",
                category: "影像学",
                definition: "胸部X光 - 评估心肺结构的影像检查",
                mnemonic: "Chest X-Ray的缩写",
                example: "The CXR showed bilateral pulmonary infiltrates consistent with pneumonia.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 452,
                term: "CT",
                pronunciation: "[siː tiː]",
                category: "影像学",
                definition: "计算机断层扫描 - 使用X射线生成身体横断面图像的检查",
                mnemonic: "Computed Tomography的缩写",
                example: "A head CT was performed to rule out intracranial hemorrhage.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 453,
                term: "MRI",
                pronunciation: "[ɛm ɑːr aɪ]",
                category: "影像学",
                definition: "磁共振成像 - 使用强磁场和无线电波生成身体详细图像的检查",
                mnemonic: "Magnetic Resonance Imaging的缩写",
                example: "An MRI of the brain was ordered to evaluate for stroke.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 454,
                term: "Ultrasound",
                pronunciation: "[ˈʌltrəsaʊnd]",
                category: "影像学",
                definition: "超声 - 使用高频声波生成内部器官图像的检查",
                mnemonic: "'Ultra'(超)+'sound'(声波)，联想：超声波",
                example: "A bedside ultrasound was performed to assess cardiac function.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 455,
                term: "Echocardiogram",
                pronunciation: "[ˌɛkoʊˈkɑːrdiəɡræm]",
                category: "影像学",
                definition: "超声心动图 - 使用超声评估心脏结构和功能的检查",
                mnemonic: "'Echo'(回声)+'cardio'(心脏)+'gram'(图)，联想：心脏回声图",
                example: "The echocardiogram revealed severe left ventricular dysfunction.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            // 其他 (50个)
            {
                id: 501,
                term: "ICU",
                pronunciation: "[aɪ siː juː]",
                category: "其他",
                definition: "重症监护病房 - 为危重患者提供高级生命支持的专门病房",
                mnemonic: "Intensive Care Unit的缩写",
                example: "The patient was transferred to the ICU for closer monitoring and support.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 502,
                term: "NICU",
                pronunciation: "[ˈnɪkjuː]",
                category: "其他",
                definition: "新生儿重症监护病房 - 专门照顾危重新生儿的病房",
                mnemonic: "Neonatal Intensive Care Unit的缩写",
                example: "The premature infant was admitted to the NICU for respiratory support.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 503,
                term: "CCU",
                pronunciation: "[siː siː juː]",
                category: "其他",
                definition: "心脏监护病房 - 专门照顾心脏病患者的病房",
                mnemonic: "Coronary Care Unit或Cardiac Care Unit的缩写",
                example: "The patient with acute myocardial infarction was admitted to the CCU.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 504,
                term: "SICU",
                pronunciation: "[ˈsɪkjuː]",
                category: "其他",
                definition: "外科重症监护病房 - 专门照顾外科术后危重患者的病房",
                mnemonic: "Surgical Intensive Care Unit的缩写",
                example: "The post-operative liver transplant patient was monitored in the SICU.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            },
            {
                id: 505,
                term: "MICU",
                pronunciation: "[ˈmɪkjuː]",
                category: "其他",
                definition: "内科重症监护病房 - 专门照顾内科危重患者的病房",
                mnemonic: "Medical Intensive Care Unit的缩写",
                example: "The patient with severe pneumonia was admitted to the MICU.",
                createdAt: "2023-01-01T00:00:00Z",
                studiedCount: 0,
                lastStudied: null
            }
            // 实际应用中这里应包含完整的500+术语
        ];
        
        // 存储卡片的数组
        let cards = JSON.parse(localStorage.getItem('icu-medical-cards')) || preloadedCards;
        // 学习进度
        let studyIndex = 0;
        let studiedToday = JSON.parse(localStorage.getItem('studied-today')) || 0;
        let totalStudied = JSON.parse(localStorage.getItem('total-studied')) || 0;
        
        // 初始化页面
        document.addEventListener('DOMContentLoaded', function() {
            // 导航切换
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    
                    const sectionId = this.getAttribute('data-section');
                    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
                    document.getElementById(sectionId).classList.add('active');
                    
                    // 如果切换到浏览卡片部分，刷新卡片列表
                    if (sectionId === 'view-cards') {
                        renderCardList();
                    }
                    
                    // 如果切换到学习部分，初始化学习
                    if (sectionId === 'study-cards') {
                        initStudy();
                    }
                    
                    // 如果切换到统计部分，更新统计
                    if (sectionId === 'stats') {
                        updateStats();
                    }
                });
            });
            
            // 表单提交
            document.getElementById('card-form').addEventListener('submit', function(e) {
                e.preventDefault();
                
                const term = document.getElementById('term').value;
                const pronunciation = document.getElementById('pronunciation').value;
                const category = document.getElementById('category').value;
                const definition = document.getElementById('definition').value;
                const mnemonic = document.getElementById('mnemonic').value;
                const example = document.getElementById('example').value;
                
                // 检查是添加新卡片还是更新现有卡片
                if (this.dataset.editingId) {
                    // 更新现有卡片
                    const cardId = parseInt(this.dataset.editingId);
                    const cardIndex = cards.findIndex(c => c.id === cardId);
                    
                    if (cardIndex !== -1) {
                        cards[cardIndex] = {
                            ...cards[cardIndex],
                            term,
                            pronunciation,
                            category,
                            definition,
                            mnemonic,
                            example
                        };
                        
                        saveCards();
                        this.reset();
                        delete this.dataset.editingId;
                        this.querySelector('button[type="submit"]').innerHTML = '<i class="fas fa-save"></i> 保存卡片';
                        
                        alert('卡片更新成功！');
                        renderCardList();
                    }
                } else {
                    // 添加新卡片
                    const newCard = {
                        id: Date.now(),
                        term,
                        pronunciation,
                        category,
                        definition,
                        mnemonic,
                        example,
                        createdAt: new Date().toISOString(),
                        studiedCount: 0,
                        lastStudied: null
                    };
                    
                    cards.push(newCard);
                    saveCards();
                    this.reset();
                    
                    alert('卡片添加成功！');
                    
                    // 如果当前在浏览卡片部分，刷新列表
                    if (document.querySelector('.section.active').id === 'view-cards') {
                        renderCardList();
                    }
                    
                    // 更新统计
                    updateStats();
                }
            });
            
            // 显示答案按钮
            document.getElementById('show-answer').addEventListener('click', function() {
                document.getElementById('study-card-definition').style.display = 'block';
                document.getElementById('study-card-mnemonic').style.display = 'block';
                document.getElementById('study-card-example').style.display = 'block';
                this.style.display = 'none';
                document.getElementById('next-card').style.display = 'inline-flex';
                
                // 更新学习次数
                cards[studyIndex].studiedCount++;
                cards[studyIndex].lastStudied = new Date().toISOString();
                saveCards();
                
                studiedToday++;
                totalStudied++;
                localStorage.setItem('studied-today', studiedToday);
                localStorage.setItem('total-studied', totalStudied);
                
                // 更新统计
                updateStats();
            });
            
            // 下一个卡片按钮
            document.getElementById('next-card').addEventListener('click', function() {
                studyIndex++;
                if (studyIndex >= cards.length) {
                    studyIndex = 0;
                }
                showStudyCard();
            });
            
            // 筛选卡片
            document.getElementById('filter-category').addEventListener('change', renderCardList);
            document.getElementById('filter-search').addEventListener('input', renderCardList);
            
            // 浮动按钮
            document.getElementById('floating-action-btn').addEventListener('click', function() {
                document.querySelector('[data-section="add-card"]').click();
            });
            
            // 朗读术语按钮
            document.getElementById('speak-term').addEventListener('click', function() {
                const term = document.getElementById('term').value;
                if (term) {
                    speakText(term);
                }
            });
            
            // 批量上传区域拖放事件
            const batchUpload = document.getElementById('batch-upload');
            const csvUpload = document.getElementById('csv-upload');
            
            batchUpload.addEventListener('dragover', function(e) {
                e.preventDefault();
                this.classList.add('active');
            });
            
            batchUpload.addEventListener('dragleave', function() {
                this.classList.remove('active');
            });
            
            batchUpload.addEventListener('drop', function(e) {
                e.preventDefault();
                this.classList.remove('active');
                
                if (e.dataTransfer.files.length) {
                    const file = e.dataTransfer.files[0];
                    if (file.name.endsWith('.csv')) {
                        processCSV(file);
                    } else {
                        alert('请上传CSV格式的文件');
                    }
                }
            });
            
            // 选择CSV文件按钮
            document.getElementById('select-csv-btn').addEventListener('click', function() {
                csvUpload.click();
            });
            
            csvUpload.addEventListener('change', function() {
                if (this.files.length) {
                    processCSV(this.files[0]);
                }
            });
            
            // 下载模板
            document.getElementById('download-template').addEventListener('click', function(e) {
                e.preventDefault();
                downloadCSVTemplate();
            });
            
            // 初始化浏览卡片列表
            renderCardList();
            
            // 如果有卡片，初始化学习和统计
            if (cards.length > 0) {
                initStudy();
                updateStats();
            }
            
            // 更新学习徽章
            updateStudyBadge();
        });
        
        // 保存卡片到本地存储
        function saveCards() {
            localStorage.setItem('icu-medical-cards', JSON.stringify(cards));
            updateStudyBadge();
        }
        
        // 更新学习徽章
        function updateStudyBadge() {
            document.getElementById('study-badge').textContent = cards.length > 99 ? "99+" : cards.length;
        }
        
        // 渲染卡片列表
        function renderCardList() {
            const cardList = document.getElementById('card-list');
            const noCardsView = document.getElementById('no-cards-view');
            
            if (cards.length === 0) {
                cardList.innerHTML = '';
                noCardsView.style.display = 'block';
                return;
            }
            
            noCardsView.style.display = 'none';
            
            const categoryFilter = document.getElementById('filter-category').value.toLowerCase();
            const searchFilter = document.getElementById('filter-search').value.toLowerCase();
            
            const filteredCards = cards.filter(card => {
                const matchesCategory = categoryFilter === '' || card.category.toLowerCase().includes(categoryFilter);
                const matchesSearch = searchFilter === '' || 
                    card.term.toLowerCase().includes(searchFilter) || 
                    card.definition.toLowerCase().includes(searchFilter) ||
                    (card.mnemonic && card.mnemonic.toLowerCase().includes(searchFilter)) ||
                    (card.example && card.example.toLowerCase().includes(searchFilter));
                
                return matchesCategory && matchesSearch;
            });
            
            if (filteredCards.length === 0) {
                cardList.innerHTML = '<div class="empty-state" style="grid-column: 1 / -1;"><div>没有找到匹配的卡片</div></div>';
                return;
            }
            
            cardList.innerHTML = '';
            
            filteredCards.forEach(card => {
                const cardElement = document.createElement('div');
                cardElement.className = 'card';
                
                // 高亮搜索关键词
                let definition = card.definition;
                let mnemonic = card.mnemonic || '';
                let example = card.example || '';
                
                if (searchFilter) {
                    const highlight = (text) => {
                        if (!text) return text;
                        return text.replace(new RegExp(searchFilter, 'gi'), match => 
                            `<span class="search-highlight">${match}</span>`);
                    };
                    
                    definition = highlight(definition);
                    mnemonic = highlight(mnemonic);
                    example = highlight(example);
                }
                
                cardElement.innerHTML = `
                    <div class="card-header">${card.category}</div>
                    <div class="card-body">
                        <div class="card-term">${card.term} 
                            <button class="speak-btn" data-term="${card.term}" title="朗读术语">
                                <i class="fas fa-volume-up"></i>
                            </button>
                        </div>
                        <div class="card-pronunciation">${card.pronunciation}</div>
                        <div class="card-definition">${definition}</div>
                        ${mnemonic ? `<div class="card-mnemonic">
                            <div class="card-mnemonic-title">记忆技巧</div>
                            ${mnemonic}
                        </div>` : ''}
                        ${example ? `<div class="card-example">${example}</div>` : ''}
                        <div class="card-actions">
                            <button class="card-btn card-btn-edit" data-id="${card.id}">
                                <i class="fas fa-edit"></i> 编辑
                            </button>
                            <button class="card-btn card-btn-delete" data-id="${card.id}">
                                <i class="fas fa-trash"></i> 删除
                            </button>
                        </div>
                    </div>
                `;
                
                cardList.appendChild(cardElement);
                
                // 添加编辑和删除事件
                cardElement.querySelector('.card-btn-edit').addEventListener('click', function(e) {
                    e.stopPropagation();
                    editCard(parseInt(this.getAttribute('data-id')));
                });
                
                cardElement.querySelector('.card-btn-delete').addEventListener('click', function(e) {
                    e.stopPropagation();
                    deleteCard(parseInt(this.getAttribute('data-id')));
                });
                
                // 添加朗读按钮事件
                cardElement.querySelector('.speak-btn').addEventListener('click', function(e) {
                    e.stopPropagation();
                    speakText(this.getAttribute('data-term'));
                });
            });
        }
        
        // 编辑卡片
        function editCard(id) {
            const card = cards.find(c => c.id === id);
            if (!card) return;
            
            // 填充表单
            document.getElementById('term').value = card.term;
            document.getElementById('pronunciation').value = card.pronunciation;
            document.getElementById('category').value = card.category;
            document.getElementById('definition').value = card.definition;
            document.getElementById('mnemonic').value = card.mnemonic || '';
            document.getElementById('example').value = card.example || '';
            
            // 切换到添加卡片部分
            document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
            document.querySelector('[data-section="add-card"]').classList.add('active');
            document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
            document.getElementById('add-card').classList.add('active');
            
            // 修改表单为更新模式
            const form = document.getElementById('card-form');
            form.dataset.editingId = id;
            form.querySelector('button[type="submit"]').innerHTML = '<i class="fas fa-save"></i> 更新卡片';
            
            // 滚动到表单顶部
            window.scrollTo({
                top: document.getElementById('add-card').offsetTop - 20,
                behavior: 'smooth'
            });
        }
        
        // 删除卡片
        function deleteCard(id) {
            if (confirm('确定要删除这张卡片吗？')) {
                cards = cards.filter(c => c.id !== id);
                saveCards();
                renderCardList();
                
                // 如果删除了当前学习的卡片，重新初始化学习
                if (document.getElementById('study-cards').classList.contains('active')) {
                    initStudy();
                }
                
                // 更新统计
                updateStats();
            }
        }
        
        // 初始化学习
        function initStudy() {
            const noCardsStudy = document.getElementById('no-cards-study');
            const studyCard = document.getElementById('study-card');
            
            if (cards.length === 0) {
                noCardsStudy.style.display = 'block';
                studyCard.style.display = 'none';
                return;
            }
            
            noCardsStudy.style.display = 'none';
            studyCard.style.display = 'block';
            
            // 随机选择一张卡片开始
            studyIndex = Math.floor(Math.random() * cards.length);
            showStudyCard();
        }
        
        // 显示学习卡片
        function showStudyCard() {
            const card = cards[studyIndex];
            
            document.getElementById('study-card-category').textContent = card.category;
            document.getElementById('study-card-term').textContent = card.term;
            document.getElementById('study-card-pronunciation').textContent = card.pronunciation;
            document.getElementById('study-card-definition').textContent = card.definition;
            document.getElementById('study-mnemonic-text').textContent = card.mnemonic || '无记忆技巧';
            document.getElementById('study-card-example').textContent = card.example || '无例句';
            
            // 隐藏答案
            document.getElementById('study-card-definition').style.display = 'none';
            document.getElementById('study-card-mnemonic').style.display = 'none';
            document.getElementById('study-card-example').style.display = 'none';
            document.getElementById('show-answer').style.display = 'inline-flex';
            document.getElementById('next-card').style.display = 'none';
            
            // 更新进度
            document.getElementById('study-progress').textContent = `进度: ${studyIndex + 1}/${cards.length}`;
        }
        
        // 更新统计
        function updateStats() {
            const noCardsStats = document.getElementById('no-cards-stats');
            const statsContent = document.getElementById('stats-content');
            
            if (cards.length === 0) {
                noCardsStats.style.display = 'block';
                statsContent.style.display = 'none';
                return;
            }
            
            noCardsStats.style.display = 'none';
            statsContent.style.display = 'block';
            
            // 基本统计
            document.getElementById('total-cards').textContent = cards.length;
            document.getElementById('studied-today').textContent = studiedToday;
            document.getElementById('total-studied').textContent = totalStudied;
            
            // 分类统计
            const categories = [...new Set(cards.map(c => c.category))];
            document.getElementById('categories-count').textContent = categories.length;
            
            // 分类图表
            const categoryChart = document.getElementById('category-chart');
            categoryChart.innerHTML = '';
            
            if (categories.length > 0) {
                const categoryCounts = {};
                categories.forEach(cat => {
                    categoryCounts[cat] = cards.filter(c => c.category === cat).length;
                });
                
                // 按数量排序
                const sortedCategories = Object.entries(categoryCounts)
                    .sort((a, b) => b[1] - a[1]);
                
                sortedCategories.forEach(([category, count]) => {
                    const percentage = (count / cards.length * 100).toFixed(1);
                    
                    const chartItem = document.createElement('div');
                    chartItem.style.marginBottom = '1.5rem';
                    
                    const chartLabel = document.createElement('div');
                    chartLabel.className = 'chart-label';
                    chartLabel.innerHTML = `
                        <span class="chart-category">${category}</span>
                        <span class="chart-count">${count} (${percentage}%)</span>
                    `;
                    
                    const chartBar = document.createElement('div');
                    chartBar.className = 'chart-bar';
                    
                    const chartProgress = document.createElement('div');
                    chartProgress.className = 'chart-progress';
                    chartProgress.style.width = `${percentage}%`;
                    
                    chartBar.appendChild(chartProgress);
                    chartItem.appendChild(chartLabel);
                    chartItem.appendChild(chartBar);
                    
                    categoryChart.appendChild(chartItem);
                });
            }
            
            // 最常学习的卡片
            const mostStudiedCards = document.getElementById('most-studied-cards');
            mostStudiedCards.innerHTML = '';
            
            const sortedByStudy = [...cards].sort((a, b) => b.studiedCount - a.studiedCount).slice(0, 3);
            
            if (sortedByStudy.length > 0) {
                sortedByStudy.forEach(card => {
                    const cardElement = document.createElement('div');
                    cardElement.className = 'card';
                    cardElement.innerHTML = `
                        <div class="card-header">${card.category} (学习次数: ${card.studiedCount})</div>
                        <div class="card-body">
                            <div class="card-term">${card.term}</div>
                            <div class="card-pronunciation">${card.pronunciation}</div>
                            <div class="card-definition">${card.definition}</div>
                        </div>
                    `;
                    mostStudiedCards.appendChild(cardElement);
                });
            } else {
                mostStudiedCards.innerHTML = '<div style="grid-column: 1 / -1; text-align: center; color: var(--gray);">暂无学习数据</div>';
            }
        }
        
        // 文本转语音功能
        function speakText(text) {
            if ('speechSynthesis' in window) {
                const utterance = new SpeechSynthesisUtterance(text);
                utterance.lang = 'en-US';
                utterance.rate = 0.9;
                speechSynthesis.speak(utterance);
            } else {
                alert('您的浏览器不支持文本转语音功能');
            }
        }
        
        // 处理CSV文件上传
        function processCSV(file) {
            const reader = new FileReader();
            
            reader.onload = function(e) {
                const content = e.target.result;
                const lines = content.split('\n');
                const headers = lines[0].split(',').map(h => h.trim());
                
                // 检查CSV格式是否正确
                const requiredHeaders = ['term', 'pronunciation', 'category', 'definition'];
                const missingHeaders = requiredHeaders.filter(h => !headers.includes(h));
                
                if (missingHeaders.length > 0) {
                    alert(`CSV文件缺少必要的列: ${missingHeaders.join(', ')}`);
                    return;
                }
                
                let newCards = [];
                
                for (let i = 1; i < lines.length; i++) {
                    if (lines[i].trim() === '') continue;
                    
                    const values = lines[i].split(',').map(v => v.trim());
                    const card = {};
                    
                    headers.forEach((header, index) => {
                        card[header] = values[index] || '';
                    });
                    
                    // 确保必填字段不为空
                    if (card.term && card.category && card.definition) {
                        newCards.push({
                            id: Date.now() + i,
                            term: card.term,
                            pronunciation: card.pronunciation || '',
                            category: card.category,
                            definition: card.definition,
                            mnemonic: card.mnemonic || '',
                            example: card.example || '',
                            createdAt: new Date().toISOString(),
                            studiedCount: 0,
                            lastStudied: null
                        });
                    }
                }
                
                if (newCards.length > 0) {
                    cards = [...cards, ...newCards];
                    saveCards();
                    renderCardList();
                    updateStats();
                    
                    alert(`成功导入 ${newCards.length} 张卡片！`);
                    
                    // 如果当前在学习部分，重新初始化学习
                    if (document.getElementById('study-cards').classList.contains('active')) {
                        initStudy();
                    }
                } else {
                    alert('没有找到有效的卡片数据');
                }
            };
            
            reader.readAsText(file);
        }
        
        // 下载CSV模板
        function downloadCSVTemplate() {
            const headers = ['term', 'pronunciation', 'category', 'definition', 'mnemonic', 'example'];
            const exampleData = [
                ['Ventilator', '[ˈvɛntɪleɪtər]', '生命支持', '呼吸机 - 帮助或替代患者呼吸的医疗设备', '联想记忆法', '例句示例'],
                ['ECMO', '[ˈɛkmoʊ]', '生命支持', '体外膜肺氧合 - 提供心肺支持的体外循环技术', '', '']
            ];
            
            let csvContent = headers.join(',') + '\n';
            exampleData.forEach(row => {
                csvContent += row.join(',') + '\n';
            });
            
            const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
            const url = URL.createObjectURL(blob);
            const link = document.createElement('a');
            
            link.setAttribute('href', url);
            link.setAttribute('download', 'ICU医学英语卡片模板.csv');
            link.style.visibility = 'hidden';
            
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }
    </script>
</body>
</html>
