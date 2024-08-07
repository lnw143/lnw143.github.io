---
authors:
  - lnw143
categories:
  - Record
date: 
  created: 2024-04-21
  updated: 2024-08-03

---

# AtCoder 训练记录

~~[先贴上本人主页](https://atcoder.jp/users/lnw143)~~

## [ABC347](https://atcoder.jp/contests/abc347/standings?watching=lnw143)

$\Delta=\color{red}{-24}$

~~蓝名保卫战，极限 1600~~

C 题还是有些思维难度的，最后才做出来，但是不够简洁

E 题忘开 `%lld` 喜提罚时

D 题最难评，又 WA 又 RE，最后如果输出不符合条件就输出 `-1` 才过

F 题[原题](https://www.luogu.com.cn/problem/P3625)，但是不会（

赛后发现就是一个二维前缀和 + 二位前缀max，还是挺简单的

~~G 题不会~~

赛时打的太急了，罚时太多，速度也被拖慢了，同分的最高 `performance` 有 2000+，还是代码实现不够快和准

## [AGC066](https://atcoder.jp/contests/agc066/standings?watching=lnw143)

$\Delta=\color{red}{-21}$

~~E 题原题，还抓了一个抄题解的~~

A 题还是挺水的，只是没想到从奇偶性的角度来想，题解给的是 $O(N ^ 2 D)$ 的做法，但是有更优且更简单的做法 $O(N ^ 2)$，但是没想到，还是考思维。

B 题有点愚人节，`python` 语言优势很大（自带高精度），用几个 $5 ^ x$ 拼起来多随机几次就完了，难绷（

~~蓝名没了 /ll~~

## [ABC348](https://atcoder.jp/contests/abc348/standings?watching=lnw143)

$\Delta=\color{green}{114}$

`performance` 2300+ 祭

0罚时切 A ~ F，~~让我又想起了那场似的 rating~~

F 题听说比较水，暴力 + O3 可过，但是我用 `bitset` $O(\frac{N ^ 2 M}{\omega})$ 也过了（

G 题决策单调性优化板题，原题两道：[here](https://atcoder.jp/contests/joisc2019/tasks/joisc2019_j) & [here](https://codeforces.com/problemset/gymProblem/104651/L) ~~（但我不会）~~

upd on 2024.4.14 : G 题改出来了，应用单调性还是比较简单的，但是难在证明

## [ABC349](https://atcoder.jp/contests/abc349/standings?watching=lnw143)

$\Delta=\color{green}{67}$

A ~ D 都比较顺畅，D 题盲猜 $\text{lowbit}$ 喜提机房一血，E 题没开 `long long` 喜提一发罚时与机房一血

然后就坐着与 F & G 干瞪眼，F 先是用 cdq 尝试水分，后来将不是 $M$ 因数的删掉了，还是不行

最后发现 $M$ 最多有 $13$ 个因数，直接 $O(2^{13}N) \approx 1.638 \times 10^9$ 过了，~~AtCoder 神机~~

但是打得太急，F 题 7 发罚时，最后 4 发最离谱，一发没取模，一发取模太慢 TLE，一发将取模改成减法写错了，最后一发两处取模是 copy 的都错了，漏了一处没改（

$\color{green}{525} \color{red}{(7)}$ ！！

G 题直接并查集开水，快 T 了就 No，过了一半的数据点

实际上还可以开随机化，因为对于 $\forall i$，有些连边是不需要的，有概率连到与目标解答案相同的状态，但比赛后才想到（

## [ABC350](https://atcoder.jp/contests/abc350/standings?watching=lnw143)

$\Delta=\color{red}{-6}$

之前的总结写的太笼统了，更像是提要。刚好今天实在是打 emo 了，犯了很多离谱的错误，想写一篇个人直观的反思，从 `rating` 和 `performance` 中跳出来，慢慢地审视整个过程。

A 题其实没有问题，可以直接A的，但是把 `%03d` 写成了 `%02d` 样例中也没有 `ABC001`，于是就挂了。

后来几道题一直很慌，越慌，越是想打快。越是快，就越出错。这很严重拖慢了整个切题的速度。C 题本来是没什么问题的，但是急着想过掉它，核心的代码几乎一半是错的，第一发直接罚时，这时心情也是很差了，很焦躁。后来逼迫自己冷静下来，又在草稿纸上画了几下，思路便逐渐清晰，于是便改对了。

到了赛点的后三题后，我其实刚刚松一口气，看到 E 题又自闭了，毕竟概率题上次就栽过，是[ABC342F](https://atcoder.jp/contests/abc342/tasks/abc342_f)，这次又看到，心里一紧，只好先尝试 F 题。

F 题读完题后没多久就想到了 dfs，然而实现中还是有一些小错误，如 `for` 循环里更新 `i` 的话，它实际上还会 `++i/--i` 一次，会跳过一个位置。好在没罚时。

切完 F 题后看了一下 G 题，一开始读错题了以为那个在线是假的，高高兴兴拿样例试水发现是错的。没办法，于是看 E 题，结果旁边的人 ~~看我蓝名快没了~~ 好心旁敲侧击，于是想到 DP，中途还有一个自己转移到自己的，想到了之前的[一道题目](https://atcoder.jp/contests/abc333/tasks/abc333_f) ~~虽然我没改出来~~ ，于是移项解方程即可。

一开始 $10^{18}$ 我认为计搜是过不了的，因此打得不够坚定，还有一个变量重名调了很久，实现不够稳和准。开始是想着拿去水分的，但是直接过了，而且时间也很充裕（7ms）。赛后看题解，计搜时间复杂度实际上是 $O(\log^3 n)$，但是主要问题是不会证明，对自己没有信心，于是犹豫了很久。

到了最后的 G 题，此时还剩下 20 分钟，已经机房内有人切了 G 题。出于对 G 题的潜意识压力以及前面比赛的表现，我此时已经基本失去思考能力了，脑子一片嗡嗡的根本想不到正解，打了一个根本就没概率的随机化过了一半，最后遗憾收场。

机房内同年级的有 4 个人过了 G 题，其中 3 人都是水过的，还包括两个代码相似的人。第四个[大佬](https://atcoder.jp/contests/abc350/standings?watching=yangjiaxi)用了 `splay`。

到这里，你可能认为 G 题还是有点难度的。但是，实际上，这也是我在比赛中犯的最后一个，也是最大的一个错误。

读完 [G 题](https://atcoder.jp/contests/abc350/tasks/abc350_g)，其实不难想到如果维护好了森林中的每棵树有确定的根（具体是哪个节点与答案无关），并且维护好了每个点在其所在连通块中的朝向这个根的父亲，那么求解答案是 $O(1)$ 的。比赛时这个念头在我脑海里一闪而过，但是很快就被否决了——原因很简单，这个维护过程直观上看是非常不可行的。后来，我转而去想 `bitset` 时间换空间，但一无所获。

然而，这就是问题所在——用暴力维护这些信息实际上的时间复杂度是正确的！因为每次连边的两个点都是在不同的连通块中，做完这次操作以后它们就会被合并，因此如果我们遍历一遍较小的连通块，总时间复杂度是 $O(n\log n)$！因此，这道 G 题出乎意料地短，甚至比我的随机化代码还要少。

---

写在最后：这次 ABC 可以看到除了少部分人，大多数人都没有取得很理想，甚至可以说糟糕的成绩。比赛结束后，我听到有人在机房里咒骂自己、题目和出题人的。还有人为了 `rating` 而闷闷不乐，诸如此类。但是有一点他们都错了，我们打比赛不是为了 `rating` 去打，不是为了成绩去打。以我为例，这次比赛我的 `delta` 是 `-6`，相对于之前 `2200+` 的 `performance`，可谓是相当的差。但是，在这背后，是我被打乱的做题节奏，被扰乱的心态，是我过于激动的心情。这次比赛，暴露了我很多问题：代码实现不准不细心，读题不仔细，对时间复杂度的不敏感，对时间复杂度证明的不熟练，而这些，都为我提供了宝贵的经验，这远远不是几点 `rating` 所能给我的。之前还看到旁边的人比赛时一起讨论题目，其实也是十分不应该——如果人人都只在乎 `rating` 以至于无人在乎算法背后的玄妙，在乎它们的出处与归宿，那么 `rating` 早已失去它本来的意义了。希望各位在天涯海角的 `OIer` 都能保住自己的初心，守住心中的一寸净土，为了 `OI`，`ACM`，乃至 `CS` 的明天而砥砺前行。