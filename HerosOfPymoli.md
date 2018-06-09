
# Heroes Of Pymoli Data Analysis


```python
import pandas as pd
```


```python
file = "/Users/roy/Desktop/DACM/Repo/02-Homework/04-Numpy-Pandas/Instructions/HeroesOfPymoli/purchase_data.json"
```


```python
df = pd.read_json(file)
df.head(20)
```




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
      <th>Age</th>
      <th>Gender</th>
      <th>Item ID</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>SN</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>38</td>
      <td>Male</td>
      <td>165</td>
      <td>Bone Crushing Silver Skewer</td>
      <td>3.37</td>
      <td>Aelalis34</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>Male</td>
      <td>119</td>
      <td>Stormbringer, Dark Blade of Ending Misery</td>
      <td>2.32</td>
      <td>Eolo46</td>
    </tr>
    <tr>
      <th>2</th>
      <td>34</td>
      <td>Male</td>
      <td>174</td>
      <td>Primitive Blade</td>
      <td>2.46</td>
      <td>Assastnya25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>Male</td>
      <td>92</td>
      <td>Final Critic</td>
      <td>1.36</td>
      <td>Pheusrical25</td>
    </tr>
    <tr>
      <th>4</th>
      <td>23</td>
      <td>Male</td>
      <td>63</td>
      <td>Stormfury Mace</td>
      <td>1.27</td>
      <td>Aela59</td>
    </tr>
    <tr>
      <th>5</th>
      <td>20</td>
      <td>Male</td>
      <td>10</td>
      <td>Sleepwalker</td>
      <td>1.73</td>
      <td>Tanimnya91</td>
    </tr>
    <tr>
      <th>6</th>
      <td>20</td>
      <td>Male</td>
      <td>153</td>
      <td>Mercenary Sabre</td>
      <td>4.57</td>
      <td>Undjaskla97</td>
    </tr>
    <tr>
      <th>7</th>
      <td>29</td>
      <td>Female</td>
      <td>169</td>
      <td>Interrogator, Blood Blade of the Queen</td>
      <td>3.32</td>
      <td>Iathenudil29</td>
    </tr>
    <tr>
      <th>8</th>
      <td>25</td>
      <td>Male</td>
      <td>118</td>
      <td>Ghost Reaver, Longsword of Magic</td>
      <td>2.77</td>
      <td>Sondenasta63</td>
    </tr>
    <tr>
      <th>9</th>
      <td>31</td>
      <td>Male</td>
      <td>99</td>
      <td>Expiration, Warscythe Of Lost Worlds</td>
      <td>4.53</td>
      <td>Hilaerin92</td>
    </tr>
    <tr>
      <th>10</th>
      <td>24</td>
      <td>Male</td>
      <td>57</td>
      <td>Despair, Favor of Due Diligence</td>
      <td>3.81</td>
      <td>Chamosia29</td>
    </tr>
    <tr>
      <th>11</th>
      <td>20</td>
      <td>Male</td>
      <td>47</td>
      <td>Alpha, Reach of Ending Hope</td>
      <td>1.55</td>
      <td>Sally64</td>
    </tr>
    <tr>
      <th>12</th>
      <td>30</td>
      <td>Male</td>
      <td>81</td>
      <td>Dreamkiss</td>
      <td>4.06</td>
      <td>Iskossa88</td>
    </tr>
    <tr>
      <th>13</th>
      <td>23</td>
      <td>Male</td>
      <td>77</td>
      <td>Piety, Guardian of Riddles</td>
      <td>3.68</td>
      <td>Seorithstilis90</td>
    </tr>
    <tr>
      <th>14</th>
      <td>40</td>
      <td>Male</td>
      <td>44</td>
      <td>Bonecarvin Battle Axe</td>
      <td>2.46</td>
      <td>Sundast29</td>
    </tr>
    <tr>
      <th>15</th>
      <td>21</td>
      <td>Male</td>
      <td>96</td>
      <td>Blood-Forged Skeletal Spine</td>
      <td>4.77</td>
      <td>Haellysu29</td>
    </tr>
    <tr>
      <th>16</th>
      <td>22</td>
      <td>Female</td>
      <td>123</td>
      <td>Twilight's Carver</td>
      <td>1.14</td>
      <td>Sundista85</td>
    </tr>
    <tr>
      <th>17</th>
      <td>22</td>
      <td>Female</td>
      <td>59</td>
      <td>Lightning, Etcher of the King</td>
      <td>1.65</td>
      <td>Aenarap34</td>
    </tr>
    <tr>
      <th>18</th>
      <td>28</td>
      <td>Male</td>
      <td>91</td>
      <td>Celeste</td>
      <td>3.71</td>
      <td>Iskista88</td>
    </tr>
    <tr>
      <th>19</th>
      <td>31</td>
      <td>Male</td>
      <td>177</td>
      <td>Winterthorn, Defender of Shifting Worlds</td>
      <td>4.89</td>
      <td>Assossa43</td>
    </tr>
  </tbody>
</table>
</div>



## Player Count


```python
total_players_unique = df.groupby('SN')['SN'].unique()
total_players = total_players_unique.count()
total_players_dic = {"Total Players":[total_players]}
total_players_df = pd.DataFrame(total_players_dic)
total_players_df
```




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
      <th>Total Players</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>573</td>
    </tr>
  </tbody>
</table>
</div>



## Purchasing Analysis (Total)


```python
Item_Name_groupby = df.groupby('Item Name')['Item Name'].unique()
unique_item_count = Item_Name_groupby.count()

average_price = df["Price"].mean()

number_of_purchase = df["Item Name"].count()

total_revenue = df["Price"].sum()

purchasing_analysis_total = {"Number of Unique Items":[unique_item_count],
                             "Average Price":[average_price],
                             "Number of Purchases":[number_of_purchase],
                             "Total Revenue":[total_revenue]
                            }
purchasing_analysis_total_df = pd.DataFrame(purchasing_analysis_total)
purchasing_analysis_total_df["Average Price"] = purchasing_analysis_total_df["Average Price"].map("${:.2f}".format)
purchasing_analysis_total_df["Total Revenue"] = purchasing_analysis_total_df["Total Revenue"].map("${:.2f}".format)
purchasing_analysis_total_df
```




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
      <th>Average Price</th>
      <th>Number of Purchases</th>
      <th>Number of Unique Items</th>
      <th>Total Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>$2.93</td>
      <td>780</td>
      <td>179</td>
      <td>$2286.33</td>
    </tr>
  </tbody>
</table>
</div>



## Gender Demographics


```python
gender_groupby = df.groupby(['SN',"Gender"]).count().reset_index()
gender_reset_index = gender_groupby.groupby('Gender').count().reset_index()
gender_drop_column = gender_reset_index.drop(columns={'Age',"Item ID",'Price','Item Name'})
gender_drop_column['Percentage'] = gender_drop_column['SN']/gender_reset_index['SN'].sum()
gender_drop_column["Percentage"] = gender_drop_column["Percentage"]*100
gender_drop_column["Percentage"] = gender_drop_column["Percentage"].map("{:.2f}%".format)
gender_drop_column = gender_drop_column.rename(columns={'SN':'Total Counts', 'Percentage':'Percentage of Players'})

gender_drop_column
#Formatting
```




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
      <th>Gender</th>
      <th>Total Counts</th>
      <th>Percentage of Players</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Female</td>
      <td>100</td>
      <td>17.45%</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Male</td>
      <td>465</td>
      <td>81.15%</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Other / Non-Disclosed</td>
      <td>8</td>
      <td>1.40%</td>
    </tr>
  </tbody>
</table>
</div>



## Purchasing Analysis (Gender)


```python
gender_groupby_count = df.groupby(["Gender"]).count().reset_index()
gender_groupby_count = gender_groupby_count.drop(columns={'Age','Item Name','Age','Price','SN'})

gender_groupby_mean = df.groupby(["Gender"]).mean().reset_index()
gender_groupby_mean = gender_groupby_mean.drop(columns={'Gender','Age','Item ID'})

gender_groupby_sum = df.groupby(["Gender"]).sum().reset_index()
gender_groupby_sum = gender_groupby_sum.drop(columns={'Gender','Item ID','Age'})

gender_groupby_count['Average Purchase Price'] = gender_groupby_mean
gender_groupby_count['Total Purchase Value'] = gender_groupby_sum

gender_groupby_count = gender_groupby_count.rename(columns={'Item ID':'Purchase Counts'})

gender_groupby_count["Average Purchase Price"] = gender_groupby_count["Average Purchase Price"].map("${:.2f}".format)
gender_groupby_count["Total Purchase Value"] = gender_groupby_count["Total Purchase Value"].map("${:.2f}".format)

gender_groupby_count
#Normalized Total & Formatting
```




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
      <th>Gender</th>
      <th>Purchase Counts</th>
      <th>Average Purchase Price</th>
      <th>Total Purchase Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Female</td>
      <td>136</td>
      <td>$2.82</td>
      <td>$382.91</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Male</td>
      <td>633</td>
      <td>$2.95</td>
      <td>$1867.68</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Other / Non-Disclosed</td>
      <td>11</td>
      <td>$3.25</td>
      <td>$35.74</td>
    </tr>
  </tbody>
</table>
</div>



## Age Demographics


```python
bins = [0,9,14,19,24,29,34,39,200]
group_names = ["<10","10-14","15-19","20-24","25-29","30-34","35-39","40+"]
df["Age Group"] = pd.cut(df["Age"], bins, labels=group_names)
age_group_unique = df.groupby(['Age Group','SN']).count().reset_index()
age_group_groupby_unique = age_group_unique.groupby('Age Group').count()
age_group_groupby_unique = age_group_groupby_unique.drop(columns={'SN','Gender','Item ID','Item Name','Price'})
age_group_groupby_unique['Percentage of Players'] = age_group_groupby_unique['Age']/total_players
age_group_groupby_unique = age_group_groupby_unique.rename(columns={'Age':'Total Count'})

age_group_groupby_unique["Percentage of Players"] = age_group_groupby_unique["Percentage of Players"]*100
age_group_groupby_unique["Percentage of Players"] = age_group_groupby_unique["Percentage of Players"].map("{:.2f}%".format)

age_group_groupby_unique

```




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
      <th>Total Count</th>
      <th>Percentage of Players</th>
    </tr>
    <tr>
      <th>Age Group</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>&lt;10</th>
      <td>19</td>
      <td>3.32%</td>
    </tr>
    <tr>
      <th>10-14</th>
      <td>23</td>
      <td>4.01%</td>
    </tr>
    <tr>
      <th>15-19</th>
      <td>100</td>
      <td>17.45%</td>
    </tr>
    <tr>
      <th>20-24</th>
      <td>259</td>
      <td>45.20%</td>
    </tr>
    <tr>
      <th>25-29</th>
      <td>87</td>
      <td>15.18%</td>
    </tr>
    <tr>
      <th>30-34</th>
      <td>47</td>
      <td>8.20%</td>
    </tr>
    <tr>
      <th>35-39</th>
      <td>27</td>
      <td>4.71%</td>
    </tr>
    <tr>
      <th>40+</th>
      <td>11</td>
      <td>1.92%</td>
    </tr>
  </tbody>
</table>
</div>



## Purchasing Analysis (Age)


```python
age_group_groupby_count = df.groupby(['Age Group'])["Item ID"].count().reset_index()
age_group_groupby_mean = df.groupby(['Age Group'])["Price"].mean().reset_index()
age_group_groupby_sum = df.groupby(['Age Group'])["Price"].sum().reset_index()
age_group_merge = pd.merge(age_group_groupby_count, age_group_groupby_mean, on="Age Group")
age_group_merge = pd.merge(age_group_merge, age_group_groupby_sum, on="Age Group")
age_group_merge = age_group_merge.rename(columns={'Item ID':'Purchase Count','Price_x':'Average Purchase Price',
                                                 'Price_y':'Total Purchase Value'})

age_group_merge["Average Purchase Price"] = age_group_merge["Average Purchase Price"].map("${:.2f}".format)
age_group_merge["Total Purchase Value"] = age_group_merge["Total Purchase Value"].map("${:.2f}".format)

age_group_merge
```




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
      <th>Age Group</th>
      <th>Purchase Count</th>
      <th>Average Purchase Price</th>
      <th>Total Purchase Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>&lt;10</td>
      <td>28</td>
      <td>$2.98</td>
      <td>$83.46</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10-14</td>
      <td>35</td>
      <td>$2.77</td>
      <td>$96.95</td>
    </tr>
    <tr>
      <th>2</th>
      <td>15-19</td>
      <td>133</td>
      <td>$2.91</td>
      <td>$386.42</td>
    </tr>
    <tr>
      <th>3</th>
      <td>20-24</td>
      <td>336</td>
      <td>$2.91</td>
      <td>$978.77</td>
    </tr>
    <tr>
      <th>4</th>
      <td>25-29</td>
      <td>125</td>
      <td>$2.96</td>
      <td>$370.33</td>
    </tr>
    <tr>
      <th>5</th>
      <td>30-34</td>
      <td>64</td>
      <td>$3.08</td>
      <td>$197.25</td>
    </tr>
    <tr>
      <th>6</th>
      <td>35-39</td>
      <td>42</td>
      <td>$2.84</td>
      <td>$119.40</td>
    </tr>
    <tr>
      <th>7</th>
      <td>40+</td>
      <td>17</td>
      <td>$3.16</td>
      <td>$53.75</td>
    </tr>
  </tbody>
</table>
</div>



## Top Spenders


```python
spending_groupby = df.groupby("SN")["Item ID"].count().reset_index()
spending_groupby_sum = df.groupby("SN")["Price"].sum().reset_index()
spending_groupby_sum
sorting_df = spending_groupby.sort_values("Item ID", ascending=False)
sorting_df_sum = spending_groupby_sum.sort_values("Price", ascending=False)
merge_df = pd.merge(sorting_df, sorting_df_sum, on="SN")
merge_df["Average Purchase Price"] = merge_df["Price"]/merge_df["Item ID"]

merge_df = merge_df.rename(columns={"Item ID":"Purchase Count","Price":"Total Purchase Value"})
merge_df["Average Purchase Price"] = merge_df["Average Purchase Price"].map("${:.2f}".format)
merge_df["Total Purchase Value"] = merge_df["Total Purchase Value"].map("${:.2f}".format)

merge_df.head(6)
```




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
      <th>SN</th>
      <th>Purchase Count</th>
      <th>Total Purchase Value</th>
      <th>Average Purchase Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Undirrala66</td>
      <td>5</td>
      <td>$17.06</td>
      <td>$3.41</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Mindimnya67</td>
      <td>4</td>
      <td>$12.74</td>
      <td>$3.18</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Qarwen67</td>
      <td>4</td>
      <td>$9.97</td>
      <td>$2.49</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Saedue76</td>
      <td>4</td>
      <td>$13.56</td>
      <td>$3.39</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Sondastan54</td>
      <td>4</td>
      <td>$10.24</td>
      <td>$2.56</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Hailaphos89</td>
      <td>4</td>
      <td>$5.87</td>
      <td>$1.47</td>
    </tr>
  </tbody>
</table>
</div>



## Most Popular Items


```python
item_name = df[["Item ID","Item Name","Price"]]
item_name
item_groupby = df.groupby("Item ID").count().reset_index()
item_groupby = item_groupby.sort_values("SN",ascending=False)
item_groupby = item_groupby.drop(columns={"Age","Gender","Item Name","Price","Age Group"})
item_groupby = pd.merge(item_groupby,item_name,on="Item ID")
#Drop all duplicates except the first
item_groupby = item_groupby.drop_duplicates(subset=["Item ID","SN"], keep= 'first')
item_groupby["Total Purchase Value"] = item_groupby['SN']*item_groupby['Price']
#Formatting
item_groupby["Price"] = item_groupby["Price"].map("${:.2f}".format)
item_groupby["Total Purchase Value"] = item_groupby["Total Purchase Value"].map("${:.2f}".format)
item_groupby.head(5)

```




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
      <th>Item ID</th>
      <th>SN</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>Total Purchase Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>39</td>
      <td>11</td>
      <td>Betrayal, Whisper of Grieving Widows</td>
      <td>$2.35</td>
      <td>$25.85</td>
    </tr>
    <tr>
      <th>11</th>
      <td>84</td>
      <td>11</td>
      <td>Arcane Gem</td>
      <td>$2.23</td>
      <td>$24.53</td>
    </tr>
    <tr>
      <th>22</th>
      <td>31</td>
      <td>9</td>
      <td>Trickster</td>
      <td>$2.07</td>
      <td>$18.63</td>
    </tr>
    <tr>
      <th>31</th>
      <td>175</td>
      <td>9</td>
      <td>Woeful Adamantite Claymore</td>
      <td>$1.24</td>
      <td>$11.16</td>
    </tr>
    <tr>
      <th>40</th>
      <td>13</td>
      <td>9</td>
      <td>Serenity</td>
      <td>$1.49</td>
      <td>$13.41</td>
    </tr>
  </tbody>
</table>
</div>



## Most Profitable Items


```python
item_groupby_price = item_groupby.sort_values("Total Purchase Value",ascending=False).reset_index()
item_groupby_price = item_groupby_price.drop(columns={"index"})
item_groupby_price = item_groupby_price.rename(columns={"SN":"Purchase Count"})

item_groupby_price.head(5)
```




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
      <th>Item ID</th>
      <th>Purchase Count</th>
      <th>Item Name</th>
      <th>Price</th>
      <th>Total Purchase Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>170</td>
      <td>5</td>
      <td>Shadowsteel</td>
      <td>$1.98</td>
      <td>$9.90</td>
    </tr>
    <tr>
      <th>1</th>
      <td>21</td>
      <td>3</td>
      <td>Souleater</td>
      <td>$3.27</td>
      <td>$9.81</td>
    </tr>
    <tr>
      <th>2</th>
      <td>37</td>
      <td>5</td>
      <td>Shadow Strike, Glory of Ending Hope</td>
      <td>$1.93</td>
      <td>$9.65</td>
    </tr>
    <tr>
      <th>3</th>
      <td>127</td>
      <td>3</td>
      <td>Heartseeker, Reaver of Souls</td>
      <td>$3.21</td>
      <td>$9.63</td>
    </tr>
    <tr>
      <th>4</th>
      <td>120</td>
      <td>5</td>
      <td>Agatha</td>
      <td>$1.91</td>
      <td>$9.55</td>
    </tr>
  </tbody>
</table>
</div>


