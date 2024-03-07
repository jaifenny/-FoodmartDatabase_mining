# Foodmart Database mining
由 Foodmart Database 超級市場的顧客及其交易資料中，探勘 Frequent Itemsets、Association Rules、Quantitative Association Rules.
### :small_blue_diamond: **從Foodmart Data 的交易資料中，探勘符合Minimum Support = 0.00015 且Minimum Confidence = 0.8 的Association Rules，列出 Confidence 最高的前10 條Rules 以及lift 最高的前10 條，比較這兩者的異同。**
- 置信度（confidence）衡量了規則中後項發生的機率，在給定前項已經發生的情況下。 較高的置信度表示規則更可靠。提升度（lift）衡量了規則中前項和後項的關聯程度，與獨立事件的期望相比。 提升度大於1表示前項與後項正相關，提升度小於1表示負相關，提升度等於1表示獨立關係。
- 
    1. ransaction = 37851
    2. 進行one-hot編碼
    3. 使用FP-growth演算法計算頻繁項集, min_support=0.00015
    4. 使用association_rules函數計算關聯規則, metric="confidence", min_threshold=0.8
    5. top_10_confidence_rules:
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>antecedents</th>
      <th>consequents</th>
      <th>antecedent support</th>
      <th>consequent support</th>
      <th>support</th>
      <th>confidence</th>
      <th>lift</th>
      <th>leverage</th>
      <th>conviction</th>
      <th>zhangs_metric</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>(Imagine Low Fat French Fries, CDR Hot Chocolate)</td>
      <td>(Quick Extra Lean Hamburger)</td>
      <td>0.000185</td>
      <td>0.003117</td>
      <td>0.000185</td>
      <td>1.000000</td>
      <td>320.771186</td>
      <td>0.000184</td>
      <td>inf</td>
      <td>0.997067</td>
    </tr>
    <tr>
      <th>14</th>
      <td>(Even Better Sharp Cheddar Cheese, High Top Su...</td>
      <td>(High Top New Potatos)</td>
      <td>0.000159</td>
      <td>0.003725</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>268.446809</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.996433</td>
    </tr>
    <tr>
      <th>6</th>
      <td>(Hilltop 200 MG Acetominifen, Cormorant Scente...</td>
      <td>(Horatio No Salt Popcorn)</td>
      <td>0.000159</td>
      <td>0.003329</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>300.404762</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.996829</td>
    </tr>
    <tr>
      <th>7</th>
      <td>(Plato French Roast Coffee, High Quality Sciss...</td>
      <td>(Dollar Monthly Sports Magazine)</td>
      <td>0.000159</td>
      <td>0.003197</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>312.818182</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.996961</td>
    </tr>
    <tr>
      <th>1</th>
      <td>(Just Right Canned Yams, Hilltop 200 MG Acetom...</td>
      <td>(Faux Products HCL Nasal Spray)</td>
      <td>0.000159</td>
      <td>0.002959</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>337.955357</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.997199</td>
    </tr>
    <tr>
      <th>12</th>
      <td>(Booker Low Fat String Cheese, Bravo Fancy Can...</td>
      <td>(High Top Oranges)</td>
      <td>0.000159</td>
      <td>0.003197</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>312.818182</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.996961</td>
    </tr>
    <tr>
      <th>2</th>
      <td>(Quick Extra Lean Hamburger, CDR Hot Chocolate)</td>
      <td>(Imagine Low Fat French Fries)</td>
      <td>0.000211</td>
      <td>0.002985</td>
      <td>0.000185</td>
      <td>0.875000</td>
      <td>293.094027</td>
      <td>0.000184</td>
      <td>7.976117</td>
      <td>0.996799</td>
    </tr>
    <tr>
      <th>0</th>
      <td>(Just Right Canned Yams, Faux Products HCL Nas...</td>
      <td>(Hilltop 200 MG Acetominifen)</td>
      <td>0.000185</td>
      <td>0.003514</td>
      <td>0.000159</td>
      <td>0.857143</td>
      <td>243.937701</td>
      <td>0.000158</td>
      <td>6.975404</td>
      <td>0.996085</td>
    </tr>
    <tr>
      <th>11</th>
      <td>(High Top Oranges, Booker Low Fat String Cheese)</td>
      <td>(Bravo Fancy Canned Anchovies)</td>
      <td>0.000185</td>
      <td>0.003382</td>
      <td>0.000159</td>
      <td>0.857143</td>
      <td>253.466518</td>
      <td>0.000158</td>
      <td>6.976328</td>
      <td>0.996239</td>
    </tr>
    <tr>
      <th>15</th>
      <td>(Even Better Sharp Cheddar Cheese, High Top Ne...</td>
      <td>(High Top Summer Squash)</td>
      <td>0.000185</td>
      <td>0.003065</td>
      <td>0.000159</td>
      <td>0.857143</td>
      <td>279.687192</td>
      <td>0.000158</td>
      <td>6.978547</td>
      <td>0.996609</td>
    </tr>
  </tbody>
</table>
</div>

6. 使用lift作為度量標準計算關聯規則, top_10_lift_rules:<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>antecedents</th>
      <th>consequents</th>
      <th>antecedent support</th>
      <th>consequent support</th>
      <th>support</th>
      <th>confidence</th>
      <th>lift</th>
      <th>leverage</th>
      <th>conviction</th>
      <th>zhangs_metric</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>236</th>
      <td>(Faux Products HCL Nasal Spray)</td>
      <td>(Just Right Canned Yams, Hilltop 200 MG Acetom...</td>
      <td>0.002959</td>
      <td>0.000159</td>
      <td>0.000159</td>
      <td>0.053571</td>
      <td>337.955357</td>
      <td>0.000158</td>
      <td>1.056436</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>233</th>
      <td>(Just Right Canned Yams, Hilltop 200 MG Acetom...</td>
      <td>(Faux Products HCL Nasal Spray)</td>
      <td>0.000159</td>
      <td>0.002959</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>337.955357</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.997199</td>
    </tr>
    <tr>
      <th>674</th>
      <td>(Imagine Low Fat French Fries, CDR Hot Chocolate)</td>
      <td>(Quick Extra Lean Hamburger)</td>
      <td>0.000185</td>
      <td>0.003117</td>
      <td>0.000185</td>
      <td>1.000000</td>
      <td>320.771186</td>
      <td>0.000184</td>
      <td>inf</td>
      <td>0.997067</td>
    </tr>
    <tr>
      <th>675</th>
      <td>(Quick Extra Lean Hamburger)</td>
      <td>(Imagine Low Fat French Fries, CDR Hot Chocolate)</td>
      <td>0.003117</td>
      <td>0.000185</td>
      <td>0.000185</td>
      <td>0.059322</td>
      <td>320.771186</td>
      <td>0.000184</td>
      <td>1.062866</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>1536</th>
      <td>(Plato French Roast Coffee, High Quality Sciss...</td>
      <td>(Dollar Monthly Sports Magazine)</td>
      <td>0.000159</td>
      <td>0.003197</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>312.818182</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.996961</td>
    </tr>
    <tr>
      <th>2099</th>
      <td>(High Top Oranges)</td>
      <td>(Booker Low Fat String Cheese, Bravo Fancy Can...</td>
      <td>0.003197</td>
      <td>0.000159</td>
      <td>0.000159</td>
      <td>0.049587</td>
      <td>312.818182</td>
      <td>0.000158</td>
      <td>1.052007</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>2098</th>
      <td>(Booker Low Fat String Cheese, Bravo Fancy Can...</td>
      <td>(High Top Oranges)</td>
      <td>0.000159</td>
      <td>0.003197</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>312.818182</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.996961</td>
    </tr>
    <tr>
      <th>1541</th>
      <td>(Dollar Monthly Sports Magazine)</td>
      <td>(Plato French Roast Coffee, High Quality Sciss...</td>
      <td>0.003197</td>
      <td>0.000159</td>
      <td>0.000159</td>
      <td>0.049587</td>
      <td>312.818182</td>
      <td>0.000158</td>
      <td>1.052007</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>1480</th>
      <td>(Hilltop 200 MG Acetominifen, Cormorant Scente...</td>
      <td>(Horatio No Salt Popcorn)</td>
      <td>0.000159</td>
      <td>0.003329</td>
      <td>0.000159</td>
      <td>1.000000</td>
      <td>300.404762</td>
      <td>0.000158</td>
      <td>inf</td>
      <td>0.996829</td>
    </tr>
    <tr>
      <th>1481</th>
      <td>(Horatio No Salt Popcorn)</td>
      <td>(Hilltop 200 MG Acetominifen, Cormorant Scente...</td>
      <td>0.003329</td>
      <td>0.000159</td>
      <td>0.000159</td>
      <td>0.047619</td>
      <td>300.404762</td>
      <td>0.000158</td>
      <td>1.049834</td>
      <td>1.000000</td>
    </tr>
  </tbody>
</table>
</div>

7. rule_comparison: 置信度規則著重於條件_結果的關聯程度，而提升規則則著重於關聯規則相對於隨機關聯的提升程度。
