# D2 929. Unique Email Addresses

## 题目链接

[929. Unique Email Addresses](https://leetcode.com/problems/unique-email-addresses/)

## 题目分析

题目要求过滤重复的邮箱地址。最终返回不重复的用户名个数。  
过滤规则是：邮箱名中的`.`要被忽略，且`+`后面的所有字符都要删去。域名部分则不进行处理。

## 思路

输入是一个数组，那么我们用`foreach`就可以了。

对于数组中的每一个元素，进行如下处理：

1. 先以`@`为分隔符拆分邮箱地址为用户名部分和域名部分。

```php
$emailStruct = explode('@', $email);
```

1. 替换`.`为空字符串。

```php
$username = str_replace($emailStruct[0],'.',''); //下标0为用户名部分，下标1为域名部分
```

1. 删去`+`后面的所有字符。

```php
$usernameStruct = explode('+',$username);
$username = $usernameStruct[0];
```

这里用的是`explode`方法。  
当然，也可以用`str_pos`获取`+`的位置，再用`strtr`函数截取字符串。

1. 把用户名塞进记录用户名的数组里面。

```php
$replacedEmails[] = $username.$emailStruct[1];
```

至此，对每个邮箱地址就处理完成了。

最后，用`foreach`包住以上代码，在`foreach`外面初始化`$replacedEmails`数组，用`array_unique`去重，再`count`该数组就完成了。

## 最终代码

```php
class Solution {
    function numUniqueEmails($emails) {
        $replacedEmails = [];
        foreach($emails as $email){
            $emailStruct = explode('@',$email);
            $username = str_replace($emailStruct[0],'.','');
            $usernameStruct = explode('+',$username);
            $username = $usernameStruct[0];
            $replacedEmails[] = $username.$emailStruct[1];
        }
        return count(array_unique($replacedEmails));
    }
}
```

## 优化方案

* 直接把用户名做为数组的键值，可以省略去重步骤。

若觉得本文章对你有用，欢迎用[爱发电](https://afdian.net/@skys215)资助。

