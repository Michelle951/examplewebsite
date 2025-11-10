---
title: "CN Example"
description: "A comprehensive guide on using TopN feature in dashboard charts to filter and rank data. "
image: "https://api.dicebear.com/9.x/glass/svg?seed=Jocelyn"
startDate: "2025-11-09"
skills: ["Visualization", "TopN", "Dashboard", "Data Analyses"]
---

## 使用 TopN 筛选仪表盘图表中的数据

### 一、功能简介

<div class="callout" style="background-color: #e7f3fe; padding: 10px; border-left: 6px solid #2196F3;">
    <strong>内测信息：</strong>功能内测中。<br>
    <strong>设备要求：</strong>支持在桌面端和网页版操作。
</div>

使用 TopN 功能可以对多维表格仪表盘图表中的数据排名，并筛选出排名前几或后几的数据。你可以在柱状图、折线图、条形图、面积图、饼图、环形图、组合图、雷达图、散点图和透视表中使用此功能。

常见使用场景：

- 在销售分析表中仅展示销量前 5 的商品。
- 在市场分析中突出表现最好的前 3 个地区。
- 在费用管理中筛选支出最多的 3 个部门。

### 二、操作流程

<div class="callout" style="background-color: #e7f3fe; padding: 10px; border-left: 6px solid #2196F3;">
    <strong>说明：</strong>每种图表支持的配置项不同，需以实际界面为准。
</div>

1. 打开仪表盘，将鼠标悬停在需要编辑的图表上，点击浮现的 **︙** 图标 > **配置**，切换至 **分析** 标签页。
2. 开启 TopN，选择排名字段、排名方式、保留数量等。

   - **排名字段**：在透视表中，可以选择 **基础配置** 页签中添加到 **行** 或 **列** 区域的字段。**排名字段** 决定了数据的统计和排名维度，例如分别统计每个省份、品类、月份的数据并按省份、品类、月份进行排名。
   - **排名方式**：在下拉列表中选择排序方式。每种图表支持的排名方式有所不同，需以实际界面为准。有关每种排名方式的具体信息，请参考本文“三、TopN 排名方式说明”。
   - **选择系列**：当 **排名方式** 选择 **按系列值排名** 时，进一步选择以哪个系列的数值为准进行排序。
   - **保留数量**
   - **前 [整数] 个**：基于所选的排名方式，从大到小展示前 N 条数据，即展示最大的几条数据。
   - **后 [整数] 个**：基于所选的排名方式，从大到小展示后 N 条数据，即展示最小的几条数据。

3. 配置完成后，用鼠标点击任意空白处，系统将根据你的设置自动更新图表。

![](https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/3d2c8fdc70944a06a751a63c8e0b44db~tplv-jbbdkfciu3-image:0:0.image)

## 三、TopN 排名方式说明

#### XY 轴类图表

XY 轴类图表指基于两个维度的数据，利用 X 轴（横轴）和 Y 轴（纵轴）绘制出来的图表。在多维表格仪表盘中，XY 轴类图表包括柱状图、折线图、条形图、面积图、组合图、雷达图和散点图。

XY 轴类图表支持 4 种排名方式：按照横轴类别求和排名、按系列值排名、按横轴类别组内排名、按系列求和排名。为了更好地理解这几种排名方式，首先需要理解“类别”和“系列”这两个概念。

- 类别指分类汇总数据时所依据的分类标准，例如以省份为类别，可以统计产品在每个省份的销量；或者以客户类型为类别，可以统计每类客户对产品的购买情况。
- 系列可以理解为同一类别的数据集合，例如柱状图或条形图中的一个数据柱、折线图中的一条折线、面积图中一条折线及其形成的填充区、散点图中同一类别的数据点、雷达图中一个完整闭合的雷达多边形等。

你可以在图表的 **基础配置** 页签中设置图表的类别和系列，二者在不同图表中对应的配置项有所不同，详见下表。

<table style="table-layout:auto; width:auto; border-collapse:collapse;">
    <thead>
        <tr>
            <th style="background-color:#cfe8ff; text-align:left; padding:8px;">图表类型</th>
            <th style="background-color:#cfe8ff; text-align:left; padding:8px;">"类别"对应的配置项</th>
            <th style="background-color:#cfe8ff; text-align:left; padding:8px;">"系列"对应的配置项</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left; padding:8px;">柱状图、折线图、面积图、组合图和散点图</td>
            <td style="text-align:left; padding:8px;"><strong>横轴（类别）</strong></td>
            <td style="text-align:left; padding:8px;"><strong>纵轴（字段）</strong> 或 <strong>分组依据</strong></td>
        </tr>
        <tr>
            <td style="text-align:left; padding:8px;">条形图</td>
            <td style="text-align:left; padding:8px;"><strong>纵轴（类别）</strong></td>
            <td style="text-align:left; padding:8px;"><strong>横轴（字段）</strong> 或 <strong>分组依据</strong></td>
        </tr>
        <tr>
            <td style="text-align:left; padding:8px;">雷达图</td>
            <td style="text-align:left; padding:8px;"><strong>类别轴</strong></td>
            <td style="text-align:left; padding:8px;"><strong>数轴值（系列）</strong> 或 <strong>分组依据</strong></td>
        </tr>
    </tbody>
</table>

##### 按横轴类别求和排名

根据图表中配置的类别，分别计算每种分类下的所有系列值之和，再按照系列值之和从大到小对这些类别进行排序。结合 **保留数量** 设置，可以分析出系列总值最高或最低的几个类别。

- 支持的图表类型：柱状图、折线图、条形图、面积图、组合图、雷达图和散点图。
- 应用场景示例：以下图配置为例，可以分析衣服、首饰、鞋、箱包这四个系列在各个大区（类别）的销量总和，并展示销量总和最高的 2 个大区。

<div style="display: flex;justify-content: space-between;">
	<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/3ee7a17eea1542d8ba5927f2aad83476~tplv-jbbdkfciu3-image:0:0.image" style="width:48%;">
	<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/838bbefbba724c3ea650a32fc7ed2938~tplv-jbbdkfciu3-image:0:0.image" style="width: 48%;">
</div>

##### 按系列值排名

根据图表中配置的类别，选择按照某个系列对应的数值从大到小，对这些类别进行排序。结合 **保留数量** 设置，可以分析出该系列值排名最高或最低的几个类别。

- 使用前提：需在图表 **基础配置** 页签中的 **纵轴（字段）** 或 **横轴（字段）** 或 **数值轴（系列）** 中至少选择 2 个字段，或者启用 **分组聚合**。
- 支持的图表类型：柱状图、折线图、条形图、面积图、组合图、雷达图和散点图。
- 应用场景示例：以下图配置为例，可以分析出今年销量（系列）最高的 2 个大区（类别）。
  <div style="display: flex;justify-content: space-between;">
  <img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/6ec6aa5f1dde468cabb3f2f01579eafe~tplv-jbbdkfciu3-image:0:0.image" style="width:48%;">
  <img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/cdeb644f8e4c46cc9f5d9c35f099e1d2~tplv-jbbdkfciu3-image:0:0.image" style="width: 48%;">
  </div>

##### 按横轴类别组内排名

根据图表中配置的类别，在每个类别中分别按照系列值从大到小对系列进行排序。结合 **保留数量** 设置，可以分析出每个类别中排名最高或最低的几个系列。

- 使用前提：需在图表 **基础配置** 页签中的 **纵轴（字段）** 或 **横轴（字段）** 或 **数值轴（系列）** 中至少选择 2 个字段，或者启用 **分组聚合**。
- 支持的图表类型：柱状图、折线图、条形图、面积图、组合图、雷达图和散点图。
- 应用场景示例：以下图配置为例，可以在每个大区（类别）中，将衣服、首饰、鞋、箱包的销量（系列）进行排名，并展示销量最高的 2 个系列。

<div style="display: flex;justify-content: space-between;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/5a81715c76974b6eb67f2810cbffb32c~tplv-jbbdkfciu3-image:0:0.image" style="width:48%;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/7df0ac62b2d9470b9e77d33a309dcfac~tplv-jbbdkfciu3-image:0:0.image" style="width: 48%;">
</div>

##### 按系列求和排名

将所有的系列值求和，结合 **保留数量** 设置分析出排名最高或最低的几个系列，然后查看这些系列在每个类别中的具体数据。

- 使用前提：需在图表 **基础配置** 页签中的 **纵轴（字段）** 或 **横轴（字段）** 或 **数值轴（系列）** 中至少选择 2 个字段，或者启用 **分组聚合**。
- 支持的图表类型：柱状图、折线图、条形图、面积图、组合图、雷达图和散点图。
- 应用场景示例：以下图配置为例，可以分析出衣服、首饰、鞋、箱包这四个系列中，销量总和最高的 2 个系列在所有大区（类别）中的具体销量。

<div style="display: flex;justify-content: space-between;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/b34290ce900c44398422956d4a5cde0a~tplv-jbbdkfciu3-image:0:0.image" style="width:48%;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/6d5ddb5364274572bbb1112c6649e123~tplv-jbbdkfciu3-image:0:0.image" style="width: 48%;">
</div>

#### 饼图和环形图

在饼图和环形图中，默认按照 **扇区数值** 从大到小排名，不支持设置其他的排名方式。结合 **保留数量** 可以分析出数值最大或最小的几个扇区。
以下图配置为例，可以分析出销售量排名前 2 的商品种类。

<div style="display: flex;justify-content: space-between;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/268d053339bb488fbb3f20a523ef6622~tplv-jbbdkfciu3-image:0:0.image" style="width:48%;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/9dcfa33d91194d71bfff62c646431050~tplv-jbbdkfciu3-image:0:0.image" style="width: 48%;">
</div>

#### 透视表

透视表支持 2 种排名方式：按总计求和排名和按系列值排名。

##### 按总计求和排名

按照 **排名字段** 中所选的分类标准，分别统计各个分类下透视表 **基础配置** 页签下 **值** 区域中所有字段的数值之和，按照数值之和从大到小对这些分类进行排序，结合 **保留数量** 设置，可以分析出某些数值之和最高或最低的几个分类。
以下图配置为例，可以分析出每一类产品中，两年总销量最低的 2 个大区。

<div style="display: flex;justify-content: space-between;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/e2dcd1aec3c74b289436ccd6c2ca0750~tplv-jbbdkfciu3-image:0:0.image" style="width:48%;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/feb88073d906411fb33ae6d7ab18d770~tplv-jbbdkfciu3-image:0:0.image" style="width: 48%;">
</div>

##### 按系列值排名

按照 排名字段 中所选的分类标准，按照 **选择系列** 中对应的字段数值从大到小，对这些分类进行排序。结合 **保留数量** 设置，可以分析出某个数值最高或最低的几个分类。
以下图配置为例，可以分析出今年销量最差的 2 个品类。

<div style="display: flex;justify-content: space-between;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/912ff3fd35114ad3b3b008c9ff2fdd6b~tplv-jbbdkfciu3-image:0:0.image" style="width:48%;">
<img src="https://p1-hera.feishucdn.com/tos-cn-i-jbbdkfciu3/c4bc7867905e4fee9b7c21d0ef3df6e1~tplv-jbbdkfciu3-image:0:0.image" style="width: 48%;">
</div>

---

来源：飞书帮助中心
