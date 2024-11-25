## Hi there 👋

- 🔭 I’m currently a master's student at Michigan Tech
  为了更好地解释更新公式中的特征影响，首先我们需要定义损失函数，然后解释特征如何通过梯度下降法影响模型参数的更新。

### 损失函数表达式

在线性回归中，常用的损失函数是均方误差（Mean Squared Error, MSE），它计算了所有样本预测值与实际值之间差的平方的平均值。对于给定的数据集 \(\{(x^{(i)}, y^{(i)})\}_{i=1}^n\)，其中 \(x^{(i)}\) 包含 \(m\) 个特征和一个常数项（通常为1，对应偏置项 \(\theta_0\)），损失函数 \(J(\theta)\) 可以表达为：

\[ J(\theta) = \frac{1}{2n} \sum_{i=1}^n \left(h_\theta(x^{(i)}) - y^{(i)}\right)^2 \]

这里，\(h_\theta(x^{(i)})\) 是模型对第 \(i\) 个样本的预测值，通常在线性回归中为 \(h_\theta(x^{(i)}) = \theta^T x^{(i)}\)。

### 特征影响的解释

**特征影响**指的是每个特征 \(x_j\) 对参数 \(\theta_j\) 更新的具体影响机制。在梯度下降法中，这种影响是通过特征值 \(x_j^{(i)}\) 与误差项 \(y^{(i)} - h_\theta(x^{(i)})\) 的乘积来实现的。具体来说：

1. **误差项** \(y^{(i)} - h_\theta(x^{(i)})\)：这表示第 \(i\) 个样本的预测误差。如果 \(h_\theta(x^{(i)})\) 小于 \(y^{(i)}\)，误差为正，表示模型低估了真实值；如果大于，则误差为负，表示模型高估了真实值。

2. **特征值** \(x_j^{(i)}\)：这个值表示第 \(i\) 个样本的第 \(j\) 个特征。它的大小和符号（正或负）直接影响误差项对参数 \(\theta_j\) 更新的贡献。具体来说：

   - 当 \(x_j^{(i)}\) 较大且误差项也较大时，它们的乘积将会很大，导致 \(\theta_j\) 的更新量也大，从而显著调整 \(\theta_j\) 以减少未来的误差。
   - 如果 \(x_j^{(i)}\) 的符号为负，它将反转误差项的贡献方向，这意味着如果误差是正的（预测值低于实际值），\(\theta_j\) 将向相反方向调整，以适应这种影响。

### 如何产生影响

在梯度下降中，我们计算损失函数 \(J(\theta)\) 关于每个参数 \(\theta_j\) 的偏导数：

\[ \frac{\partial J(\theta)}{\partial \theta_j} = \frac{1}{n} \sum_{i=1}^n \left(h_\theta(x^{(i)}) - y^{(i)}\right) x_j^{(i)} \]

这个偏导数表示了损失函数在参数 \(\theta_j\) 方向上的梯度，即参数 \(\theta_j\) 应该如何调整以最小化总损失。通过更新公式 \(\theta_j := \theta_j - \alpha \frac{\partial J(\theta)}{\partial \theta_j}\)，参数 \(\theta_j\) 会根据其对应特征 \(x_j^{(i)}\) 和观测到的误差调整，以期达到更好的模型性能。这种更新机制确保了模型能够学习数据中的模式，调整自身参数来逐步减少预测误差。
<!--

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
