<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>郭宥瑄 | 網路行銷AI協作專員</title>
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@300;400;500;700;900&display=swap');
        body { font-family: 'Noto Sans TC', sans-serif; text-align: left; }
    </style>
</head>
<body>
    <div id="root"></div>

    <script type="text/babel">
        // 這裡就是你剛才提供的那段專業版 React 程式碼
        const { useState, useEffect } = React;
        
        // 圖標元件適配器
        const Icon = ({ name, size = 24, className = "" }) => {
            useEffect(() => { if (window.lucide) window.lucide.createIcons(); }, []);
            return <i data-lucide={name} style={{ width: size, height: size }} className={className}></i>;
        };

        const App = () => {
            const [scrolled, setScrolled] = useState(false);
            const [showScrollTop, setShowScrollTop] = useState(false);
            const [keyword, setKeyword] = useState("");
            const [isGenerating, setIsGenerating] = useState(false);
            const [showResult, setShowResult] = useState(false);

            useEffect(() => {
                const handleScroll = () => {
                    setScrolled(window.scrollY > 50);
                    setShowScrollTop(window.scrollY > 300);
                };
                window.addEventListener('scroll', handleScroll);
                if (window.lucide) window.lucide.createIcons();
                return () => window.removeEventListener('scroll', handleScroll);
            }, []);

            const scrollToTop = () => { window.scrollTo({ top: 0, behavior: 'smooth' }); };

            const handleGenerate = () => {
                if (!keyword) return;
                setIsGenerating(true);
                setShowResult(false);
                setTimeout(() => { setIsGenerating(false); setShowResult(true); }, 2000);
            };

            const skills = [
                { name: 'AI 視覺設計實戰 🎨', desc: '善用 AI 繪圖技術製作平面文宣、海報及 DM，並透過 Canva 進行精細化調整。', icon: 'palette', accent: 'from-orange-400 to-rose-500' },
                { name: 'AI SEO 內容產出 🎯', desc: '擅長利用 AI 高效產出符合搜尋引擎優化的內容，協助品牌穩定獲取精準流量。', icon: 'trending-up', accent: 'from-blue-400 to-indigo-600' },
                { name: '跨領域知識轉譯 💡', desc: '結合科學傳播背景，我擅長將專業、冷門的資訊，拆解為受眾易於理解的知識懶人包。', icon: 'book-open', accent: 'from-emerald-400 to-teal-600' },
                { name: '高效影音內容生產 🎬', desc: '打造流暢的剪輯工作流。頻道累計觀看突破 10 萬次，深知如何利用 AI 提升後製效率。', icon: 'video', accent: 'from-rose-400 to-orange-500' },
                { name: 'LINE 用戶增長 🤝', desc: '設計從 Web 到 LINE 的全鏈路獲客漏斗。建立長期且具溫度的品牌黏著度。', icon: 'message-circle', accent: 'from-indigo-400 to-blue-600' },
                { name: '數位增長實務 🚀', desc: '透過精準對話讓 AI 真正懂你的需求，協助團隊實現顯著的產能提升與效能突破。', icon: 'cpu', accent: 'from-amber-400 to-orange-600' },
            ];

            return (
                <div className="min-h-screen bg-[#fcfcfd] text-slate-900 overflow-x-hidden antialiased text-left">
                    {/* 導覽列 */}
                    <nav className={`fixed top-0 w-full z-50 transition-all duration-700 ${scrolled ? 'bg-white/90 backdrop-blur-md py-4 shadow-xl' : 'bg-transparent py-8'}`}>
                        <div className="max-w-7xl mx-auto px-6 flex justify-between items-center">
                            <div className="font-black bg-slate-900 text-white px-6 py-2 rounded-2xl">網路行銷AI協作專員 郭宥瑄</div>
                            <div className="hidden md:flex gap-10 font-bold text-slate-500">
                                <a href="#results" className="hover:text-orange-500">成果指標</a>
                                <a href="#lab" className="hover:text-orange-500">AI 實驗室</a>
                                <a href="mailto:ysnewmedia@gmail.com" className="bg-orange-500 text-white px-6 py-2 rounded-full shadow-lg">期待洽談</a>
                            </div>
                        </div>
                    </nav>

                    {/* 主視覺 */}
                    <section className="pt-52 pb-32 px-6 max-w-7xl mx-auto">
                        <div className="flex items-center gap-4 mb-8">
                            <span className="h-px w-12 bg-slate-200"></span>
                            <span className="text-2xl font-bold text-slate-400 tracking-widest uppercase">我不只是</span>
                        </div>
                        <h1 className="text-6xl md:text-9xl font-black tracking-tighter leading-tight mb-10">
                            工具使用者<br/>
                            <span className="text-transparent bg-clip-text bg-gradient-to-r from-orange-500 via-rose-500 to-indigo-600 italic">並肩作戰的夥伴</span>
                        </h1>
                        <p className="text-2xl text-slate-500 max-w-3xl leading-relaxed font-medium">
                            我具備將「艱澀專業知識」轉譯為「高易讀性內容」的敏銳度。協助團隊在 AI 浪潮中建立穩定的優勢。
                        </p>
                    </section>

                    {/* 成果指標 */}
                    <section id="results" className="py-20 px-6 bg-slate-50">
                        <div className="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-10">
                            {[
                                { val: "10萬+", label: "頻道累計觀看", desc: "憑藉優化後製呈現觸及精準受眾。", color: "text-orange-600" },
                                { val: "30+", label: "場實體課程統籌", desc: "將行政流程轉化為高效增長引擎。", color: "text-blue-600" },
                                { val: "1.6w", label: "單支影片自然流", desc: "發揮知識轉譯專長獲得高曝光。", color: "text-emerald-600" }
                            ].map((item, idx) => (
                                <div key={idx} className="bg-white p-12 rounded-[3rem] shadow-xl border border-white">
                                    <div className={`text-7xl font-black ${item.color} mb-6`}>{item.val}</div>
                                    <div className="font-black text-slate-400 uppercase tracking-widest mb-4">{item.label}</div>
                                    <p className="text-xl text-slate-600 font-medium">{item.desc}</p>
                                </div>
                            ))}
                        </div>
                    </section>

                    {/* AI 實驗室 */}
                    <section id="lab" className="py-32 px-6">
                        <div className="max-w-5xl mx-auto bg-white p-12 md:p-20 rounded-[4rem] shadow-2xl border border-slate-50">
                            <h2 className="text-4xl md:text-6xl font-black mb-10">AI 實驗室：<span className="text-orange-500">SEO文章生成</span></h2>
                            <div className="space-y-8">
                                <input 
                                    className="w-full bg-slate-50 border-2 border-slate-100 rounded-3xl px-8 py-6 text-2xl font-bold focus:border-orange-500 outline-none transition-all"
                                    placeholder="例如：AI 行銷趨勢..."
                                    value={keyword}
                                    onChange={(e) => setKeyword(e.target.value)}
                                />
                                <button onClick={handleGenerate} className="w-full py-6 bg-slate-900 text-white rounded-3xl text-xl font-black hover:bg-orange-500 transition-all shadow-xl">
                                    {isGenerating ? "正在解析內容權重..." : "執行分析報告"}
                                </button>
                                {showResult && (
                                    <div className="p-10 bg-emerald-50 border border-emerald-100 rounded-[2.5rem] animate-pulse">
                                        <div className="font-black text-emerald-600 mb-4">分析完成</div>
                                        <div className="text-2xl font-extrabold text-slate-800">2026 {keyword} 全攻略：從策略佈局到 AI 實踐的關鍵解答</div>
                                    </div>
                                )}
                            </div>
                        </div>
                    </section>

                    {/* 技能卡片 */}
                    <section className="py-32 px-6 bg-slate-900 text-white rounded-[5rem] mx-4">
                        <div className="max-w-7xl mx-auto">
                            <h2 className="text-5xl font-black mb-20 text-center text-orange-500">專業管線服務</h2>
                            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
                                {skills.map((skill, idx) => (
                                    <div key={idx} className="p-10 bg-white/5 rounded-[3rem] border border-white/10 hover:bg-white/10 transition-all">
                                        <div className="w-16 h-16 bg-orange-500 rounded-2xl flex items-center justify-center mb-8">
                                            <Icon name={skill.icon} className="text-white" size={32} />
                                        </div>
                                        <h3 className="text-2xl font-black mb-6">{skill.name}</h3>
                                        <p className="text-lg text-slate-400 leading-relaxed font-medium">{skill.desc}</p>
                                    </div>
                                ))}
                            </div>
                        </div>
                    </section>

                    {/* 頁尾 */}
                    <footer className="py-32 text-center">
                        <h3 className="text-5xl md:text-8xl font-black mb-12">期待與您<br/><span className="text-orange-500 italic">並肩作戰</span></h3>
                        <p className="text-slate-300 font-bold tracking-[0.5em] mb-8">數據驅動 • AI 協作 • © 2026 郭宥瑄</p>
                        <a href="mailto:ysnewmedia@gmail.com" className="text-2xl md:text-4xl font-black text-slate-900 hover:text-orange-500 underline decoration-orange-200 transition-colors">
                            ysnewmedia@gmail.com
                        </a>
                    </footer>
                </div>
            );
        };

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>
