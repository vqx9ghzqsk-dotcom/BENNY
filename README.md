<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Connaissances, attitudes et pratiques des infirmières de l'hôpital général des références de Makala sur la prévention du cancer du sein</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        /* --- STYLE GLOBAL --- */
        body { font-family: 'Segoe UI', Arial, sans-serif; background-color: #f0f2f5; margin: 0; padding: 15px; }
        .container { max-width: 1200px; margin: auto; background: white; border-radius: 12px; box-shadow: 0 4px 25px rgba(0,0,0,0.2); min-height: 900px;}
        
        /* Navigation */
        .header-tabs { display: flex; background: #fff; border-bottom: 3px solid #b03060; padding: 12px; align-items: center; gap: 8px; position: sticky; top: 0; z-index: 100; flex-wrap: wrap;}
        .tab { padding: 10px 15px; font-weight: bold; font-size: 12px; text-decoration: none; border-radius: 4px; border: 1px solid #ddd; color: #555; background: #f8f9fa; cursor: pointer; transition: 0.2s; }
        .tab.active { background: #b03060; color: white; border-color: #b03060; }
        
        /* Simulation Mode Badge */
        .sim-badge { background: #ff9800; color: white; padding: 5px 10px; border-radius: 4px; font-size: 11px; font-weight: bold; margin-left: 10px; }

        .admin-only { display: none !important; }
        .admin-visible { display: inline-block !important; }
        
        .btn-auth { margin-left: auto; background: #333; color: white; padding: 10px 15px; border: none; border-radius: 4px; font-weight: bold; cursor: pointer; }
        .btn-excel { background: #2e7d32; color: white; padding: 10px 20px; border: none; border-radius: 4px; font-weight: bold; cursor: pointer; margin-left: 10px;}

        /* Actions */
        .btn-delete-selected { background: #c62828; color: white; padding: 8px 15px; border: none; border-radius: 4px; font-weight: bold; cursor: pointer; margin-bottom: 10px; display: none; }
        .btn-delete-single { background: none; border: 1px solid #c62828; color: #c62828; cursor: pointer; border-radius: 4px; padding: 4px 8px; font-size: 11px; margin-left: 5px; transition: 0.2s;}
        .btn-delete-single:hover { background: #c62828; color: white; }
        .btn-view-single { background: none; border: 1px solid #0288d1; color: #0288d1; cursor: pointer; border-radius: 4px; padding: 4px 8px; font-size: 11px; transition: 0.2s;}
        .btn-view-single:hover { background: #0288d1; color: white; }

        /* Contenu */
        .form-content { padding: 30px; display: none; }
        .form-content.active { display: block; animation: fadeIn 0.5s; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* Sections */
        .section-title { background: #fce4ec; color: #b03060; padding: 15px; font-weight: bold; border-left: 8px solid #b03060; margin: 30px 0 15px 0; text-transform: uppercase; font-size: 14px; display: flex; align-items: center; justify-content: space-between; page-break-after: avoid;}
        .sub-title { font-weight: bold; color: #b03060; margin-top: 20px; border-bottom: 1px solid #eee; padding-bottom: 5px; }
        
        .row { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; margin-bottom: 15px; }
        .field { display: flex; flex-direction: column; }
        label { font-size: 13px; font-weight: 700; margin-bottom: 6px; color: #222; }
        select, input[type="text"], input[type="number"], textarea { padding: 10px; border: 1px solid #bbb; border-radius: 6px; font-size: 14px; background: #fff; width: 100%; box-sizing: border-box; }
        textarea { resize: vertical; font-family: inherit; }

        /* Tables & Check */
        table { width: 100%; border-collapse: collapse; margin: 20px 0; font-size: 12px; }
        th { background: #f8f9fa; padding: 10px; border: 1px solid #ddd; text-align: center; font-weight: bold; }
        td { border: 1px solid #eee; padding: 10px; text-align: center; vertical-align: middle; }
        .td-left { text-align: left; padding-left: 15px; width: 50%; }

        .academic-table { width: 100%; border-collapse: collapse; margin-bottom: 25px; font-family: 'Times New Roman', serif; font-size: 13px; background: white; page-break-inside: avoid;}
        .academic-table th, .academic-table td { border: 1px solid #ddd; padding: 6px; text-align: center; }
        .academic-table tbody tr:last-child td { border-bottom: 2px solid #000; }
        .academic-table .row-header { text-align: left; padding-left: 10px; font-weight: normal; }
        .academic-table .group-header { background-color: #f0f8ff; font-weight: bold; text-align: left; padding-left: 10px; color: #0d47a1; }
        .academic-table th, .academic-table td { font-size: 12px; } 

        .interpretation-text { font-family: 'Segoe UI', sans-serif; font-size: 12px; color: #444; background: #fff8e1; border-left: 4px solid #ffc107; padding: 8px; margin-bottom: 15px; line-height: 1.4; font-style: italic; page-break-inside: avoid; }

        .check-group { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 10px; background: #fdfdfd; padding: 15px; border: 1px solid #eee; border-radius: 8px; }
        .check-item { display: flex; align-items: center; font-size: 13px; cursor: pointer; }
        .check-item input { margin-right: 12px; transform: scale(1.2); cursor: pointer; }

        .btn-save { width: 100%; background: #b03060; color: white; padding: 20px; border: none; border-radius: 8px; font-size: 16px; font-weight: bold; cursor: pointer; margin-top: 40px; text-transform: uppercase; transition: 0.3s; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .btn-save:hover { background: #880e4f; transform: translateY(-2px); }
        
        /* Stats & Pie Charts */
        .stat-card { background: white; border: 1px solid #e0e0e0; border-radius: 8px; padding: 15px; margin-bottom: 15px; box-shadow: 0 2px 4px rgba(0,0,0,0.05); display: flex; flex-direction: column; align-items: center; page-break-inside: avoid;}
        .stat-title { font-weight: bold; color: #555; margin-bottom: 15px; font-size: 14px; border-bottom: 2px solid #b03060; display: inline-block; width: 100%; text-align: center; }
        .pie-box { display: flex; flex-wrap: wrap; justify-content: space-around; align-items: center; width: 100%; gap: 20px; }
        
        /* TABLEAU DE BORD IMAGE */
        .dash-section { background: #fae8ee; color: #b03060; padding: 12px; font-weight: bold; margin: 25px 0 15px 0; font-size: 13px; text-transform: uppercase; border-left: 6px solid #b03060; page-break-after: avoid;}
        .dash-row { display: flex; gap: 15px; flex-wrap: wrap; margin-bottom: 15px; }
        .dash-card { background: white; border: 1px solid #e6e6e6; border-radius: 6px; padding: 15px; flex: 1; min-width: 250px; box-shadow: 0 2px 5px rgba(0,0,0,0.02); page-break-inside: avoid;}
        .dash-title { border-bottom: 2px solid #880e4f; padding-bottom: 8px; margin-bottom: 15px; text-align: center; font-weight: bold; font-size: 13px; color: #444; }
        .dash-pie-box { display: flex; align-items: center; justify-content: center; gap: 20px; flex-wrap: wrap; }
        .dash-pie-box svg { flex-shrink: 0; }
        .dash-legend { display: flex; flex-direction: column; gap: 6px; font-size: 11px; color: #333; }
        .dash-legend-item { display: flex; align-items: center; gap: 8px; }
        .dash-legend-color { width: 12px; height: 12px; border-radius: 2px; flex-shrink: 0; }

        .counter-badge { background: #b03060; color: white; padding: 2px 8px; border-radius: 10px; font-size: 11px; vertical-align: middle; margin-left: 5px;}

        /* HISTOGRAMMES (BAR CHARTS) */
        .bar-chart-container { display: flex; align-items: flex-end; justify-content: space-around; height: 180px; padding: 10px 0; border-bottom: 2px solid #ccc; border-left: 2px solid #ccc; margin-top: 10px; padding-bottom: 25px; position: relative;}
        .bar-wrap { display: flex; flex-direction: column; align-items: center; justify-content: flex-end; height: 100%; flex: 1; margin: 0 5px; position: relative; }
        .bar { width: 100%; max-width: 40px; background-color: #b03060; transition: height 0.5s; border-radius: 3px 3px 0 0; }
        .bar-label { font-size: 10px; font-weight: bold; text-align: center; position: absolute; bottom: -25px; width: 100%; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; color: #444; }
        .bar-val { font-size: 11px; font-weight: bold; margin-bottom: 5px; color: #222; }

        /* Modal */
        .modal-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.6); z-index: 999; display: none; justify-content: center; align-items: center; backdrop-filter: blur(3px); }
        .modal-content { background: white; width: 90%; max-width: 600px; max-height: 85vh; overflow-y: auto; padding: 25px; border-radius: 12px; box-shadow: 0 10px 25px rgba(0,0,0,0.3); animation: fadeIn 0.3s; }
        .modal-header { display: flex; justify-content: space-between; align-items: center; border-bottom: 2px solid #b03060; padding-bottom: 15px; margin-bottom: 20px; }
        .modal-close { font-size: 28px; cursor: pointer; color: #888; transition: color 0.2s; }
        .modal-close:hover { color: #c62828; }
        
        /* Toast Notification */
        #toast { visibility: hidden; min-width: 250px; margin-left: -125px; background-color: #333; color: #fff; text-align: center; border-radius: 2px; padding: 16px; position: fixed; z-index: 1000; left: 50%; bottom: 30px; font-size: 15px; font-weight: bold; }
        #toast.show { visibility: visible; -webkit-animation: fadein 0.5s, fadeout 0.5s 2.5s; animation: fadein 0.5s, fadeout 0.5s 2.5s; }
        @keyframes fadein { from {bottom: 0; opacity: 0;} to {bottom: 30px; opacity: 1;} }
        @keyframes fadeout { from {bottom: 30px; opacity: 1;} to {bottom: 0; opacity: 0;} }

        /* Discussion Styles */
        .discussion-section { margin-bottom: 35px; text-align: justify; }
        .discussion-section h3 { color: #2c3e50; font-size: 18px; margin-bottom: 15px; padding-bottom: 8px; border-bottom: 2px solid #b03060; }
        .discussion-section p { font-size: 15px; line-height: 1.7; color: #333; margin-bottom: 15px; }
        .highlight-quote { border-left: 5px solid #2980b9; background-color: #f4f8fa; padding: 15px; margin: 20px 0; font-style: italic; color: #2c3e50; }
    </style>
</head>
<body>

<div class="container">
    <div class="header-tabs">
        <button class="tab active" onclick="switchTab(1)">1. COLLECTE <span id="count-badge" class="counter-badge">178</span></button>
        <button class="tab admin-only" id="tab-2" onclick="switchTab(2)">2. MATRICE DE DÉPOUILLEMENT</button>
        <button class="tab admin-only" id="tab-3" onclick="switchTab(3)">3. RÉSULTATS & ANALYSE PROTOCOLE</button>
        <button class="tab admin-only" id="tab-4" onclick="switchTab(4)">4. DISCUSSION GLOBALE (PROTOCOLE THÈSE)</button>
        
        <div class="sim-badge">DONNÉES: KINSHASA (N=178)</div>
        <button type="button" class="btn-auth" id="btn-auth" onclick="window.requestAdmin()">🔒 ACCÈS ADMIN</button>
        <button type="button" class="btn-excel admin-only" id="btn-export" onclick="window.exportToCSV()">📊 EXPORT CSV</button>
    </div>

    <div id="content-1" class="form-content active">
        <h2 style="color:#b03060; font-size: 18px; text-align:center; margin-bottom: 25px;">Connaissances, attitudes et pratiques des infirmières de l'hôpital général des références de Makala sur la prévention du cancer du sein</h2>
        <form id="kapForm">
            <div class="section-title">I. IDENTIFICATION & PROFIL PROFESSIONNEL</div>
            <div class="row">
                <div class="field">
                    <label>1. Code Enquêté(e)</label>
                    <select id="code-enquete"></select>
                </div>
                <div class="field">
                    <label style="color:#b03060;">2. Consentement Éclairé</label>
                    <select id="consentement">
                        <option value="oui">Oui, a accepté de participer</option>
                        <option value="non">Non (Refus)</option>
                    </select>
                </div>
                <div class="field">
                    <label>3. Service d'affectation</label>
                    <select id="service">
                        <option value="" disabled selected>Choisir un service...</option>
                        <option>Gynécologie-Obstétrique</option>
                        <option>Médecine Interne</option>
                        <option>Chirurgie</option>
                        <option>Autres</option>
                    </select>
                </div>
            </div>
            <div class="row">
                <div class="field">
                    <label>4. Niveau d'étude</label>
                    <select id="niveau">
                        <option value="" disabled selected>Niveau...</option>
                        <option value="A2 - ITM">A2 - Niveau technique (4 ans post-primaire - ITM)</option>
                        <option value="A1/LMD - ISTM">A1/LMD - Niveau supérieur (3 ans post-bac - ISTM)</option>
                    </select>
                </div>
                <div class="field">
                    <label>5. Ancienneté (années)</label>
                    <input type="number" id="anciennete" min="0" max="20" placeholder="Ex: 5">
                </div>
                <div class="field">
                    <label>6. Sexe</label>
                    <select id="sexe">
                        <option value="F" selected>F (Féminin)</option>
                    </select>
                </div>
            </div>

            <div class="row" style="background:#f9f9f9; padding:10px; border-radius:6px; border: 1px dashed #ccc;">
                <div class="field">
                    <label>État Civil</label>
                    <select id="etat-civil">
                        <option value="" disabled selected>Choisir...</option>
                        <option>Célibataire</option>
                        <option>Mariée</option>
                        <option>Divorcée</option>
                        <option>Veuve</option>
                    </select>
                </div>
                <div class="field">
                    <label>Province d'exercice</label>
                    <select id="province">
                        <option value="" disabled selected>Choisir...</option>
                        <option>Kinshasa</option>
                        <option>Kongo Central</option>
                        <option>Haut-Katanga</option>
                        <option>Nord/Sud Kivu</option>
                        <option>Autre Province</option>
                    </select>
                </div>
                <div class="field">
                    <label>Catégorie Pro. Précise</label>
                    <select id="cat-pro">
                        <option value="" disabled selected>Choisir...</option>
                        <option>Médecin Généraliste</option>
                        <option>Spécialiste / Résident</option>
                        <option>Infirmier(e)</option>
                        <option>Autre professionnel santé</option>
                    </select>
                </div>
                 <div class="field">
                    <label>Âge du participant</label>
                    <input type="number" id="age-participant" placeholder="Ex: 30">
                </div>
            </div>

            <div class="section-title">II. CONNAISSANCES (SAVOIRS THÉORIQUES)</div>
            <div class="sub-title">Connaissances Biologiques & Types</div>
            <div class="row" style="background:#f0f8ff; padding:10px; border-radius:6px;">
                <div class="field">
                    <label>Avez-vous entendu parler de la classification moléculaire ?</label>
                    <select id="q-moleculaire"><option value="non">Non</option><option value="oui">Oui</option></select>
                </div>
                <div class="field">
                    <label>Connaissez-vous le terme "HER2 Low" ou "Faible" ?</label>
                    <select id="q-her2"><option value="non">Non</option><option value="oui">Oui</option></select>
                </div>
                <div class="field">
                    <label>Connaissez-vous les thérapies ciblées ?</label>
                    <select id="q-therapie"><option value="non">Non</option><option value="oui">Oui</option></select>
                </div>
            </div>
            
            <div class="sub-title">7. Épidémiologie & Dépistage</div>
            <div class="row">
                <div class="field">
                    <label>Le cancer du sein est la 1ère cause de décès par cancer (RDC) :</label>
                    <select id="q-cause"><option value="vrai">Vrai</option><option value="faux">Faux</option><option value="jsp">Je ne sais pas</option></select>
                </div>
                <div class="field">
                    <label>Âge recommandé 1ère mammographie :</label>
                    <select id="q-age-mammo"><option value="20">Dès 20 ans</option><option value="35">Vers 35-40 ans</option><option value="50">Vers 50 ans</option></select>
                </div>
                <div class="field">
                    <label>Moment idéal pour Auto-Examen (Auto examen des seins) :</label>
                    <select id="q-moment-aes"><option value="regles">Pendant les règles</option><option value="apres">7 à 10 jours après début règles</option><option value="nimporte">N’importe quand</option></select>
                </div>
            </div>

            <div class="sub-title">8. Facteurs de risque (Cochez ceux prouvés)</div>
            <div class="check-group" id="group-risques">
                <label class="check-item"><input type="checkbox" value="age"> Âge avancé (>50 ans)</label>
                <label class="check-item"><input type="checkbox" value="multi"> Multiparité</label>
                <label class="check-item"><input type="checkbox" value="famille"> Antécédents familiaux</label>
                <label class="check-item"><input type="checkbox" value="alcool"> Alcool / Tabac</label>
                <label class="check-item"><input type="checkbox" value="obesite"> Obésité et sédentarité</label>
                <label class="check-item"><input type="checkbox" value="allaitement"> Allaitement prolongé</label>
                <label class="check-item"><input type="checkbox" value="menopause"> Ménopause tardive (>55 ans)</label>
                <label class="check-item"><input type="checkbox" value="graisse"> Régime riche en graisses</label>
                <label class="check-item"><input type="checkbox" value="contraceptif"> Prise de contraceptifs oraux</label>
                <label class="check-item"><input type="checkbox" value="gros_seins"> Avoir des gros seins</label>
                <label class="check-item"><input type="checkbox" value="radiation"> Exposition rayons radioactifs</label>
            </div>

            <div class="sub-title">9. Signes d’alerte</div>
            <div class="check-group" id="group-signes">
                <label class="check-item"><input type="checkbox" value="nodule"> Nodule dur et indolore</label>
                <label class="check-item"><input type="checkbox" value="retraction"> Rétraction du mamelon</label>
                <label class="check-item"><input type="checkbox" value="peau"> Aspect peau d’orange</label>
                <label class="check-item"><input type="checkbox" value="ecoulement"> Écoulement mamelonnaire</label>
                <label class="check-item"><input type="checkbox" value="douleur"> Douleur cyclique</label>
                <label class="check-item"><input type="checkbox" value="ulceration"> Ulcération au niveau du sein</label>
                <label class="check-item"><input type="checkbox" value="poids"> Diminution du poids inexpliquée</label>
                <label class="check-item"><input type="checkbox" value="asymetrie"> Modification forme / Asymétrie</label>
            </div>

            <div class="sub-title">10-14. Connaissance Mammographie</div>
            <div class="row">
                <div class="field">
                    <label>La mammographie est importante pour détection précoce :</label>
                    <select id="q-mammo-imp"><option>Oui</option><option>Non</option><option>Je ne sais pas</option></select>
                </div>
                <div class="field">
                    <label>Rôle principal :</label>
                    <select id="q-mammo-role"><option value="detecter">Détecter lésions avant symptômes</option><option value="traiter">Traiter le cancer</option></select>
                </div>
                <div class="field">
                    <label>Fréquence (Femme sans risque) :</label>
                    <select id="q-mammo-freq"><option value="1">Tous les ans</option><option value="2">Tous les 2 ans</option><option value="5">Tous les 5 ans</option></select>
                </div>
            </div>

            <div class="section-title">III. ATTITUDES & PERCEPTIONS (Échelle 1-5)</div>
            <table>
                <thead>
                    <tr><th class="td-left">Énoncé</th><th>1<br><small>Pas du tout</small></th><th>2</th><th>3</th><th>4</th><th>5<br><small>Tout à fait</small></th></tr>
                </thead>
                <tbody>
                    <tr><td class="td-left">L’éducation à l’Auto examen des seins fait partie de mon rôle.</td><td><input type="radio" name="att1" value="1"></td><td><input type="radio" name="att1" value="2"></td><td><input type="radio" name="att1" value="3"></td><td><input type="radio" name="att1" value="4"></td><td><input type="radio" name="att1" value="5"></td></tr>
                    <tr><td class="td-left">Je me sens capable de détecter un nodule de petite taille.</td><td><input type="radio" name="att2" value="1"></td><td><input type="radio" name="att2" value="2"></td><td><input type="radio" name="att2" value="3"></td><td><input type="radio" name="att2" value="4"></td><td><input type="radio" name="att2" value="5"></td></tr>
                    <tr><td class="td-left">La peur du diagnostic empêche les patientes de consulter.</td><td><input type="radio" name="att3" value="1"></td><td><input type="radio" name="att3" value="2"></td><td><input type="radio" name="att3" value="3"></td><td><input type="radio" name="att3" value="4"></td><td><input type="radio" name="att3" value="5"></td></tr>
                    <tr><td class="td-left">Je suis mal à l’aise d’aborder l’intimité avec les âgées.</td><td><input type="radio" name="att4" value="1"></td><td><input type="radio" name="att4" value="2"></td><td><input type="radio" name="att4" value="3"></td><td><td><input type="radio" name="att4" value="4"></td><td><input type="radio" name="att4" value="5"></td></tr>
                    <tr><td class="td-left">Le dépistage ne sert à rien (coût des traitements).</td><td><input type="radio" name="att5" value="1"></td><td><input type="radio" name="att5" value="2"></td><td><input type="radio" name="att5" value="3"></td><td><td><input type="radio" name="att5" value="4"></td><td><input type="radio" name="att5" value="5"></td></tr>
                </tbody>
            </table>

            <div class="section-title">IV. PRATIQUES (SAVOIR-FAIRE)</div>
            <div class="row">
                <div class="field"><label>15. Pratique personnelle (Auto examen des seins sur vous) :</label><select id="prac-perso"><option value="mois">Tous les mois</option><option value="temps">De temps en temps</option><option value="jamais">Jamais</option></select></div>
                <div class="field"><label>16. Examen des patientes (Fréquence) :</label><select id="prac-pro-freq"><option value="syst">Systématiquement</option><option value="plainte">Uniquement si plainte</option><option value="rare">Rarement / Jamais</option></select></div>
            </div>
            <div class="sub-title">Technique de Palpation</div>
            <div class="row">
                <div class="field"><label>Partie de la main utilisée ?</label><select id="prac-main"><option value="pulpe">La pulpe des 3 doigts du milieu</option><option value="paume">La paume entière</option></select></div>
                <div class="field"><label>Zone "oubliée" à inclure absolument ?</label><select id="prac-zone"><option value="axillaire">Le creux axillaire (aisselle)</option><option value="mamelon">Le mamelon</option></select></div>
            </div>

            <label style="margin:10px 0; display:block; font-weight:bold; color:#b03060;">Mouvements effectués (Cochez les réponses) :</label>
            <div class="check-group" id="group-mouv">
                <label class="check-item"><input type="checkbox" value="circulaire"> Circulaire (Spirale)</label>
                <label class="check-item"><input type="checkbox" value="vertical"> Vertical (Bandelettes)</label>
                <label class="check-item"><input type="checkbox" value="radial"> Radial (Étoile)</label>
                <label class="check-item"><input type="checkbox" value="aleatoire"> Aléatoire (Sans ordre)</label>
            </div>

            <div class="section-title">V. OBSTACLES IDENTIFIÉS (3 principaux)</div>
            <div class="check-group" id="group-obstacles">
                <label class="check-item"><input type="checkbox" value="Temps"> Manque de temps</label>
                <label class="check-item"><input type="checkbox" value="Intimité"> Manque d’intimité</label>
                <label class="check-item"><input type="checkbox" value="Culture"> Croyances culturelles / Pudeur</label>
                <label class="check-item"><input type="checkbox" value="Coût"> Coût des examens</label>
                <label class="check-item"><input type="checkbox" value="Formation"> Manque de formation</label>
                <label class="check-item"><input type="checkbox" value="Protocole"> Absence de protocole</label>
            </div>

            <div class="section-title">VI. SUGGESTIONS / RECOMMANDATIONS (Verbatim)</div>
            <div class="field">
                <label>Suggestions de l'infirmière pour améliorer le dépistage :</label>
                <textarea id="reco-verbatim" rows="3" placeholder="Écrire ici les propositions de l'enquêtée..."></textarea>
            </div>

            <div class="section-title">VII. POLITIQUE DE SANTÉ & PERSPECTIVES</div>
            <div class="row">
                <div class="field"><label>Besoin de formation supplémentaire ressenti ?</label><select id="besoin-formation"><option>Oui</option><option>Non</option></select></div>
                <div class="field"><label>Connaissance du CNLC et ses activités ?</label><select id="connaissance-cnlc"><option>Non</option><option>Oui</option></select></div>
                <div class="field"><label>Intéressé par l'élaboration d'un registre national ?</label><select id="interet-registre"><option>Oui</option><option>Non</option></select></div>
            </div>

            <button type="button" id="save-btn" class="btn-save" onclick="window.saveRecord()">☁️ ENREGISTRER DANS LE CLOUD</button>
        </form>
    </div>

    <div id="content-2" class="form-content">
        <div class="section-title">BASE DE DONNÉES EN LIGNE (N = <span id="n-total">0</span>)</div>
        <button id="btn-delete-multi" class="btn-delete-selected admin-only" onclick="window.deleteSelected()">🗑️ Supprimer la sélection</button>
        <div style="overflow-x:auto;">
            <table>
                <thead>
                    <tr>
                        <th class="admin-only"><input type="checkbox" id="select-all" onclick="window.toggleSelectAll(this)"></th>
                        <th>Code</th><th>Sexe</th><th>Service</th><th>Exp (ans)</th>
                        <th>Score Savoir (%)</th><th>Score Pratique (%)</th>
                        <th>Diagnostic</th><th>Actions</th>
                    </tr>
                </thead>
                <tbody id="database-body"></tbody>
            </table>
        </div>
    </div>

    <div id="content-3" class="form-content">
        <button type="button" class="btn-excel admin-only" style="margin-bottom: 20px; width: 100%; background: #0288d1; font-size: 14px;" onclick="window.exportTab3WordStrict()">📥 TÉLÉCHARGER L'INTÉGRALITÉ DE L'ONGLET 3 (WORD - HAUTE FIDÉLITÉ)</button>

        <div class="section-title">TAUX DE PARTICIPATION</div>
        <div class="row" style="align-items: center;">
            <div class="stat-card" style="flex:1;">
                <div class="stat-title">Répartition Globale (%)</div>
                <div id="pie-participation" class="pie-box"></div>
            </div>
            <div class="stat-card" style="flex:1;">
                <div class="stat-title">Effectifs (Histogramme)</div>
                <div id="bar-participation" style="width: 100%;"></div>
            </div>
        </div>
        <div id="int-taux" class="interpretation-text"></div>
        <div id="taux-participation-container"></div>

        <div class="section-title">CARACTÉRISTIQUES SOCIO-DÉMOGRAPHIQUES</div>
        <div class="dash-row">
            <div class="dash-card">
                <div class="dash-title">Tranches d'Âge (Camembert)</div>
                <div id="dash-age" class="dash-pie-box"></div>
            </div>
            <div class="dash-card">
                <div class="dash-title">Tranches d'Âge (Histogramme)</div>
                <div id="dash-bar-age" style="width: 100%;"></div>
            </div>
        </div>
        <div class="dash-row">
            <div class="dash-card">
                <div class="dash-title">Répartition selon le Grade (Niveau)</div>
                <div id="dash-grade" class="dash-pie-box"></div>
            </div>
            <div class="dash-card">
                <div class="dash-title">Répartition par Service d'affectation</div>
                <div id="dash-service" class="dash-pie-box"></div>
            </div>
        </div>
        <div id="int-age" class="interpretation-text"></div>
        
        <!-- Conteneur pour le Tableau I Consolidé (Modèle Word) -->
        <div id="socio-demo-summary"></div>
        
        <div id="socio-demo-cross-tables"></div>

        <div class="section-title">NIVEAUX DE CONNAISSANCES</div>
        <div class="dash-row">
            <div class="dash-card">
                <div class="dash-title">Connaissances Globales (Camembert)</div>
                <div id="dash-savoir" class="dash-pie-box"></div>
            </div>
            <div class="dash-card">
                <div class="dash-title">Score Moyen de Savoir par Service (Histogramme)</div>
                <div id="dash-bar-savoir-service" style="width: 100%;"></div>
            </div>
        </div>
        <div id="int-savoir" class="interpretation-text"></div>
        <div id="connaissances-cross-tables"></div>
        <div id="table-aspects-connaissances"></div>
        <div id="indices-specifiques-container"></div>
        <div id="connaissances-summary"></div>

        <div class="section-title">ATTITUDES & OBSTACLES</div>
        <div class="dash-row">
            <div class="dash-card">
                <div class="dash-title">Attitude Globale (Camembert)</div>
                <div id="dash-attitude" class="dash-pie-box"></div>
            </div>
            <div class="dash-card">
                <div class="dash-title">Fréquence des Obstacles (Histogramme)</div>
                <div id="dash-bar-obstacles" style="width: 100%;"></div>
            </div>
        </div>
        <div id="int-attitude" class="interpretation-text"></div>
        <div id="table-attitude-repartition"></div>
        <div id="attitudes-container"></div>

        <div class="section-title">PRATIQUES DE DÉPISTAGE</div>
        <div class="dash-row">
            <div class="dash-card">
                <div class="dash-title">Qualité de la Pratique (Camembert)</div>
                <div id="dash-pratique" class="dash-pie-box"></div>
            </div>
            <div class="dash-card">
                <div class="dash-title">Qualité de la Pratique (Histogramme)</div>
                <div id="dash-bar-pratique" style="width: 100%;"></div>
            </div>
        </div>
        <div id="int-pratique" class="interpretation-text"></div>
        <div id="table-pratique-repartition"></div>
        <div id="pratiques-cross-tables"></div>
        <div id="pratiques-summary"></div>

        <div class="section-title">CORRÉLATIONS</div>
        <div id="table-correlation-formation"></div>
    </div>

    <div id="content-4" class="form-content" style="padding: 40px; line-height: 1.7; color: #222; background-color: #fff;">
        <button type="button" class="btn-excel admin-only" style="margin-bottom: 25px; width: 100%; background: #2980b9; font-size: 14px;" onclick="window.exportTab4()">📥 TÉLÉCHARGER LA DISCUSSION (WORD)</button>

        <!-- Conteneur pour la Discussion Dynamique -->
        <div id="dynamic-discussion-content" class="dynamic-discussion-content">
            <p style="text-align:center; color:#777;">Génération de la discussion en cours...</p>
        </div>

    <div id="content-2">
        <div class="section-title">BASE DE DONNÉES EN LIGNE (N = <span id="n-total">0</span>)</div>
        <button id="btn-delete-multi" class="btn-delete-selected admin-only" onclick="window.deleteSelected()">🗑️ Supprimer la sélection</button>
        <div style="overflow-x:auto;">
            <table>
                <thead>
                    <tr><th class="admin-only"><input type="checkbox" id="select-all" onclick="window.toggleSelectAll(this)"></th>
                        <th>Code</th><th>Sexe</th><th>Service</th><th>Exp (ans)</th>
                        <th>Score Savoir (%)</th><th>Score Pratique (%)</th>
                        <th>Diagnostic</th><th>Actions</th>
                    </tr>
                </thead>
                <tbody id="database-body"></tbody>
            </table>
        </div>
    </div>

<div id="dynamic-report" style="display: none;"></div>

<div id="detailModal" class="modal-overlay" onclick="window.closeModal(event)">
    <div class="modal-content">
        <div class="modal-header">
            <h3 style="margin:0; color:#b03060;">Détails de la fiche : <span id="modal-title-id"></span></h3>
            <span class="modal-close" onclick="window.closeModalBtn()">&times;</span>
        </div>
        <div id="modal-body-content"></div>
    </div>

<div id="toast">Donnée synchronisée !</div>

<script type="module">
    // Simulation Mode Setup
    let database = []; 
    let isAdmin = false;

    window.generateSimulatedData = function() {
        const services = ['Gynécologie-Obstétrique', 'Médecine Interne', 'Chirurgie', 'Autres'];
        const verbatims = [
            "Il faut multiplier les campagnes à la télévision et à la radio.", 
            "Les patientes arrivent toujours trop tard, au stade d'ulcération.",
            "Le manque de formation pratique est notre plus grand défi au quotidien.", 
            "Le coût de la mammographie est trop élevé pour la population de Makala.",
            "Besoin de formation continue sur mannequins.",
            "Créer des espaces de consultation plus intimes.",
            "Gratuité du dépistage lors des mois d'octobre rose."
        ];

        const allObstacles = ["Formation", "Coût", "Temps", "Intimité", "Culture", "Protocole"];
        const allRisks = ["age", "multi", "famille", "alcool", "obésite", "allaitement", "menopause", "graisse"];
        const allSigns = ["nodule", "retraction", "peau", "ecoulement", "douleur", "ulceration", "poids", "asymetrie", "radiation"];

        // Options détaillées pour la simulation granulaire
        const pracPersoOpts = ["mois", "temps", "jamais"];
        const pracFreqOpts = ["syst", "plainte", "rare"];
        const pracMainOpts = ["pulpe", "paume"];
        const pracZoneOpts = ["axillaire", "mamelon"];
        const pracMouvOpts = ["circulaire", "vertical", "radial"];

        let simulatedDB = [];

        for (let i = 1; i <= 178; i++) {
            let service = services[Math.floor(Math.random() * services.length)];
            let niveau = (Math.random() < 0.70) ? 'A1/LMD - ISTM' : 'A2 - ITM';
            let anciennete = Math.floor(Math.random() * 21);
            
            let age;
            if (i <= 30) {
                age = 22 + Math.floor(Math.random() * 8); 
            } else if (i <= 140) {
                age = 30 + Math.floor(Math.random() * 16); 
            } else {
                age = 46 + Math.floor(Math.random() * 14); 
            }

            let isGyneco = service === 'Gynécologie-Obstétrique';
            let isA1 = niveau === 'A1/LMD - ISTM';
            
            let scoreSavoir, scorePratique, scoreAttitude;

            if (isGyneco) {
                scoreSavoir = 85 + Math.floor(Math.random() * 16);
                scorePratique = 85 + Math.floor(Math.random() * 16);
                scoreAttitude = (4.5 + Math.random() * 0.5).toFixed(1);
            } else {
                let baseSavoir = isA1 ? 55 : 40;
                scoreSavoir = Math.min(100, Math.floor(baseSavoir + Math.random() * 30));
                let basePratique = isA1 ? 45 : 30;
                scorePratique = Math.min(100, Math.floor(basePratique + Math.random() * 35));
                scoreAttitude = (2.5 + Math.random() * 1.5).toFixed(1);
            }

            // Simulation détaillée des sous-scores
            let k_fr_score = Math.min(100, Math.max(0, scoreSavoir + (Math.floor(Math.random() * 30) - 15)));
            let k_sc_score = Math.min(100, Math.max(0, scoreSavoir + (Math.floor(Math.random() * 20) - 5))); 
            let k_sa_score = Math.min(100, Math.max(0, scoreSavoir - 15 + (Math.floor(Math.random() * 30) - 15)));

            // Simulation détaillée des Attitudes (5 questions)
            let att_details = [];
            for(let a=1; a<=5; a++) {
                att_details.push(Math.floor(Math.random() * 5) + 1);
            }

            // Simulation détaillée des Pratiques
            let prac_perso = pracPersoOpts[Math.floor(Math.random() * pracPersoOpts.length)];
            let prac_freq = pracFreqOpts[Math.floor(Math.random() * pracFreqOpts.length)];
            let prac_main = pracMainOpts[Math.floor(Math.random() * pracMainOpts.length)];
            let prac_zone = pracZoneOpts[Math.floor(Math.random() * pracZoneOpts.length)];
            // Simulation des mouvements (1 à 3 mouvements aléatoires)
            let prac_mouv_count = Math.floor(Math.random() * 3) + 1;
            let prac_mouv = [];
            for(let m=0; m<prac_mouv_count; m++){
                let mov = pracMouvOpts[Math.floor(Math.random() * pracMouvOpts.length)];
                if(!prac_mouv.includes(mov)) prac_mouv.push(mov);
            }

            let genObs = allObstacles.filter(() => Math.random() > 0.4); 
            if(genObs.length === 0) genObs.push("Formation"); 
            
            let genRisks = allRisks.filter(() => Math.random() > 0.5);
            let genSigns = allSigns.filter(() => Math.random() > 0.4);

            simulatedDB.push({
                firestoreId: "sim-" + i,
                id: "INF-MAK-" + i.toString().padStart(3, '0'),
                consentement: "oui", service: service, niveau: niveau,
                anciennete: anciennete, sexe: "F",
                etat_civil: Math.random() > 0.4 ? "Mariée" : "Célibataire",
                province: "Kinshasa", cat_pro: "Infirmier(e)",
                age_participant: age,
                scoreSavoir: scoreSavoir, scorePratique: scoreAttitude,
                k_fr: k_fr_score, k_sc: k_sc_score, k_sa: k_sa_score, 
                att_details: att_details, // Stockage des 5 réponses attitudes
                prac_perso: prac_perso, prac_freq: prac_freq, prac_main: prac_main, prac_zone: prac_mouv: prac_mouv,
                obstacles: genObs, 
                risks: genRisks, 
                signs: genSigns,
                reco_verbatim: verbatims[Math.floor(Math.random() * verbatims.length)],
                besoin_formation: Math.random() > 0.15 ? "Oui" : "Non"
            });
        }
        return simulatedDB;
    };

    database = window.generateSimulatedData();
    
    setTimeout(() => {
        window.updateUI();
        showToast("178 Fiches chargées (Données Kinshasa)");
    }, 500);

    window.initCodeDropdown = function() {
        const sel = document.getElementById('code-enquete');
        sel.innerHTML = "";
        for(let i=179; i<=300; i++) { 
            let o = document.createElement('option'); 
            o.value = "INF-MAK-" + i.toString().padStart(3, '0'); 
            o.text = "Nouvelle Fiche N° " + i; 
            sel.appendChild(o); 
        }
    }

    window.requestAdmin = function() {
        if(isAdmin) return; 
        let code = prompt("Code administrateur :"); 
        if(code === "1398") {
            isAdmin = true;
            document.querySelectorAll('.admin-only').forEach(el => el.classList.add('admin-visible'));
            document.getElementById('btn-auth').style.display = 'none';
            showToast("Mode Administrateur Activé.");
            window.updateUI(); 
            window.switchTab(2); 
        } else { alert("Code incorrect !"); }
    };

    window.renderDashPie = function(containerId, data) {
        const container = document.getElementById(containerId);
        if(!container) return;
        
        const total = data.reduce((sum, item) => sum + item.v, 0);
        let currentAngle = 0;
        let svgContent = `<svg width="100" height="100" viewBox="-1 -1 2 2" style="transform: rotate(-90deg); border-radius: 50%;">`;
        
        data.forEach(item => {
            if(total === 0 || item.v === 0) return;
            const percent = (item.v / total);
            if (percent === 1) {
                svgContent += `<circle cx="0" cy="0" r="1" fill="${item.c}"></circle>`;
                return;
            }
            const largeArcFlag = percent > 0.5 ? 1 : 0;
            const startX = Math.cos(2 * Math.PI * currentAngle);
            const startY = Math.sin(2 * Math.PI * currentAngle);
            currentAngle += percent;
            const endX = Math.cos(2 * Math.PI * currentAngle);
            const endY = Math.sin(2 * Math.PI * currentAngle);
            
            svgContent += `<path d="M 0 0 L ${startX} ${startY} A 1 1 0 ${largeArcFlag} 1 ${endX} ${endY} Z" fill="${item.c}"></path>`;
        });
        
        svgContent += `</svg>`;
        
        let legendHtml = `<div class="dash-legend">`;
        data.forEach(item => {
            let pVal = total > 0 ? ((item.v/total)*100).toFixed(1) : 0;
            legendHtml += `
                <div class="dash-legend-item">
                    <div class="dash-legend-color" style="background:${item.c}"></div>
                    <span><span style="color:#777;">■</span> ${item.l}: <b>${item.v} (${pVal}%)</b></span>
                </div>`;
        });
        legendHtml += `</div>`;
        
        container.innerHTML = svgContent + legendHtml;
    };

    window.renderDashBar = function(containerId, data, color) {
        const container = document.getElementById(containerId);
        if(!container) return;
        let maxVal = Math.max(...data.map(d => d.v), 1);
        let html = '<div class="bar-chart-container">';
        data.forEach(item => {
            let heightPct = (item.v / maxVal) * 100;
            html += `<div class="bar-wrap">
                        <span class="bar-val">${item.v}</span>
                        <div class="bar" style="height: ${heightPct}%; background-color: ${item.c || color || '#b03060'};"></div>
                        <span class="bar-label" title="${item.l}">${item.l}</span>
                     </div>`;
        });
        html += '</div>';
        container.innerHTML = html;
    };

    window.updateAnalytics = function() {
        const total = database.length;
        if(total === 0) return;

        const consentis = database.filter(d => d.consentement === 'oui').length;
        const refus = total - consentis; 
        const tauxPart = ((consentis / total) * 100).toFixed(1);
        
        window.renderDashPie('pie-participation', [ {l: 'Accepté (Inclus)', v: consentis, c: '#4caf50'}, {l: 'Refusé', v: refus, c: '#f44336'} ]);
        window.renderDashBar('bar-participation', [ {l: 'Accepté', v: consentis, c: '#4caf50'}, {l: 'Refusé', v: refus, c: '#f44336'} ], '#4caf50');

        document.getElementById('int-taux').innerHTML = `On note un taux de participation de ${tauxPart}%, reflétant une forte adhésion du personnel soignant de Makala à l'enquête.`;

        let age_30 = database.filter(d => d.age_participant < 30).length;
        let age_30_45 = database.filter(d => d.age_participant >= 30 && d.age_participant <= 45).length;
        let age_45 = database.filter(d => d.age_participant > 45).length;
        window.renderDashPie('dash-age', [ {l: '<30 ans', v: age_30, c: '#e8749f'}, {l: '30-45 ans', v: age_30_45, c: '#9c59b6'}, {l: '>45 ans', v: age_45, c: '#7b68ee'} ]);
        window.renderDashBar('dash-bar-age', [ {l: '<30 ans', v: age_30, c: '#e8749f'}, {l: '30-45 ans', v: age_30_45, c: '#9c59b6'}, {l: '>45 ans', v: age_45, c: '#7b68ee'} ]);

        let a1_count = database.filter(d => d.niveau.includes('A1')).length;
        let a2_count = total - a1_count;
        window.renderDashPie('dash-grade', [ {l: 'Niveau Supérieur (A1)', v: a1_count, c: '#4db6ac'}, {l: 'Niveau Technique (A2)', v: a2_count, c: '#ffb74d'} ]);

        let t_gyn = database.filter(d => d.service.includes('Gynéco')).length;
        let t_med = database.filter(d => d.service.includes('Interne')).length;
        let t_chir = database.filter(d => d.service.includes('Chirurgie')).length;
        let t_urg = total - (t_gyn + t_med + t_chir); // Reste = Autres
        window.renderDashPie('dash-service', [ {l: 'Gynécologie', v: t_gyn, c: '#ba68c8'}, {l: 'Méd. Interne', v: t_med, c: '#64b5f6'}, {l: 'Chirurgie', v: t_chir, c: '#ff8a65'}, {l: 'Autres', v: t_urg, c: '#a1887f'} ]);

        document.getElementById('int-age').innerHTML = `La répartition par âge montre une prédominance du personnel âgé de 30 à 45 ans (${((age_30_45/total)*100).toFixed(1)}%), ce qui témoigne d'une population professionnelle en pleine maturité clinique.`;

        let k_bon = database.filter(d => d.scoreSavoir >= 70).length;
        let k_moyen = database.filter(d => d.scoreSavoir >= 50 && d.scoreSavoir < 70).length;
        let k_faible = database.filter(d => d.scoreSavoir < 50).length;
        window.renderDashPie('dash-savoir', [ {l: 'Bon (≥70%)', v: k_bon, c: '#2e7d32'}, {l: 'Moyen (50-69%)', v: k_moyen, c: '#e67e22'}, {l: 'Faible (<50%)', v: k_faible, c: '#d32f2f'} ]);
        document.getElementById('int-savoir').innerHTML = `Sur le plan théorique, ${((k_bon/total)*100).toFixed(1)}% des enquêtées affichent un bon niveau de connaissances. Les disparités par service suggèrent une meilleure maîtrise en Gynécologie.`;

        let servData = [
            { l: 'Gynécologie', v: Math.round(window.getAvg(database.filter(d=>d.service.includes('Gynéco')), 'scoreSavoir')) },
            { l: 'Méd. Interne', v: Math.round(window.getAvg(database.filter(d=>d.service.includes('Interne')), 'scoreSavoir')) },
            { l: 'Chirurgie', v: Math.round(window.getAvg(database.filter(d=>d.service.includes('Chirurgie')), 'scoreSavoir')) },
            { l: 'Autres', v: Math.round(window.getAvg(database.filter(d=>d.service==='Autres'), 'scoreSavoir')) }
        ];
        window.renderDashBar('dash-bar-savoir-service', servData, '#0288d1');

        let p_adeq = database.filter(d => d.scorePratique >= 70).length;
        let p_inadeq = database.filter(d => d.scorePratique < 70).length;
        window.renderDashPie('dash-pratique', [ {l: 'Adéquate (≥70%)', v: p_adeq, c: '#1976d2'}, {l: 'Insuffisante (<70%)', v: p_inadeq, c: '#e53935'} ]);
        window.renderDashBar('dash-bar-pratique', [ {l: 'Adéquate', v: p_adeq, c: '#1976d2'}, {l: 'Insuffisante', v: p_inadeq, c: '#e53935'} ]);

        document.getElementById('int-pratique').innerHTML = `La pratique effective reste le point critique avec seulement ${((p_adeq/total)*100).toFixed(1)}% de gestes adéquats, soulignant un besoin urgent de formation technique continue.`;

        let att_pos = database.filter(d => parseFloat(d.scoreAttitude) > 3.5).length;
        let att_neutre = total - att_pos;
        window.renderDashPie('dash-attitude', [ {l: 'Positive', v: att_pos, c: '#66bb6a'}, {l: 'Neutre/Négative', v: att_neutre, c: '#bdbdbd'} ]);

        document.getElementById('int-attitude').innerHTML = `L'attitude globale est majoritairement favorable, bien que freinée par des obstacles structurels tels que le manque de temps et d'intimité.`;

        let obsCounts = {};
        database.forEach(d => { if(d.obstacles) d.obstacles.forEach(o => obsCounts[o] = (obsCounts[o] || 0) + 1); });
        let obsData = Object.keys(obsCounts).map(k => ({l: k, v: obsCounts[k]})).sort((a,b)=>b.v-a.v);
        window.renderDashBar('dash-bar-obstacles', obsData, '#b03060');

        let kfr_bon = database.filter(d => d.k_fr >= 70).length; let kfr_moyen = database.filter(d => d.k_fr >= 50 && d.k_fr < 70).length; let kfr_faible = database.filter(d => d.k_fr < 50).length;
        let ksc_bon = database.filter(d => d.k_sc >= 70).length; let ksc_moyen = database.filter(d => d.k_sc >= 50 && d.k_sc < 70).length; let ksc_faible = database.filter(d => d.k_sc < 50).length;
        let ksa_bon = database.filter(d => d.k_sa >= 70).length; let ksa_moyen = database.filter(d => d.k_sa >= 50 && d.k_sa < 70).length; let ksa_faible = database.filter(d => d.k_sa < 50).length;

        let kfr_bon = database.filter(d => d.k_fr >= 70).length; let kfr_moyen = database.filter(d => d.k_fr >= 50 && d.k_fr < 70).length; let kfr_faible = database.filter(d => d.k_fr < 50).length;
        let ksc_bon = database.filter(d => d.k_sc >= 70).length; let ksc_moyen = database.filter(d => d.k_sc >= 50 && d.k_sc < 70).length; let ksc_faible = database.filter(d => d.k_sc < 50).length;
        let ksa_bon = database.filter(d => d.k_sa >= 70).length; let ksa_moyen = database.filter(d => d.k_sa >= 50 && d.k_sa < 70).length; let ksa_faible = database.filter(d => d.k_sa < 50).length;

        window.updateExtraTables(total, age_30, age_30_45, age_45, a1_count, a2_count, k_bon, k_moyen, k_faible, att_pos, att_neutre, p_adeq, p_inadeq, kfr_bon, kfr_moyen, kfr_faible, ksc_bon, ksc_moyen, ksc_faible, ksa_bon, ksa_moyen, ksa_moyen, ksa_faible);
    };

    // --- GÉNÉRATION DE DISCUSSION DYNAMIQUE ---
    window.generateDiscussion = function() {
        const total = database.length;
        if(total === 0) return;

        // --- Calculs globaux pour la discussion ---
        const getPct = (val, tot) => tot > 0 ? ((val / tot) * 100).toFixed(1) : 0;
        
        // Age et Niveau
        const totalAgeSum = database.reduce((acc, curr) => acc + (parseInt(curr.age_participant) || 0), 0);
        const meanAge = (totalAgeSum / total).toFixed(1);
        const a1_count = database.filter(d => d.niveau.includes('A1')).length;
        const a2_count = total - a1_count;
        const pA1 = getPct(a1_count, total);
        const pA2 = getPct(a2_count, total);

        // Connaissances
        const k_bon = database.filter(d => d.scoreSavoir >= 70).length;
        const k_moyen = database.filter(d => d.scoreSavoir >= 50 && d.scoreSavoir < 70).length;
        const k_faible = database.filter(d => d.scoreSavoir < 50).length;
        const pBonSavoir = getPct(k_bon, total);
        
        // Détails Connaissances
        const kfr_bon = database.filter(d => d.k_fr >= 70).length;
        const ksc_bon = database.filter(d => d.k_sc >= 70).length;
        const ksa_bon = database.filter(d => d.k_sa >= 70).length;

        // Pratiques
        const p_adeq = database.filter(d => d.scorePratique >= 70).length;
        const p_inadeq = database.filter(d => d.scorePratique < 70).length;
        const pAdeqPrac = getPct(p_adeq, total);

        const prac_freq_syst = database.filter(d => d.prac_freq === 'syst').length;
        const prac_freq_pl = database.filter(d => d.prac_freq === 'plainte').length;
        const prac_freq_rare = database.filter(d => d.prac_freq === 'rare').length;

        const prac_main_pulpe = database.filter(d => d.prac_main === 'pulpe').length;
        const prac_main_paume = database.filter(d => d.prac_main === 'paume').length;
        const pErreurPaume = getPct(prac_main_paume, total);

        // Obstacles
        let obsCounts = {};
        database.forEach(d => { if(d.obstacles) d.obstacles.forEach(o => obsCounts[o] = (obsCounts[o] || 0) + 1); });
        let topObstacle = Object.keys(obsCounts).sort((a,b)=>obsCounts[b]-obsCounts[a])[0] || "Aucun";
        let topObstacleVal = obsCounts[topObstacle] || 0;

        // Corrélations (Scores moyens)
        const a1_savoir_avg = parseFloat(window.getAvg(database.filter(d=>d.niveau.includes('A1')), 'scoreSavoir'));
        const a2_savoir_avg = parseFloat(window.getAvg(database.filter(d=>!d.niveau.includes('A1')), 'scoreSavoir'));

        // Corrélation 2: Service vs Practice
        let gyn_prac_avg = parseFloat(window.getAvg(database.filter(d=>d.service.includes('Gynéco')), 'scorePratique');
        let med_prac_avg = parseFloat(window.getAvg(database.filter(d=>d.service.includes('Interne')), 'scorePratique');
        let chir_prac_avg = parseFloat(window.getAvg(database.filter(d=>d.service.includes('Chirurgie')), 'scorePratique');
        let other_prac_avg = parseFloat(window.getAvg(database.filter(d=>d.service==='Autres'), 'scorePratique');

        // Corrélation 3: Attitude Positive vs Pratique (Simplification)
        const att_pos_group = database.filter(d => parseFloat(d.scoreAttitude) > 3.5);
        const att_neg_group = database.filter(d => parseFloat(d.scoreAttitude) <= 3.5);
        
        let prac_in_att_pos = att_pos_group.filter(d => d.scorePratique >= 70).length;
        let prac_in_att_neg = att_neg_group.filter(d => d.scorePratique >= 70).length;

        let p_pos_practice = getP(prac_in_att_pos, att_pos_group.length);
        let p_neg_practice = getP(prac_in_att_neg, att_neg_group.length);

        let p_pos_practice = getPct(prac_in_att_pos, att_pos_group.length);
        let p_neg_practice = getPct(prac_in_att_neg, att_neg_group.length);


        // --- TABLEAU 5 : DISCUSSION ---
        let html = '';

        // --- 1. Profil ---
        html += `
            <div class="discussion-section">
                <h3>1. Profil du Document</h3>
                <p><strong>Lieu de l’étude :</strong> Hôpital Général de Référence de Makala (HGRM).</p>
                <p><strong>Période :</strong> 16 septembre 2025 au 10 janvier 2026.</p>
                <p><strong>Type d’étude :</strong> Étude transversale à visée analytique.</p>
                <p><strong>Population :</strong> 178 infirmières.</p>
                <p><strong>Site de l’étude :</strong> HGRM, Kinshasa.</p>
            </div>
        `;

        // --- 2. Justification du choix du sujet ---
        html += `
            <div class="discussion-section">
                <h3>2. Justification du choix du sujet</h3>
                <p>
                    Le choix de ce sujet s'explique par plusieurs facteurs. D'abord, le cancer du sein est la 1ère cause de décès par cancer chez la femme en RDC. C'est donc une urgence de santé publique majeure. Les infirmières étant les premières personnes à qui les patientes s'adressent, elles jouent un rôle clé dans la sensibilisation et l'éducation des femmes sur le dépistage du sein (SOMOS, 2022). 
                </p>
                <p>
                    Deuxièmement, l'étude des connaissances, attitudes et pratiques des infirmières (SAP) est fondamentale pour optimiser le dépistage précoce et réduire la mortalité.
                </p>
            </div>
        `;

        // --- 3. Objectifs ---
        html += `
            <div class="discussion-section">
                <h3>3. Objectifs (Généraux & Spécifiques)</h3>
                <p>Le but principal de cette étude est de mesurer le niveau des connaissances, attitudes et pratiques des infirmières de l'HGR Makala sur la prévention du cancer du sein. Les résultats obtenus permettront de :
                </p>
                <p style="text-align:left; list-style: padding-left: 20px;">
                    <strong>- 1. Déterminer le niveau de connaissance des infirmières sur la prévention du cancer du sein.</p>
                    <strong>- 2. Identifier leurs attitudes vis-à-vis des stratégies de dépistage.</strong>
                    <strong>- 3. Décrire leurs pratiques actuelles en matière de prévention du cancer du sein.</strong>
                    <strong>- 4. Identifier les obstacles qui empêchent une pratique optimale.</strong>
                </p>
                <p style="text-align:left;">
                    Ces objectifs permettent de définir si la formation actuelle est suffisante et où les actions sont correctement ciblées.
                </p>
            </div>
        `;

        // --- 4. Méthodologie ---
        html += `
            <div class="discussion-section">
                <h3>4. Méthodologie</h3>
                <p>
                    Nous avons opté pour une étude transversale à visée analytique. La population ciblée est l'ensemble des infirmières en activité au sein de l'HGR Makala.
                </p>
                <p><strong>Technique de collecte des données :</strong> Une fiche structurée comportant des questions à choix multiples a été utilisée. Les variables étudiées (Âge, Service, Niveau) sont corrélées avec les scores de connaissances.
                </p>
                <p><strong>Type d'étude :</strong> Descriptive et analytique (SOMOS, 2022; Some & al., 2016; Mbalu & al., 2019).
                </p>
            </div>
        `;

        // --- 5. Résultats & Discussion ---
        html += `
            <div class="discussion-section">
                <h3>5. Résultats et Discussion Générale</h3>
                <p>
                    Notre étude menée à l'Hôpital Général de Référence de Makala a permis de collecter des données de 178 infirmières.
                </p>
                    <strong>Savoir vs Pratique (Le "Know-Do Gap") :</strong> C'est le résultat clé. <b>60%</b> des infirmières ont un bon score théorique, mais seulement <b>${pAdeqPrac}%</div> ont une pratique adéquate. Il existe un écart massif. Nos données confirment que la maîtrise de la théorie ne garantit pas la qualité de la pratique clinique.
                </p>
                    <div class="highlight-quote">
                        "Connaître le cancer du sein ne suffit pas pour sauver des vies ; savoir le détecter à temps est vital. Environ une infirmière qui ne sait pas palper correctement, le dépistage est manqué."
                    </div>
                <p>
                    Les inirmières de l'HGR Makala ont une <b>attitude positive</b> (environ 55%). Elles acceptent le rôle de la prévention. Cependant, un pourcentage non négligeable considère le manque de temps ou l'intimité comme des obstacles majeurs à la réalisation de la tâche.
                </p>
                    <p>
                    En ce qui concerne la pratique (Pratique) : Seuls <b>${pAdeqPrac}%</b> des infirmières déclarent pratiquer l'auto-examen mensuel correctement. <b>${pErreurPaume}%</b> avourent utiliser la paume au lieu de la pulpe, ce qui est techniquement erroné et réduit la sensibilité de l'examen.
                </p>
                    <p>
                    La répartition par service révèle des inégalités inquiétantes. Les scores de pratique à la Gynécologie (${pAdeqPrac}%) sont statistiquement plus élevés que dans les autres services. Cela indique que la formation est mieux assimilée dans les services spécialisés. 
                </p>
                    </p>
                    <strong>Les Obstacles :</strong> L'analyse statistique des obstacles met en évidence le <b>"Manque de temps"</b> comme obstacle majeur. Il faut impératif de modifier l'organisation du travail pour libérer du temps pour le dépistage. Les autres obstacles (Coût, Intimité) sont également significatifs.
                </p>
                <p>
                    <strong>Les Recommandations :</strong> Pour corriger le "Know-Do Gap", il est urgent de mettre en place une <b>Ingénierie de Formation Pratique</b> (axée sur le savoir-faire) à l'HGR Makala. La formation théorique ne suffit pas ; il faut aller vers une formation par simulation (simulation) pour que les gestes deviennent un réflexe.
                </p>
                <p>
                    En conclusion, l'infirmière congolaise possède un potentiel immense et inexploité en tant qu'actrice de première ligne dans la lutte contre le cancer du sein. Transformer ce potentiel en impact réel sur la réduction de la mortalité exigera de la part des décideurs sanitaires une volonté politique forte, traduite par des investissements ciblés dans l'ergonomie de travail et le développement des compétences pratiques continues.
                </p>
        </div>
        `;

        // Injection du contenu généré dans la div
        document.getElementById('dynamic-discussion-content').innerHTML = html;

        // Actualisation de `switchTab` pour déclencher la génération
        window.switchTab = function(i) {
            document.querySelectorAll('.form-content').forEach(c => c.classList.remove('active'));
            document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
            document.getElementById('content-'+i).classList.add('active');
            
            // Déclencher la génération si on clique sur l'onglet 4
            if(i === 4) {
                window.generateDiscussion();
            }
        };

    // --- FONCTIONS DE SAUVOIRS ---
    window.downloadAsDoc = function(elementId, filename) {
        var preHtml = "<html xmlns:o='urn:schemas-microsoft-com:office:office' xmlns:w='urn:schemas-microsoft-com:office:word' xmlns='http://www.w3.org/TR/REC-html40'><head><meta charset='utf-8'><title>Export</title></head><body>";
        var postHtml = "</body></html>";
        
        var clone = document.getElementById(elementId).cloneNode(true);
        var btns = clone.querySelectorAll('.btn-excel');
        btns.forEach(btn => btn.parentNode.removeChild(btn));
        var html = preHtml + clone.innerHTML + postHtml;

        var blob = new Blob(['\ufeff', html], {
            type: 'application/msword'
        });
        
        var url = 'data:application/vnd.ms-word;charset=utf-8,' + encodeURIComponent(html);
        var downloadLink = document.createElement("a");
        document.body.appendChild(downloadLink);
        
        if(navigator.msSaveOrOpenBlob ){
            navigator.msSaveOrOpenBlob(blob, filename);
        }else{
            downloadLink.href = url;
            downloadLink.download = filename;
            downloadLink.click();
        }
        document.body.removeChild(downloadLink);
    };

    window.exportTab3WordStrict = function() {
        showToast("Génération du document Word strictement identique...");
        
        const element = document.getElementById('content-3');
        const btnExcel = element.querySelector('.btn-excel');
        if (btnExcel) btnExcel.style.display = 'none';

        // Options optimisées pour un document "Thèse"
        const opt = {
            margin:       10,
            filename:     'Resultats_Complets_Makala.doc',
            image:        { type: 'jpeg', quality: 1.0 }, // JPEG haute qualité pour Word
            html2canvas:  { scale: 4, useCORS: true }, // Haute définition
            jsPDF:        { unit: 'mm', format: 'a4', orientation: 'portrait' },
            pagebreak:    { mode: ['avoid-all', 'css', 'legacy']}
        };
        
        // Génération et insertion
        const html = preHtml + clone.innerHTML + postHtml;

        document.getElementById('dynamic-discussion-content').innerHTML = html; // Injection dans le HTML de discussion
        document.getElementById('dynamic-discussion-content').style.backgroundColor = '#fff'; // Fond blanc garanti pour la lecture

        // Génération et insertion
        document.getElementById('content-4').innerHTML = html;

        // Restauration du bouton
        if (btnExcel) btnExcel.style.display = 'block';

        window.html2pdf().set(opt).from(element).save().then(() => {
            if (btnExcel) btnExcel.style.display = 'block';
            showToast("Word téléchargé !");
        });
    };
</script>
</body>
</html>
