##### 1339. 你的旅途由此开始 [https://www.acwing.com/problem/content/1341/](https://www.acwing.com/problem/content/1341/)

有一个众所周知的事实，每个彗星的背后都藏着一个UFO。

这些UFO经常到地球来带走一些它们的忠实支持者。

不幸的是，UFO的空间有限，每次星际之旅都只能带走一组支持者。

为了让所有的支持者团队能够提前知道究竟哪组支持者会被带走，UFO们设计了如下方案：

它们给彗星制定一个名称，通过将该名称和某一组支持团队的名称进行比较，从而判断这一组支持团队是否会被带走。

具体的比较方式如下：

首先，我们将彗星和支持者团队的名称通过以下方式转化为数字：

1. 每个大写字母对应一个整数，A对应1，B对应2，…，Z对应26。
2. 将名称中的每个字母转化为对应数字，再将这些数字相乘，例如，USACO对应的数字相乘为21 * 19 * 1 * 3 * 15 = 17955。
3. 将得到的乘积 mod 47 就可得到最终数字。

我们将彗星和支持者团队的名称都通过上述方式转化为最终数字后，如果两个名称对应的数字相同，那么这组支持者就将被带走。

现在，请你编写一个程序，读取彗星和支持者团队的名称，并根据上述方案判断两个名称是否匹配。

输入格式

第一行，一个由大写字母构成，长度不超过6的字符串，表示彗星的名称。

第二行，一个由大写字母构成，长度不超过6的字符串，表示支持者团队的名称。

输出格式

如果两个名称可以匹配，则输出”GO”，否则输出”STAY”。

输入样例1：

```
COMETQ
HVNGAT
```

输出样例1：

```
GO
```

```java
import java.util.Scanner;

public class Main {
    public static void main (String[] args) {
        Scanner sc = new Scanner(System.in);

        String s = sc.next();
        String n = sc.next();
        int a = 1, b = 1;
        for (int i = 0; i < s.length(); i ++) {
            a *= (int)(s.charAt(i) - 'A' + 1);
        }
        for (int i = 0; i < n.length(); i ++) {
            b *= (int)(n.charAt(i) - 'A' + 1);
        }
        if ((a % 47) == (b % 47)) {
            System.out.print("GO");
        } else {
            System.out.print("STAY");
        }
    }
}
```

