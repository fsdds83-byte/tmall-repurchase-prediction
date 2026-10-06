# Tmall Repurchase Prediction

基于天猫用户行为数据构建用户复购预测模型，预测用户在未来是否会再次购买指定商家的商品。

## 项目流程

项目主要包括：

1. 数据清洗与缺失值处理
2. 用户、商家、用户-商家三个维度的特征工程
3. 特征标准化与训练集构建
4. Logistic Regression、SVM、MLP、Random Forest、AdaBoost、XGBoost 等模型训练
5. 交叉验证与超参数调优
6. Stacking 模型融合
7. 生成用户-商家复购概率预测结果

## 特征工程

最终构建 **123 个模型特征**，主要分为三类：

- **用户特征**
  - 用户点击、加购、购买、收藏行为
  - 行为比例与差异特征
  - 商品、品类、商家、品牌覆盖范围
  - 活跃天数
  - 月度行为特征
  - 历史重复购买特征

- **商家特征**
  - 各类行为总量
  - 商品、品类、品牌数量
  - 不同行为用户数量
  - 历史重复购买人数

- **用户-商家交互特征**
  - 用户对指定商家的点击、加购、购买、收藏行为
  - 行为比例
  - 活跃天数
  - 商品、品类、品牌交互数量

## 模型

主要使用：

- Logistic Regression
- Linear SVM
- MLP
- Random Forest
- AdaBoost
- XGBoost
- Stacking

部分模型通过交叉验证进一步进行参数选择。

最终 Random Forest 参数：

```text
n_estimators = 155
max_depth = 15
max_features = 16
criterion = entropy