# 🤖 AI Trading Army - Crypto Multi-Agent Bot (v1.0)

ระบบ AI Trading Army แบบ Multi-Agent จำนวน 11 ตัว  
สำหรับวิเคราะห์ตลาดคริปโต, ออกคำสั่งเทรดอัตโนมัติ, ทำกำไรจาก DeFi และตลาดอนุพันธ์  
รองรับ Arbitrage, Flash Loan, DEX, CEX, Sniper, Sandwich และกลยุทธ์ขั้นสูง

---

## 🧠 AI Agent ที่รวมอยู่

| Agent | หน้าที่ |
|-------|--------|
| 🧠 `ArbitrageAI` | ค้นหาราคาแตกต่างระหว่างตลาด (DEX ↔ CEX) แล้วส่งคำสั่งซื้อขาย |
| ⚡ `FlashLoanAI` | ใช้ Flash Loan ทำกำไรแบบไม่ต้องใช้ทุนตัวเอง |
| 🦈 `SandwichAI` | ดักหน้าหลังคำสั่งซื้อใหญ่เพื่อกินค่าส่วนต่าง |
| 🎯 `SniperAI` | ตรวจจับเหรียญใหม่/Presale แล้วเข้าเทรดในมิลลิวินาทีแรก |
| 🧭 `TrendFollowerAI` | วิเคราะห์เทรนด์จากกราฟราคาและอารมณ์ตลาด |
| 🔮 `OracleWatchAI` | เฝ้าราคาจาก Oracle (เช่น Chainlink, Pyth) เพื่อเทรดอัตโนมัติ |
| 🔁 `DEXSwapAI` | เชื่อม DEX (Uniswap, Sushi) และใช้ Web3 ยิงคำสั่ง Swap |
| 🧬 `VolumeSurgeAI` | วิเคราะห์ Volume ผิดปกติเพื่อเข้าออก position |
| 📈 `FuturesBot` | เทรด Futures ผ่าน CEX API เช่น Binance/Bybit |
| 💰 `FundingRateAI` | วางกลยุทธ์ตาม funding rate ในตลาด perp |
| 🧯 `RiskControllerAI` | จัดการความเสี่ยง + Stop-Loss, Gas Control, Capital Allocation |

---

## 🧩 โครงสร้างระบบ

ai-trading-army/
├── agents/ # โฟลเดอร์รวม AI แต่ละตัว
│ ├── arbitrage_ai.py
│ ├── flashloan_ai.py
│ ├── sandwich_ai.py
│ └── ...
├── config/
│ └── settings.yaml # ตั้งค่ากลยุทธ์, RPC, เหรียญ, ฯลฯ
├── core/
│ ├── executor.py # ตัวจัดการคำสั่งเทรดทั้งหมด
│ ├── web3_client.py # เชื่อม Blockchain
│ └── oracle_feed.py # ดึงข้อมูล oracle
├── dashboard/ # Frontend แสดงผลแบบ Dashboard
│ └── index.html
├── scripts/
│ └── run_all_agents.py # สั่งให้ AI ทุกตัวทำงานพร้อมกัน
├── utils/
│ └── logger.py # จัดการ log
└── README.md

yaml
คัดลอก
แก้ไข

---

## 🚀 วิธีใช้งาน

### 1. ติดตั้ง Dependencies

```bash
pip install -r requirements.txt
2. ตั้งค่า RPC, Private Key และเหรียญที่ต้องการเทรด
แก้ไขไฟล์ config/settings.yaml

yaml
คัดลอก
แก้ไข
rpc_url: https://mainnet.infura.io/v3/...
private_key: 0xabc...
tokens:
  - name: USDT
    address: 0xdAC1...
  - name: WETH
    address: 0xC02...
3. เริ่มรัน AI ทั้งหมด
bash
คัดลอก
แก้ไข
python scripts/run_all_agents.py
หรือเลือกแค่ตัวใดตัวหนึ่ง:

bash
คัดลอก
แก้ไข
python agents/flashloan_ai.py
📊 Dashboard
Dashboard แบบ HTML + JS อยู่ใน dashboard/index.html

ใช้แสดง performance ของแต่ละ AI

กดเปิดกราฟ, สถิติ, รายงานกำไรขาดทุนแบบเรียลไทม์

📦 คุณสมบัติเด่น
✅ รองรับ Flash Loan (Aave, dYdX)

✅ รองรับ Oracle Feed (Pyth, Chainlink)

✅ รองรับ Multi-Chain (ETH, Polygon, Arbitrum, BSC)

✅ รันพร้อมกันหลาย AI ได้

✅ ใช้ได้ทั้ง DEX และ CEX

✅ รักษาความปลอดภัยของ Private Key ใน local หรือ Hardware Wallet

⚠️ คำเตือน
ระบบนี้เหมาะสำหรับนักพัฒนาที่มีความเข้าใจ DeFi, Smart Contract, การเทรดเชิงเทคนิค และความเสี่ยงสูงของ Flash Loan
การใช้งานจริงอาจทำให้ขาดทุนหากวางกลยุทธ์ผิดพลาด
