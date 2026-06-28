<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jaidev M. | Equity Research Portfolio</title>
    <style>
        :root {
            --slate-primary: #0f172a;
            --slate-muted: #475569;
            --corporate-blue: #1d4ed8;
            --ledger-bg: #f8fafc;
            --grid-border: #cbd5e1;
            --max-width: 950px;
        }
        
        * { box-sizing: border-box; margin: 0; padding: 0; }
        
        /* Lock scrolling entirely to enforce a multi-page app experience */
        body { 
            font-family: "Times New Roman", Times, Georgia, serif; 
            color: var(--slate-primary); 
            background: var(--ledger-bg); 
            overflow: hidden; 
            -webkit-font-smoothing: antialiased; 
            min-height: 100vh; 
            display: flex; 
            flex-direction: column; 
        }

        /* Fixed Corporate Navigation Matrix */
        nav { position: fixed; top: 0; left: 0; width: 100%; background: #ffffff; border-bottom: 2px solid var(--slate-primary); z-index: 1000; display: flex; justify-content: center; padding: 0 20px; }
        .nav-container { display: flex; justify-content: space-between; align-items: center; max-width: var(--max-width); width: 100%; height: 65px; }
        .nav-brand { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-weight: 700; font-size: 0.85rem; letter-spacing: 0.08em; color: var(--slate-primary); text-transform: uppercase; cursor: pointer; }
        .nav-links { display: flex; gap: 24px; align-items: center; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }
        .nav-links button { background: none; border: none; cursor: pointer; color: var(--slate-muted); font-size: 0.75rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.08em; padding-bottom: 4px; border-bottom: 2px solid transparent; transition: all 0.2s ease; }
        .nav-links button:hover, .nav-links button.active { color: var(--corporate-blue); border-bottom-color: var(--corporate-blue); outline: none; }
        .nav-links .cta-contact { border: 1px solid var(--slate-primary); padding: 6px 14px; font-size: 0.7rem; color: var(--slate-primary); transition: all 0.2s; letter-spacing: 0.05em; text-decoration: none; font-weight: 600; text-transform: uppercase; }
        .nav-links .cta-contact:hover { background: var(--slate-primary); color: #ffffff; }

        /* Structural Container for Viewports */
        main { flex: 1; display: flex; align-items: center; justify-content: center; width: 100%; padding: 85px 20px 40px 20px; position: relative; }

        /* Component Visibility Engine */
        .viewport-panel { display: none; width: 100%; max-width: var(--max-width); animation: panelFade 0.3s ease-in-out forwards; overflow-y: auto; max-height: calc(100vh - 150px); padding-right: 8px; }
        .viewport-panel.active { display: block; }

        @keyframes panelFade {
            from { opacity: 0; transform: scale(0.995); }
            to { opacity: 1; transform: scale(1); }
        }

        /* ------------------------------------------------------------------ */
        /* LANDING PAGE SPECIFIC STYLING (Split Layout) */
        /* ------------------------------------------------------------------ */
        .landing-grid { display: grid; grid-template-columns: 320px 1fr; gap: 48px; align-items: center; background: #ffffff; border: 1px solid var(--grid-border); padding: 48px; }
        
        .photo-frame { width: 100%; aspect-ratio: 1 / 1; border: 1px solid var(--grid-border); background: #f1f5f9; display: flex; align-items: center; justify-content: center; position: relative; }
        .photo-frame img { width: 100%; height: 100%; object-fit: cover; }
        .photo-placeholder-text { font-family: -apple-system, sans-serif; font-size: 0.8rem; color: var(--slate-muted); text-transform: uppercase; letter-spacing: 0.05em; text-align: center; padding: 20px; }
        
        .intro-text h1 { font-size: 3.4rem; font-weight: 400; color: var(--slate-primary); letter-spacing: -0.02em; margin-bottom: 2px; line-height: 1.1; }
        .intro-subtitle { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-size: 1.05rem; color: var(--corporate-blue); font-weight: 600; text-transform: uppercase; letter-spacing: 0.12em; margin-bottom: 24px; }
        .intro-brief { font-size: 1.2rem; line-height: 1.65; text-align: justify; color: #1e293b; }

        /* ------------------------------------------------------------------ */
        /* SUB-SECTION SPECIFIC STYLING */
        /* ------------------------------------------------------------------ */
        h2 { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; color: var(--slate-primary); font-size: 1.25rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.1em; border-bottom: 2px solid var(--slate-primary); padding-bottom: 8px; margin-bottom: 32px; display: flex; justify-content: space-between; align-items: flex-end; }
        h2 .section-meta { font-size: 0.7rem; color: var(--slate-muted); font-weight: 500; letter-spacing: 0.02em; text-transform: uppercase; }
        
        /* Grid Framework for Competencies Matrix */
        .matrix-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 24px; width: 100%; }
        .matrix-box { background: #ffffff; border: 1px solid var(--grid-border); padding: 24px; }
        .matrix-box h3 { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-size: 0.85rem; font-weight: 700; text-transform: uppercase; color: var(--slate-primary); letter-spacing: 0.08em; border-bottom: 1px solid var(--slate-primary); padding-bottom: 6px; margin-bottom: 16px; }
        .matrix-box ul { list-style: none; }
        .matrix-box li { font-size: 1.1rem; margin-bottom: 8px; position: relative; padding-left: 20px; text-align: justify; color: #1e293b; }
        .matrix-box li::before { content: "▪"; color: var(--corporate-blue); position: absolute; left: 0; font-size: 0.75rem; top: 1px; }

        /* Dossier Experience Blocks */
        .report-block { margin-bottom: 36px; width: 100%; background: #ffffff; border: 1px solid var(--grid-border); padding: 28px; }
        .report-block:last-child { margin-bottom: 0; }
        .report-header { display: flex; justify-content: space-between; align-items: baseline; font-weight: bold; font-size: 1.25rem; color: var(--slate-primary); border-bottom: 1px solid var(--grid-border); padding-bottom: 6px; }
        .report-sub { display: flex; justify-content: space-between; align-items: baseline; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-size: 0.85rem; font-weight: 600; color: var(--corporate-blue); margin-top: 8px; margin-bottom: 14px; text-transform: uppercase; letter-spacing: 0.05em; }
        .report-date { color: var(--slate-muted); font-weight: 500; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-size: 0.8rem; letter-spacing: 0; text-transform: none; }
        .report-block ul { list-style: none; }
        .report-block li { font-size: 1.1rem; margin-bottom: 10px; position: relative; padding-left: 22px; text-align: justify; color: #1e293b; line-height: 1.6; }
        .report-block li::before { content: "—"; color: var(--slate-muted); position: absolute; left: 0; }

        /* Document / Publication Tables */
        .deck-row { display: flex; flex-direction: column; gap: 24px; width: 100%; }
        .pub-panel { background: #ffffff; border: 1px solid var(--grid-border); padding: 24px; width: 100%; }
        .pub-top { display: flex; justify-content: space-between; align-items: center; margin-bottom: 12px; border-bottom: 1px dashed var(--grid-border); padding-bottom: 10px; }
        .pub-title { font-weight: bold; font-size: 1.25rem; color: var(--slate-primary); }
        .pub-link { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-size: 0.7rem; font-weight: 700; letter-spacing: 0.08em; border: 1px solid var(--corporate-blue); color: var(--corporate-blue); padding: 5px 14px; text-decoration: none; text-transform: uppercase; transition: all 0.15s ease-in-out; }
        .pub-link:hover { background: var(--corporate-blue); color: #ffffff; }

        /* Academic Grid Matrix */
        .edu-matrix { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; width: 100%; }
        .edu-node { background: #ffffff; border: 1px solid var(--grid-border); border-top: 4px solid var(--slate-primary); padding: 24px; display: flex; flex-direction: column; justify-content: space-between; }
        .edu-node h3 { font-size: 1.2rem; color: var(--slate-primary); font-weight: bold; line-height: 1.25; }
        .edu-inst { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-size: 0.8rem; color: var(--corporate-blue); text-transform: uppercase; font-weight: 600; margin-top: 6px; letter-spacing: 0.02em; }
        .edu-score-row { margin-top: 24px; display: flex; justify-content: space-between; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; font-size: 0.8rem; border-top: 1px solid #f1f5f9; padding-top: 14px; color: var(--slate-muted); font-weight: 500; }

        /* Custom Scrollbar for inner components if required on low-res screens */
        .viewport-panel::-webkit-scrollbar { width: 6px; }
        .viewport-panel::-webkit-scrollbar-track { background: transparent; }
        .viewport-panel::-webkit-scrollbar-thumb { background: var(--grid-border); border-radius: 3px; }

        @media (max-width: 820px) {
            body { overflow-y: auto; }
            .nav-brand { display: none; }
            .nav-container { justify-content: center; }
            .nav-links { gap: 12px; }
            .nav-links button { font-size: 0.65rem; }
            main { padding-top: 100px; }
            .viewport-panel { max-height: none; overflow-y: visible; }
            .landing-grid { grid-template-columns: 1fr; padding: 24px; gap: 24px; }
            .photo-frame { max-width: 260px; margin: 0 auto; }
            .intro-text h1 { font-size: 2.4rem; text-align: center; }
            .intro-subtitle { text-align: center; }
            .matrix-grid, .edu-matrix { grid-template-columns: 1fr; }
            .report-header, .report-sub, .pub-top { flex-direction: column; align-items: flex-start; gap: 4px; }
            .pub-link { margin-top: 6px; display: inline-block; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="nav-container">
            <div class="nav-brand" onclick="switchTab('home')">JAIDEV M.</div>
            <div class="nav-links">
                <button onclick="switchTab('home')" id="btn-home" class="active">Overview</button>
                <button onclick="switchTab('skills')" id="btn-skills">Competencies</button>
                <button onclick="switchTab('experience')" id="btn-experience">Track Record</button>
                <button onclick="switchTab('publications')" id="btn-publications">Research Output</button>
                <button onclick="switchTab('education')" id="btn-education">Credentials</button>
                <a href="mailto:cfajaidev@gmail.com" class="cta-contact">Contact</a>
            </div>
        </div>
    </nav>

    <main>
        
        <!-- INITIAL LANDING PAGE VIEW (Only Photo and Who Am I Statement) -->
        <div id="home" class="viewport-panel active">
            <div class="landing-grid">
                <div class="photo-frame">
                    <!-- Replace 'profile.jpg' with your photo filename when uploaded to your repo -->
                    <!-- <img src="profile.jpg" alt="Jaidev M."> -->
                    <div class="photo-placeholder-text">Place Professional Image File in Repository Container</div>
                </div>
                <div class="intro-text">
                    <h1>JAIDEV M.</h1>
                    <div class="intro-subtitle">Equity Research Analyst</div>
                    <div class="intro-brief">
                        I am an Equity Research Analyst with 4 years of active investment experience across fundamental analysis, financial modelling, and portfolio management. I specialize in bottom-up stock selection across FMCG, NBFC, IT services, pharma, and semiconductor spaces, generating 5-10% alpha above the Nifty 50 benchmark[cite: 1]. I hold a SEBI-mandated NISM Research Analyst validation and specialize in institutional-grade three-statement models, DCF architecture, and sector tracking mechanisms[cite: 1].
                    </div>
                </div>
            </div>
        </div>

        <!-- COMPETENCIES & CERTIFICATIONS TAB -->
        <div id="skills" class="viewport-panel">
            <h2>Core Capabilities & Frameworks <span class="section-meta">Technical Breakdown</span></h2>
            
            <div class="matrix-grid" style="margin-bottom: 24px;">
                <div class="matrix-box" style="border-top: 3px solid var(--corporate-blue);">
                    <h3>NISM Series XV — Research Analyst</h3>
                    <p style="font-size:0.95rem; line-height:1.45; color:var(--slate-muted); font-family:-apple-system, sans-serif;">National Institute of Securities Markets | Issued April 2026[cite: 1]. SEBI-mandated operational validation for publishing public and private equity research frameworks within Indian capital markets[cite: 1].</p>
                </div>
                <div class="matrix-box" style="border-top: 3px solid var(--corporate-blue);">
                    <h3>Financial Modelling & Valuation</h3>
                    <p style="font-size:0.95rem; line-height:1.45; color:var(--slate-muted); font-family:-apple-system, sans-serif;">NSE - Grant Thornton | Matrix Framework 2025[cite: 1]. Specialized institutional engineering credential focusing on dynamic valuation modeling structures[cite: 1].</p>
                </div>
            </div>

            <div class="matrix-grid">
                <div class="matrix-box">
                    <h3>Investment Analysis</h3>
                    <ul>
                        <li>DCF valuation with WACC sensitivity analysis[cite: 1]</li>
                        <li>Comparable company analysis (CCA)[cite: 1]</li>
                        <li>DuPont ROE decomposition & Altman Z-score[cite: 1]</li>
                        <li>IPO valuation & fair value estimation[cite: 1]</li>
                    </ul>
                </div>
                <div class="matrix-box">
                    <h3>Research & Coverage</h3>
                    <ul>
                        <li>Three-statement financial modelling[cite: 1]</li>
                        <li>Sector initiation reports & earnings notes[cite: 1]</li>
                        <li>Longitudinal stock tracking & earnings quality[cite: 1]</li>
                        <li>Sectors: FMCG, NBFC, IT, Pharma, Semiconductors[cite: 1]</li>
                    </ul>
                </div>
                <div class="matrix-box">
                    <h3>Tools & Operational Platforms</h3>
                    <ul>
                        <li>Advanced Excel — Dynamic Financial Models[cite: 1]</li>
                        <li>Python Data Analysis (Pandas, Libraries)[cite: 1]</li>
                        <li>Power BI Architecture & Executive Dashboards[cite: 1]</li>
                        <li>Screener.in, Trendlyne, Regulatory Filing Portals[cite: 1]</li>
                    </ul>
                </div>
                <div class="matrix-box">
                    <h3>Analytical Output</h3>
                    <ul>
                        <li>Buy/hold/sell target parameters[cite: 1]</li>
                        <li>Institutional grade multi-model pitch books[cite: 1]</li>
                        <li>Investment thesis & structural margin of safety[cite: 1]</li>
                        <li>Data reporting engines for executive leadership[cite: 1]</li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- EXPERIENCE TAB -->
        <div id="experience" class="viewport-panel">
            <h2>Professional Track Record <span class="section-meta">Operational Mandates</span></h2>
            
            <div class="report-block">
                <div class="report-header">
                    <span>Personal & Family Private Office Portfolio</span>
                    <span class="report-date">2022 – Present[cite: 1]</span>
                </div>
                <div class="report-sub">
                    <span>Equity Research & Investment Portfolio Management[cite: 1]</span>
                </div>
                <ul>
                    <li>Co-managed a 10-50L multi-asset equity portfolio, generating 5-10% alpha above the Nifty 50 CAGR through bottom-up stock selection, DCF-driven valuation, and active sector rotation across FMCG, NBFC, IT services, and pharma[cite: 1].</li>
                    <li>Built three-statement financial models and authored initiation and earnings notes for 4+ listed equities (Nestle, Muthoot Finance, Coforge, and Hindustan Unilever) producing buy/hold/sell recommendations with 12-month price targets backed by DCF and EV/EBITDA analysis[cite: 1].</li>
                    <li>Conducted pre-IPO valuation assessments for Ixigo, Meesho, and Pine Labs, deriving fair value ranges using DCF analysis to evaluate long-term investment thesis and pricing[cite: 1].</li>
                    <li>Applied technical analysis including RSI, moving average crossovers, and support/resistance levels as a secondary overlay to time entry and exit points, improving cost basis on 6+ positions against fundamental conviction calls[cite: 1].</li>
                    <li>Maintained a structured investment tracker consolidating position-level P&L, portfolio turnover, and return attribution across holdings; used periodic performance reviews to assess stock-specific alpha versus broader market and sectoral tailwinds[cite: 1].</li>
                    <li>Monitored key financial and macro indicators—earnings revisions, margins, RoE/RoCE trends, credit growth, and policy rate movements—to assess sector-level headwinds and refine coverage universe prioritization[cite: 1].</li>
                </ul>
            </div>

            <div class="report-block">
                <div class="report-header">
                    <span>Subhiksha Hotels and Resorts Pvt. Ltd.</span>
                    <span class="report-date">Jan 2024 – Jun 2024[cite: 1]</span>
                </div>
                <div class="report-sub">
                    <span>Corporate Finance Intern[cite: 1]</span>
                </div>
                <ul>
                    <li>Designed and implemented cost optimisation strategies by building cost-variance and trend-forecasting models, directly driving a 10% improvement in net profit margins within the 6-month internship period[cite: 1].</li>
                    <li>Executed end-to-end financial planning and analysis (FP&A) — monitoring KPIs, tracking operational performance, and identifying structural inefficiencies across departments[cite: 1].</li>
                    <li>Translated financial statements into concise executive dashboards for senior leadership, enabling data-driven quarterly planning and budget vs. actuals review[cite: 1].</li>
                </ul>
            </div>
        </div>

        <!-- PUBLICATIONS TAB -->
        <div id="publications" class="viewport-panel">
            <h2>Formal Equity Research & Publications <span class="section-meta">Institutional Artifacts</span></h2>
            <div class="deck-row">
                
                <div class="pub-panel">
                    <div class="pub-top">
                        <div class="pub-title">Semiconductor Ecosystem Valuation Book</div>
                        <a href="#" class="pub-link" target="_blank">Access Pitch Book ↗[cite: 1]</a>
                    </div>
                    <p>Authored an institutional-grade pitch book on India's semiconductor ecosystem covering 4 listed players (Tata Elxsi, ASM Technologies, Hind Rectifiers, RIR Power Electronics)[cite: 1]. Built a multi-model valuation framework combining DCF with dynamic WACC sensitivity, relative valuation (P/E, EV/EBITDA), DuPont analysis, and Altman Z-score to deconstruct ROE drivers and risk profiles[cite: 1].</p>
                </div>

                <div class="pub-panel">
                    <div class="pub-top">
                        <div class="pub-title">Natco Pharma: 5-Year Longitudinal Model</div>
                        <a href="#" class="pub-link" target="_blank">Access Research ↗[cite: 1]</a>
                    </div>
                    <p>Conducted a 5-year longitudinal tracking and financial performance analysis of Natco Pharma through Q3-2026, covering earnings quality, pipeline developments, margin expansion, and macro regulatory compliance impacts[cite: 1].</p>
                </div>

                <div class="pub-panel">
                    <div class="pub-top">
                        <div class="pub-title">"Equity Insights" Analytics Platform</div>
                        <a href="#" class="pub-link" target="_blank">Access Platform ↗[cite: 1]</a>
                    </div>
                    <p>Founder and author of a dedicated platform publishing regular analytical commentary on Indian capital markets, covering corporate actions, macroeconomic developments, and geopolitical impacts on listed equities[cite: 1].</p>
                </div>

            </div>
        </div>

        <!-- EDUCATION TAB -->
        <div id="education" class="viewport-panel">
            <h2>Academic Foundations & Mandates <span class="section-meta">Verification Matrix</span></h2>
            <div class="edu-matrix">
                
                <div class="edu-node">
                    <div>
                        <h3>MBA — Finance & Analytics</h3>
                        <div class="edu-inst">VIT University, Chennai[cite: 1]</div>
                    </div>
                    <div class="edu-score-row">
                        <span>CGPA: 8.13 / 10.0[cite: 1]</span>
                        <span>Class of 2026[cite: 1]</span>
                    </div>
                </div>

                <div class="edu-node">
                    <div>
                        <h3>BBA — Financial Planning</h3>
                        <div class="edu-inst">MGR University, Chennai[cite: 1]</div>
                    </div>
                    <div class="edu-score-row">
                        <span>CGPA: 8.86 / 10.0[cite: 1]</span>
                        <span>Class of 2024[cite: 1]</span>
                    </div>
                </div>

                <div class="edu-node" style="border-top-color: var(--corporate-blue);">
                    <div>
                        <h3>CFA® Program Candidate</h3>
                        <div class="edu-inst">CFA Institute[cite: 1]</div>
                    </div>
                    <div class="edu-score-row">
                        <span>Level 1 Target[cite: 1]</span>
                        <span>Exam: Feb 2027[cite: 1]</span>
                    </div>
                </div>

            </div>
        </div>

    </main>

    <!-- State View Tab Engine -->
    <script>
        function switchTab(tabId) {
            // Locate all structural panels and mask them completely
            const panels = document.querySelectorAll('.viewport-panel');
            panels.forEach(panel => {
                panel.classList.remove('active');
            });

            // Strip active indicators from navigation hooks
            const buttons = document.querySelectorAll('.nav-links button');
            buttons.forEach(btn => btn.classList.remove('active'));

            // Focus targets
            const targetPanel = document.getElementById(tabId);
            targetPanel.classList.add('active');
            
            const targetBtn = document.getElementById('btn-' + tabId);
            if(targetBtn) targetBtn.classList.add('active');

            // Explicitly force scroll resetting to structural element borders
            targetPanel.scrollTop = 0;
        }
    </script>
</body>
</html>
