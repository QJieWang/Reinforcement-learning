# First Day

## 概括与基础

授课老师：周博磊（小雷军）//只是个人觉得长得很像

[课程链接](https://www.bilibili.com/video/BV1LE411G7Xj)

[课程 Github 地址](https://github.com/zhoubolei/introRL)

[课件](https://github.com/zhoubolei/introRL/blob/master/lecture1.pdf)

## Main Problem

Agent（智能体）Pursues maximum reward in the Environment(环境)

## Difference between RL and Supervised Learning

1. 强化学习的输入是序列数据，而不是单独的数据。
2. 没有告知正确的答案，需要学习器自己探索。
3. 强化学习是一个不断试错的过程。
4. 惩罚与奖励都是延后的，无监督是实时的。

## Features of RL

1. 探索与试错。
2. 延迟奖惩。
3. 时间因素被考虑在内。
4. Agent（智能体）的行为将会影响最终的结果。

## Big deal

能过获得超人类的学习能力与表现。
监督学习的上限就是人类的上限，但是强化学习的上限超越人类。

## Why RL Works NOW

1. 算力的提升
2. 进行更多的尝试
3. 端到端的训练，使得特征提取与决策器朝着同一个目标一同优化。

## Application

了解更多的前沿应用，分布式的强化学习能够进行更多的尝试，获得更多的反馈。

## Major Components of an RL Agent

1. Policy：agent behavior function(决策函数)
2. Value function：how good is each state or action（价值函数）
3. Model：agent's state representation of the enviro
   nment.(agent 对模型的理解)

## Tyoes of RL

![强化学习分类]("https://github.com/wangxiatian/Reinforcement-learning/blob/main/image/TypeofRL.jpg");

## Exploration and Exploitation

Exploration：探索未知

Exploitation：挖掘已知

## OpenAI

gymz 中提供课很多可学习的游戏与 Examples。

## 作业

![概论作业]("https://github.com/wangxiatian/Reinforcement-learning/blob/main/image/RL%E6%A6%82%E8%AE%BA%E4%BD%9C%E4%B8%9A.jpg");

## [Datawale 官方笔记](https://datawhalechina.github.io/leedeeprl-notes/#/chapter1/chapter1_questions&keywords)

由于第一天的作业是概念性的了解，就直接复制粘贴了官方的笔记内容，用来纠正自己的一些错误理解。再次强调，以下内容来自 DataWhale

## 关键词 Keywords

**强化学习**（Reinforcement Learning）：Agent 可以在与复杂且不确定的 Environment 进行交互时，尝试使所获得的 Reward 最大化的计算算法。

**Action:** Environment 接收到的 Agent 当前状态的输出。

**State：** Agent 从 Environment 中获取到的状态。

**Reward**：Agent 从 Environment 中获取的反馈信号，这个信号指定了 Agent 在某一步采取了某个策略以后是否得到奖励。

**Exploration：** 在当前的情况下，继续尝试新的 Action，其有可能会使你得到更高的这个奖励，也有可能使你一无所有。

**Exploitation**：在当前的情况下，继续尝试已知的可以获得最大 Reward 的过程，即重复执行这个 Action 就可以了。

**深度强化学习（Deep Reinforcement Learning）：** 不需要手工设计特征，仅需要输入 State 让系统直接输出 Action 的一个 end-to-end training 的强化学习方法。通常使用神经网络来拟合 value function 或者 policy network。
Full observability、fully observed 和 partially observed：当 Agent 的状态跟 Environment 的状态等价的时候，我们就说现在 Environment 是 full observability（全部可观测），当 Agent 能够观察到 Environment 的所有状态时，我们称这个环境是 fully observed（完全可观测）。一般我们的 Agent 不能观察到 Environment 的所有状态时，我们称这个环境是 partially observed（部分可观测）。

**POMDP**（Partially Observable Markov Decision Processes）：部分可观测马尔可夫决策过程，即马尔可夫决策过程的泛化。POMDP 依然具有马尔可夫性质，但是假设智能体无法感知环境的状态 ss，只能知道部分观测值 oo。

**Action space**（discrete action spaces and continuous action spaces）：在给定的 Environment 中，有效动作的集合经常被称为动作空间（Action space），Agent 的动作数量是有限的动作空间为离散动作空间（discrete action spaces），反之，称为连续动作空间（continuous action spaces）。

**policy-based**（基于策略的）：Agent 会制定一套动作策略（确定在给定状态下需要采取何种动作），并根据这个策略进行操作。强化学习算法直接对策略进行优化，使制定的策略能够获得最大的奖励。
valued-based（基于价值的）：Agent 不需要制定显式的策略，它维护一个价值表格或价值函数，并通过这个价值表格或价值函数来选取价值最大的动作。
model-based（有模型结构）：Agent 通过学习状态的转移来采取措施。
model-free（无模型结构）：Agent 没有去直接估计状态的转移，也没有得到 Environment 的具体转移变量。它通过学习 value function 和 policy function 进行决策。

## Questions

**强化学习的基本结构是什么？**

答：本质上是 Agent 和 Environment 间的交互。具体地，当 Agent 在 Environment 中得到当前时刻的 State，Agent 会基于此状态输出一个 Action。然后这个 Action 会加入到 Environment 中去并输出下一个 State 和当前的这个 Action 得到的 Reward。Agent 在 Environment 里面存在的目的就是为了极大它的期望积累的 Reward。

**强化学习相对于监督学习为什么训练会更加困难（强化学习的特征）？**

答：

强化学习处理的多是序列数据，其很难像监督学习的样本一样满足 IID（独立同分布）条件。

强化学习有奖励的延迟（Delay Reward），即在 Agent 的 action 作用在 Environment 中时，Environment 对于 Agent 的 State 的奖励的延迟（Delayed Reward），使得反馈不及时。

相比于监督学习有正确的 label，可以通过其修正自己的预测，强化学习相当于一个“试错”的过程，其完全根据 Environment 的“反馈”更新对自己最有利的 Action。

**强化学习的基本特征有哪些？**

答：

有 trial-and-error exploration 的过程，即需要通过探索 Environment 来获取对这个 Environment 的理解。
强化学习的 Agent 会从 Environment 里面获得延迟的 Reward。
强化学习的训练过程中时间非常重要，因为数据都是有时间关联的，而不是像监督学习一样是 IID 分布的。
强化学习中 Agent 的 Action 会影响它随后得到的反馈

**近几年强化学习发展迅速的原因？**

答：

1. 算力（GPU、TPU）的提升，我们可以更快地做更多的 trial-and-error 的尝试来使得 Agent 在 Environment 里面获得很多信息，取得更大的 Reward。
2. 我们有了深度强化学习这样一个端到端的训练方法，可以把特征提取和价值估计或者决策一起优化，这样就可以得到一个更强的决策网络。

**状态和观测有什么关系？**

答：状态（state）是对世界的完整描述，不会隐藏世界的信息。观测（observation）是对状态的部分描述，可能会遗漏一些信息。在深度强化学习中，我们几乎总是用一个实值向量、矩阵或者更高阶的张量来表示状态和观测。

**对于一个强化学习 Agent，它由什么组成？**

答：

1. 策略函数（policy function），Agent 会用这个函数来选取它下一步的动作，包括随机性策略（stochastic policy）和确定性策略（deterministic policy）。
2. 价值函数（value function），我们用价值函数来对当前状态进行评估，即进入现在的状态，到底可以对你后面的收益带来多大的影响。当这个价值函数大的时候，说明你进入这个状态越有利。
3. 模型（model），其表示了 Agent 对这个 Environment 的状态进行的理解，它决定了这个系统是如何进行的。

**根据强化学习 Agent 的不同，我们可以将其分为哪几类？**

答：

基于价值函数的 Agent。 显式学习的就是价值函数，隐式的学习了它的策略。因为这个策略是从我们学到的价值函数里面推算出来的。
基于策略的 Agent。它直接去学习 policy，就是说你直接给它一个 state，它就会输出这个动作的概率。然后在这个 policy-based agent 里面并没有去学习它的价值函数。
然后另外还有一种 Agent 是把这两者结合。把 value-based 和 policy-based 结合起来就有了 Actor-Critic agent。这一类 Agent 就把它的策略函数和价值函数都学习了，然后通过两者的交互得到一个更佳的状态。

**基于策略迭代和基于价值迭代的强化学习方法有什么区别?**

答：

基于策略迭代的强化学习方法，agent 会制定一套动作策略（确定在给定状态下需要采取何种动作），并根据这个策略进行操作。强化学习算法直接对策略进行优化，使制定的策略能够获得最大的奖励；基于价值迭代的强化学习方法，agent 不需要制定显式的策略，它维护一个价值表格或价值函数，并通过这个价值表格或价值函数来选取价值最大的动作。
基于价值迭代的方法只能应用在不连续的、离散的环境下（如围棋或某些游戏领域），对于行为集合规模庞大、动作连续的场景（如机器人控制领域），其很难学习到较好的结果（此时基于策略迭代的方法能够根据设定的策略来选择连续的动作)；
基于价值迭代的强化学习算法有 Q-learning、 Sarsa 等，而基于策略迭代的强化学习算法有策略梯度算法等。
此外， Actor-Critic 算法同时使用策略和价值评估来做出决策，其中，智能体会根据策略做出动作，而价值函数会对做出的动作给出价值，这样可以在原有的策略梯度算法的基础上加速学习过程，取得更好的效果。

**有模型（model-based）学习和免模型（model-free）学习有什么区别？**

答：针对是否需要对真实环境建模，强化学习可以分为有模型学习和免模型学习。 有模型学习是指根据环境中的经验，构建一个虚拟世界，同时在真实环境和虚拟世界中学习；免模型学习是指不对环境进行建模，直接与真实环境进行交互来学习到最优策略。总的来说，有模型学习相比于免模型学习仅仅多出一个步骤，即对真实环境进行建模。免模型学习通常属于数据驱动型方法，需要大量的采样来估计状态、动作及奖励函数，从而优化动作策略。免模型学习的泛化性要优于有模型学习，原因是有模型学习算需要对真实环境进行建模，并且虚拟世界与真实环境之间可能还有差异，这限制了有模型学习算法的泛化性。

**强化学习的通俗理解**

答：environment 跟 reward function 不是我们可以控制的，environment 跟 reward function 是在开始学习之前，就已经事先给定的。我们唯一能做的事情是调整 actor 里面的 policy，使得 actor 可以得到最大的 reward。Actor 里面会有一个 policy， 这个 policy 决定了 actor 的行为。Policy 就是给一个外界的输入，然后它会输出 actor 现在应该要执行的行为。
