<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tinh Hoa Nhạc Cụ Việt</title>
    <script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/3.4.0/model-viewer.min.js"></script>
    
    <style>
        :root {
            --gold: #d4af37;
            --dark-red: #800000;
            --paper: #f9f4e8;
        }
        body { font-family: 'Segoe UI', sans-serif; margin: 0; background: var(--paper); }
        
        /* Menu điều hướng */
        nav { background: var(--dark-red); display: flex; justify-content: center; position: sticky; top: 0; z-index: 100; }
        nav button {
            background: none; border: none; color: white; padding: 15px 25px;
            cursor: pointer; font-size: 16px; font-weight: bold; transition: 0.3s;
        }
        nav button:hover, nav button.active-nav { background: var(--gold); color: black; }

        .tab-content { display: none; padding: 40px 20px; max-width: 1000px; margin: auto; animation: fadeIn 0.5s; }
        .active-tab { display: block; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* Trang chủ: Các nút chọn đàn */
        .instrument-nav { display: flex; gap: 10px; justify-content: center; flex-wrap: wrap; margin-bottom: 30px; }
        .btn-dan {
            padding: 10px 20px; border: 2px solid var(--dark-red); background: white;
            border-radius: 25px; cursor: pointer; font-weight: bold;
        }
        .btn-dan:hover { background: var(--dark-red); color: white; }

        /* Khu vực hiển thị nội dung đàn */
        #display-box { 
            background: white; border-radius: 15px; padding: 30px; 
            box-shadow: 0 10px 30px rgba(0,0,0,0.1); display: none;
        }
        .grid-container { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; }
        @media (max-width: 768px) { .grid-container { grid-template-columns: 1fr; } }

        img.dan-img { width: 100%; border-radius: 10px; border: 3px solid #eee; }
        model-viewer { width: 100%; height: 350px; background: #f0f0f0; border-radius: 10px; }

        h2 { color: var(--dark-red); border-bottom: 2px solid var(--gold); padding-bottom: 10px; }
    </style>
</head>
<body>

<nav>
    <button onclick="openTab('home', this)" class="active-nav">TRANG CHỦ</button>
    <button onclick="openTab('intro', this)">GIỚI THIỆU</button>
    <button onclick="openTab('game', this)">TRÒ CHƠI</button>
    <button onclick="openTab('collection', this)">SƯU TẦM</button>
</nav>

<div id="home" class="tab-content active-tab">
    <h1 style="text-align:center;">Khám Phá Nhạc Cụ 3D</h1>
    <div class="instrument-nav">
        <button class="btn-dan" onclick="viewDan('tranh')">Đàn Tranh</button>
        <button class="btn-dan" onclick="viewDan('nhi')">
