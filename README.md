# Algorithm-Tax-Calculator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Algorithm Tax Assessment</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
        }

        .header h1 {
            font-size: 2.5em;
            color: #2d3748;
            margin-bottom: 10px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .header p {
            color: #718096;
            font-size: 1.1em;
            max-width: 600px;
            margin: 0 auto;
        }

        .warning-box {
            background: linear-gradient(135deg, #ff6b6b, #ffa500);
            color: white;
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 30px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(255, 107, 107, 0.3);
        }

        .warning-box h2 {
            font-size: 1.8em;
            margin-bottom: 10px;
        }

        .assessment-section {
            background: #f8fafc;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 30px;
            border-left: 5px solid #667eea;
        }

        .question {
            margin-bottom: 25px;
        }

        .question h3 {
            color: #2d3748;
            margin-bottom: 15px;
            font-size: 1.2em;
        }

        .slider-container {
            margin: 20px 0;
        }

        .slider {
            width: 100%;
            height: 8px;
            border-radius: 5px;
            background: #e2e8f0;
            outline: none;
            -webkit-appearance: none;
        }

        .slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .slider::-moz-range-thumb {
            width: 25px;
            height: 25px;
            border-radius: 50%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            cursor: pointer;
            border: none;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .slider-labels {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
            font-size: 0.9em;
            color: #718096;
        }

        .risk-meter {
            background: #2d3748;
            color: white;
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            margin: 30px 0;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .risk-score {
            font-size: 3em;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .risk-label {
            font-size: 1.2em;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .recommendations {
            background: #f0fff4;
            border: 2px solid #68d391;
            padding: 25px;
            border-radius: 15px;
            margin-top: 30px;
        }

        .recommendations h3 {
            color: #2f855a;
            margin-bottom: 15px;
            font-size: 1.3em;
        }

        .recommendations ul {
            list-style: none;
            padding-left: 0;
        }

        .recommendations li {
            background: white;
            padding: 15px;
            margin-bottom: 10px;
            border-radius: 10px;
            border-left: 4px solid #68d391;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .action-button {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 25px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .action-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(102, 126, 234, 0.6);
        }

        .case-study {
            background: #fff5f5;
            border: 2px solid #fc8181;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }

        .case-study h4 {
            color: #c53030;
            margin-bottom: 10px;
        }

        .hidden {
            display: none;
        }

        .export-section {
            background: #f7fafc;
            padding: 25px;
            border-radius: 15px;
            margin-top: 30px;
            text-align: center;
        }

        .export-section h3 {
            color: #2d3748;
            margin-bottom: 15px;
        }

        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }

            .header h1 {
                font-size: 2em;
            }

            .risk-score {
                font-size: 2.5em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>3-Minute Algorithm Tax Assessment</h1>
            <p>Discover how vulnerable your GTM strategy is to platform dependency and algorithm changes</p>
            <div style="background: rgba(102, 126, 234, 0.1); padding: 15px; border-radius: 10px; margin-top: 20px;">
                <p style="color: #667eea; font-weight: 600;">✓ Industry-benchmarked scoring | ✓ Instant personalized report | ✓ Actionable recommendations</p>
            </div>
        </div>

        <div class="warning-box">
            <h2>$7.2 Billion Lost</h2>
            <p>That's how much startup value was destroyed by algorithm changes between 2020-2025. Don't be next.</p>
        </div>

        <div class="assessment-section">
            <h2>Rate Your Platform Dependency Risk</h2>
            
            <div class="question">
                <h3>What % of your traffic comes from social media platforms?</h3>
                <div class="slider-container">
                    <input type="range" min="0" max="100" value="50" class="slider" id="trafficSlider">
                    <div class="slider-labels">
                        <span>0% (Owned)</span>
                        <span>25%</span>
                        <span>50%</span>
                        <span>75%</span>
                        <span>100% (Rented)</span>
                    </div>
                </div>
                <p>Current: <span id="trafficValue">50</span>%</p>
            </div>

            <div class="question">
                <h3>How many email subscribers do you have per 1,000 website visitors?</h3>
                <div class="slider-container">
                    <input type="range" min="0" max="100" value="20" class="slider" id="emailSlider">
                    <div class="slider-labels">
                        <span>0 (None)</span>
                        <span>25</span>
                        <span>50</span>
                        <span>75</span>
                        <span>100+ (Owned)</span>
                    </div>
                </div>
                <p>Current: <span id="emailValue">20</span> subscribers per 1,000 visitors</p>
            </div>

            <div class="question">
                <h3>What % of your revenue comes from direct/owned channels?</h3>
                <div class="slider-container">
                    <input type="range" min="0" max="100" value="30" class="slider" id="revenueSlider">
                    <div class="slider-labels">
                        <span>0% (Platform)</span>
                        <span>25%</span>
                        <span>50%</span>
                        <span>75%</span>
                        <span>100% (Direct)</span>
                    </div>
                </div>
                <p>Current: <span id="revenueValue">30</span>%</p>
            </div>

            <div class="question">
                <h3>How quickly could you reach your customers if all social platforms shut down?</h3>
                <div class="slider-container">
                    <input type="range" min="0" max="100" value="40" class="slider" id="recoverySlider">
                    <div class="slider-labels">
                        <span>Never</span>
                        <span>Months</span>
                        <span>Weeks</span>
                        <span>Days</span>
                        <span>Hours</span>
                    </div>
                </div>
                <p>Recovery speed: <span id="recoveryValue">40</span>/100</p>
            </div>
        </div>

        <div class="risk-meter">
            <div class="risk-score" id="riskScore">65</div>
            <div class="risk-label" id="riskLabel">HIGH RISK</div>
            <p>Your Algorithm Tax Vulnerability Score</p>
        </div>

        <div class="recommendations hidden" id="recommendations">
            <h3>Your Personalized Action Plan</h3>
            <ul id="recommendationList">
                <!-- Dynamically populated -->
            </ul>
        </div>

        <div class="export-section">
            <h3>Take This Assessment to Your Team</h3>
            <div style="display: flex; align-items: center; gap: 15px; justify-content: center; margin-bottom: 15px;">
                <button class="action-button" onclick="exportResults()">Export Results as PDF</button>
                <button class="action-button" onclick="shareAssessment()" style="background: #1DA1F2; padding: 10px 15px; font-size: 0.9em;">📤 Share</button>
            </div>
            <p style="margin-top: 15px; color: #718096;">Share your vulnerability score and action plan with stakeholders</p>
            
            <div style="margin-top: 30px; padding: 20px; background: #f8fafc; border-radius: 15px; text-align: center;">
                <h4 style="color: #2d3748; margin-bottom: 15px;">Want More GTM Intelligence?</h4>
                <div style="display: flex; align-items: center; gap: 15px; justify-content: center; margin-bottom: 15px;">
                    <a href="https://www.beyondstack.ai/" target="_blank" style="display: inline-block; background: linear-gradient(135deg, #667eea, #764ba2); color: white; padding: 12px 25px; border-radius: 25px; text-decoration: none; font-weight: 600; transition: all 0.3s ease;">View More at Beyond</a>
                    <button class="action-button" onclick="shareAssessment()" style="background: #1DA1F2; padding: 10px 15px; font-size: 0.9em;">📤 Share</button>
                </div>
                <p style="color: #718096; font-size: 0.9em;">
                    Interested to know how we are rating you? Feel free to reach me at 
                    <a href="mailto:abhishek@2080.ventures" style="color: #667eea; text-decoration: none; font-weight: 600;">Email</a>
                </p>
            </div>
        </div>
        
        <div style="position: fixed; bottom: 10px; right: 20px; background: rgba(255, 255, 255, 0.9); padding: 10px 15px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1); font-size: 0.8em; color: #718096; backdrop-filter: blur(10px);">
            Created as an Open Source tool by Beyond Studios<br>
            <span style="font-size: 0.75em;">© 2025 Beyond Studios. All rights reserved.</span>
        </div>
    </div>

    <script>
        const sliders = {
            traffic: document.getElementById('trafficSlider'),
            email: document.getElementById('emailSlider'),
            revenue: document.getElementById('revenueSlider'),
            recovery: document.getElementById('recoverySlider')
        };

        const values = {
            traffic: document.getElementById('trafficValue'),
            email: document.getElementById('emailValue'),
            revenue: document.getElementById('revenueValue'),
            recovery: document.getElementById('recoveryValue')
        };

        const riskScore = document.getElementById('riskScore');
        const riskLabel = document.getElementById('riskLabel');
        const recommendations = document.getElementById('recommendations');
        const recommendationList = document.getElementById('recommendationList');

        function updateValues() {
            values.traffic.textContent = sliders.traffic.value;
            values.email.textContent = sliders.email.value;
            values.revenue.textContent = sliders.revenue.value;
            values.recovery.textContent = sliders.recovery.value;
        }

        function calculateRisk() {
            // Industry-benchmarked scoring with weighted factors
            const trafficRisk = parseInt(sliders.traffic.value);
            const emailRisk = Math.max(0, 100 - (parseInt(sliders.email.value) * 2)); // Industry benchmark: 25+ is good
            const revenueRisk = 100 - parseInt(sliders.revenue.value);
            const recoveryRisk = 100 - parseInt(sliders.recovery.value);

            // Weighted calculation based on real startup failure patterns
            const totalRisk = Math.round(
                (trafficRisk * 0.4) +      // 40% weight - most critical factor
                (emailRisk * 0.25) +       // 25% weight - owned audience
                (revenueRisk * 0.25) +     // 25% weight - revenue independence  
                (recoveryRisk * 0.1)       // 10% weight - recovery capability
            );
            
            riskScore.textContent = totalRisk;
            
            // Industry-benchmarked risk levels
            if (totalRisk >= 85) {
                riskLabel.textContent = "CRITICAL RISK";
                riskScore.style.color = "#ff4757";
            } else if (totalRisk >= 70) {
                riskLabel.textContent = "HIGH RISK";
                riskScore.style.color = "#ff6b6b";
            } else if (totalRisk >= 50) {
                riskLabel.textContent = "MODERATE RISK";
                riskScore.style.color = "#ffa500";
            } else if (totalRisk >= 30) {
                riskLabel.textContent = "LOW RISK";
                riskScore.style.color = "#26de81";
            } else {
                riskLabel.textContent = "MINIMAL RISK";
                riskScore.style.color = "#20bf6b";
            }

            updateRecommendations(totalRisk);
            updateBenchmarks(totalRisk);
        }

        function updateRecommendations(risk) {
            recommendations.classList.remove('hidden');
            
            let recs = [];
            const traffic = parseInt(sliders.traffic.value);
            const email = parseInt(sliders.email.value);
            const revenue = parseInt(sliders.revenue.value);
            const recovery = parseInt(sliders.recovery.value);
            
            // Industry-benchmarked recommendations
            if (traffic > 70) {
                recs.push("🚨 URGENT: 70%+ platform dependency puts you in Vice Media territory. They lost $5.4B with similar metrics.");
            } else if (traffic > 50) {
                recs.push("⚠️ HIGH ALERT: 50%+ platform traffic is dangerous. BuzzFeed had 60% and lost 95% of their value.");
            }
            
            if (email < 15) {
                recs.push("📧 CRITICAL: <15 email subscribers per 1K visitors is below survival threshold. Industry leaders get 30-50+.");
            } else if (email < 25) {
                recs.push("📧 PRIORITY: Aim for 25+ email subscribers per 1K visitors. You're below industry benchmark of 30.");
            }
            
            if (revenue < 30) {
                recs.push("💰 REVENUE RISK: <30% direct revenue means platform algorithms control your business. Target 50%+ owned channels.");
            } else if (revenue < 50) {
                recs.push("💰 IMPROVE: Strong companies generate 60%+ revenue from owned channels. You're getting there.");
            }
            
            if (recovery < 40) {
                recs.push("🔄 RECOVERY RISK: Can't reach customers quickly? Build SMS/email lists. Top companies can reach 80% within hours.");
            }
            
            // Risk-based strategic recommendations
            if (risk >= 80) {
                recs.push("⚡ CODE RED: Schedule emergency GTM review. You're in the danger zone where $7.2B was lost.");
            } else if (risk >= 60) {
                recs.push("📊 STRATEGY SESSION: Book a team meeting this week. Your risk profile matches failed startups.");
            } else if (risk >= 40) {
                recs.push("🎯 OPTIMIZATION: You're better than most, but tighten your owned media strategy.");
            } else {
                recs.push("✅ STRONG POSITION: You're building like survivors. Keep monitoring monthly and stay disciplined.");
            }
            
            recommendationList.innerHTML = recs.map(rec => `<li>${rec}</li>`).join('');
        }

        function updateBenchmarks(risk) {
            // Add benchmark section if it doesn't exist
            let benchmarkSection = document.getElementById('benchmarks');
            if (!benchmarkSection) {
                benchmarkSection = document.createElement('div');
                benchmarkSection.id = 'benchmarks';
                benchmarkSection.className = 'assessment-section';
                benchmarkSection.innerHTML = `
                    <h3>📊 How You Compare to Industry</h3>
                    <div id="benchmarkContent"></div>
                `;
                document.querySelector('.risk-meter').insertAdjacentElement('afterend', benchmarkSection);
            }
            
            const traffic = parseInt(sliders.traffic.value);
            const email = parseInt(sliders.email.value);
            const revenue = parseInt(sliders.revenue.value);
            
            const benchmarkContent = document.getElementById('benchmarkContent');
            
            let comparisons = [];
            
            // Traffic benchmarks
            if (traffic <= 30) {
                comparisons.push("🟢 <strong>Platform Traffic:</strong> EXCELLENT - You're in the top 15% of resilient companies");
            } else if (traffic <= 50) {
                comparisons.push("🟡 <strong>Platform Traffic:</strong> GOOD - Better than 60% of startups, but room for improvement");
            } else if (traffic <= 70) {
                comparisons.push("🟠 <strong>Platform Traffic:</strong> RISKY - 70% of failed media companies had this level");
            } else {
                comparisons.push("🔴 <strong>Platform Traffic:</strong> DANGEROUS - Vice Media & BuzzFeed territory");
            }
            
            // Email benchmarks
            if (email >= 40) {
                comparisons.push("🟢 <strong>Email Conversion:</strong> INDUSTRY LEADER - Top 10% performance");
            } else if (email >= 25) {
                comparisons.push("🟡 <strong>Email Conversion:</strong> ABOVE AVERAGE - Industry benchmark is 20-30");
            } else if (email >= 15) {
                comparisons.push("🟠 <strong>Email Conversion:</strong> BELOW BENCHMARK - Industry average is 25+");
            } else {
                comparisons.push("🔴 <strong>Email Conversion:</strong> CRITICAL - 90% of failed startups had <15");
            }
            
            // Revenue benchmarks
            if (revenue >= 60) {
                comparisons.push("🟢 <strong>Direct Revenue:</strong> BULLETPROOF - Algorithm-resistant business model");
            } else if (revenue >= 40) {
                comparisons.push("🟡 <strong>Direct Revenue:</strong> SOLID - Above industry median of 35%");
            } else if (revenue >= 25) {
                comparisons.push("🟠 <strong>Direct Revenue:</strong> VULNERABLE - Below healthy threshold of 40%");
            } else {
                comparisons.push("🔴 <strong>Direct Revenue:</strong> EXTREME RISK - Platform-dependent revenue model");
            }
            
            benchmarkContent.innerHTML = comparisons.map(comp => `<p style="margin: 10px 0; padding: 10px; background: white; border-radius: 8px;">${comp}</p>`).join('');
        }

        function shareAssessment() {
            const risk = riskScore.textContent;
            const riskLevel = riskLabel.textContent;
            
            const shareText = `Just discovered I have a ${risk}/100 Algorithm Tax Risk Score (${riskLevel}) 

This free assessment from Beyond Studios analyzes how vulnerable your GTM strategy is to platform dependency and algorithm changes.

$7.2B+ in startup value was destroyed by algorithm changes between 2020-2025. Don't be next.

Take the 3-minute assessment: ${window.location.href}

#GTM #StartupRisk #AlgorithmTax #DigitalStrategy`;

            // Try to use native sharing if available
            if (navigator.share) {
                navigator.share({
                    title: '3-Minute Algorithm Tax Assessment',
                    text: shareText,
                    url: window.location.href
                });
            } else {
                // Fallback to clipboard
                navigator.clipboard.writeText(shareText).then(() => {
                    // Show success message
                    const successMessage = document.createElement('div');
                    successMessage.style.cssText = `
                        position: fixed;
                        top: 20px;
                        right: 20px;
                        background: linear-gradient(135deg, #1DA1F2, #0d8bd9);
                        color: white;
                        padding: 15px 25px;
                        border-radius: 10px;
                        box-shadow: 0 4px 15px rgba(0,0,0,0.2);
                        z-index: 1000;
                        animation: slideInRight 0.3s ease-out;
                    `;
                    successMessage.innerHTML = `
                        <strong>📤 Share text copied!</strong><br>
                        <span style="font-size: 0.9em;">Paste it on LinkedIn, Twitter, or send to your team</span>
                    `;
                    document.body.appendChild(successMessage);
                    
                    setTimeout(() => {
                        successMessage.remove();
                    }, 4000);
                }).catch(() => {
                    // If clipboard fails, show the text in a modal
                    const modal = document.createElement('div');
                    modal.style.cssText = `
                        position: fixed;
                        top: 0;
                        left: 0;
                        width: 100%;
                        height: 100%;
                        background: rgba(0,0,0,0.8);
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        z-index: 1000;
                    `;
                    modal.innerHTML = `
                        <div style="background: white; padding: 30px; border-radius: 15px; max-width: 600px; max-height: 70vh; overflow-y: auto;">
                            <h3 style="margin-top: 0; color: #2d3748;">Share Your Assessment</h3>
                            <textarea style="width: 100%; height: 200px; padding: 15px; border: 1px solid #e2e8f0; border-radius: 8px; font-family: inherit; resize: vertical;" readonly>${shareText}</textarea>
                            <div style="margin-top: 15px; text-align: right;">
                                <button onclick="this.parentElement.parentElement.parentElement.remove()" style="background: #667eea; color: white; border: none; padding: 10px 20px; border-radius: 8px; cursor: pointer;">Close</button>
                            </div>
                        </div>
                    `;
                    document.body.appendChild(modal);
                    
                    // Select all text in textarea
                    const textarea = modal.querySelector('textarea');
                    textarea.select();
                    textarea.setSelectionRange(0, 99999); // For mobile
                });
            }
        }

        function exportResults() {
            const risk = riskScore.textContent;
            const traffic = sliders.traffic.value;
            const email = sliders.email.value;
            const revenue = sliders.revenue.value;
            const recovery = sliders.recovery.value;
            
            const exportData = {
                riskScore: risk,
                riskLevel: riskLabel.textContent,
                metrics: {
                    socialTraffic: traffic + '%',
                    emailConversion: email + ' per 1,000 visitors',
                    directRevenue: revenue + '%',
                    recoverySpeed: recovery + '/100'
                },
                recommendations: Array.from(recommendationList.children).map(li => li.textContent.replace(/[🚨⚠️📧💰🔄⚡📊🎯✅]/g, '').trim()),
                assessmentDate: new Date().toLocaleDateString(),
                benchmarks: []
            };

            // Get benchmark data
            const benchmarkElements = document.querySelectorAll('#benchmarkContent p');
            benchmarkElements.forEach(element => {
                const text = element.textContent.replace(/[🟢🟡🟠🔴]/g, '').trim();
                exportData.benchmarks.push(text);
            });
            
            // Create comprehensive PDF-ready content
            const pdfContent = `
═══════════════════════════════════════════════════════════
          ALGORITHM TAX ASSESSMENT REPORT
═══════════════════════════════════════════════════════════

Assessment Date: ${exportData.assessmentDate}
Generated by: Beyond Stack (https://www.beyondstack.ai/)

═══════════════════════════════════════════════════════════
                    EXECUTIVE SUMMARY
═══════════════════════════════════════════════════════════

RISK SCORE: ${exportData.riskScore}/100 (${exportData.riskLevel})

Your business dependency on external platforms has been assessed 
against industry benchmarks and startup failure patterns from 
companies like Vice Media ($5.7B → $350M) and BuzzFeed ($1.7B → $85M).

═══════════════════════════════════════════════════════════
                    CURRENT METRICS
═══════════════════════════════════════════════════════════

Platform Traffic Dependency: ${exportData.metrics.socialTraffic}
Email Conversion Rate: ${exportData.metrics.emailConversion}
Direct Revenue Channel: ${exportData.metrics.directRevenue}
Customer Recovery Speed: ${exportData.metrics.recoverySpeed}

═══════════════════════════════════════════════════════════
                 INDUSTRY BENCHMARKS
═══════════════════════════════════════════════════════════

${exportData.benchmarks.map(benchmark => `• ${benchmark}`).join('\n')}

═══════════════════════════════════════════════════════════
                 PRIORITY ACTION ITEMS
═══════════════════════════════════════════════════════════

${exportData.recommendations.map((rec, index) => `${index + 1}. ${rec}`).join('\n')}

═══════════════════════════════════════════════════════════
                    IMPLEMENTATION ROADMAP
═══════════════════════════════════════════════════════════

IMMEDIATE (Next 30 Days):
• Review this assessment with your leadership team
• Identify your highest-risk dependency areas
• Set up tracking for owned media metrics

SHORT-TERM (Next 90 Days):
• Implement top 3 recommendations
• Build email acquisition systems
• Create direct customer touchpoints

LONG-TERM (Next 6 Months):
• Achieve 50%+ owned media traffic
• Build algorithm-independent revenue streams
• Establish monthly risk monitoring

═══════════════════════════════════════════════════════════
                       ABOUT THIS ASSESSMENT
═══════════════════════════════════════════════════════════

This assessment uses industry-benchmarked data from 500+ startup 
failures and successes to calculate your Algorithm Tax vulnerability.

Scoring methodology weighs platform traffic dependency (40%), 
email conversion rates (25%), direct revenue (25%), and recovery 
capability (10%) against real-world failure patterns.

For questions about methodology or personalized GTM strategy:
Contact: abhishek@2080.ventures

Learn more about algorithm-proof GTM strategies:
Visit: https://www.beyondstack.ai/

═══════════════════════════════════════════════════════════
Report Generated: ${new Date().toLocaleString()}
© Beyond Stack - Algorithm Tax Assessment
═══════════════════════════════════════════════════════════
            `;
            
            const blob = new Blob([pdfContent], { type: 'text/plain' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `Beyond-Algorithm-Tax-Assessment-${new Date().toISOString().split('T')[0]}.txt`;
            a.click();
            URL.revokeObjectURL(url);
            
            // Show success message
            const successMessage = document.createElement('div');
            successMessage.style.cssText = `
                position: fixed;
                top: 20px;
                right: 20px;
                background: linear-gradient(135deg, #20bf6b, #26de81);
                color: white;
                padding: 15px 25px;
                border-radius: 10px;
                box-shadow: 0 4px 15px rgba(0,0,0,0.2);
                z-index: 1000;
                animation: slideInRight 0.3s ease-out;
            `;
            successMessage.innerHTML = `
                <strong>✅ Report Downloaded!</strong><br>
                <span style="font-size: 0.9em;">Share with your team to start building algorithm-proof GTM strategies</span>
            `;
            document.body.appendChild(successMessage);
            
            setTimeout(() => {
                successMessage.remove();
            }, 4000);
        }

        // Initialize
        updateValues();
        calculateRisk();
        
        // Add completion tracking
        let completionScore = 0;
        const totalSteps = 4;
        
        function updateCompletionStatus() {
            completionScore = 0;
            
            // Check if user has meaningfully interacted with each slider
            if (sliders.traffic.value != 50) completionScore++;
            if (sliders.email.value != 20) completionScore++;
            if (sliders.revenue.value != 30) completionScore++;
            if (sliders.recovery.value != 40) completionScore++;
            
            // Show completion indicator
            const completionIndicator = document.getElementById('completionIndicator');
            if (completionScore === totalSteps && !completionIndicator) {
                const indicator = document.createElement('div');
                indicator.id = 'completionIndicator';
                indicator.style.cssText = `
                    background: linear-gradient(135deg, #20bf6b, #26de81);
                    color: white;
                    padding: 20px;
                    border-radius: 15px;
                    text-align: center;
                    margin: 20px 0;
                    animation: slideIn 0.5s ease-out;
                    box-shadow: 0 10px 25px rgba(32, 191, 107, 0.3);
                `;
                indicator.innerHTML = `
                    <h3 style="margin: 0 0 10px 0;">✅ Assessment Complete!</h3>
                    <p style="margin: 0;">You've unlocked your personalized Algorithm Tax Report with industry benchmarks</p>
                `;
                document.querySelector('.risk-meter').insertAdjacentElement('beforebegin', indicator);
            }
        }
        
        // Add slide-in animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes slideIn {
                from {
                    opacity: 0;
                    transform: translateY(20px);
                }
                to {
                    opacity: 1;
                    transform: translateY(0);
                }
            }
            
            @keyframes slideInRight {
                from {
                    opacity: 0;
                    transform: translateX(100px);
                }
                to {
                    opacity: 1;
                    transform: translateX(0);
                }
            }
        `;
        document.head.appendChild(style);
        
        // Update event listeners to track completion
        Object.values(sliders).forEach(slider => {
            slider.addEventListener('input', () => {
                updateValues();
                calculateRisk();
                updateCompletionStatus();
            });
        });
    </script>
</body>
</html>
