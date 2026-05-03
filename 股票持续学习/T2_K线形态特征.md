# T2 K线形态特征手册

> **版本**：v2.1 初学者优化版（内嵌SVG图示）
> **创建日期**：2026-04-27
> **更新日期**：2026-05-03
> **用途**：技术分析核心工具，辅助识别趋势反转与持续信号
> **配色**：红涨绿跌（A股惯例）

---

## 阅读说明

本文档在每个形态旁直接嵌入了SVG图示，支持以下环境直接查看：

- VS Code（安装 Markdown Preview Enhanced 等预览插件）
- Typora / Obsidian
- GitHub / Gitee（直接渲染）
- 支持HTML的Markdown阅读器

如您的阅读器不支持SVG，可同时打开同目录下的 `T2_K线形态特征.html` 查看完整交互版。

---

## 目录

1. [认识K线](#一认识k线)
2. [单根反转形态](#二单根反转形态)
3. [十字星系列](#三十字星系列)
4. [双根K线组合](#四双根k线组合)
5. [三根K线组合](#五三根k线组合)
6. [多K线反转图形](#六多k线反转图形)
7. [整理形态中继](#七整理形态中继)
8. [缺口形态](#八缺口形态)
9. [实战应用要点](#九实战应用要点)
10. [形态强度速查表](#十形态强度速查表)

---

## 一、认识K线

一根K线记录了一天内四个关键价格，读懂它是一切的起点。

### K线结构

<svg viewBox="0 0 600 140" xmlns="http://www.w3.org/2000/svg" style="max-width:600px">
  <rect x="0" y="0" width="600" height="140" rx="8" fill="#fff" stroke="#B4B2A9" stroke-width="0.5"/>
  <!-- 阳线示例 -->
  <line x1="100" y1="15" x2="100" y2="110" stroke="#A32D2D" stroke-width="1.5"/>
  <rect x="80" y="30" width="40" height="55" rx="2" fill="#E24B4A"/>
  <line x1="145" y1="15" x2="175" y2="15" stroke="#A32D2D" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="180" y="19" font-size="10" fill="#791F1F">最高价</text>
  <line x1="145" y1="30" x2="175" y2="30" stroke="#A32D2D" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="180" y="34" font-size="10" fill="#791F1F">收盘价(顶部)</text>
  <line x1="145" y1="85" x2="175" y2="85" stroke="#A32D2D" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="180" y="89" font-size="10" fill="#791F1F">开盘价(底部)</text>
  <line x1="145" y1="110" x2="175" y2="110" stroke="#A32D2D" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="180" y="114" font-size="10" fill="#791F1F">最低价</text>
  <text x="100" y="130" text-anchor="middle" font-size="11" font-weight="600" fill="#A32D2D">阳线 (收盘价&gt;开盘价)</text>
  <!-- 阴线示例 -->
  <g transform="translate(240,0)">
    <line x1="100" y1="15" x2="100" y2="110" stroke="#27500A" stroke-width="1.5"/>
    <rect x="80" y="30" width="40" height="55" rx="2" fill="#639922"/>
    <line x1="145" y1="15" x2="175" y2="15" stroke="#27500A" stroke-width="0.5" stroke-dasharray="3,2"/>
    <text x="180" y="19" font-size="10" fill="#173404">最高价</text>
    <line x1="145" y1="30" x2="175" y2="30" stroke="#27500A" stroke-width="0.5" stroke-dasharray="3,2"/>
    <text x="180" y="34" font-size="10" fill="#173404">开盘价(顶部)</text>
    <line x1="145" y1="85" x2="175" y2="85" stroke="#27500A" stroke-width="0.5" stroke-dasharray="3,2"/>
    <text x="180" y="89" font-size="10" fill="#173404">收盘价(底部)</text>
    <line x1="145" y1="110" x2="175" y2="110" stroke="#27500A" stroke-width="0.5" stroke-dasharray="3,2"/>
    <text x="180" y="114" font-size="10" fill="#173404">最低价</text>
    <text x="100" y="130" text-anchor="middle" font-size="11" font-weight="600" fill="#27500A">阴线 (收盘价&lt;开盘价)</text>
  </g>
</svg>


| 部位 | 含义 |
|------|------|
| **实体** | 开盘价→收盘价之间的矩形，代表多空博弈最终结果 |
| **上影线** | 最高价→实体顶端的细线，代表多头冲高后被压回的距离 |
| **下影线** | 实体底端→最低价的细线，代表空头打压后被接回的距离 |

> **记忆口诀**：阳线 = 收盘在上方（红色实体）；阴线 = 收盘在下方（绿色实体）。影线越长，说明那一端被"拉扯"得越厉害。

### 阳线与阴线

<svg viewBox="0 0 400 120" xmlns="http://www.w3.org/2000/svg" style="max-width:400px">
  <!-- 大阳线 -->
  <rect x="5" y="5" width="80" height="105" rx="6" fill="#FCEBEB" stroke="#F09595" stroke-width="0.5"/>
  <rect x="25" y="15" width="40" height="60" rx="2" fill="#E24B4A"/>
  <line x1="45" y1="5" x2="45" y2="105" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="45" y="95" text-anchor="middle" font-size="9" fill="#791F1F">实体长</text>
  <text x="45" y="118" text-anchor="middle" font-size="10" font-weight="600" fill="#A32D2D">大阳线</text>
  <!-- 小阳线 -->
  <rect x="105" y="5" width="80" height="105" rx="6" fill="#FCEBEB" stroke="#F09595" stroke-width="0.5" opacity="0.7"/>
  <rect x="125" y="45" width="40" height="15" rx="2" fill="#E24B4A"/>
  <line x1="145" y1="5" x2="145" y2="105" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="145" y="95" text-anchor="middle" font-size="9" fill="#791F1F">实体短</text>
  <text x="145" y="118" text-anchor="middle" font-size="10" font-weight="600" fill="#A32D2D">小阳线</text>
  <!-- 大阴线 -->
  <rect x="215" y="5" width="80" height="105" rx="6" fill="#EAF3DE" stroke="#97C459" stroke-width="0.5"/>
  <rect x="235" y="15" width="40" height="60" rx="2" fill="#639922"/>
  <line x1="255" y1="5" x2="255" y2="105" stroke="#27500A" stroke-width="1.2"/>
  <text x="255" y="95" text-anchor="middle" font-size="9" fill="#173404">实体长</text>
  <text x="255" y="118" text-anchor="middle" font-size="10" font-weight="600" fill="#27500A">大阴线</text>
  <!-- 小阴线 -->
  <rect x="315" y="5" width="80" height="105" rx="6" fill="#EAF3DE" stroke="#97C459" stroke-width="0.5" opacity="0.7"/>
  <rect x="335" y="45" width="40" height="15" rx="2" fill="#639922"/>
  <line x1="355" y1="5" x2="355" y2="105" stroke="#27500A" stroke-width="1.2"/>
  <text x="355" y="95" text-anchor="middle" font-size="9" fill="#173404">实体短</text>
  <text x="355" y="118" text-anchor="middle" font-size="10" font-weight="600" fill="#27500A">小阴线</text>
</svg>

| 形态 | 特征 | 市场含义 |
|-----|------|---------|
| **大阳线** | 实体长，收盘远高于开盘 | 强势多头，买方力量强。底部出现是强力反转信号 |
| **大阴线** | 实体长，收盘远低于开盘 | 强势空头，卖方力量强。顶部出现是危险信号 |
| **小阳线** | 实体短，波动小 | 多头犹豫，方向不明。单独出现意义不大 |
| **小阴线** | 实体短，波动小 | 空头犹豫，方向不明。需结合前后K线判断 |

> **注意**：单根K线只是"线索"，不是"结论"。永远不要因为一根大阳线就追涨，也不要因为一根大阴线就恐慌割肉。要看位置、看成交量、看确认信号。

---

## 二、单根反转形态

出现在趋势末端，暗示方向即将改变。影线越长大，反转信号越强。

### 锤子线（底部反转）

<svg viewBox="0 0 300 180" xmlns="http://www.w3.org/2000/svg" style="max-width:300px">
  <rect x="5" y="5" width="130" height="165" rx="8" fill="#FCEBEB" stroke="#F09595" stroke-width="0.5"/>
  <text x="70" y="25" text-anchor="middle" font-size="12" font-weight="600" fill="#A32D2D">锤子线</text>
  <rect x="45" y="35" width="28" height="18" rx="2" fill="#E24B4A"/>
  <line x1="59" y1="35" x2="59" y2="145" stroke="#A32D2D" stroke-width="1.5"/>
  <line x1="100" y1="80" x2="118" y2="80" stroke="#A32D2D" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="122" y="84" font-size="9" fill="#A32D2D">下影线≥2倍实体</text>
  <path d="M59 155 L59 165 M54 160 L59 165 L64 160" stroke="#E24B4A" stroke-width="1.5" fill="none"/>
  <text x="59" y="175" text-anchor="middle" font-size="10" font-weight="600" fill="#E24B4A">见底信号</text>
  <text x="70" y="195" text-anchor="middle" font-size="9" fill="#791F1F">出现在下跌趋势末端</text>
</svg>

- **特征**：实体小（可阳可阴），下影线≥实体2倍，上影线很短或没有
- **位置**：下跌趋势末端
- **画面感**：白天股价一路下跌（下影线），像被锤子砸下去，但尾盘买方强力拉回，收出一根小实体。说明卖方虽然使劲砸了，但买方在低位大量接盘，空头的"弹药"可能打完了。
- **确认**：次日收阳线，且收盘价高于锤子线实体顶部
- **强度**：★★★☆☆

### 上吊线（顶部反转）

<svg viewBox="0 0 300 180" xmlns="http://www.w3.org/2000/svg" style="max-width:300px">
  <rect x="5" y="5" width="130" height="165" rx="8" fill="#EAF3DE" stroke="#97C459" stroke-width="0.5"/>
  <text x="70" y="25" text-anchor="middle" font-size="12" font-weight="600" fill="#27500A">上吊线</text>
  <rect x="45" y="35" width="28" height="18" rx="2" fill="#639922"/>
  <line x1="59" y1="35" x2="59" y2="145" stroke="#27500A" stroke-width="1.5"/>
  <line x1="100" y1="80" x2="118" y2="80" stroke="#27500A" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="122" y="84" font-size="9" fill="#27500A">下影线≥2倍实体</text>
  <path d="M59 155 L59 165 M54 160 L59 165 L64 160" stroke="#639922" stroke-width="1.5" fill="none" transform="rotate(180,59,160)"/>
  <text x="59" y="175" text-anchor="middle" font-size="10" font-weight="600" fill="#639922">见顶信号</text>
  <text x="70" y="195" text-anchor="middle" font-size="9" fill="#173404">出现在上涨趋势末端</text>
</svg>

- **特征**：形态与锤子线完全一样
- **位置**：上涨趋势末端（关键区别在于位置，而非形状！）
- **画面感**：白天开盘后股价大幅下跌（下影线），尾盘虽被拉回，但只在低位徘徊。多头勉强撑住了，但已经很吃力。
- **确认**：次日收阴线，且收盘价低于上吊线实体底部
- **强度**：★★★☆☆

> **新手最常犯的错**：看到锤子形状就喊"见底"。一定要先判断当前是上涨还是下跌趋势！

### 倒锤子线（底部反转）

<svg viewBox="0 0 300 180" xmlns="http://www.w3.org/2000/svg" style="max-width:300px">
  <rect x="5" y="5" width="130" height="165" rx="8" fill="#FCEBEB" stroke="#F09595" stroke-width="0.5"/>
  <text x="70" y="25" text-anchor="middle" font-size="12" font-weight="600" fill="#A32D2D">倒锤子线</text>
  <rect x="45" y="135" width="28" height="18" rx="2" fill="#E24B4A"/>
  <line x1="59" y1="5" x2="59" y2="135" stroke="#A32D2D" stroke-width="1.5"/>
  <line x1="100" y1="40" x2="118" y2="40" stroke="#A32D2D" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="122" y="44" font-size="9" fill="#A32D2D">上影线≥2倍实体</text>
  <path d="M59 155 L59 165 M54 160 L59 165 L64 160" stroke="#E24B4A" stroke-width="1.5" fill="none"/>
  <text x="59" y="175" text-anchor="middle" font-size="10" font-weight="600" fill="#E24B4A">见底信号</text>
  <text x="70" y="195" text-anchor="middle" font-size="9" fill="#791F1F">出现在下跌趋势末端</text>
</svg>

- **特征**：实体小，上影线≥实体2倍，下影线很短或没有
- **位置**：下跌趋势末端
- **画面感**：白天买方尝试拉高股价（上影线），但没撑住，收盘回落到开盘附近。虽然上攻失败，但空头已无力继续打压。
- **确认**：次日高开或收阳线
- **强度**：★★☆☆☆（弱于锤子线，必须确认）

### 流星线（顶部反转）

<svg viewBox="0 0 300 180" xmlns="http://www.w3.org/2000/svg" style="max-width:300px">
  <rect x="5" y="5" width="130" height="165" rx="8" fill="#EAF3DE" stroke="#97C459" stroke-width="0.5"/>
  <text x="70" y="25" text-anchor="middle" font-size="12" font-weight="600" fill="#27500A">流星线</text>
  <rect x="45" y="135" width="28" height="18" rx="2" fill="#639922"/>
  <line x1="59" y1="5" x2="59" y2="135" stroke="#27500A" stroke-width="1.5"/>
  <line x1="100" y1="40" x2="118" y2="40" stroke="#27500A" stroke-width="0.5" stroke-dasharray="3,2"/>
  <text x="122" y="44" font-size="9" fill="#27500A">上影线≥2倍实体</text>
  <path d="M59 155 L59 165 M54 160 L59 165 L64 160" stroke="#639922" stroke-width="1.5" fill="none" transform="rotate(180,59,160)"/>
  <text x="59" y="175" text-anchor="middle" font-size="10" font-weight="600" fill="#639922">见顶信号</text>
  <text x="70" y="195" text-anchor="middle" font-size="9" fill="#173404">出现在上涨趋势末端</text>
</svg>

- **特征**：形态与倒锤子线完全一样
- **位置**：上涨趋势末端
- **画面感**：开盘后股价冲得很高（上影线），但卖方强力砸盘，收盘回到开盘附近。多头冲高乏力，卖方开始掌控局面。
- **确认**：次日收阴线
- **强度**：★★☆☆☆

> **关键原则**：形态相同，位置决定一切。锤子线/上吊线、倒锤子线/流星线形状完全一样，区别仅在于出现在上涨末端还是下跌末端。判断趋势方向永远是第一步！

---

## 三、十字星系列

开盘价≈收盘价，多空打成平手。十字星本身不表态，但暗示"暴风雨前的宁静"。

### 四种十字星

<svg viewBox="0 0 480 180" xmlns="http://www.w3.org/2000/svg" style="max-width:480px">
  <!-- 普通十字星 -->
  <rect x="5" y="5" width="110" height="165" rx="8" fill="#F1EFE8" stroke="#D3D1C7" stroke-width="0.5"/>
  <line x1="60" y1="20" x2="60" y2="150" stroke="#5F5E5A" stroke-width="1.5"/>
  <rect x="57" y="82" width="6" height="6" rx="1" fill="#444441"/>
  <text x="60" y="175" text-anchor="middle" font-size="10" font-weight="500" fill="#5F5E5A">普通十字星</text>
  <text x="60" y="195" text-anchor="middle" font-size="8" fill="#888780">多空平衡</text>
  <!-- 长腿十字星 -->
  <rect x="125" y="5" width="110" height="165" rx="8" fill="#FAEEDA" stroke="#BA7517" stroke-width="0.5"/>
  <line x1="180" y1="15" x2="180" y2="165" stroke="#854F0B" stroke-width="1.5"/>
  <rect x="177" y="88" width="6" height="6" rx="1" fill="#412402"/>
  <text x="180" y="175" text-anchor="middle" font-size="10" font-weight="500" fill="#854F0B">长腿十字星</text>
  <text x="180" y="195" text-anchor="middle" font-size="8" fill="#854F0B">剧烈博弈</text>
  <!-- 蜻蜓十字星 -->
  <rect x="245" y="5" width="110" height="165" rx="8" fill="#FCEBEB" stroke="#F09595" stroke-width="0.5"/>
  <line x1="300" y1="30" x2="300" y2="165" stroke="#A32D2D" stroke-width="1.5"/>
  <rect x="297" y="24" width="6" height="6" rx="1" fill="#791F1F"/>
  <text x="300" y="175" text-anchor="middle" font-size="10" font-weight="500" fill="#A32D2D">蜻蜓十字星</text>
  <text x="300" y="195" text-anchor="middle" font-size="8" fill="#A32D2D">底部信号</text>
  <!-- 墓碑十字星 -->
  <rect x="365" y="5" width="110" height="165" rx="8" fill="#EAF3DE" stroke="#97C459" stroke-width="0.5"/>
  <line x1="420" y1="15" x2="420" y2="150" stroke="#27500A" stroke-width="1.5"/>
  <rect x="417" y="144" width="6" height="6" rx="1" fill="#173404"/>
  <text x="420" y="175" text-anchor="middle" font-size="10" font-weight="500" fill="#27500A">墓碑十字星</text>
  <text x="420" y="195" text-anchor="middle" font-size="8" fill="#27500A">顶部信号</text>
</svg>

| 类型 | 特征 | 含义 |
|-----|------|------|
| **普通十字星** | 上下影线适中，实体极小 | 多空打平，变盘信号 |
| **长腿十字星** | 上下影线都很长 | 剧烈博弈后回归平衡，**强烈变盘信号** |
| **蜻蜓十字星** | 只有下影线，无上影线 | 空头使劲砸但全被买方接住，**底部信号** |
| **墓碑十字星** | 只有上影线，无下影线 | 多头冲高但全被卖方砸回，**顶部信号** |

> **位置最重要**：上涨末期出现 = 见顶；下跌末期出现 = 见底；盘整中出现 = 继续震荡。脱离位置谈十字星没有意义。

---

## 四、双根K线组合

两根K线的关系比单根更可靠。"组合"的核心是看**前后两天的力量对比**。

### 看涨吞没（阳包阴）- 底部反转 ★★★★☆

<svg viewBox="0 0 280 200" xmlns="http://www.w3.org/2000/svg" style="max-width:280px">
  <text x="140" y="20" text-anchor="middle" font-size="12" font-weight="600" fill="#A32D2D">看涨吞没（底部反转）</text>
  <!-- Day1 阴线 -->
  <rect x="50" y="35" width="24" height="60" rx="2" fill="#639922"/>
  <line x1="62" y1="30" x2="62" y2="100" stroke="#27500A" stroke-width="1.2"/>
  <text x="62" y="115" text-anchor="middle" font-size="9" fill="#27500A">Day1 阴线</text>
  <!-- Day2 阳线（包住） -->
  <rect x="35" y="30" width="48" height="80" rx="2" fill="#E24B4A" opacity="0.85"/>
  <line x1="59" y1="25" x2="59" y2="115" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="59" y="130" text-anchor="middle" font-size="9" fill="#A32D2D">Day2 阳线（完全包住）</text>
  <!-- 箭头 -->
  <path d="M140 160 L140 175 M135 170 L140 175 L145 170" stroke="#E24B4A" stroke-width="1.5" fill="none"/>
  <text x="140" y="190" text-anchor="middle" font-size="11" font-weight="600" fill="#E24B4A">看涨吞没</text>
</svg>

- **特征**：阴线后出现更大的阳线，阳线实体完全包含阴线实体
- **位置**：下跌趋势末端
- **画面感**：前一天收了一根阴线（跌），看起来很弱。第二天突然来一根更大的阳线，把前一天阴线的实体完全"吃掉"。就像弱队突然换了个强力选手，直接碾压了对方。
- **要点**：Day2的阳线越大越好，伴随放量更可靠
- **强度**：★★★★☆

### 看跌吞没（阴包阳）- 顶部反转 ★★★★☆

<svg viewBox="0 0 280 200" xmlns="http://www.w3.org/2000/svg" style="max-width:280px">
  <text x="140" y="20" text-anchor="middle" font-size="12" font-weight="600" fill="#27500A">看跌吞没（顶部反转）</text>
  <!-- Day1 阳线 -->
  <rect x="50" y="35" width="24" height="60" rx="2" fill="#E24B4A"/>
  <line x1="62" y1="30" x2="62" y2="100" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="62" y="115" text-anchor="middle" font-size="9" fill="#A32D2D">Day1 阳线</text>
  <!-- Day2 阴线（包住） -->
  <rect x="35" y="30" width="48" height="80" rx="2" fill="#639922" opacity="0.85"/>
  <line x1="59" y1="25" x2="59" y2="115" stroke="#27500A" stroke-width="1.2"/>
  <text x="59" y="130" text-anchor="middle" font-size="9" fill="#27500A">Day2 阴线（完全包住）</text>
  <!-- 箭头 -->
  <text x="140" y="185" text-anchor="middle" font-size="11" font-weight="600" fill="#639922">看跌吞没</text>
</svg>

- **特征**：阳线后出现更大的阴线，阴线实体完全包含阳线实体
- **位置**：上涨趋势末端
- **画面感**：前一天大家还在欢呼涨了，第二天就被一根大阴线浇了冷水。卖方突然发力，多头措手不及。
- **强度**：★★★★☆

### 看涨孕线 - 底部反转

<svg viewBox="0 0 280 200" xmlns="http://www.w3.org/2000/svg" style="max-width:280px">
  <text x="140" y="20" text-anchor="middle" font-size="12" font-weight="600" fill="#A32D2D">看涨孕线（身怀六甲）</text>
  <!-- Day1 大阴线 -->
  <rect x="40" y="30" width="28" height="80" rx="2" fill="#639922"/>
  <line x1="54" y1="25" x2="54" y2="115" stroke="#27500A" stroke-width="1.2"/>
  <text x="54" y="130" text-anchor="middle" font-size="9" fill="#27500A">Day1 大阴线</text>
  <!-- Day2 小K线（体内） -->
  <rect x="47" y="65" width="14" height="16" rx="2" fill="#E24B4A"/>
  <line x1="54" y1="60" x2="54" y2="85" stroke="#A32D2D" stroke-width="1"/>
  <text x="54" y="155" text-anchor="middle" font-size="9" fill="#A32D2D">Day2 完全在大阴线体内</text>
  <text x="140" y="185" text-anchor="middle" font-size="11" font-weight="600" fill="#E24B4A">可能见底</text>
</svg>

- **特征**：大阴线后出现小K线，小K线完全在大阴线实体范围内
- **位置**：下跌趋势末端
- **画面感**：大阴线"怀了"一根小K线。前一天空头还很强势（大阴线），但第二天空头突然"没劲了"，只能收出一根小K线。力量的转变正在悄悄发生。
- **要点**：Day2越小越标准；如果Day2是十字星，信号更强（叫"十字孕线"）
- **强度**：★★★☆☆

### 乌云盖顶 - 顶部反转

<svg viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg" style="max-width:300px">
  <text x="150" y="20" text-anchor="middle" font-size="12" font-weight="600" fill="#27500A">乌云盖顶（顶部反转）</text>
  <!-- Day1 阳线 -->
  <rect x="60" y="35" width="28" height="65" rx="2" fill="#E24B4A"/>
  <line x1="74" y1="30" x2="74" y2="105" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="74" y="120" text-anchor="middle" font-size="9" fill="#A32D2D">Day1 阳线</text>
  <!-- Day2 阴线（高开低走，深入内部） -->
  <rect x="55" y="45" width="28" height="65" rx="2" fill="#639922" opacity="0.85"/>
  <line x1="74" y1="40" x2="74" y2="115" stroke="#27500A" stroke-width="1.2"/>
  <text x="74" y="130" text-anchor="middle" font-size="8" fill="#27500A">阴线深入50%+</text>
  <!-- 中点线 -->
  <line x1="95" y1="77" x2="115" y2="77" stroke="#BA7517" stroke-width="0.8" stroke-dasharray="4,2"/>
  <text x="118" y="81" font-size="8" fill="#BA7517">Day1中点</text>
  <text x="150" y="185" text-anchor="middle" font-size="11" font-weight="600" fill="#639922">见顶信号</text>
</svg>

- **特征**：阳线后高开，阴线收盘深入阳线实体内部（超过50%）
- **位置**：上涨趋势末端
- **画面感**：阳线（晴天）之后，第二天阴线高开低走，收盘深深扎入阳线实体内部，像乌云盖住了太阳。多头试图继续冲高，但卖方在中途强力介入。
- **强度**：★★★★☆

### 刺透形态 - 底部反转

<svg viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg" style="max-width:300px">
  <text x="150" y="20" text-anchor="middle" font-size="12" font-weight="600" fill="#A32D2D">刺透形态（底部反转）</text>
  <!-- Day1 阴线 -->
  <rect x="60" y="35" width="28" height="65" rx="2" fill="#639922"/>
  <line x1="74" y1="30" x2="74" y2="105" stroke="#27500A" stroke-width="1.2"/>
  <text x="74" y="120" text-anchor="middle" font-size="9" fill="#27500A">Day1 阴线</text>
  <!-- Day2 阳线（低开高走，刺入内部） -->
  <rect x="55" y="35" width="28" height="70" rx="2" fill="#E24B4A" opacity="0.85"/>
  <line x1="74" y1="30" x2="74" y2="115" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="74" y="130" text-anchor="middle" font-size="8" fill="#A32D2D">阳线刺入50%+</text>
  <!-- 中点线 -->
  <line x1="95" y1="77" x2="115" y2="77" stroke="#BA7517" stroke-width="0.8" stroke-dasharray="4,2"/>
  <text x="118" y="81" font-size="8" fill="#BA7517">Day1中点</text>
  <text x="150" y="185" text-anchor="middle" font-size="11" font-weight="600" fill="#E24B4A">见底信号</text>
</svg>

- **特征**：阴线后低开，阳线收盘深入阴线实体内部（超过50%）
- **位置**：下跌趋势末端
- **画面感**：与乌云盖顶互为"镜像"——阴线（黑暗）后阳线刺入，像阳光穿透乌云。
- **强度**：★★★★☆

> 刺透形态和乌云盖顶是镜像关系：一个是阴线后阳线刺入（看涨），一个是阳线后阴线盖顶（看跌）。

---

## 五、三根K线组合

三根K线组合是技术分析中**最经典、最可靠**的信号。三根K线构成了一个完整的故事。

### 早晨之星 - 底部反转 ★★★★★

<svg viewBox="0 0 400 220" xmlns="http://www.w3.org/2000/svg" style="max-width:400px">
  <text x="200" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#A32D2D">早晨之星（底部反转）</text>
  <!-- Day1 大阴线 -->
  <rect x="50" y="35" width="30" height="60" rx="2" fill="#639922"/>
  <line x1="65" y1="30" x2="65" y2="100" stroke="#27500A" stroke-width="1.2"/>
  <text x="65" y="115" text-anchor="middle" font-size="9" fill="#27500A">Day1 大阴线</text>
  <!-- 跳空指示 -->
  <line x1="82" y1="55" x2="95" y2="55" stroke="#5F5E5A" stroke-width="0.5" stroke-dasharray="2,1"/>
  <text x="98" y="59" font-size="7" fill="#5F5E5A">跳空低开</text>
  <!-- Day2 小K线/十字星 -->
  <rect x="105" y="70" width="14" height="8" rx="1" fill="#444441"/>
  <line x1="112" y1="62" x2="112" y2="85" stroke="#5F5E5A" stroke-width="1"/>
  <text x="112" y="110" text-anchor="middle" font-size="8" fill="#5F5E5A">Day2 跳空低开</text>
  <!-- 跳空指示 -->
  <line x1="127" y1="75" x2="140" y2="75" stroke="#5F5E5A" stroke-width="0.5" stroke-dasharray="2,1"/>
  <text x="143" y="79" font-size="7" fill="#5F5E5A">跳空高开</text>
  <!-- Day3 大阳线 -->
  <rect x="155" y="35" width="45" height="60" rx="2" fill="#E24B4A" opacity="0.9"/>
  <line x1="177" y1="30" x2="177" y2="100" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="177" y="115" text-anchor="middle" font-size="9" fill="#A32D2D">Day3 大阳线</text>
  <!-- 三部曲文字 -->
  <text x="65" y="140" text-anchor="middle" font-size="8" fill="#27500A">空头大胜</text>
  <text x="112" y="140" text-anchor="middle" font-size="8" fill="#5F5E5A">多空犹豫</text>
  <text x="177" y="140" text-anchor="middle" font-size="8" fill="#A32D2D">多头大反攻</text>
  <path d="M200 165 L200 178 M195 173 L200 178 L205 173" stroke="#E24B4A" stroke-width="1.5" fill="none"/>
  <text x="200" y="195" text-anchor="middle" font-size="11" font-weight="600" fill="#E24B4A">黑暗中看到曙光</text>
</svg>

**三部曲故事：**

| 阶段 | K线 | 市场 |
|-----|-----|------|
| Day1 | 大阴线 | 空头大胜，市场一片恐慌 |
| Day2 | 小K线/十字星 | 多空犹豫，市场"停滞"（跳空低开）|
| Day3 | 大阳线 | 多头大反攻，买方重新掌控（跳空高开）|

- **画面感**：就像漫长黑夜（下跌）后，天色变亮（Day2的小K线），然后太阳升起（Day3大阳线）
- **识别要点**：Day2实体越小越好（十字星最优）；Day3阳线收盘至少深入Day1实体上半部
- **强度**：★★★★★（最强反转信号之一）

### 黄昏之星 - 顶部反转 ★★★★★

<svg viewBox="0 0 400 220" xmlns="http://www.w3.org/2000/svg" style="max-width:400px">
  <text x="200" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#27500A">黄昏之星（顶部反转）</text>
  <!-- Day1 大阳线 -->
  <rect x="155" y="35" width="45" height="60" rx="2" fill="#E24B4A" opacity="0.9"/>
  <line x1="177" y1="30" x2="177" y2="100" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="177" y="115" text-anchor="middle" font-size="9" fill="#A32D2D">Day1 大阳线</text>
  <!-- 跳空指示 -->
  <line x1="197" y1="55" x2="210" y2="55" stroke="#5F5E5A" stroke-width="0.5" stroke-dasharray="2,1"/>
  <text x="213" y="59" font-size="7" fill="#5F5E5A">跳空高开</text>
  <!-- Day2 小K线 -->
  <rect x="230" y="45" width="14" height="8" rx="1" fill="#444441"/>
  <line x1="237" y1="37" x2="237" y2="60" stroke="#5F5E5A" stroke-width="1"/>
  <text x="237" y="110" text-anchor="middle" font-size="8" fill="#5F5E5A">Day2 跳空高开</text>
  <!-- 跳空指示 -->
  <line x1="247" y1="52" x2="260" y2="52" stroke="#5F5E5A" stroke-width="0.5" stroke-dasharray="2,1"/>
  <text x="263" y="56" font-size="7" fill="#5F5E5A">跳空低开</text>
  <!-- Day3 大阴线 -->
  <rect x="290" y="35" width="45" height="60" rx="2" fill="#639922" opacity="0.9"/>
  <line x1="312" y1="30" x2="312" y2="100" stroke="#27500A" stroke-width="1.2"/>
  <text x="312" y="115" text-anchor="middle" font-size="9" fill="#27500A">Day3 大阴线</text>
  <!-- 三部曲文字 -->
  <text x="177" y="140" text-anchor="middle" font-size="8" fill="#A32D2D">多头大胜</text>
  <text x="237" y="140" text-anchor="middle" font-size="8" fill="#5F5E5A">多头涨不动</text>
  <text x="312" y="140" text-anchor="middle" font-size="8" fill="#27500A">空头大反击</text>
  <text x="200" y="185" text-anchor="middle" font-size="11" font-weight="600" fill="#639922">太阳落山了</text>
</svg>

- **画面感**：和早晨之星完全对称。太阳落山前最后的余晖（Day2），然后天色变暗（Day3大阴线）
- **识别要点**：与早晨之星完全对称；Day2是十字星时信号更强（"十字黄昏之星"）；配合天量见顶，准确率极高
- **强度**：★★★★★

### 三白兵（三连阳）- 底部反转 ★★★★★

<svg viewBox="0 0 320 130" xmlns="http://www.w3.org/2000/svg" style="max-width:320px">
  <text x="160" y="18" text-anchor="middle" font-size="11" font-weight="600" fill="#A32D2D">三白兵</text>
  <rect x="20" y="35" width="24" height="40" rx="2" fill="#E24B4A"/>
  <line x1="32" y1="30" x2="32" y2="80" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="32" y="98" text-anchor="middle" font-size="8" fill="#A32D2D">Day1</text>
  <rect x="85" y="25" width="24" height="50" rx="2" fill="#E24B4A"/>
  <line x1="97" y1="20" x2="97" y2="80" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="97" y="98" text-anchor="middle" font-size="8" fill="#A32D2D">Day2</text>
  <rect x="155" y="15" width="24" height="60" rx="2" fill="#E24B4A"/>
  <line x1="167" y1="10" x2="167" y2="80" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="167" y="98" text-anchor="middle" font-size="8" fill="#A32D2D">Day3</text>
  <!-- 递进箭头 -->
  <path d="M45 55 L75 45" stroke="#A32D2D" stroke-width="1" fill="none" marker-end="url(#arrow)"/>
  <path d="M110 45 L145 35" stroke="#A32D2D" stroke-width="1" fill="none" marker-end="url(#arrow)"/>
  <text x="65" y="40" text-anchor="middle" font-size="7" fill="#A32D2D">创新高</text>
  <text x="140" y="28" text-anchor="middle" font-size="7" fill="#A32D2D">创新高</text>
  <text x="160" y="120" text-anchor="middle" font-size="9" fill="#A32D2D">每根实体递增，收盘创新高</text>
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round"/>
    </marker>
  </defs>
</svg>

- **特征**：连续三根阳线，每根开盘在前根实体内，收盘创新高
- **位置**：下跌趋势末端或盘整突破
- **注意**：如果三根阳线越来越短（上涨乏力），反而要小心"多头衰竭"。标准的三白兵应该越涨越有力
- **强度**：★★★★★

### 三只乌鸦（三连阴）- 顶部反转 ★★★★★

<svg viewBox="0 0 320 130" xmlns="http://www.w3.org/2000/svg" style="max-width:320px">
  <text x="160" y="18" text-anchor="middle" font-size="11" font-weight="600" fill="#27500A">三只乌鸦</text>
  <rect x="20" y="15" width="24" height="40" rx="2" fill="#639922"/>
  <line x1="32" y1="10" x2="32" y2="60" stroke="#27500A" stroke-width="1.2"/>
  <text x="32" y="78" text-anchor="middle" font-size="8" fill="#27500A">Day1</text>
  <rect x="85" y="25" width="24" height="50" rx="2" fill="#639922"/>
  <line x1="97" y1="20" x2="97" y2="80" stroke="#27500A" stroke-width="1.2"/>
  <text x="97" y="98" text-anchor="middle" font-size="8" fill="#27500A">Day2</text>
  <rect x="155" y="35" width="24" height="60" rx="2" fill="#639922"/>
  <line x1="167" y1="30" x2="167" y2="100" stroke="#27500A" stroke-width="1.2"/>
  <text x="167" y="118" text-anchor="middle" font-size="8" fill="#27500A">Day3</text>
  <text x="160" y="130" text-anchor="middle" font-size="9" fill="#27500A">每根实体递增，收盘创新低</text>
</svg>

- **特征**：连续三根阴线，每根开盘在前根实体内，收盘创新低
- **位置**：上涨趋势末端
- **强度**：★★★★★

---

## 六、多K线反转图形

由多根K线组成的"地形图"。需要更长时间形成，信号更可靠，但需要**耐心等待**。

### 头肩顶 - 顶部反转 ★★★★★

<svg viewBox="0 0 480 200" xmlns="http://www.w3.org/2000/svg" style="max-width:480px">
  <text x="240" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#27500A">头肩顶</text>
  <!-- 价格走势 -->
  <polyline points="30,120 80,90 130,130 200,50 270,120 340,80 390,130 440,160"
            fill="none" stroke="#5F5E5A" stroke-width="1.5"/>
  <!-- 标记各点 -->
  <circle cx="80" cy="90" r="4" fill="#5F5E5A"/>
  <circle cx="200" cy="50" r="5" fill="#A32D2D"/>
  <circle cx="340" cy="80" r="4" fill="#5F5E5A"/>
  <!-- 标签 -->
  <text x="80" y="82" text-anchor="middle" font-size="9" fill="#5F5E5A">左肩</text>
  <text x="200" y="42" text-anchor="middle" font-size="10" font-weight="600" fill="#A32D2D">头(最高点)</text>
  <text x="340" y="72" text-anchor="middle" font-size="9" fill="#5F5E5A">右肩</text>
  <!-- 回调低点 -->
  <circle cx="130" cy="130" r="3" fill="#185FA5"/>
  <circle cx="270" cy="120" r="3" fill="#185FA5"/>
  <!-- 颈线 -->
  <line x1="130" y1="125" x2="400" y2="125" stroke="#185FA5" stroke-width="1" stroke-dasharray="5,3"/>
  <text x="130" y="143" font-size="9" fill="#185FA5">颈线</text>
  <text x="130" y="156" font-size="8" fill="#185FA5">(连接两次回调低点)</text>
  <!-- 跌破箭头 -->
  <path d="M370 135 L370 155 M365 148 L370 153 L375 148" stroke="#639922" stroke-width="1.5" fill="none"/>
  <text x="370" y="175" text-anchor="middle" font-size="9" font-weight="600" fill="#639922">跌破颈线→看跌</text>
  <text x="370" y="190" text-anchor="middle" font-size="8" fill="#27500A">跌幅≥头顶到颈线距离</text>
</svg>

- **特征**：左肩（第一波高点）→ 回调 → 头（冲到更高点）→ 回调 → 右肩（再冲一次但高度不如头）
- **为什么会形成**：第一次冲高（左肩），多头很兴奋。第二次冲得更高（头），但已有买方获利了结。第三次再冲（右肩），买方力量明显不足——"三鼓而竭"
- **颈线**：连接两次回调低点的水平线。**跌破颈线 = 形态确认**
- **量度目标**：从头顶到颈线的距离 = 跌破颈线后至少的下跌空间
- **要点**：右肩是最后逃跑机会；不跌破颈线就不是头肩顶（可能只是整理）
- **强度**：★★★★★

### 头肩底 - 底部反转 ★★★★★

<svg viewBox="0 0 480 200" xmlns="http://www.w3.org/2000/svg" style="max-width:480px">
  <text x="240" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#A32D2D">头肩底</text>
  <!-- 价格走势（倒置） -->
  <polyline points="30,80 80,110 130,70 200,150 270,80 340,120 390,70 440,40"
            fill="none" stroke="#5F5E5A" stroke-width="1.5"/>
  <circle cx="80" cy="110" r="4" fill="#5F5E5A"/>
  <circle cx="200" cy="150" r="5" fill="#A32D2D"/>
  <circle cx="340" cy="120" r="4" fill="#5F5E5A"/>
  <text x="80" y="128" text-anchor="middle" font-size="9" fill="#5F5E5A">左肩</text>
  <text x="200" y="168" text-anchor="middle" font-size="10" font-weight="600" fill="#A32D2D">头(最低点)</text>
  <text x="340" y="148" text-anchor="middle" font-size="9" fill="#5F5E5A">右肩</text>
  <!-- 反弹高点 -->
  <circle cx="130" cy="70" r="3" fill="#185FA5"/>
  <circle cx="270" cy="80" r="3" fill="#185FA5"/>
  <!-- 颈线 -->
  <line x1="130" y1="75" x2="400" y2="75" stroke="#185FA5" stroke-width="1" stroke-dasharray="5,3"/>
  <text x="130" y="68" font-size="9" fill="#185FA5">颈线</text>
  <!-- 突破箭头 -->
  <path d="M370 60 L370 40 M365 52 L370 47 L375 52" stroke="#E24B4A" stroke-width="1.5" fill="none"/>
  <text x="370" y="30" text-anchor="middle" font-size="9" font-weight="600" fill="#E24B4A">突破颈线→看涨</text>
  <text x="370" y="15" text-anchor="middle" font-size="8" fill="#A32D2D">涨幅≥头到颈线距离</text>
</svg>

- **特征**：头肩顶的"倒影"。两个谷底中间一个更深的谷底
- **确认**：突破颈线，目标涨幅 = 头到颈线距离
- **要点**：突破时**必须放量**，否则可能是假突破
- **强度**：★★★★★

### 双底（W底）- 底部反转 ★★★★☆

<svg viewBox="0 0 400 160" xmlns="http://www.w3.org/2000/svg" style="max-width:400px">
  <text x="200" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#A32D2D">双底（W底）</text>
  <polyline points="30,50 100,130 180,60 260,130 330,50"
            fill="none" stroke="#5F5E5A" stroke-width="1.5"/>
  <circle cx="100" cy="130" r="4" fill="#A32D2D"/>
  <circle cx="260" cy="130" r="4" fill="#A32D2D"/>
  <circle cx="180" cy="60" r="4" fill="#185FA5"/>
  <text x="100" y="148" text-anchor="middle" font-size="9" fill="#A32D2D">底1</text>
  <text x="260" y="148" text-anchor="middle" font-size="9" fill="#A32D2D">底2</text>
  <text x="180" y="52" text-anchor="middle" font-size="9" fill="#185FA5">反弹高点</text>
  <!-- 颈线 -->
  <line x1="180" y1="55" x2="380" y2="55" stroke="#185FA5" stroke-width="1" stroke-dasharray="5,3"/>
  <text x="180" y="46" font-size="9" fill="#185FA5">颈线</text>
  <!-- 突破箭头 -->
  <path d="M380 45 L400 25" stroke="#E24B4A" stroke-width="1.5" fill="none" marker-end="url(#arrw)"/>
  <text x="380" y="18" text-anchor="end" font-size="9" font-weight="600" fill="#E24B4A">突破→看涨</text>
  <defs>
    <marker id="arrw" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5"/>
    </marker>
  </defs>
</svg>

- **特征**：两次跌到差不多同一个价位都被买方接住，中间有反弹
- **确认**：突破中间反弹的高点（颈线）
- **要点**：第二个底可以略高（更标准）或略低，关键是两个极端价位"差不多"
- **强度**：★★★★☆

### 双顶（M顶）- 顶部反转 ★★★★☆

<svg viewBox="0 0 400 160" xmlns="http://www.w3.org/2000/svg" style="max-width:400px">
  <text x="200" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#27500A">双顶（M顶）</text>
  <polyline points="30,130 100,50 180,120 260,50 330,130"
            fill="none" stroke="#5F5E5A" stroke-width="1.5"/>
  <circle cx="100" cy="50" r="4" fill="#27500A"/>
  <circle cx="260" cy="50" r="4" fill="#27500A"/>
  <circle cx="180" cy="120" r="4" fill="#185FA5"/>
  <text x="100" y="42" text-anchor="middle" font-size="9" fill="#27500A">顶1</text>
  <text x="260" y="42" text-anchor="middle" font-size="9" fill="#27500A">顶2</text>
  <text x="180" y="132" text-anchor="middle" font-size="9" fill="#185FA5">回调低点</text>
  <!-- 颈线 -->
  <line x1="180" y1="115" x2="380" y2="115" stroke="#185FA5" stroke-width="1" stroke-dasharray="5,3"/>
  <text x="180" y="112" font-size="9" fill="#185FA5">颈线</text>
  <!-- 跌破箭头 -->
  <path d="M380 125 L400 145" stroke="#639922" stroke-width="1.5" fill="none" marker-end="url(#arrw2)"/>
  <text x="380" y="150" text-anchor="end" font-size="9" font-weight="600" fill="#639922">跌破→看跌</text>
  <defs>
    <marker id="arrw2" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="5" markerHeight="5" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5"/>
    </marker>
  </defs>
</svg>

- **特征**：两次冲到差不多同一个高度都被卖方砸回来，中间有回调
- **确认**：跌破中间回调的低点（颈线）
- **强度**：★★★★☆

### 三重底/顶

- **特征**：双底/双顶的变体，三个低点/高点相近
- **含义**：比双底/双顶更扎实的反转信号
- **强度**：★★★★★

---

## 七、整理形态中继

股价"歇脚"的地方。整理完成后通常会继续原来的方向，但也可能反方向突破——**必须等确认**。

### 箱体整理（矩形通道）

<svg viewBox="0 0 400 160" xmlns="http://www.w3.org/2000/svg" style="max-width:400px">
  <text x="200" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#5F5E5A">箱体整理</text>
  <!-- 箱体 -->
  <line x1="30" y1="50" x2="380" y2="50" stroke="#A32D2D" stroke-width="1.2"/>
  <text x="35" y="44" font-size="9" fill="#A32D2D">上沿（压力）</text>
  <line x1="30" y1="130" x2="380" y2="130" stroke="#27500A" stroke-width="1.2"/>
  <text x="35" y="144" font-size="9" fill="#27500A">下沿（支撑）</text>
  <!-- 价格震荡 -->
  <polyline points="50,120 90,70 130,110 170,65 210,100 250,75 290,110 340,80"
            fill="none" stroke="#378ADD" stroke-width="1.2"/>
  <!-- 操作提示 -->
  <text x="200" y="170" text-anchor="middle" font-size="9" fill="#5F5E5A">下沿附近考虑买入，上沿附近考虑卖出</text>
  <text x="200" y="185" text-anchor="middle" font-size="9" fill="#185FA5">向上突破上沿→买点 | 向下跌破下沿→卖点</text>
</svg>

- **特征**：价格在水平通道内来回波动
- **策略**：下沿附近买入、上沿附近卖出（高抛低吸）；突破上沿→买点；跌破下沿→卖点

### 三角形整理

<svg viewBox="0 0 480 180" xmlns="http://www.w3.org/2000/svg" style="max-width:480px">
  <text x="240" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#5F5E5A">三角形整理</text>
  <!-- 上升三角形 -->
  <text x="70" y="42" text-anchor="middle" font-size="10" font-weight="500" fill="#A32D2D">上升三角形</text>
  <line x1="20" y1="55" x2="120" y2="55" stroke="#A32D2D" stroke-width="1" stroke-dasharray="4,2"/>
  <text x="25" y="50" font-size="8" fill="#A32D2D">上沿水平</text>
  <line x1="25" y1="140" x2="130" y2="60" stroke="#27500A" stroke-width="1" stroke-dasharray="4,2"/>
  <text x="25" y="155" font-size="8" fill="#27500A">下沿上升</text>
  <polyline points="20,135 45,80 70,125 95,75 120,110" fill="none" stroke="#5F5E5A" stroke-width="1"/>
  <text x="70" y="170" text-anchor="middle" font-size="8" fill="#E24B4A">通常向上突破</text>
  <!-- 下降三角形 -->
  <text x="240" y="42" text-anchor="middle" font-size="10" font-weight="500" fill="#27500A">下降三角形</text>
  <line x1="190" y1="60" x2="300" y2="140" stroke="#A32D2D" stroke-width="1" stroke-dasharray="4,2"/>
  <text x="280" y="155" font-size="8" fill="#A32D2D">上沿下降</text>
  <line x1="190" y1="140" x2="300" y2="140" stroke="#27500A" stroke-width="1" stroke-dasharray="4,2"/>
  <text x="195" y="135" font-size="8" fill="#27500A">下沿水平</text>
  <polyline points="190,70 215,125 240,85 265,120 290,95" fill="none" stroke="#5F5E5A" stroke-width="1"/>
  <text x="240" y="170" text-anchor="middle" font-size="8" fill="#639922">通常向下跌破</text>
  <!-- 对称三角形 -->
  <text x="400" y="42" text-anchor="middle" font-size="10" font-weight="500" fill="#185FA5">对称三角形</text>
  <line x1="350" y1="60" x2="460" y2="140" stroke="#A32D2D" stroke-width="1" stroke-dasharray="4,2"/>
  <line x1="350" y1="140" x2="460" y2="60" stroke="#27500A" stroke-width="1" stroke-dasharray="4,2"/>
  <polyline points="350,125 370,85 390,115 410,90 430,110" fill="none" stroke="#5F5E5A" stroke-width="1"/>
  <text x="400" y="170" text-anchor="middle" font-size="8" fill="#185FA5">方向不确定,等突破</text>
</svg>

| 类型 | 特征 | 通常方向 |
|-----|------|---------|
| **上升三角形** | 上沿水平，下沿上升 | 向上突破概率大 |
| **下降三角形** | 上沿下降，下沿水平 | 向下跌破概率大 |
| **对称三角形** | 上下沿均收敛 | 不确定，等突破确认 |

> **突破位置**：三角形越往后突破，信号越弱。在三角形前半段（1/2~3/4处）突破最可靠。

### 旗形整理

<svg viewBox="0 0 400 180" xmlns="http://www.w3.org/2000/svg" style="max-width:400px">
  <text x="200" y="20" text-anchor="middle" font-size="13" font-weight="600" fill="#5F5E5A">旗形整理</text>
  <!-- 上升旗形 -->
  <text x="100" y="42" text-anchor="middle" font-size="10" font-weight="500" fill="#A32D2D">上升旗形</text>
  <!-- 旗杆 -->
  <line x1="50" y1="50" x2="50" y2="5" stroke="#E24B4A" stroke-width="2"/>
  <text x="50" y="2" text-anchor="middle" font-size="8" fill="#E24B4A">旗杆(急涨)</text>
  <!-- 旗面 -->
  <line x1="50" y1="50" x2="120" y2="70" stroke="#A32D2D" stroke-width="0.8" stroke-dasharray="3,2"/>
  <line x1="50" y1="80" x2="120" y2="100" stroke="#A32D2D" stroke-width="0.8" stroke-dasharray="3,2"/>
  <text x="85" y="120" text-anchor="middle" font-size="8" fill="#A32D2D">旗面(回调)</text>
  <!-- 突破 -->
  <line x1="120" y1="60" x2="120" y2="5" stroke="#E24B4A" stroke-width="2"/>
  <text x="120" y="2" text-anchor="middle" font-size="8" fill="#E24B4A">继续上涨</text>
  <!-- 下降旗形 -->
  <text x="320" y="42" text-anchor="middle" font-size="10" font-weight="500" fill="#27500A">下降旗形</text>
  <line x1="270" y1="5" x2="270" y2="50" stroke="#639922" stroke-width="2"/>
  <text x="310" y="2" text-anchor="middle" font-size="8" fill="#639922">旗杆(急跌)</text>
  <line x1="270" y1="50" x2="340" y2="30" stroke="#27500A" stroke-width="0.8" stroke-dasharray="3,2"/>
  <line x1="270" y1="80" x2="340" y2="60" stroke="#27500A" stroke-width="0.8" stroke-dasharray="3,2"/>
  <text x="305" y="120" text-anchor="middle" font-size="8" fill="#27500A">旗面(反弹)</text>
  <line x1="340" y1="40" x2="340" y2="130" stroke="#639922" stroke-width="2"/>
  <text x="310" y="155" text-anchor="middle" font-size="8" fill="#639922">继续下跌</text>
</svg>

- **特征**：急涨/急跌后，出现与趋势相反的整理
- **画面感**：就像一面旗帜插在旗杆上——旗杆是之前的急涨/急跌，旗面是短暂的休息
- **要点**：旗形是最可靠的中继形态，整理时间通常不超过3周
- **强度**：★★★★☆

---

## 八、缺口形态

K线图上两个交易日之间出现的"空白区域"——当天的最低价高于前一天的最高价（向上缺口），或最高价低于前一天的最低价（向下缺口）。

| 缺口类型 | 出现位置 | 成交量 | 含义 |
|---------|---------|--------|------|
| **突破缺口** | 突破关键位（压力/支撑） | 放大 | 新趋势开始，信号最强 |
| **中继缺口** | 趋势中途 | 温和 | 趋势延续，可用它估算趋势终点 |
| **衰竭缺口** | 趋势末端 | 萎缩 | 最后一搏，趋势即将反转 |
| **普通缺口** | 盘整中 | 无规律 | 几天内就会被回补，无特殊含义 |

### 缺口定律

> ① 突破缺口通常不会被回补
> ② 普通缺口通常3天内回补
> ③ 三个缺口理论：一段趋势中如果出现第三个缺口，大概率是衰竭缺口，要小心反转

> 缺口也是支撑/压力：向上缺口形成后成为支撑位，向下缺口形成后成为压力位。

---

## 九、实战应用要点

### 1. 形态识别优先级（从高到低）

```
大周期形态（周线/月线） > 小周期形态（日线）
多根K线组合 > 单根K线形态
颈线突破确认 > 形态初步形成
放量确认 > 缩量形态
```

### 2. 成交量配合

| 形态类型 | 成交量要求 | 原因 |
|---------|-----------|------|
| 底部反转 | **放量**突破颈线 | 放量说明真金白银在进场 |
| 顶部反转 | 可缩量也可放量 | 放量=恐慌抛售；缩量=买方撤离 |
| 上升中继 | 缩量回调，放量突破 | 回调缩量=卖方不积极；突破放量=买方回来了 |
| 下降中继 | 缩量反弹，放量跌破 | 反弹缩量=买方无力；跌破放量=卖方加速 |

### 3. 止损设置参考

```
头肩顶/底：颈线位置 ± 3%
双底/双顶：颈线位置 ± 3%
箱体突破：箱体边界 ± 2%
单根形态：形态最低/最高价 ± 1%
```

### 4. 形态失败

> **真相：约30%的形态会失败。** 没有任何形态是100%可靠的。
>
> 应对策略：
> ① 永远设止损
> ② 等确认再入场（不要"猜"形态）
> ③ 多个信号共振时才出手
> ④ 形态失败本身就是新信号（假突破往往预示反向运动）

---

## 十、快速识别清单

### 底部反转信号组合

- [ ] 出现在明确的下跌趋势末端（不是半山腰）
- [ ] 出现锤子线/倒锤子/看涨吞没等底部形态
- [ ] 成交量放大（至少比前5日平均高50%）
- [ ] 次日阳线确认（收盘高于形态高点）

### 顶部反转信号组合

- [ ] 出现在明确的上涨趋势末端
- [ ] 出现上吊线/流星线/看跌吞没等顶部形态
- [ ] 成交量萎缩（买方不积极）或异常放大（恐慌抛售）
- [ ] 次日阴线确认（收盘低于形态低点）

### 趋势延续信号

- [ ] 上升旗形向上突破（伴随放量）
- [ ] 下降旗形向下跌破
- [ ] 上升三角形向上突破
- [ ] 缺口未回补（特别是突破缺口）

---

## 十一、形态强度速查表

| 形态 | 类型 | 强度 | 参考胜率 | 备注 |
|-----|------|------|---------|------|
| 早晨/黄昏之星 | 三根反转 | ★★★★★ | 70%+ | 需确认K线 |
| 头肩顶/底 | 图形反转 | ★★★★★ | 75%+ | 需突破颈线 |
| 三白兵/三乌鸦 | 三根反转 | ★★★★★ | 70%+ | 标准形态最可靠 |
| 吞没形态 | 双根反转 | ★★★★☆ | 60%+ | 阳/阴线越大越好 |
| 双底/双顶 | 图形反转 | ★★★★☆ | 65%+ | 第二底/顶可略偏 |
| 乌云盖顶/刺透 | 双根反转 | ★★★★☆ | 60%+ | 深入50%+更可靠 |
| 旗形整理 | 中继 | ★★★★☆ | 65%+ | 整理不超过3周 |
| 箱体突破 | 中继/反转 | ★★★☆☆ | 55%+ | 需放量确认 |
| 锤子/上吊线 | 单根反转 | ★★★☆☆ | 50%+ | 必须等确认 |
| 十字星 | 变盘信号 | ★★☆☆☆ | 不定 | 位置决定一切 |

---

*本手册将随学习深入持续更新。v2.1 内嵌SVG图示版*
