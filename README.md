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
 
### :small_blue_diamond: **有興趣的資料不只有產品間的資訊，由User Profile 探勘顧客的基本資料。在給定Minimum Support = 0.05 且Minimum Confidence = 0.9 的條件下，探勘Foodmart 顧客基本資料的屬性 {customer_state_province, yearly_income, gender, total_children, num_children_at_home, education, occupation, homeowner} 間的 Association Rules.**
- 
    1. 選擇感興趣的顧客基本屬性:
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>customer_state_province</th>
      <th>yearly_income</th>
      <th>gender</th>
      <th>total_children</th>
      <th>num_children_at_home</th>
      <th>education</th>
      <th>occupation</th>
      <th>homeowner</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Oaxaca</td>
      <td>$30K - $50K</td>
      <td>F</td>
      <td>4</td>
      <td>2</td>
      <td>Partial High School</td>
      <td>Skilled Manual</td>
      <td>Y</td>
    </tr>
    <tr>
      <th>1</th>
      <td>BC</td>
      <td>$70K - $90K</td>
      <td>M</td>
      <td>1</td>
      <td>0</td>
      <td>Partial High School</td>
      <td>Professional</td>
      <td>N</td>
    </tr>
    <tr>
      <th>2</th>
      <td>WA</td>
      <td>$50K - $70K</td>
      <td>F</td>
      <td>1</td>
      <td>1</td>
      <td>Bachelors Degree</td>
      <td>Professional</td>
      <td>Y</td>
    </tr>
    <tr>
      <th>3</th>
      <td>BC</td>
      <td>$10K - $30K</td>
      <td>M</td>
      <td>4</td>
      <td>4</td>
      <td>Partial High School</td>
      <td>Skilled Manual</td>
      <td>N</td>
    </tr>
    <tr>
      <th>4</th>
      <td>CA</td>
      <td>$30K - $50K</td>
      <td>F</td>
      <td>3</td>
      <td>0</td>
      <td>Partial College</td>
      <td>Manual</td>
      <td>N</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>10276</th>
      <td>OR</td>
      <td>$90K - $110K</td>
      <td>M</td>
      <td>4</td>
      <td>3</td>
      <td>Partial High School</td>
      <td>Management</td>
      <td>N</td>
    </tr>
    <tr>
      <th>10277</th>
      <td>BC</td>
      <td>$30K - $50K</td>
      <td>F</td>
      <td>0</td>
      <td>0</td>
      <td>Partial College</td>
      <td>Professional</td>
      <td>N</td>
    </tr>
    <tr>
      <th>10278</th>
      <td>CA</td>
      <td>$130K - $150K</td>
      <td>M</td>
      <td>3</td>
      <td>0</td>
      <td>Partial High School</td>
      <td>Management</td>
      <td>Y</td>
    </tr>
    <tr>
      <th>10279</th>
      <td>WA</td>
      <td>$150K +</td>
      <td>F</td>
      <td>5</td>
      <td>2</td>
      <td>High School Degree</td>
      <td>Professional</td>
      <td>Y</td>
    </tr>
    <tr>
      <th>10280</th>
      <td>BC</td>
      <td>$50K - $70K</td>
      <td>F</td>
      <td>5</td>
      <td>0</td>
      <td>Bachelors Degree</td>
      <td>Management</td>
      <td>N</td>
    </tr>
  </tbody>
</table>
</div>
    
2. 進行one-hot編碼
3. 使用關聯規則挖掘, metric="confidence", min_threshold=0.9
4. Top 10 Association Rules:
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
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
      <th>0</th>
      <td>(yearly_income_$10K - $30K)</td>
      <td>(education_Partial High School)</td>
      <td>0.216127</td>
      <td>0.300943</td>
      <td>0.200564</td>
      <td>0.927993</td>
      <td>3.083611</td>
      <td>0.135522</td>
      <td>9.708147</td>
      <td>0.862008</td>
    </tr>
    <tr>
      <th>1</th>
      <td>(total_children_0)</td>
      <td>(num_children_at_home_0)</td>
      <td>0.100963</td>
      <td>0.628052</td>
      <td>0.100963</td>
      <td>1.000000</td>
      <td>1.592225</td>
      <td>0.037553</td>
      <td>inf</td>
      <td>0.413718</td>
    </tr>
    <tr>
      <th>2</th>
      <td>(yearly_income_$10K - $30K, customer_state_pro...</td>
      <td>(education_Partial High School)</td>
      <td>0.089875</td>
      <td>0.300943</td>
      <td>0.083455</td>
      <td>0.928571</td>
      <td>3.085534</td>
      <td>0.056408</td>
      <td>9.786791</td>
      <td>0.742653</td>
    </tr>
    <tr>
      <th>3</th>
      <td>(gender_F, yearly_income_$10K - $30K)</td>
      <td>(education_Partial High School)</td>
      <td>0.107869</td>
      <td>0.300943</td>
      <td>0.099698</td>
      <td>0.924256</td>
      <td>3.071195</td>
      <td>0.067236</td>
      <td>9.229210</td>
      <td>0.755936</td>
    </tr>
    <tr>
      <th>4</th>
      <td>(yearly_income_$10K - $30K, gender_M)</td>
      <td>(education_Partial High School)</td>
      <td>0.108258</td>
      <td>0.300943</td>
      <td>0.100866</td>
      <td>0.931716</td>
      <td>3.095984</td>
      <td>0.068286</td>
      <td>10.237499</td>
      <td>0.759189</td>
    </tr>
    <tr>
      <th>5</th>
      <td>(num_children_at_home_0, yearly_income_$10K - ...</td>
      <td>(education_Partial High School)</td>
      <td>0.134423</td>
      <td>0.300943</td>
      <td>0.125182</td>
      <td>0.931259</td>
      <td>3.094465</td>
      <td>0.084729</td>
      <td>10.169433</td>
      <td>0.781955</td>
    </tr>
    <tr>
      <th>6</th>
      <td>(yearly_income_$10K - $30K, occupation_Manual)</td>
      <td>(education_Partial High School)</td>
      <td>0.105145</td>
      <td>0.300943</td>
      <td>0.101449</td>
      <td>0.964847</td>
      <td>3.206075</td>
      <td>0.069806</td>
      <td>19.886318</td>
      <td>0.768943</td>
    </tr>
    <tr>
      <th>7</th>
      <td>(yearly_income_$10K - $30K, occupation_Skilled...</td>
      <td>(education_Partial High School)</td>
      <td>0.103297</td>
      <td>0.300943</td>
      <td>0.099115</td>
      <td>0.959510</td>
      <td>3.188341</td>
      <td>0.068028</td>
      <td>17.265070</td>
      <td>0.765423</td>
    </tr>
    <tr>
      <th>8</th>
      <td>(yearly_income_$10K - $30K, homeowner_N)</td>
      <td>(education_Partial High School)</td>
      <td>0.092501</td>
      <td>0.300943</td>
      <td>0.084914</td>
      <td>0.917981</td>
      <td>3.050344</td>
      <td>0.057076</td>
      <td>8.523112</td>
      <td>0.740682</td>
    </tr>
    <tr>
      <th>9</th>
      <td>(yearly_income_$10K - $30K, homeowner_Y)</td>
      <td>(education_Partial High School)</td>
      <td>0.123626</td>
      <td>0.300943</td>
      <td>0.115650</td>
      <td>0.935484</td>
      <td>3.108503</td>
      <td>0.078446</td>
      <td>10.835376</td>
      <td>0.773987</td>
    </tr>
  </tbody>
</table>
</div>

    

