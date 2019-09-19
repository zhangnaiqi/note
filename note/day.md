##1、计算机早期历史

算盘——>步进计算器——>差分器——>分析机——>打孔卡片制表机

##2、电子计算机

继电器——>真空管——>晶体管

1944 最大机电计算器IBM  马克一号（1秒能做3次加减法，6秒做一次乘法，15秒做一次除法）

1946宾夕法尼亚大学ENIAC第一个通用可编程计算机（5000十位数加减法/s）

BUG（由于计算机进入虫子而得名）

##3、布尔逻辑

NOT、AND、or、xor

##4、二进制

1992 Unicode编码（解决ASCII不能表示所有语言）

##5、算数逻辑单元（ALU）

包括运算单元和逻辑单元，

##6、寄存器与内存

寄存器（用来暂存指令、数据和位址）

内存（一般分为只读存储器（ROM）、随机存储器（RAM）和高速缓存存储器（cache））

##7、CPU

CPU=RAM+寄存器+ALU
CPU工作状态：取指令——>解码——>执行

# LeetCode 解题


```javascript
// 1
var twoSum = function(nums, target) {
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] == target) {
                return [i, j]
            }
        }
    }
};
// 3
var lengthOfLongestSubstring = function(s) {
    let maxLength = 0;
    let arr = [];
    for (let i = 0; i < s.length; i++) {
        if (arr.indexOf(s[i]) < 0) {
            arr.push(s[i]);
            if (arr.length > maxLength) {
                maxLength = arr.length;
            }
        } else {
            arr.splice(0, arr.indexOf(s[i]) + 1);
            arr.push(s[i]);
        }
    }
    return maxLength;
};
// 7
var reverse = function(x) {
    let a = Math.floor(Math.abs(x)).toString();
    let b = '';
    for (let i = 0; i < a.length; i++) {
        b += a[a.length - i - 1].toString()
    }
    if (Number(b) > (2 ** 31 - 1)) {
        return 0
    }
    if (x >= 0) {
        return Number(b)
    } else {
        return -Number(b)
    }
};
// 9
var isPalindrome = function(x) {
    const str = x + "";
    if (str.length === 1) {
        return true;
    }
    const length = Math.floor(str.length / 2);

    for (let i = 0, l = length; i < l; i++) {
        if (str[i] !== str[str.length - 1 - i]) {
            return false;
        }
    }
    return true;
};
// 13
var romanToInt = function(s) {
    const map = {
        I: 1,
        IV: 4,
        V: 5,
        IX: 9,
        X: 10,
        XL: 40,
        L: 50,
        XC: 90,
        C: 100,
        CD: 400,
        D: 500,
        CM: 900,
        M: 1000
    };
    let num = 0;
    for (let i = 0; i < s.length;) {
        if (i + 1 < s.length && map[s.substring(i, i + 2)]) {
            num += map[s.substring(i, i + 2)];
            i += 2;
        } else {
            num += map[s.substring(i, i + 1)];
            i++;
        }
    }
    return num;
};
// 14
var longestCommonPrefix = function(strs) {
    var re = '';
    if (!strs.length) return re;
    for (var j = 0; j < strs[0].length; j++) {
        for (var i = 1; i < strs.length; i++) {
            if (strs[i][j] != strs[0][j]) return re
        }
        re += strs[0][j];
    }
    return re;
};
// 26
var removeDuplicates = function(nums) {
    for (var i = 0; i < nums.length;) {
        if (nums[i] === nums[i + 1]) {
            nums.splice(i, 1)
        } else {
            i++
        }
    }
    return i;
};
// 27
var removeElement = function(nums, val) {
    for (var i = 0; i < nums.length;) {
        if (nums[i] === val) {
            nums.splice(i, 1)
        } else {
            i++
        }
    }
    return nums.length;
};
```


