# eurusd-ai-dashboard
analisa trading forex
// DEPLOY ONLINE: // 1. Upload project to GitHub // 2. Deploy using Vercel // 3. Connect custom domain // 4. Add TradingView widget + MT5 API backend // // Recommended Stack: // Frontend: Next.js + TailwindCSS // Backend: Python FastAPI // Hosting: Vercel + Railway/VPS // Database: PostgreSQL // Live Data: MetaTrader5 + TradingView // // Vercel Website Deployment: // https://vercel.com // // GitHub: // https://github.com // // After deployment your website can be opened like: // https://eurusd-ai.vercel.app // // FEATURES: // - Live EURUSD M15 Analysis // - AI BUY/SELL Signals // - Entry / Stop Loss / Take Profit // - AI Candlestick Detection // - Premium Dashboard UI // - TradingView Integration // - MT5 Real-time Data // - Mobile Responsive

export default function ForexAIDashboard() { const signals = [ { type: 'BUY', entry: '1.08420', sl: '1.08340', tp: '1.08600', confidence: '87%', status: 'Strong Trend' }, { type: 'SELL', entry: '1.08310', sl: '1.08400', tp: '1.08150', confidence: '79%', status: 'Reversal Detected' } ];

return ( <div className="min-h-screen bg-black text-white p-6"> <div className="max-w-7xl mx-auto"> <div className="flex items-center justify-between mb-8"> <div> <h1 className="text-5xl font-bold bg-gradient-to-r from-yellow-400 to-orange-500 bg-clip-text text-transparent"> EURUSD AI PRO </h1> <p className="text-gray-400 mt-2 text-lg"> Professional AI Forex Analysis Dashboard • M15 Scalping System </p> </div>

<div className="bg-zinc-900 border border-zinc-800 rounded-2xl px-6 py-4 shadow-2xl">
        <div className="text-sm text-gray-400">AI STATUS</div>
        <div className="flex items-center gap-2 mt-1">
          <div className="w-3 h-3 rounded-full bg-green-500 animate-pulse"></div>
          <span className="font-semibold text-green-400">LIVE ANALYZING</span>
        </div>
      </div>
    </div>

    <div className="grid grid-cols-1 lg:grid-cols-3 gap-6">
      <div className="lg:col-span-2 bg-zinc-900 border border-zinc-800 rounded-3xl overflow-hidden shadow-2xl">
        <div className="p-5 border-b border-zinc-800 flex items-center justify-between">
          <div>
            <h2 className="text-2xl font-bold">EUR/USD Live Chart</h2>
            <p className="text-gray-400">AI Candlestick Detection • Timeframe M15</p>
          </div>

          <div className="bg-black px-4 py-2 rounded-xl border border-zinc-700">
            <span className="text-green-400 font-semibold">Market Open</span>
          </div>
        </div>

        <div className="h-[500px] bg-black flex items-center justify-center relative">
          <div className="absolute inset-0 opacity-20 bg-[radial-gradient(circle_at_center,_#facc15,_transparent_70%)]"></div>

          <div className="text-center z-10">
            <div className="text-6xl mb-4">📈</div>
            <h3 className="text-3xl font-bold mb-2">TradingView Integration</h3>
            <p className="text-gray-400">
              Real-time EURUSD M15 Chart with AI Candlestick Scanner
            </p>
          </div>
        </div>
      </div>

      <div className="space-y-6">
        <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
          <h2 className="text-2xl font-bold mb-5 text-yellow-400">AI Signal</h2>

          <div className="space-y-5">
            {signals.map((signal, index) => (
              <div
                key={index}
                className="bg-black rounded-2xl p-5 border border-zinc-800"
              >
                <div className="flex items-center justify-between mb-4">
                  <div
                    className={`px-4 py-2 rounded-xl font-bold text-lg ${
                      signal.type === 'BUY'
                        ? 'bg-green-500/20 text-green-400'
                        : 'bg-red-500/20 text-red-400'
                    }`}
                  >
                    {signal.type}
                  </div>

                  <div className="text-sm text-gray-400">
                    {signal.confidence}
                  </div>
                </div>

                <div className="space-y-3 text-sm">
                  <div className="flex justify-between">
                    <span className="text-gray-400">Entry</span>
                    <span className="font-semibold">{signal.entry}</span>
                  </div>

                  <div className="flex justify-between">
                    <span className="text-gray-400">Stop Loss</span>
                    <span className="text-red-400 font-semibold">{signal.sl}</span>
                  </div>

                  <div className="flex justify-between">
                    <span className="text-gray-400">Take Profit</span>
                    <span className="text-green-400 font-semibold">{signal.tp}</span>
                  </div>
                </div>

                <div className="mt-4 pt-4 border-t border-zinc-800">
                  <div className="text-xs text-yellow-400 font-semibold">
                    {signal.status}
                  </div>
                </div>
              </div>
            ))}
          </div>
        </div>

        <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
          <h2 className="text-2xl font-bold mb-5 text-cyan-400">AI Market Analysis</h2>

          <div className="space-y-4">
            <div>
              <div className="flex justify-between mb-1">
                <span>Trend Strength</span>
                <span>92%</span>
              </div>
              <div className="h-3 bg-zinc-800 rounded-full overflow-hidden">
                <div className="h-full w-[92%] bg-cyan-400"></div>
              </div>
            </div>

            <div>
              <div className="flex justify-between mb-1">
                <span>Buy Pressure</span>
                <span>81%</span>
              </div>
              <div className="h-3 bg-zinc-800 rounded-full overflow-hidden">
                <div className="h-full w-[81%] bg-green-400"></div>
              </div>
            </div>

            <div>
              <div className="flex justify-between mb-1">
                <span>Volatility</span>
                <span>67%</span>
              </div>
              <div className="h-3 bg-zinc-800 rounded-full overflow-hidden">
                <div className="h-full w-[67%] bg-orange-400"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div className="grid grid-cols-1 md:grid-cols-4 gap-6 mt-8">
      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <div className="text-gray-400 text-sm">Win Rate</div>
        <div className="text-4xl font-bold mt-2 text-green-400">78%</div>
      </div>

      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <div className="text-gray-400 text-sm">Signals Today</div>
        <div className="text-4xl font-bold mt-2 text-yellow-400">24</div>
      </div>

      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <div className="text-gray-400 text-sm">AI Accuracy</div>
        <div className="text-4xl font-bold mt-2 text-cyan-400">84%</div>
      </div>

      <div className="bg-zinc-900 border border-zinc-800 rounded-3xl p-6 shadow-2xl">
        <div className="text-gray-400 text-sm">Active Pair</div>
        <div className="text-4xl font-bold mt-2 text-orange-400">EURUSD</div>
      </div>
    </div>

    <div className="mt-8 bg-zinc-900 border border-zinc-800 rounded-3xl p-8 shadow-2xl">
      <div className="flex items-center justify-between mb-6">
        <div>
          <h2 className="text-3xl font-bold">AI Candlestick Detection</h2>
          <p className="text-gray-400 mt-1">
            Advanced Pattern Recognition System
          </p>
        </div>

        <button className="bg-gradient-to-r from-yellow-400 to-orange-500 text-black font-bold px-6 py-3 rounded-2xl hover:scale-105 transition-all">
          Start AI Analysis
        </button>
      </div>

      <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div className="bg-black border border-zinc-800 rounded-2xl p-5">
          <div className="text-green-400 text-xl font-bold mb-2">
            Bullish Engulfing
          </div>
          <p className="text-gray-400 text-sm">
            Strong bullish reversal detected on M15 timeframe.
          </p>
        </div>

        <div className="bg-black border border-zinc-800 rounded-2xl p-5">
          <div className="text-red-400 text-xl font-bold mb-2">
            Bearish Rejection
          </div>
          <p className="text-gray-400 text-sm">
            Resistance rejection identified by AI scanner.
          </p>
        </div>

        <div className="bg-black border border-zinc-800 rounded-2xl p-5">
          <div className="text-cyan-400 text-xl font-bold mb-2">
            Momentum Breakout
          </div>
          <p className="text-gray-400 text-sm">
            Volatility spike detected before breakout movement.
          </p>
        </div>
      </div>
    </div>
  </div>
</div>

); }