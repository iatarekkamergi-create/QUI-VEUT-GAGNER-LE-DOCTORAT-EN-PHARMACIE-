<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>QUI VEUT GAGNER LE DOCTORAT EN PHARMACIE ?</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #8B0000, #B22222, #8B0000);
            color: white;
            min-height: 100vh;
            padding: 20px;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1"/></svg>');
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            padding: 20px 0;
            margin-bottom: 20px;
            position: relative;
        }
        
        header h1 {
            font-size: 2.8rem;
            text-shadow: 0 4px 8px rgba(0,0,0,0.5);
            margin-bottom: 10px;
            color: #FFD700;
            animation: titleGlow 2s infinite alternate;
        }
        
        @keyframes titleGlow {
            from { text-shadow: 0 0 10px #FFD700, 0 0 20px #FFD700; }
            to { text-shadow: 0 0 20px #FFD700, 0 0 40px #FFD700; }
        }
        
        .game-container {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 20px;
            margin-bottom: 30px;
        }
        
        @media (max-width: 768px) {
            .game-container {
                grid-template-columns: 1fr;
            }
        }
        
        /* Style du tableau des gains */
        .money-tree {
            background: rgba(0, 0, 0, 0.8);
            border-radius: 15px;
            padding: 20px;
            border: 3px solid #FFD700;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            position: relative;
            overflow: hidden;
        }
        
        .money-tree::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,215,0,0.1) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        
        .money-tree.highlight::before {
            opacity: 1;
        }
        
        .money-tree h2 {
            text-align: center;
            margin-bottom: 20px;
            color: #FFD700;
            font-size: 1.5rem;
            text-shadow: 0 0 10px rgba(255,215,0,0.5);
        }
        
        .prize-levels {
            display: flex;
            flex-direction: column;
            gap: 8px;
            max-height: 600px;
            overflow-y: auto;
            padding-right: 10px;
        }
        
        .prize-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 12px 15px;
            text-align: right;
            border-radius: 8px;
            transition: all 0.3s ease;
            position: relative;
            border-left: 4px solid transparent;
            transform: translateX(0);
        }
        
        .prize-item.active {
            background: rgba(255, 215, 0, 0.3);
            border-left-color: #FFD700;
            color: #FFD700;
            font-weight: bold;
            transform: translateX(10px);
            animation: pulseItem 1.5s infinite;
        }
        
        @keyframes pulseItem {
            0% { box-shadow: 0 0 5px #FFD700; }
            50% { box-shadow: 0 0 15px #FFD700; }
            100% { box-shadow: 0 0 5px #FFD700; }
        }
        
        .prize-item.guaranteed {
            background: rgba(0, 128, 0, 0.3);
            border-left-color: #008000;
            color: #90EE90;
        }
        
        .prize-item.won {
            background: rgba(0, 128, 0, 0.5);
            border-left-color: #00FF00;
            color: #00FF00;
        }
        
        .prize-amount {
            font-weight: bold;
            font-size: 1.1rem;
        }
        
        .prize-description {
            font-size: 0.85rem;
            opacity: 0.8;
        }
        
        /* Style de la question */
        .question-section {
            background: rgba(0, 0, 0, 0.8);
            border-radius: 15px;
            padding: 30px;
            border: 3px solid #FFD700;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            position: relative;
            overflow: hidden;
        }
        
        .question-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, #FFD700, transparent);
            animation: scanLine 3s infinite;
        }
        
        @keyframes scanLine {
            0% { transform: translateY(-100%); }
            100% { transform: translateY(100vh); }
        }
        
        .question-number {
            text-align: center;
            font-size: 1.2rem;
            margin-bottom: 20px;
            color: #FFD700;
            text-shadow: 0 0 5px rgba(255,215,0,0.5);
        }
        
        .question-text {
            background: rgba(255, 255, 255, 0.1);
            padding: 25px;
            border-radius: 10px;
            margin-bottom: 30px;
            font-size: 1.4rem;
            line-height: 1.4;
            min-height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            border: 2px solid rgba(255,215,0,0.3);
            animation: fadeIn 0.8s ease-out;
        }
        
        .options-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }
        
        @media (max-width: 600px) {
            .options-grid {
                grid-template-columns: 1fr;
            }
        }
        
        .option-btn {
            background: linear-gradient(135deg, #4A4A4A, #2A2A2A);
            border: 2px solid #FFD700;
            color: white;
            padding: 20px;
            border-radius: 10px;
            font-size: 1.2rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: left;
            min-height: 80px;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
        }
        
        .option-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,215,0,0.3), transparent);
            transition: left 0.5s;
        }
        
        .option-btn:hover::before {
            left: 100%;
        }
        
        .option-btn:hover {
            background: linear-gradient(135deg, #5A5A5A, #3A3A3A);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
        }
        
        .option-btn:disabled {
            opacity: 0.7;
            cursor: not-allowed;
            transform: none;
        }
        
        .option-letter {
            background: #FFD700;
            color: #8B0000;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-right: 15px;
            flex-shrink: 0;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        
        .controls {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 25px;
        }
        
        .control-btn {
            background: linear-gradient(135deg, #FFD700, #FFA500);
            color: #8B0000;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            min-width: 150px;
            position: relative;
            overflow: hidden;
        }
        
        .control-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transform: translateX(-100%);
            transition: transform 0.6s;
        }
        
        .control-btn:hover::after {
            transform: translateX(100%);
        }
        
        .control-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.4);
        }
        
        .control-btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none;
        }
        
        .lifelines {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .lifeline-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid #FFD700;
            color: white;
            padding: 8px 15px;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            position: relative;
        }
        
        .lifeline-btn:hover:not(:disabled) {
            background: rgba(255, 215, 0, 0.3);
            transform: scale(1.05);
        }
        
        .lifeline-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
        }
        
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            animation: modalFadeIn 0.5s ease-out;
        }
        
        @keyframes modalFadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }
        
        .modal-content {
            background: linear-gradient(135deg, #8B0000, #B22222);
            padding: 30px;
            border-radius: 20px;
            border: 3px solid #FFD700;
            text-align: center;
            max-width: 500px;
            width: 90%;
            position: relative;
            overflow: hidden;
        }
        
        .modal-content::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,215,0,0.2) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }
        
        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        .modal h2 {
            color: #FFD700;
            margin-bottom: 20px;
            font-size: 2rem;
            text-shadow: 0 0 10px rgba(255,215,0,0.5);
        }
        
        .modal p {
            margin-bottom: 25px;
            font-size: 1.2rem;
            line-height: 1.5;
        }
        
        .hidden {
            display: none;
        }
        
        .pulse {
            animation: pulse 1.5s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .confetti {
            position: fixed;
            width: 10px;
            height: 10px;
            background-color: #FFD700;
            opacity: 0;
            z-index: 2000;
        }
        
        .level-indicator {
            text-align: center;
            margin: 15px 0;
            font-size: 1.2rem;
            color: #FFD700;
            text-shadow: 0 0 5px rgba(255,215,0,0.5);
        }
        
        /* Animation de victoire */
        @keyframes victoryShine {
            0% { transform: scale(1); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: scale(3); opacity: 0; }
        }
        
        .victory-effect {
            position: absolute;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: radial-gradient(circle, #FFD700, transparent);
            opacity: 0;
            pointer-events: none;
        }
        
        /* Audio controls */
        .audio-controls {
            position: absolute;
            top: 20px;
            right: 20px;
            z-index: 100;
        }
        
        .audio-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid #FFD700;
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 18px;
            transition: all 0.3s ease;
        }
        
        .audio-btn:hover {
            background: rgba(255, 215, 0, 0.3);
            transform: scale(1.1);
        }
        
        .audio-btn.muted {
            color: #ff6b6b;
        }
        
        /* Graphique public */
        .audience-graph {
            background: rgba(0, 0, 0, 0.9);
            border-radius: 15px;
            padding: 20px;
            border: 2px solid #FFD700;
            margin-top: 20px;
            max-width: 400px;
            margin: 20px auto;
        }
        
        .graph-title {
            text-align: center;
            color: #FFD700;
            margin-bottom: 15px;
            font-size: 1.2rem;
        }
        
        .graph-bar {
            height: 30px;
            background: linear-gradient(90deg, #4ECDC4, #45B7D1);
            margin: 8px 0;
            border-radius: 15px;
            position: relative;
            overflow: hidden;
        }
        
        .graph-bar.correct {
            background: linear-gradient(90deg, #2ecc71, #27ae60);
        }
        
        .graph-label {
            position: absolute;
            left: 10px;
            top: 5px;
            color: white;
            font-weight: bold;
        }
        
        .graph-percentage {
            position: absolute;
            right: 10px;
            top: 5px;
            color: white;
            font-weight: bold;
        }
        
        .graph-container {
            height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
    </style>
</head>
<body>
    <!-- Contrôles audio -->
    <div class="audio-controls">
        <button class="audio-btn" id="audioToggle">🔊</button>
    </div>
    
    <div class="container">
        <header>
            <h1>QUI VEUT GAGNER LE DOCTORAT EN PHARMACIE ?</h1>
            <p>20 niveaux de difficulté - 100 questions dans la banque - Testez votre expertise !</p>
        </header>
        
        <div class="game-container">
            <!-- Tableau des gains -->
            <div class="money-tree" id="moneyTree">
                <h2>TABLEAU DES GAINS</h2>
                <div class="prize-levels" id="prizeLevels">
                    <!-- Généré dynamiquement -->
                </div>
                
                <div class="level-indicator" id="levelIndicator">
                    Niveau: 1/20
                </div>
            </div>
            
            <!-- Section question -->
            <div class="question-section">
                <div class="question-number" id="questionNumber">Niveau 1</div>
                <div class="question-text" id="questionText">Chargement...</div>
                
                <div class="options-grid" id="optionsGrid">
                    <!-- Options générées dynamiquement -->
                </div>
                
                <div class="lifelines">
                    <button class="lifeline-btn" id="fiftyFifty" onclick="useFiftyFifty()">50:50</button>
                    <button class="lifeline-btn" id="phoneFriend" onclick="usePhoneFriend()">Appel à un ami</button>
                    <button class="lifeline-btn" id="askAudience" onclick="useAskAudience()">Public</button>
                </div>
                
                <div class="controls">
                    <button class="control-btn" id="quitBtn" onclick="quitGame()">Arrêter et partir avec mes gains</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Modal pour les résultats -->
    <div id="resultModal" class="modal hidden">
        <div class="modal-content">
            <h2 id="modalTitle">Félicitations !</h2>
            <p id="modalMessage">Vous avez gagné le doctorat en pharmacie !</p>
            <div style="margin: 20px 0;">
                <input type="text" id="playerName" placeholder="Entrez votre nom" style="padding: 10px; width: 80%; border-radius: 5px; border: 1px solid #FFD700; background: #333; color: white;">
            </div>
            <button class="control-btn" onclick="saveScore()">Enregistrer mon score</button>
            <button class="control-btn" style="margin-top: 10px;" onclick="location.reload()">Rejouer</button>
        </div>
    </div>

    <!-- Modal pour le graphique du public -->
    <div id="audienceModal" class="modal hidden">
        <div class="modal-content" style="max-width: 500px;">
            <h2>Résultats du Public</h2>
            <div class="audience-graph">
                <div class="graph-title">Répartition des votes</div>
                <div class="graph-container" id="graphContainer">
                    <!-- Graphique généré dynamiquement -->
                </div>
            </div>
            <button class="control-btn" onclick="closeAudienceModal()">Fermer</button>
        </div>
    </div>

    <script>
        // État audio
        let audioEnabled = true;
        let themePlaying = false;

        // Création des éléments audio avec Web Audio API
        const audioContext = new (window.AudioContext || window.webkitAudioContext)();
        
        function playSound(frequency, duration, type = 'sine', volume = 0.3) {
            if (!audioEnabled) return;
            
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            oscillator.frequency.value = frequency;
            oscillator.type = type;
            
            gainNode.gain.setValueAtTime(volume, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + duration);
            
            oscillator.start(audioContext.currentTime);
            oscillator.stop(audioContext.currentTime + duration);
        }
        
        function playCorrectSound() {
            // Son de succès amélioré (accord majeur)
            playSound(523.25, 0.3, 'sine', 0.4); // C5
            setTimeout(() => playSound(659.25, 0.3, 'sine', 0.4), 250); // E5
            setTimeout(() => playSound(783.99, 0.4, 'sine', 0.4), 500); // G5
            setTimeout(() => playSound(1046.50, 0.5, 'sine', 0.5), 800); // C6 - finale triomphale
        }
        
        function playWrongSound() {
            // Son d'erreur plus dramatique
            playSound(220, 0.2, 'square', 0.5); // A3
            setTimeout(() => playSound(196, 0.2, 'square', 0.5), 150); // G3
            setTimeout(() => playSound(174.61, 0.3, 'square', 0.5), 300); // F3
            setTimeout(() => playSound(146.83, 0.4, 'square', 0.6), 500); // D3
        }
        
        function playLifelineSound() {
            // Son de joker plus riche
            playSound(440, 0.15, 'sine', 0.3); // A4
            setTimeout(() => playSound(554.37, 0.15, 'sine', 0.3), 120); // C#5
            setTimeout(() => playSound(659.25, 0.15, 'sine', 0.3), 240); // E5
            setTimeout(() => playSound(880, 0.25, 'sine', 0.4), 360); // A5
        }
        
        function playThemeMusic() {
            if (!audioEnabled || themePlaying) return;
            themePlaying = true;
            
            // Boucle de musique d'ambiance plus riche
            function playNoteSequence() {
                const notes = [261.63, 329.63, 392.00, 523.25, 392.00, 329.63]; // C4, E4, G4, C5, G4, E4
                let time = audioContext.currentTime;
                
                notes.forEach((note, index) => {
                    const oscillator = audioContext.createOscillator();
                    const gainNode = audioContext.createGain();
                    
                    oscillator.connect(gainNode);
                    gainNode.connect(audioContext.destination);
                    
                    oscillator.frequency.value = note;
                    oscillator.type = 'sine';
                    
                    gainNode.gain.setValueAtTime(0.15, time);
                    gainNode.gain.exponentialRampToValueAtTime(0.01, time + 0.6);
                    
                    oscillator.start(time);
                    oscillator.stop(time + 0.6);
                    
                    time += 0.6;
                });
                
                // Répéter après 3.6 secondes
                setTimeout(playNoteSequence, 3600);
            }
            
            playNoteSequence();
        }

        // Banque de 100 questions - 5 par niveau (20 niveaux)
        const questionBank = [
            // Niveau 1 (Très facile)
            { question: "Quel instrument mesure précisément des volumes ?", options: ["Éprouvette", "Bécher", "Pipette jaugée", "Fiole"], correct: 2, level: 1 },
            { question: "Quelle est l'unité de concentration molaire ?", options: ["g/L", "mol/L", "mol/kg", "%"], correct: 1, level: 1 },
            { question: "Quel est le symbole chimique de l'or ?", options: ["Ag", "Au", "Hg", "Pb"], correct: 1, level: 1 },
            { question: "Quel pH indique une solution acide ?", options: ["pH = 7", "pH > 7", "pH < 7", "pH = 14"], correct: 2, level: 1 },
            { question: "Quel est le principal constituant de l'air ?", options: ["Oxygène", "Azote", "Dioxyde de carbone", "Argon"], correct: 1, level: 1 },
            
            // Niveau 2
            { question: "Quelle technique sépare les composants d'un mélange ?", options: ["Distillation", "Filtration", "Chromatographie", "Extraction"], correct: 2, level: 2 },
            { question: "Quel indicateur est utilisé en titration acido-basique ?", options: ["Phénolphtaléine", "Chlorure de sodium", "Eau distillée", "Éthanol"], correct: 0, level: 2 },
            { question: "Quelle est la formule de l'acide sulfurique ?", options: ["HCl", "HNO3", "H2SO4", "H3PO4"], correct: 2, level: 2 },
            { question: "Quel instrument mesure le pH ?", options: ["Thermomètre", "pH-mètre", "Balance", "Spectrophotomètre"], correct: 1, level: 2 },
            { question: "Quelle est la température normale du corps humain ?", options: ["35°C", "37°C", "39°C", "41°C"], correct: 1, level: 2 },
            
            // Niveau 3
            { question: "Quelle technique utilise la lumière pour analyser ?", options: ["Chromatographie", "Spectroscopie", "Distillation", "Titration"], correct: 1, level: 3 },
            { question: "Quel est le principe de la loi de Beer-Lambert ?", options: ["Concentration proportionnelle à l'absorbance", "Température proportionnelle à la pression", "Volume proportionnel au nombre de moles", "Densité proportionnelle à la masse"], correct: 0, level: 3 },
            { question: "Quel type de liaison est dans les molécules d'eau ?", options: ["Liaison ionique", "Liaison covalente", "Liaison métallique", "Liaison hydrogène"], correct: 1, level: 3 },
            { question: "Quelle est la température d'ébullition de l'eau ?", options: ["0°C", "50°C", "100°C", "150°C"], correct: 2, level: 3 },
            { question: "Quel est le gaz responsable de l'effet de serre ?", options: ["Oxygène", "Azote", "Dioxyde de carbone", "Hydrogène"], correct: 2, level: 3 },
            
            // Niveau 4
            { question: "Quelle technique détermine la structure moléculaire ?", options: ["Titration", "Spectroscopie RMN", "Chromatographie", "pH-métrie"], correct: 1, level: 4 },
            { question: "Quel est le rôle d'un catalyseur ?", options: ["Augmenter l'énergie d'activation", "Diminuer l'énergie d'activation", "Modifier les produits", "Consommer les réactifs"], correct: 1, level: 4 },
            { question: "Quelle est la formule du chlorure de sodium ?", options: ["NaCl", "KCl", "CaCl2", "MgCl2"], correct: 0, level: 4 },
            { question: "Quel gaz est produit par acide + carbonate ?", options: ["Oxygène", "Hydrogène", "Dioxyde de carbone", "Azote"], correct: 2, level: 4 },
            { question: "Quel est le pH d'une solution neutre ?", options: ["pH = 0", "pH = 7", "pH = 14", "pH = 1"], correct: 1, level: 4 },
            
            // Niveau 5
            { question: "Quelle technique purifie des solides ?", options: ["Distillation", "Filtration", "Recristallisation", "Extraction"], correct: 2, level: 5 },
            { question: "Quel est le principe de la chromatographie sur couche mince ?", options: ["Différence de solubilité", "Différence d'adsorption", "Différence de densité", "Différence de température"], correct: 1, level: 5 },
            { question: "Quelle est la masse molaire de l'eau (H2O) ?", options: ["18 g/mol", "20 g/mol", "22 g/mol", "24 g/mol"], correct: 0, level: 5 },
            { question: "Quel est l'état d'oxydation du fer dans Fe2O3 ?", options: ["+1", "+2", "+3", "+4"], correct: 2, level: 5 },
            { question: "Quelle est la formule chimique du glucose ?", options: ["C6H12O6", "C12H22O11", "CH3COOH", "C2H5OH"], correct: 0, level: 5 },
            
            // Niveau 6
            { question: "Quelle technique sépare des liquides miscibles ?", options: ["Filtration", "Décantation", "Distillation", "Extraction"], correct: 2, level: 6 },
            { question: "Quel est le rôle d'un tampon en solution ?", options: ["Augmenter le pH", "Diminuer le pH", "Stabiliser le pH", "Mesurer le pH"], correct: 2, level: 6 },
            { question: "Quelle est la longueur d'onde UV pour composés aromatiques ?", options: ["190 nm", "254 nm", "350 nm", "450 nm"], correct: 1, level: 6 },
            { question: "Quel est le nom de la réaction acide-base ?", options: ["Oxydation", "Réduction", "Neutralisation", "Précipitation"], correct: 2, level: 6 },
            { question: "Quelle est la constante d'Avogadro ?", options: ["6.022 × 10^23", "3.141 × 10^23", "2.718 × 10^23", "1.602 × 10^23"], correct: 0, level: 6 },
            
            // Niveau 7
            { question: "Quelle technique identifie les groupes fonctionnels ?", options: ["Chromatographie", "Spectroscopie IR", "Titration", "Conductimétrie"], correct: 1, level: 7 },
            { question: "Quel est le principe de la spectroscopie d'absorption atomique ?", options: ["Émission de photons", "Absorption de photons par les atomes", "Diffraction des rayons X", "Résonance magnétique"], correct: 1, level: 7 },
            { question: "Quelle est la limite de détection typique ?", options: ["Concentration où S/N = 1", "Concentration où S/N = 3", "Concentration où S/N = 10", "Concentration maximale"], correct: 1, level: 7 },
            { question: "Quel est l'élément le plus abondant dans l'univers ?", options: ["Oxygène", "Carbone", "Hydrogène", "Azote"], correct: 2, level: 7 },
            { question: "Quelle est la formule du peroxyde d'hydrogène ?", options: ["H2O", "H2O2", "HO", "H3O"], correct: 1, level: 7 },
            
            // Niveau 8
            { question: "Quelle technique détermine la masse moléculaire ?", options: ["Spectroscopie UV", "Spectroscopie de masse", "Spectroscopie IR", "RMN"], correct: 1, level: 8 },
            { question: "Quel est le rôle de la phase mobile en chromatographie ?", options: ["Fixer les composés", "Transporter les composés", "Détecter les composés", "Visualiser les composés"], correct: 1, level: 8 },
            { question: "Quelle est la pureté minimale pour un principe actif ?", options: ["90%", "95%", "98%", "99.5%"], correct: 3, level: 8 },
            { question: "Quel est le nom de la réaction qui forme un ester ?", options: ["Hydrolyse", "Esterification", "Saponification", "Oxydation"], correct: 1, level: 8 },
            { question: "Quelle est la température critique de l'eau ?", options: ["100°C", "212°C", "374°C", "450°C"], correct: 2, level: 8 },
            
            // Niveau 9
            { question: "Quelle technique étudie la structure 3D des protéines ?", options: ["Chromatographie", "Diffraction des rayons X", "Spectroscopie UV", "Titration"], correct: 1, level: 9 },
            { question: "Quel est le principe de la polarographie ?", options: ["Mesure de la tension", "Mesure du courant en fonction du potentiel", "Mesure de la résistance", "Mesure de la conductivité"], correct: 1, level: 9 },
            { question: "Quelle est la température critique de l'eau ?", options: ["100°C", "212°C", "374°C", "450°C"], correct: 2, level: 9 },
            { question: "Quel est le nombre d'Avogadro ?", options: ["6.022 × 10^23", "3.141 × 10^23", "2.718 × 10^23", "1.602 × 10^23"], correct: 0, level: 9 },
            { question: "Quelle est la constante de Planck ?", options: ["6.626 × 10^-34 J·s", "3.00 × 10^8 m/s", "1.38 × 10^-23 J/K", "9.11 × 10^-31 kg"], correct: 0, level: 9 },
            
            // Niveau 10
            { question: "Quelle technique étudie les interactions moléculaires ?", options: ["Spectroscopie UV", "Calorimétrie", "Chromatographie", "Titration"], correct: 1, level: 10 },
            { question: "Quel est le rôle d'un étalon en analyse chimique ?", options: ["Nettoyer le matériel", "Étalonner l'instrument", "Réagir avec l'échantillon", "Modifier le pH"], correct: 1, level: 10 },
            { question: "Quelle est la constante de Planck ?", options: ["6.626 × 10^-34 J·s", "3.00 × 10^8 m/s", "1.38 × 10^-23 J/K", "9.11 × 10^-31 kg"], correct: 0, level: 10 },
            { question: "Quel est le pH d'une solution 0.01 M d'acide chlorhydrique ?", options: ["1", "2", "3", "4"], correct: 1, level: 10 },
            { question: "Quelle est l'énergie de liaison O-H dans l'eau ?", options: ["200 kJ/mol", "463 kJ/mol", "600 kJ/mol", "800 kJ/mol"], correct: 1, level: 10 },
            
            // Niveau 11
            { question: "Quelle technique étudie les transitions électroniques ?", options: ["Spectroscopie RMN", "Spectroscopie UV-Visible", "Spectroscopie IR", "Spectroscopie de masse"], correct: 1, level: 11 },
            { question: "Quel est le principe de la voltammétrie ?", options: ["Mesure du courant en fonction du temps", "Mesure du courant en fonction du potentiel", "Mesure de la tension en fonction du temps", "Mesure de la résistance"], correct: 1, level: 11 },
            { question: "Quelle est l'énergie de liaison O-H dans l'eau ?", options: ["200 kJ/mol", "463 kJ/mol", "600 kJ/mol", "800 kJ/mol"], correct: 1, level: 11 },
            { question: "Quel est le nombre de coordination pour le fer dans l'hémoglobine ?", options: ["2", "4", "6", "8"], correct: 2, level: 11 },
            { question: "Quelle est la constante des gaz parfaits R ?", options: ["0.0821 L·atm·mol⁻¹·K⁻¹", "8.314 J·mol⁻¹·K⁻¹", "Les deux sont correctes", "Aucune des réponses"], correct: 2, level: 11 },
            
            // Niveau 12
            { question: "Quelle technique détermine la configuration absolue ?", options: ["Spectroscopie UV", "Diffraction des rayons X", "Spectroscopie IR", "Chromatographie"], correct: 1, level: 12 },
            { question: "Quel est le principe de la spectrométrie d'émission atomique ?", options: ["Absorption de photons", "Émission de photons par atomes excités", "Diffraction d'électrons", "Résonance magnétique"], correct: 1, level: 12 },
            { question: "Quelle est la constante des gaz parfaits R ?", options: ["0.0821 L·atm·mol⁻¹·K⁻¹", "8.314 J·mol⁻¹·K⁻¹", "Les deux sont correctes", "Aucune des réponses"], correct: 2, level: 12 },
            { question: "Quel est le potentiel standard de réduction de Ag⁺/Ag ?", options: ["+0.34 V", "+0.80 V", "-0.76 V", "-2.37 V"], correct: 1, level: 12 },
            { question: "Quelle est l'énergie libre standard de formation de H₂O(l) ?", options: ["-237 kJ/mol", "-120 kJ/mol", "0 kJ/mol", "+237 kJ/mol"], correct: 0, level: 12 },
            
            // Niveau 13
            { question: "Quelle technique étudie les cinétiques de réaction en temps réel ?", options: ["Spectroscopie UV-Visible", "Chromatographie", "Titration", "Conductimétrie"], correct: 0, level: 13 },
            { question: "Quel est le principe de la résonance magnétique nucléaire (RMN) ?", options: ["Absorption de rayons X", "Résonance des noyaux dans un champ magnétique", "Diffraction des électrons", "Émission de photons"], correct: 1, level: 13 },
            { question: "Quelle est l'énergie libre standard de formation de H₂O(l) ?", options: ["-237 kJ/mol", "-120 kJ/mol", "0 kJ/mol", "+237 kJ/mol"], correct: 0, level: 13 },
            { question: "Quel est le nombre quantique principal pour la couche L ?", options: ["n=1", "n=2", "n=3", "n=4"], correct: 1, level: 13 },
            { question: "Quelle est la température de Néel pour le MnO ?", options: ["100 K", "118 K", "200 K", "300 K"], correct: 1, level: 13 },
            
            // Niveau 14
            { question: "Quelle technique étudie les transitions spin dans les complexes métalliques ?", options: ["Spectroscopie IR", "Résonance paramagnétique électronique", "Spectroscopie de masse", "Diffraction des neutrons"], correct: 1, level: 14 },
            { question: "Quel est le principe de l'effet Mössbauer ?", options: ["Résonance magnétique", "Résonance nucléaire sans recul", "Diffraction des rayons X", "Effet photoélectrique"], correct: 1, level: 14 },
            { question: "Quelle est la température de Néel pour le MnO ?", options: ["100 K", "118 K", "200 K", "300 K"], correct: 1, level: 14 },
            { question: "Quel est le moment dipolaire de l'eau ?", options: ["0 D", "1.85 D", "2.95 D", "4.00 D"], correct: 1, level: 14 },
            { question: "Quelle est l'énergie de liaison du N₂ ?", options: ["418 kJ/mol", "945 kJ/mol", "1200 kJ/mol", "1500 kJ/mol"], correct: 1, level: 14 },
            
            // Niveau 15
            { question: "Quelle technique permet d'étudier les transitions spin dans les complexes métalliques ?", options: ["Spectroscopie IR", "Résonance paramagnétique électronique", "Spectroscopie de masse", "Diffraction des neutrons"], correct: 1, level: 15 },
            { question: "Quel est le principe de la spectroscopie EXAFS ?", options: ["Diffraction des rayons X", "Absorption fine des rayons X", "Résonance magnétique", "Diffusion des neutrons"], correct: 1, level: 15 },
            { question: "Quelle est l'énergie de liaison du N₂ ?", options: ["418 kJ/mol", "945 kJ/mol", "1200 kJ/mol", "1500 kJ/mol"], correct: 1, level: 15 },
            { question: "Quel est le rayon ionique de Na⁺ en coordination octaédrique ?", options: ["0.50 Å", "0.95 Å", "1.35 Å", "1.80 Å"], correct: 1, level: 15 },
            { question: "Quelle est la constante de Rydberg ?", options: ["1.097 × 10^7 m⁻¹", "6.626 × 10^-34 J·s", "8.314 J·mol⁻¹·K⁻¹", "9.109 × 10^-31 kg"], correct: 0, level: 15 },
            
            // Niveau 16 (Expert)
            { question: "Quelle technique permet de déterminer la structure électronique des surfaces ?", options: ["Spectroscopie photoélectronique XPS", "Spectroscopie IR", "Chromatographie", "Titration"], correct: 0, level: 16 },
            { question: "Quel est le principe de la diffraction des neutrons ?", options: ["Interaction avec les noyaux atomiques", "Interaction avec les électrons", "Absorption des photons", "Résonance magnétique"], correct: 0, level: 16 },
            { question: "Quelle est la température de Debye du cuivre ?", options: ["150 K", "343 K", "500 K", "700 K"], correct: 1, level: 16 },
            { question: "Quel est le moment magnétique du Fe³⁺ ?", options: ["3.87 μB", "5.92 μB", "4.90 μB", "2.83 μB"], correct: 1, level: 16 },
            { question: "Quelle est la constante de Boltzmann ?", options: ["1.38 × 10^-23 J/K", "6.626 × 10^-34 J·s", "8.314 J·mol⁻¹·K⁻¹", "9.109 × 10^-31 kg"], correct: 0, level: 16 },
            
            // Niveau 17
            { question: "Quelle technique permet d'étudier les vibrations moléculaires à basse fréquence ?", options: ["Spectroscopie Raman", "Spectroscopie IR", "Spectroscopie UV", "RMN"], correct: 0, level: 17 },
            { question: "Quel est le principe de la microscopie à effet tunnel ?", options: ["Tunneling quantique d'électrons", "Diffraction d'électrons", "Émission de photons", "Résonance magnétique"], correct: 0, level: 17 },
            { question: "Quelle est l'énergie de Fermi du cuivre ?", options: ["5.5 eV", "7.0 eV", "9.0 eV", "11.0 eV"], correct: 1, level: 17 },
            { question: "Quel est le coefficient de diffusion de l'eau à 25°C ?", options: ["1.0 × 10^-9 m²/s", "2.3 × 10^-9 m²/s", "5.0 × 10^-9 m²/s", "1.0 × 10^-8 m²/s"], correct: 1, level: 17 },
            { question: "Quelle est la constante de Faraday ?", options: ["96485 C/mol", "8.314 J·mol⁻¹·K⁻¹", "6.022 × 10^23 mol⁻¹", "1.602 × 10^-19 C"], correct: 0, level: 17 },
            
            // Niveau 18
            { question: "Quelle technique permet de cartographier la distribution élémentaire ?", options: ["Microscopie électronique à balayage", "Spectroscopie de masse", "Chromatographie", "Titration"], correct: 0, level: 18 },
            { question: "Quel est le principe de la spectroscopie Mössbauer ?", options: ["Résonance nucléaire sans recul", "Résonance magnétique", "Absorption des rayons X", "Diffraction des neutrons"], correct: 0, level: 18 },
            { question: "Quelle est la température de Curie du fer ?", options: ["580°C", "770°C", "950°C", "1100°C"], correct: 1, level: 18 },
            { question: "Quel est le rayon de Bohr ?", options: ["0.529 Å", "1.000 Å", "2.000 Å", "5.290 Å"], correct: 0, level: 18 },
            { question: "Quelle est la constante de Stefan-Boltzmann ?", options: ["5.67 × 10^-8 W·m⁻²·K⁻⁴", "1.38 × 10^-23 J/K", "6.626 × 10^-34 J·s", "8.314 J·mol⁻¹·K⁻¹"], correct: 0, level: 18 },
            
            // Niveau 19
            { question: "Quelle technique permet d'étudier les états électroniques des matériaux ?", options: ["Spectroscopie photoélectronique", "Spectroscopie IR", "Chromatographie", "Titration"], correct: 0, level: 19 },
            { question: "Quel est le principe de la diffraction des électrons ?", options: ["Ondes de matière", "Résonance magnétique", "Absorption des photons", "Effet photoélectrique"], correct: 0, level: 19 },
            { question: "Quelle est l'énergie de bande interdite du silicium ?", options: ["0.67 eV", "1.12 eV", "1.42 eV", "2.30 eV"], correct: 1, level: 19 },
            { question: "Quel est le coefficient de viscosité de l'eau à 20°C ?", options: ["0.89 × 10^-3 Pa·s", "1.00 × 10^-3 Pa·s", "1.20 × 10^-3 Pa·s", "1.50 × 10^-3 Pa·s"], correct: 1, level: 19 },
            { question: "Quelle est la constante de permittivité du vide ?", options: ["8.854 × 10^-12 F/m", "4π × 10^-7 H/m", "9 × 10^9 N·m²/C²", "1.257 × 10^-6 H/m"], correct: 0, level: 19 },
            
            // Niveau 20 (Doctorat)
            { question: "Quelle technique permet de déterminer la structure locale des matériaux amorphes ?", options: ["Diffraction des rayons X", "Spectroscopie EXAFS", "Microscopie électronique", "Spectroscopie RMN"], correct: 1, level: 20 },
            { question: "Quel est le principe de la spectroscopie de résonance cyclotronique ?", options: ["Mouvement cyclotronique des ions", "Résonance magnétique", "Absorption des photons", "Diffraction des électrons"], correct: 0, level: 20 },
            { question: "Quelle est la température de transition vitreuse du polystyrène ?", options: ["50°C", "100°C", "150°C", "200°C"], correct: 1, level: 20 },
            { question: "Quel est le coefficient de conductivité thermique du cuivre ?", options: ["200 W·m⁻¹·K⁻¹", "400 W·m⁻¹·K⁻¹", "600 W·m⁻¹·K⁻¹", "800 W·m⁻¹·K⁻¹"], correct: 1, level: 20 },
            { question: "Quelle est la constante de structure fine ?", options: ["1/137", "1/100", "1/50", "1/10"], correct: 0, level: 20 }
        ];

        // Tableau des gains par niveau (20 niveaux)
        const prizeLevels = [
            { amount: "100 €", description: "Certificat de participation" },
            { amount: "200 €", description: "Stage d'observation" },
            { amount: "300 €", description: "Manuel de TP", guaranteed: true }, // Palier 1
            { amount: "500 €", description: "Kit de verrerie" },
            { amount: "1 000 €", description: "Balance de précision" },
            { amount: "2 000 €", description: "Spectrophotomètre", guaranteed: true }, // Palier 2
            { amount: "4 000 €", description: "HPLC portable" },
            { amount: "8 000 €", description: "Spectromètre IR" },
            { amount: "15 000 €", description: "Laboratoire mobile", guaranteed: true }, // Palier 3
            { amount: "30 000 €", description: "Bourse de recherche" },
            { amount: "60 000 €", description: "Doctorat partiel" },
            { amount: "120 000 €", description: "Post-doctorat", guaranteed: true }, // Palier 4
            { amount: "250 000 €", description: "Laboratoire de recherche" },
            { amount: "500 000 €", description: "Chaire universitaire" },
            { amount: "750 000 €", description: "Centre de recherche", guaranteed: true }, // Palier 5
            { amount: "1 000 000 €", description: "DOCTORAT EN PHARMACIE", guaranteed: true } // Palier final
        ];

        // État du jeu
        let gameQuestions = [];
        let currentQuestionIndex = 0;
        let lifelinesUsed = {
            fiftyFifty: false,
            phoneFriend: false,
            askAudience: false
        };
        let gameActive = true;
        let playerName = "Joueur";

        // Initialisation audio toggle
        document.getElementById('audioToggle').addEventListener('click', function() {
            audioEnabled = !audioEnabled;
            this.textContent = audioEnabled ? '🔊' : '🔇';
            this.classList.toggle('muted', !audioEnabled);
            
            if (audioEnabled && !themePlaying) {
                playThemeMusic();
            }
        });

        // Effets visuels améliorés
        function createConfetti() {
            const colors = ['#FFD700', '#FF6B6B', '#4ECDC4', '#45B7D1', '#96CEB4', '#FF9F1C', '#2EC4B6'];
            const container = document.body;
            
            for (let i = 0; i < 200; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-10px';
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.width = Math.random() * 12 + 6 + 'px';
                confetti.style.height = Math.random() * 12 + 6 + 'px';
                confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '0';
                confetti.style.opacity = '0';
                container.appendChild(confetti);
                
                // Animation améliorée
                const animation = confetti.animate([
                    { transform: 'translateY(0) rotate(0deg) scale(0)', opacity: 0 },
                    { transform: `translateY(${window.innerHeight * 0.3}px) rotate(${Math.random() * 360}deg) scale(1)`, opacity: 1 },
                    { transform: `translateY(${window.innerHeight}px) rotate(${Math.random() * 720}deg) scale(${Math.random() * 2})`, opacity: 0 }
                ], {
                    duration: Math.random() * 4000 + 3000,
                    easing: 'cubic-bezier(0.1, 0.8, 0.2, 1)',
                    delay: Math.random() * 1000
                });
                
                animation.onfinish = () => confetti.remove();
            }
        }

        function createVictoryEffect() {
            const container = document.querySelector('.modal-content');
            for (let i = 0; i < 12; i++) {
                const effect = document.createElement('div');
                effect.className = 'victory-effect';
                effect.style.left = Math.random() * 100 + '%';
                effect.style.top = Math.random() * 100 + '%';
                effect.style.width = Math.random() * 100 + 100 + 'px';
                effect.style.height = effect.style.width;
                container.appendChild(effect);
                
                effect.animate([
                    { transform: 'scale(0)', opacity: 0 },
                    { transform: 'scale(1)', opacity: 0.4 },
                    { transform: 'scale(3)', opacity: 0 }
                ], {
                    duration: 2500,
                    delay: i * 150,
                    easing: 'ease-out'
                });
                
                setTimeout(() => effect.remove(), 2500);
            }
        }

        // Fonction pour fermer le modal du public
        function closeAudienceModal() {
            document.getElementById('audienceModal').classList.add('hidden');
        }

        // Initialisation
        function initGame() {
            selectRandomQuestions();
            updatePrizeTree();
            loadQuestion();
            updateLifelines();
            loadLeaderboard();
            
            // Jouer la musique d'ambiance
            if (audioEnabled) {
                playThemeMusic();
            }
        }

        function selectRandomQuestions() {
            gameQuestions = [];
            for (let level = 1; level <= 20; level++) {
                const levelQuestions = questionBank.filter(q => q.level === level);
                const randomIndex = Math.floor(Math.random() * levelQuestions.length);
                gameQuestions.push(levelQuestions[randomIndex]);
            }
        }

        function updatePrizeTree() {
            const prizeLevelsContainer = document.getElementById('prizeLevels');
            prizeLevelsContainer.innerHTML = '';
            
            prizeLevels.forEach((prize, index) => {
                const prizeItem = document.createElement('div');
                prizeItem.className = 'prize-item';
                
                if (index === currentQuestionIndex) {
                    prizeItem.classList.add('active');
                } else if (index < currentQuestionIndex && prize.guaranteed) {
                    prizeItem.classList.add('guaranteed');
                } else if (index < currentQuestionIndex) {
                    prizeItem.classList.add('won');
                }
                
                prizeItem.innerHTML = `
                    <div class="prize-amount">${prize.amount}</div>
                    <div class="prize-description">${prize.description}</div>
                `;
                prizeLevelsContainer.appendChild(prizeItem);
            });
            
            document.getElementById('levelIndicator').textContent = `Niveau: ${currentQuestionIndex + 1}/20`;
        }

        function loadQuestion() {
            if (currentQuestionIndex >= gameQuestions.length) {
                showWinModal();
                return;
            }
            
            const question = gameQuestions[currentQuestionIndex];
            document.getElementById('questionNumber').textContent = `Niveau ${currentQuestionIndex + 1}`;
            document.getElementById('questionText').textContent = question.question;
            
            const optionsGrid = document.getElementById('optionsGrid');
            optionsGrid.innerHTML = '';
            
            const letters = ['A', 'B', 'C', 'D'];
            question.options.forEach((option, index) => {
                const optionBtn = document.createElement('button');
                optionBtn.className = 'option-btn';
                optionBtn.innerHTML = `
                    <span class="option-letter">${letters[index]}</span>
                    ${option}
                `;
                optionBtn.onclick = () => selectAnswer(index);
                optionsGrid.appendChild(optionBtn);
            });
            
            updatePrizeTree();
        }

        function selectAnswer(selectedIndex) {
            if (!gameActive) return;
            
            const question = gameQuestions[currentQuestionIndex];
            const optionButtons = document.querySelectorAll('.option-btn');
            
            optionButtons.forEach(btn => btn.disabled = true);
            
            if (selectedIndex === question.correct) {
                optionButtons[selectedIndex].style.background = 'linear-gradient(135deg, #00ff00, #00cc00)';
                optionButtons[selectedIndex].style.borderColor = '#00ff00';
                playCorrectSound();
                
                setTimeout(() => {
                    currentQuestionIndex++;
                    if (currentQuestionIndex <= gameQuestions.length) {
                        loadQuestion();
                        resetLifelines();
                    }
                }, 2000);
            } else {
                optionButtons[selectedIndex].style.background = 'linear-gradient(135deg, #ff0000, #cc0000)';
                optionButtons[selectedIndex].style.borderColor = '#ff0000';
                optionButtons[question.correct].style.background = 'linear-gradient(135deg, #00ff00, #00cc00)';
                optionButtons[question.correct].style.borderColor = '#00ff00';
                playWrongSound();
                
                gameActive = false;
                setTimeout(() => {
                    showLoseModal();
                }, 2500);
            }
        }

        function useFiftyFifty() {
            if (lifelinesUsed.fiftyFifty || !gameActive) return;
            
            lifelinesUsed.fiftyFifty = true;
            updateLifelines();
            playLifelineSound();
            
            const question = gameQuestions[currentQuestionIndex];
            const optionButtons = document.querySelectorAll('.option-btn');
            const wrongOptions = [];
            
            for (let i = 0; i < 4; i++) {
                if (i !== question.correct) {
                    wrongOptions.push(i);
                }
            }
            
            const toRemove = [];
            while (toRemove.length < 2 && wrongOptions.length > 0) {
                const randomIndex = Math.floor(Math.random() * wrongOptions.length);
                toRemove.push(wrongOptions.splice(randomIndex, 1)[0]);
            }
            
            toRemove.forEach(index => {
                optionButtons[index].style.opacity = '0.3';
                optionButtons[index].style.textDecoration = 'line-through';
                optionButtons[index].disabled = true;
            });
        }

        function usePhoneFriend() {
            if (lifelinesUsed.phoneFriend || !gameActive) return;
            
            lifelinesUsed.phoneFriend = true;
            updateLifelines();
            playLifelineSound();
            
            const question = gameQuestions[currentQuestionIndex];
            const letters = ['A', 'B', 'C', 'D'];
            const correctLetter = letters[question.correct];
            
            // L'ami donne toujours la bonne réponse avec confiance
            const advice = `Je suis absolument certain que la réponse correcte est la ${correctLetter} ! Je viens de vérifier dans mon manuel de référence.`;
            
            alert(`Votre ami expert en pharmacie vous dit : "${advice}"`);
        }

        function useAskAudience() {
            if (lifelinesUsed.askAudience || !gameActive) return;
            
            lifelinesUsed.askAudience = true;
            updateLifelines();
            playLifelineSound();
            
            const question = gameQuestions[currentQuestionIndex];
            const percentages = [0, 0, 0, 0];
            
            // Le public a tendance à voter majoritairement pour la bonne réponse
            const difficulty = question.level;
            let correctPercentage;
            
            if (difficulty <= 5) {
                correctPercentage = 70 + Math.floor(Math.random() * 20); // 70-90%
            } else if (difficulty <= 10) {
                correctPercentage = 50 + Math.floor(Math.random() * 25); // 50-75%
            } else if (difficulty <= 15) {
                correctPercentage = 35 + Math.floor(Math.random() * 20); // 35-55%
            } else {
                correctPercentage = 25 + Math.floor(Math.random() * 15); // 25-40%
            }
            
            percentages[question.correct] = correctPercentage;
            let remaining = 100 - correctPercentage;
            
            // Distribuer le reste aux autres options
            const otherIndices = [0, 1, 2, 3].filter(i => i !== question.correct);
            otherIndices.forEach((index, i) => {
                if (i === otherIndices.length - 1) {
                    percentages[index] = remaining;
                } else {
                    const value = Math.floor(Math.random() * Math.min(remaining, Math.floor(remaining / (otherIndices.length - i))));
                    percentages[index] = value;
                    remaining -= value;
                }
            });
            
            // Afficher le graphique
            showAudienceGraph(percentages, question.correct);
        }

        function showAudienceGraph(percentages, correctIndex) {
            const graphContainer = document.getElementById('graphContainer');
            graphContainer.innerHTML = '';
            const letters = ['A', 'B', 'C', 'D'];
            
            // Trier par pourcentage décroissant pour un affichage plus clair
            const sortedIndices = [0, 1, 2, 3].sort((a, b) => percentages[b] - percentages[a]);
            
            sortedIndices.forEach(index => {
                const bar = document.createElement('div');
                bar.className = 'graph-bar';
                if (index === correctIndex) {
                    bar.classList.add('correct');
                }
                
                // Calculer la largeur en fonction du pourcentage
                const width = Math.max(20, percentages[index]); // Minimum 20% pour la visibilité
                
                bar.style.width = width + '%';
                bar.innerHTML = `
                    <div class="graph-label">${letters[index]}</div>
                    <div class="graph-percentage">${percentages[index]}%</div>
                `;
                graphContainer.appendChild(bar);
            });
            
            document.getElementById('audienceModal').classList.remove('hidden');
        }

        function updateLifelines() {
            document.getElementById('fiftyFifty').disabled = lifelinesUsed.fiftyFifty;
            document.getElementById('phoneFriend').disabled = lifelinesUsed.phoneFriend;
            document.getElementById('askAudience').disabled = lifelinesUsed.askAudience;
        }

        function resetLifelines() {
            // Les jokers restent utilisés pour toute la partie
        }

        function quitGame() {
            if (!gameActive) return;
            
            let winningsLevel = -1;
            for (let i = currentQuestionIndex - 1; i >= 0; i--) {
                if (prizeLevels[i].guaranteed) {
                    winningsLevel = i;
                    break;
                }
            }
            
            if (winningsLevel === -1 && currentQuestionIndex > 0) {
                winningsLevel = currentQuestionIndex - 1;
            }
            
            showQuitModal(winningsLevel);
        }

        function showWinModal() {
            document.getElementById('modalTitle').textContent = 'FÉLICITATIONS !';
            document.getElementById('modalMessage').textContent = 'Vous avez remporté le DOCTORAT EN PHARMACIE et 1 000 000 € !\n\nVotre expertise en chimie analytique est désormais reconnue mondialement !';
            document.getElementById('resultModal').classList.remove('hidden');
            gameActive = false;
            
            // Effets de victoire améliorés
            createConfetti();
            createVictoryEffect();
            playCorrectSound();
            setTimeout(playCorrectSound, 800);
            setTimeout(() => {
                playSound(1046.50, 1.0, 'sine', 0.6); // Note finale triomphale
            }, 1600);
        }

        function showLoseModal() {
            let lastGuaranteed = -1;
            for (let i = currentQuestionIndex - 1; i >= 0; i--) {
                if (prizeLevels[i].guaranteed) {
                    lastGuaranteed = i;
                    break;
                }
            }
            
            const amountWon = lastGuaranteed >= 0 ? prizeLevels[lastGuaranteed].amount : "0 €";
            const description = lastGuaranteed >= 0 ? prizeLevels[lastGuaranteed].description : "rien, mais vous pouvez réessayer !";
            
            document.getElementById('modalTitle').textContent = 'DOMMAGE !';
            document.getElementById('modalMessage').textContent = `La bonne réponse était : ${gameQuestions[currentQuestionIndex].options[gameQuestions[currentQuestionIndex].correct]}\n\nVous repartez avec ${amountWon} et ${description.toLowerCase()} !\nNe perdez pas espoir, révisez vos techniques analytiques !`;
            document.getElementById('resultModal').classList.remove('hidden');
            playWrongSound();
        }

        function showQuitModal(winningsLevel) {
            gameActive = false;
            const amountWon = winningsLevel >= 0 ? prizeLevels[winningsLevel].amount : "0 €";
            const description = winningsLevel >= 0 ? prizeLevels[winningsLevel].description : "rien";
            
            document.getElementById('modalTitle').textContent = 'CHOIX SAGE !';
            document.getElementById('modalMessage').textContent = `Vous avez choisi d'arrêter et de repartir avec ${amountWon} et ${description.toLowerCase()} !\n\nUne décision prudente pour un futur pharmacien !`;
            document.getElementById('resultModal').classList.remove('hidden');
            playCorrectSound(); // Son positif pour choix sage
        }

        function saveScore() {
            playerName = document.getElementById('playerName').value.trim() || "Joueur anonyme";
            const score = currentQuestionIndex;
            
            let leaderboard = JSON.parse(localStorage.getItem('pharmaLeaderboard') || '[]');
            leaderboard.push({ name: playerName, score: score });
            leaderboard.sort((a, b) => b.score - a.score);
            leaderboard = leaderboard.slice(0, 10);
            localStorage.setItem('pharmaLeaderboard', JSON.stringify(leaderboard));
            
            loadLeaderboard();
            document.getElementById('resultModal').classList.add('hidden');
        }

        function loadLeaderboard() {
            let leaderboard = JSON.parse(localStorage.getItem('pharmaLeaderboard') || '[]');
            const leaderboardList = document.getElementById('leaderboardList');
            if (!leaderboardList) return;
            
            leaderboardList.innerHTML = '';
            if (leaderboard.length === 0) {
                leaderboardList.innerHTML = '<div style="text-align: center; padding: 10px; color: #ccc;">Aucun score enregistré</div>';
                return;
            }
            
            leaderboard.forEach((player, index) => {
                const scoreItem = document.createElement('div');
                scoreItem.className = 'score-item';
                if (player.name === playerName && player.score === currentQuestionIndex) {
                    scoreItem.classList.add('you');
                }
                scoreItem.innerHTML = `
                    <span>${index + 1}. ${player.name}</span>
                    <span>${player.score}/20 niveaux</span>
                `;
                leaderboardList.appendChild(scoreItem);
            });
        }

        // Initialiser le jeu
        window.onload = initGame;
    </script>
</body>
</html>


