<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8"><title>郭宥瑄 | AI 協作專員</title>
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
</head>
<body>
    <div id="root"></div>
    <script type="text/babel">
        const App = () => (
            <div className="min-h-screen bg-slate-50 p-10 font-sans">
                <div className="max-w-4xl mx-auto bg-white rounded-[3rem] p-12 shadow-2xl">
                    <h1 className="text-6xl font-black text-slate-900 mb-6">我是郭宥瑄 🚀</h1>
                    <p className="text-2xl text-slate-500 italic">我不只是工具使用者，更是並肩作戰的夥伴。</p>
                    <div className="mt-10 p-8 bg-orange-50 rounded-3xl border border-orange-100">
                        <h2 className="text-2xl font-bold text-orange-600 mb-4">實戰成果</h2>
                        <ul className="space-y-4 text-xl font-medium text-slate-700">
                            <li>✨ YouTube 累計觀看突破 100,000 次</li>
                            <li>🎯 單場活動創造 100% 滿座紀錄</li>
                            <li>💡 擅長將冷門資訊轉譯為熱門內容</li>
                        </ul>
                    </div>
                    <div className="mt-12 text-center">
                        <a href="mailto:ysnewmedia@gmail.com" className="text-xl font-black text-slate-900 underline">ysnewmedia@gmail.com</a>
                    </div>
                </div>
            </div>
        );
        ReactDOM.createRoot(document.getElementById('root')).render(<App />);
    </script>
</body>
</html>
