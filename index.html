<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Block Speed - Klasik Mod</title>
    <style>
        * { box-sizing: border-box; user-select: none; -webkit-touch-callout: none; -webkit-tap-highlight-color: transparent; }
        body { margin: 0; padding: 0; background-color: #050208; color: #fff; font-family: 'Segoe UI', sans-serif; overflow: hidden; touch-action: none; background-image: radial-gradient(circle at 50% 0%, #1a0b2e 0%, #050208 70%); display: flex; flex-direction: column; align-items: center; height: 100vh; }
        .hidden { opacity: 0; pointer-events: none; display: none !important; }
        
        #game-ui { width: 100%; height: 100%; display: flex; flex-direction: column; align-items: center; z-index: 10; position: relative;}
        #top-bar { width: 100%; display: flex; justify-content: space-between; align-items: center; padding: 6vh 25px 3vh 25px; max-width: 450px; }
        .score-box { display: flex; flex-direction: column; align-items: flex-start; }
        .score-box:last-child { align-items: flex-end; }
        .score-label { font-size: 0.8rem; color: #aaa; text-transform: uppercase; letter-spacing: 2px; font-weight: 600;}
        .score-value { font-size: 2.2rem; font-weight: 900; transition: transform 0.1s; }
        
        .btn-pause { background: rgba(255,255,255,0.05); border: 1px solid rgba(255,255,255,0.2); border-radius: 12px; width: 45px; height: 45px; display: flex; justify-content: center; align-items: center; color: #fff; cursor: pointer; backdrop-filter: blur(5px); transition: background 0.2s, transform 0.1s; }
        .btn-pause:active { transform: scale(0.9); background: rgba(255,255,255,0.2); }

        #grid-container { position: relative; background-color: rgba(20, 10, 30, 0.6); padding: 6px; border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.1); box-shadow: inset 0 5px 20px rgba(0, 0, 0, 0.8), 0 20px 40px rgba(0,0,0,0.5); }
        #grid { display: grid; gap: 3px; }
        .grid-cell { background-color: rgba(30, 20, 45, 0.8); border-radius: 6px; box-shadow: inset 0 2px 4px rgba(0,0,0,0.5); transition: background-color 0.2s; }
        .glass-block { border-radius: 6px; border: 1px solid rgba(255,255,255,0.4); border-bottom: 3px solid rgba(0,0,0,0.4); border-right: 2px solid rgba(0,0,0,0.3); background-image: linear-gradient(135deg, rgba(255,255,255,0.3) 0%, rgba(255,255,255,0) 40%, rgba(0,0,0,0.1) 100%); box-shadow: inset 0 2px 5px rgba(255,255,255,0.4); }
        
        #spawn-area { display: flex; justify-content: space-evenly; align-items: center; width: 100%; max-width: 450px; margin-top: auto; margin-bottom: 5vh; height: 120px; }
        .shape-container { width: 30%; height: 100%; display: flex; justify-content: center; align-items: center; position: relative; }
        .draggable-shape { position: absolute; cursor: pointer; will-change: transform; transform: translate3d(0,0,0) scale(0.55); transition: transform 0.05s cubic-bezier(0.2, 1, 0.3, 1); }
        .draggable-shape::after { content: ''; position: absolute; top: -80px; bottom: -80px; left: -80px; right: -80px; z-index: 1; }
        .draggable-shape.dragging { transition: none !important; z-index: 1000; opacity: 0.95; }
        .draggable-shape.returning { transition: transform 0.2s ease-out !important; }
        .shape-block { position: absolute; z-index: 2; pointer-events: none; }
        
        .overlay-screen { position: absolute; top: 0; left: 0; width: 100%; height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; background: rgba(5, 2, 8, 0.85); backdrop-filter: blur(15px); z-index: 2000; transition: opacity 0.3s ease; }
        .logo-text { font-size: 3rem; font-weight: 900; color: #fff; margin-bottom: 30px; text-align: center; }
        .btn-group { display: flex; flex-direction: column; gap: 15px; width: 250px; }
        .btn-menu { background: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.3); border-radius: 12px; padding: 15px; font-size: 1.2rem; font-weight: bold; color: #fff; cursor: pointer; transition: all 0.2s ease; backdrop-filter: blur(5px); }
        .btn-menu:active { transform: scale(0.95); background: rgba(255,255,255,0.2); }
        .btn-primary { background: linear-gradient(135deg, #00f3ff, #0088ff); border-color: transparent; }

        #fx-canvas { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 999; }
        .floating-text { position: absolute; font-weight: 900; font-size: 1.5rem; color: #fff; text-shadow: 0 0 10px #ff00ea, 0 0 20px #ff00ea; pointer-events: none; z-index: 1000; animation: floatUp 1s cubic-bezier(0.2, 1, 0.3, 1) forwards; }
        @keyframes floatUp { 0% { transform: translateY(0) scale(0.5); opacity: 0; } 20% { transform: translateY(-20px) scale(1.2); opacity: 1; } 100% { transform: translateY(-60px) scale(1); opacity: 0; } }
        @keyframes shake { 0%, 100% { transform: translateX(0); } 25% { transform: translateX(-4px); } 75% { transform: translateX(4px); } }
        .shake { animation: shake 0.2s ease-in-out; }
    </style>
</head>
<body>

    <canvas id="fx-canvas"></canvas>

    <div id="game-ui">
        <div id="top-bar">
            <div class="score-box">
                <span class="score-label">SKOR</span>
                <span id="score-board" class="score-value">0</span>
            </div>
            <button class="btn-pause" onclick="togglePause()">
                <svg viewBox="0 0 24 24" width="22" height="22" stroke="currentColor" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"><rect x="6" y="4" width="4" height="16"></rect><rect x="14" y="4" width="4" height="16"></rect></svg>
            </button>
            <div class="score-box">
                <span class="score-label">EN YÜKSEK</span>
                <span id="highscore-board" class="score-value" style="font-size: 1.5rem; color:#aaa;">0</span>
            </div>
        </div>
        <div id="grid-container"><div id="grid"></div></div>
        <div id="spawn-area">
            <div class="shape-container" id="spawn-0"></div>
            <div class="shape-container" id="spawn-1"></div>
            <div class="shape-container" id="spawn-2"></div>
        </div>
    </div>

    <div id="pause-menu" class="overlay-screen hidden">
        <div class="logo-text" style="text-shadow: 0 0 20px #00f3ff;">DURAKLATILDI</div>
        <div class="btn-group">
            <button class="btn-menu btn-primary" onclick="togglePause()">OYUNA DÖN</button>
            <button class="btn-menu" onclick="restartGame()">YENİDEN BAŞLAT</button>
            <button class="btn-menu" style="border-color: #ff00ea; color: #ff00ea;" onclick="exitToMenu()">ANA MENÜYE ÇIK</button>
        </div>
    </div>

    <div id="game-over-screen" class="overlay-screen hidden">
        <div class="logo-text" style="text-shadow: 0 0 20px #ff00ea; color: #ff00ea;">SİSTEM ÇÖKTÜ</div>
        <div style="font-size: 1.2rem; color: #aaa; text-align: center; margin-bottom: 30px;">
            SKOR <br><span id="go-score" style="color: #fff; font-size: 3rem; font-weight: 900;">0</span>
        </div>
        <div class="btn-group">
            <button class="btn-menu btn-primary" onclick="restartGame()">YENİDEN DENE</button>
            <button class="btn-menu" onclick="exitToMenu()">ANA MENÜ</button>
        </div>
    </div>

    <script>
        const screenWidth = window.innerWidth;
        const GRID_SIZE = 8;
        const CELL_GAP = 3;
        let CELL_SIZE = Math.floor((Math.min(screenWidth * 0.92, 420) - (GRID_SIZE * CELL_GAP)) / GRID_SIZE);
        let STRIDE = CELL_SIZE + CELL_GAP;
        
        // GLOBAL GRID CACHE (KASMA ÇÖZÜMÜ)
        let GLOBAL_GRID_RECT = null;
        window.addEventListener('resize', () => {
            if(document.getElementById('grid-container')) {
                GLOBAL_GRID_RECT = document.getElementById('grid-container').getBoundingClientRect();
            }
        });

        const GameState = { score: 0, highScore: 0, combo: 0, grid: [], isPaused: false };
        const COLORS = { cyan: '#00e5ff', magenta: '#f50057', yellow: '#ffea00', green: '#00e676', purple: '#d500f9', orange: '#ff9100' };
        const SHAPES = [
            { weight: 1, color: COLORS.cyan, matrix: [[1]] }, { weight: 1, color: COLORS.magenta, matrix: [[1,1]] },
            { weight: 1, color: COLORS.green, matrix: [[1,1,1]] }, { weight: 2, color: COLORS.orange, matrix: [[1,1,1,1]] },
            { weight: 2, color: COLORS.purple, matrix: [[1,0],[1,1]] }, { weight: 2, color: COLORS.purple, matrix: [[0,1],[1,1]] },
            { weight: 3, color: COLORS.yellow, matrix: [[1,1],[1,1]] }, { weight: 4, color: COLORS.cyan, matrix: [[1,1,1],[1,1,1],[1,1,1]] },
            { weight: 3, color: COLORS.magenta, matrix: [[1,1,1],[0,1,0]] },
        ];

        window.onload = () => {
            initGrid(); initParticles();
            GameState.highScore = parseInt(localStorage.getItem('BlockSpeedHighScore')) || 0;
            const urlParams = new URLSearchParams(window.location.search);
            if (urlParams.get('continue') === 'true') loadGame();
            else startNewGame();
            
            // Grid Rect'i bir kere hesapla ve sabitle
            setTimeout(() => { GLOBAL_GRID_RECT = document.getElementById('grid-container').getBoundingClientRect(); }, 100);
        };

        function togglePause() {
            if(!document.getElementById('game-over-screen').classList.contains('hidden')) return;
            GameState.isPaused = !GameState.isPaused;
            const pauseMenu = document.getElementById('pause-menu');
            if (GameState.isPaused) { pauseMenu.classList.remove('hidden'); saveGameState(); } 
            else pauseMenu.classList.add('hidden');
        }

        function exitToMenu() { saveGameState(); window.location.href = 'index.html'; }
        function restartGame() { document.getElementById('pause-menu').classList.add('hidden'); document.getElementById('game-over-screen').classList.add('hidden'); startNewGame(); }

        function clearSave() { localStorage.removeItem('BlockSpeedSaveState'); }

        function startNewGame() {
            clearSave(); resetGrid();
            GameState.score = 0; GameState.combo = 0; GameState.isPaused = false; updateScoreUI();
            for (let i = 0; i < 3; i++) document.getElementById(`spawn-${i}`).innerHTML = '';
            spawnShapes();
        }

        function loadGame() {
            const savedData = JSON.parse(localStorage.getItem('BlockSpeedSaveState'));
            if (!savedData) { startNewGame(); return; }
            resetGrid(); GameState.score = savedData.score; GameState.combo = 0; updateScoreUI();
            for (let r = 0; r < GRID_SIZE; r++) {
                for (let c = 0; c < GRID_SIZE; c++) {
                    if (savedData.grid[r][c].filled) {
                        const cell = GameState.grid[r][c]; cell.filled = true; cell.color = savedData.grid[r][c].color;
                        cell.el.classList.add('filled', 'glass-block'); cell.el.style.backgroundColor = cell.color;
                    }
                }
            }
            for (let i = 0; i < 3; i++) {
                const container = document.getElementById(`spawn-${i}`); container.innerHTML = '';
                if (savedData.spawns[i]) createShapeDom(container, savedData.spawns[i]);
            }
            setTimeout(checkGameOver, 200);
        }

        function saveGameState() {
            const gridData = GameState.grid.map(row => row.map(cell => ({ filled: cell.filled, color: cell.color })));
            const spawnData = [];
            for (let i = 0; i < 3; i++) {
                const container = document.getElementById(`spawn-${i}`); const shapeEl = container.querySelector('.draggable-shape');
                if (shapeEl) spawnData.push({ matrix: JSON.parse(shapeEl.dataset.matrix), color: shapeEl.dataset.color });
                else spawnData.push(null);
            }
            localStorage.setItem('BlockSpeedSaveState', JSON.stringify({ score: GameState.score, grid: gridData, spawns: spawnData }));
        }

        function initGrid() {
            const gridEl = document.getElementById('grid');
            gridEl.style.gridTemplateColumns = `repeat(${GRID_SIZE}, ${CELL_SIZE}px)`; gridEl.style.gridTemplateRows = `repeat(${GRID_SIZE}, ${CELL_SIZE}px)`;
            for (let r = 0; r < GRID_SIZE; r++) {
                GameState.grid[r] = [];
                for (let c = 0; c < GRID_SIZE; c++) {
                    const cell = document.createElement('div'); cell.className = 'grid-cell'; cell.style.width = `${CELL_SIZE}px`; cell.style.height = `${CELL_SIZE}px`;
                    gridEl.appendChild(cell); GameState.grid[r][c] = { el: cell, filled: false, color: null };
                }
            }
        }

        function resetGrid() {
            for (let r = 0; r < GRID_SIZE; r++) {
                for (let c = 0; c < GRID_SIZE; c++) {
                    const cell = GameState.grid[r][c]; cell.filled = false; cell.color = null;
                    cell.el.className = 'grid-cell'; cell.el.style.backgroundColor = '';
                }
            }
        }

        function updateScoreUI() {
            const sb = document.getElementById('score-board'); sb.innerText = GameState.score;
            document.getElementById('highscore-board').innerText = GameState.highScore;
            sb.classList.add('score-pop'); setTimeout(() => sb.classList.remove('score-pop'), 150);
        }

        function getAdaptiveShape() {
            let filledCount = 0;
            for(let r=0; r<GRID_SIZE; r++) for(let c=0; c<GRID_SIZE; c++) if(GameState.grid[r][c].filled) filledCount++;
            let density = filledCount / (GRID_SIZE * GRID_SIZE); let availableShapes = [...SHAPES];
            if (density > 0.6) { availableShapes = availableShapes.filter(s => s.weight <= 2); availableShapes.push(SHAPES[0], SHAPES[0], SHAPES[1]); }
            return availableShapes[Math.floor(Math.random() * availableShapes.length)];
        }

        function spawnShapes() {
            for (let i = 0; i < 3; i++) {
                const container = document.getElementById(`spawn-${i}`);
                if (container.children.length === 0) createShapeDom(container, getAdaptiveShape());
            }
            saveGameState(); setTimeout(checkGameOver, 150);
        }

        function createShapeDom(container, shapeData) {
            const wrapper = document.createElement('div'); wrapper.className = 'draggable-shape';
            wrapper.dataset.matrix = JSON.stringify(shapeData.matrix); wrapper.dataset.color = shapeData.color;
            let w = shapeData.matrix[0].length * STRIDE - CELL_GAP; let h = shapeData.matrix.length * STRIDE - CELL_GAP;
            wrapper.style.width = `${w}px`; wrapper.style.height = `${h}px`;
            shapeData.matrix.forEach((row, r) => {
                row.forEach((val, c) => {
                    if (val === 1) {
                        const block = document.createElement('div'); block.className = 'shape-block glass-block';
                        block.style.width = `${CELL_SIZE}px`; block.style.height = `${CELL_SIZE}px`;
                        block.style.left = `${c * STRIDE}px`; block.style.top = `${r * STRIDE}px`;
                        block.style.backgroundColor = shapeData.color; wrapper.appendChild(block);
                    }
                });
            });
            setupDragEvents(wrapper, container); container.appendChild(wrapper);
        }

        function showFloatingText(text, x, y, color) {
            const el = document.createElement('div'); el.className = 'floating-text'; el.innerText = text;
            el.style.left = `${x}px`; el.style.top = `${y}px`; el.style.color = color;
            document.body.appendChild(el); setTimeout(() => el.remove(), 1000);
        }

        function setupDragEvents(el, container) {
            let isDragging = false, isReturning = false, startX, startY, currentX = 0, currentY = 0;
            const touchOffsetY = -90; let animationFrameId = null;

            el.addEventListener('touchstart', dragStart, { passive: false }); el.addEventListener('mousedown', dragStart);

            function dragStart(e) {
                if (isReturning || GameState.isPaused) return; e.preventDefault(); isDragging = true;
                el.classList.remove('returning'); el.classList.add('dragging');
                
                const clientX = e.type === 'touchstart' ? e.touches[0].clientX : e.clientX;
                const clientY = e.type === 'touchstart' ? e.touches[0].clientY : e.clientY;
                startX = clientX; startY = clientY; currentX = 0; currentY = touchOffsetY;
                updateTransform();
                document.addEventListener('touchmove', dragMove, { passive: false }); document.addEventListener('mousemove', dragMove);
                document.addEventListener('touchend', dragEnd); document.addEventListener('mouseup', dragEnd);
            }
            function dragMove(e) {
                if (!isDragging || GameState.isPaused) return; e.preventDefault();
                const clientX = e.type === 'touchmove' ? e.touches[0].clientX : e.clientX;
                const clientY = e.type === 'touchmove' ? e.touches[0].clientY : e.clientY;
                currentX = clientX - startX; currentY = (clientY - startY) + touchOffsetY;
                if (!animationFrameId) animationFrameId = requestAnimationFrame(updateTransform);
            }
            function updateTransform() { el.style.transform = `translate3d(${currentX}px, ${currentY}px, 0) scale(1)`; animationFrameId = null; }
            function dragEnd() {
                if (!isDragging) return; isDragging = false; el.classList.remove('dragging');
                if (animationFrameId) cancelAnimationFrame(animationFrameId); animationFrameId = null;
                document.removeEventListener('touchmove', dragMove); document.removeEventListener('mousemove', dragMove);
                document.removeEventListener('touchend', dragEnd); document.removeEventListener('mouseup', dragEnd);
                
                if (GameState.isPaused) return;

                const shapeRect = el.getBoundingClientRect();
                // DİNAMİK HESAPLAMA YERİNE SABİT CACHE KULLANILDI (SIFIR KASMA)
                const relativeX = shapeRect.left - GLOBAL_GRID_RECT.left - 5; 
                const relativeY = shapeRect.top - GLOBAL_GRID_RECT.top - 5;
                const gridCol = Math.round(relativeX / STRIDE); const gridRow = Math.round(relativeY / STRIDE);
                const matrix = JSON.parse(el.dataset.matrix);
                
                if (canPlace(matrix, gridRow, gridCol)) {
                    placeShape(matrix, gridRow, gridCol, el.dataset.color); el.remove();
                    if (document.querySelectorAll('#spawn-area .draggable-shape').length === 0) spawnShapes();
                    else { saveGameState(); checkGameOver(); }
                } else {
                    isReturning = true; el.classList.add('returning'); el.style.transform = `translate3d(0,0,0) scale(0.55)`; 
                    setTimeout(() => { isReturning = false; currentX = 0; currentY = 0; }, 200);
                }
            }
        }

        function canPlace(matrix, startR, startC) {
            for (let r = 0; r < matrix.length; r++) {
                for (let c = 0; c < matrix[r].length; c++) {
                    if (matrix[r][c] === 1) {
                        if (startR + r < 0 || startR + r >= GRID_SIZE || startC + c < 0 || startC + c >= GRID_SIZE) return false;
                        if (GameState.grid[startR+r][startC+c].filled) return false;
                    }
                }
            }
            return true;
        }

        function placeShape(matrix, startR, startC, color) {
            let blocksPlaced = 0;
            for (let r = 0; r < matrix.length; r++) {
                for (let c = 0; c < matrix[r].length; c++) {
                    if (matrix[r][c] === 1) {
                        const cellData = GameState.grid[startR + r][startC + c];
                        cellData.filled = true; cellData.color = color;
                        cellData.el.classList.add('filled', 'glass-block'); cellData.el.style.backgroundColor = color; blocksPlaced++;
                    }
                }
            }
            GameState.score += (blocksPlaced * 2); updateScoreUI(); checkAndClearLines();
        }

        function checkAndClearLines() {
            let cellsToClear = []; let linesCleared = 0;
            for (let r = 0; r < GRID_SIZE; r++) { if (GameState.grid[r].every(cell => cell.filled)) { linesCleared++; GameState.grid[r].forEach(cell => cellsToClear.push(cell)); } }
            for (let c = 0; c < GRID_SIZE; c++) {
                let colFull = true; for (let r = 0; r < GRID_SIZE; r++) { if (!GameState.grid[r][c].filled) colFull = false; }
                if (colFull) { linesCleared++; for (let r = 0; r < GRID_SIZE; r++) cellsToClear.push(GameState.grid[r][c]); }
            }

            if (cellsToClear.length > 0) {
                GameState.combo++; let earnedPoints = (linesCleared * 100) * GameState.combo; GameState.score += earnedPoints;
                document.getElementById('grid-container').classList.add('shake'); setTimeout(() => document.getElementById('grid-container').classList.remove('shake'), 200);
                let firstCellRect = cellsToClear[0].el.getBoundingClientRect();
                [...new Set(cellsToClear)].forEach(cell => {
                    const rect = cell.el.getBoundingClientRect(); createParticles(rect.left + CELL_SIZE/2, rect.top + CELL_SIZE/2, cell.color);
                    cell.filled = false; cell.color = null; cell.el.className = 'grid-cell'; cell.el.style.backgroundColor = '';
                });
                let text = `+${earnedPoints}`; if(GameState.combo > 1) text = `COMBO x${GameState.combo}!`;
                showFloatingText(text, firstCellRect.left, firstCellRect.top - 20, '#00f3ff'); updateScoreUI();
            } else { GameState.combo = 0; }
        }

        function checkGameOver() {
            const shapes = document.querySelectorAll('.draggable-shape'); if (shapes.length === 0) return;
            let canPlaceAny = false;
            shapes.forEach(shapeElem => {
                if (canPlaceAny) return; const matrix = JSON.parse(shapeElem.dataset.matrix);
                for (let r = 0; r <= GRID_SIZE - matrix.length; r++) {
                    for (let c = 0; c <= GRID_SIZE - matrix[0].length; c++) { if (canPlace(matrix, r, c)) { canPlaceAny = true; return; } }
                }
            });
            if (!canPlaceAny) {
                clearSave();
                if(GameState.score > GameState.highScore) { GameState.highScore = GameState.score; localStorage.setItem('BlockSpeedHighScore', GameState.highScore); }
                document.getElementById('go-score').innerText = GameState.score; 
                setTimeout(() => { document.getElementById('game-over-screen').classList.remove('hidden'); }, 600);
            }
        }

        const canvas = document.getElementById('fx-canvas'); const ctx = canvas.getContext('2d'); let particles = [];
        function initParticles() { canvas.width = window.innerWidth; canvas.height = window.innerHeight; requestAnimationFrame(renderParticles); }
        function createParticles(x, y, color) { for (let i = 0; i < 6; i++) { particles.push({ x: x, y: y, vx: (Math.random() - 0.5) * 12, vy: (Math.random() - 0.5) * 12, life: 1.0, color: color }); } }
        function renderParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            if (GameState.isPaused) { requestAnimationFrame(renderParticles); return; }
            for (let i = particles.length - 1; i >= 0; i--) {
                let p = particles[i]; p.x += p.vx; p.y += p.vy; p.life -= 0.04;
                if (p.life <= 0) { particles.splice(i, 1); continue; }
                ctx.globalAlpha = p.life; ctx.fillStyle = p.color; ctx.beginPath(); ctx.arc(p.x, p.y, 3, 0, Math.PI * 2); ctx.fill();
            }
            ctx.globalAlpha = 1; requestAnimationFrame(renderParticles);
        }
    </script>
</body>
</html>
