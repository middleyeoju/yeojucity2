<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2학년 기술가정 수업</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px 20px;
            margin-bottom: 30px;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
        }

        h1 {
            color: white;
            font-size: 2.5rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .subtitle {
            color: rgba(255, 255, 255, 0.9);
            font-size: 1.2rem;
            font-weight: 300;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }

        .menu-card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .menu-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .menu-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
        }

        .menu-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            display: block;
        }

        .card-1 .menu-icon { color: #ff6b6b; }
        .card-2 .menu-icon { color: #4ecdc4; }
        .card-3 .menu-icon { color: #45b7d1; }

        .menu-title {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 15px;
            color: #333;
        }

        .menu-description {
            color: #666;
            line-height: 1.6;
            margin-bottom: 20px;
        }

        .menu-button {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
            width: 100%;
        }

        .menu-button:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .content-area {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 30px;
            margin-top: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            display: none;
        }

        .content-area.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .back-button {
            background: #6c757d;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
            margin-bottom: 20px;
        }

        .back-button:hover {
            background: #5a6268;
        }

        footer {
            text-align: center;
            padding: 30px 0;
            color: rgba(255, 255, 255, 0.8);
            margin-top: 50px;
        }

        @media (max-width: 768px) {
            h1 { font-size: 2rem; }
            .menu-grid { grid-template-columns: 1fr; }
            .container { padding: 15px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>2학년 기술가정 수업</h1>
            <p class="subtitle">창의적 사고와 실생활 능력을 키우는 수업</p>
        </header>

        <div id="mainMenu" class="menu-grid">
            <div class="menu-card card-1" onclick="showContent('assignment')">
                <span class="menu-icon">📝</span>
                <h2 class="menu-title">과제 제출란</h2>
                <p class="menu-description">수업 과제를 확인하고 제출할 수 있습니다. 마감일과 평가 기준을 확인해보세요.</p>
                <button class="menu-button">과제 확인하기</button>
            </div>

            <div class="menu-card card-2" onclick="showContent('stickers')">
                <span class="menu-icon">⭐</span>
                <h2 class="menu-title">칭찬스티커</h2>
                <p class="menu-description">열심히 참여한 학생들의 칭찬스티커 현황을 확인할 수 있습니다.</p>
                <button class="menu-button">스티커 현황 보기</button>
            </div>

            <div class="menu-card card-3" onclick="showContent('materials')">
                <span class="menu-icon">📚</span>
                <h2 class="menu-title">보조자료</h2>
                <p class="menu-description">수업에 도움이 되는 참고자료와 학습 도구들을 제공합니다.</p>
                <button class="menu-button">자료 둘러보기</button>
            </div>
        </div>

        <!-- 과제 제출란 내용 -->
        <div id="assignment" class="content-area">
            <button class="back-button" onclick="showMain()">← 메인으로 돌아가기</button>
            <h2>📝 과제 제출란</h2>
            <div style="margin-top: 20px;">
                <h3>현재 과제 목록</h3>
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin: 15px 0;">
                    <h4>🔧 기술 영역 과제</h4>
                    <p><strong>제목:</strong> 생활 속 기술 문제 해결하기</p>
                    <p><strong>마감일:</strong> 2025년 9월 15일</p>
                    <p><strong>내용:</strong> 일상생활에서 발견한 불편함을 기술적으로 해결하는 아이디어 제시</p>
                </div>
                <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin: 15px 0;">
                    <h4>🏠 가정 영역 과제</h4>
                    <p><strong>제목:</strong> 건강한 식단 계획하기</p>
                    <p><strong>마감일:</strong> 2025년 9월 20일</p>
                    <p><strong>내용:</strong> 일주일간의 균형잡힌 식단표 작성 및 조리법 연구</p>
                </div>
            </div>
        </div>

        <!-- 칭찬스티커 내용 -->
        <div id="stickers" class="content-area">
            <button class="back-button" onclick="showMain()">← 메인으로 돌아가기</button>
            <h2>⭐ 칭찬스티커 현황</h2>
            <div style="margin-top: 20px;">
                <h3>이번 달 스티커 랭킹</h3>
                <div style="background: linear-gradient(45deg, #fff3cd, #ffeaa7); padding: 20px; border-radius: 10px; margin: 15px 0;">
                    <h4>🥇 1위: 김OO (15개)</h4>
                    <p>적극적인 수업 참여와 창의적인 아이디어 제시</p>
                </div>
                <div style="background: linear-gradient(45deg, #d1ecf1, #74b9ff); padding: 20px; border-radius: 10px; margin: 15px 0;">
                    <h4>🥈 2위: 박OO (12개)</h4>
                    <p>꼼꼼한 과제 완성도와 도움이 되는 질문</p>
                </div>
                <div style="background: linear-gradient(45deg, #f8d7da, #fd79a8); padding: 20px; border-radius: 10px; margin: 15px 0;">
                    <h4>🥉 3위: 이OO (10개)</h4>
                    <p>성실한 수업 태도와 친구들과의 협력</p>
                </div>
            </div>
        </div>

        <!-- 보조자료 내용 -->
        <div id="materials" class="content-area">
            <button class="back-button" onclick="showMain()">← 메인으로 돌아가기</button>
            <h2>📚 보조자료</h2>
            <div style="margin-top: 20px;">
                <h3>학습 자료 모음</h3>
                <div style="display: grid; gap: 15px;">
                    <div style="background: #e8f5e8; padding: 15px; border-radius: 10px;">
                        <h4>🔧 기술 영역 자료</h4>
                        <ul style="margin: 10px 0; padding-left: 20px;">
                            <li>발명품 아이디어 가이드</li>
                            <li>3D 프린팅 기초</li>
                            <li>로봇 만들기 튜토리얼</li>
                        </ul>
                    </div>
                    <div style="background: #fff0e8; padding: 15px; border-radius: 10px;">
                        <h4>🏠 가정 영역 자료</h4>
                        <ul style="margin: 10px 0; padding-left: 20px;">
                            <li>영양소별 식품 분류표</li>
                            <li>안전한 조리법 가이드</li>
                            <li>생활용품 만들기</li>
                        </ul>
                    </div>
                    <div style="background: #e8f0ff; padding: 15px; border-radius: 10px;">
                        <h4>📖 참고 사이트</h4>
                        <ul style="margin: 10px 0; padding-left: 20px;">
                            <li>온라인 요리 강의</li>
                            <li>발명 아이디어 갤러리</li>
                            <li>생활 속 과학 원리</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>

        <footer>
            <p>&copy; 2025 2학년 기술가정 수업 | 함께 배우고 성장해요! 🌱</p>
        </footer>
    </div>

    <script>
        function showContent(section) {
            // 메인 메뉴 숨기기
            document.getElementById('mainMenu').style.display = 'none';
            
            // 모든 컨텐츠 영역 숨기기
            const contentAreas = document.querySelectorAll('.content-area');
            contentAreas.forEach(area => {
                area.classList.remove('active');
            });
            
            // 선택된 컨텐츠 영역 보이기
            document.getElementById(section).classList.add('active');
        }

        function showMain() {
            // 모든 컨텐츠 영역 숨기기
            const contentAreas = document.querySelectorAll('.content-area');
            contentAreas.forEach(area => {
                area.classList.remove('active');
            });
            
            // 메인 메뉴 보이기
            document.getElementById('mainMenu').style.display = 'grid';
        }

        // 부드러운 스크롤 효과
        document.addEventListener('DOMContentLoaded', function() {
            const cards = document.querySelectorAll('.menu-card');
            cards.forEach((card, index) => {
                card.style.animationDelay = `${index * 0.1}s`;
                card.style.animation = 'fadeIn 0.6s ease forwards';
            });
        });
    </script>
</body>
</html>
