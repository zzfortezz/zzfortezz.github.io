---
layout: post
title: HackerRank - Đảo chiều array
---

A left rotation operation on an array shifts each of the array's elements **1** unit to the left. For example, if **2** left rotations are performed on array **[1,2,3,4,5]**, then the array would become **[3,4,5,1,2]**. Note that the lowest index item moves to the highest index in a rotation. This is called a circular array.

---

Chúng ta có 1 array với *n* phần tử, và input đầu vào là 1 số **d** _integer_. Và chúng ra sẽ phải trả về array
đã được đổi chiều từ vị trí **d**

Ví dụ:
Input
```phpregexp
$d = 13
$array = [33, 47, 70, 37, 8, 53, 13, 93, 71, 72, 51, 100, 60, 87, 97];
```
Expected Output
```phpregexp
$array = [87, 97, 33, 47, 70, 37, 8, 53, 13, 93, 71, 72, 51, 100, 60]
```

cách xử lý là chúng ta sẽ cắt array thành 2 array khác nhau, array thứ 1 `($arr1)` sẽ từ vị trí 0 tới vị trí **d**, và array thứ 2 `($arr2)` từ vị trí **d** đến hết.
sau đó ta sẽ merge 2 array lại với nhau nhưng với vị trí đảo ngược lại 
`array_merge($arr2, $arr1)`

*Code hoàn chỉnh sẽ là:*
```phpregexp
    function rotLeft($array, $d) {
        $arr1 = array_slice($array, 0, $d);
        $arr2 = array_slice($array, $d);
        return array_merge($arr2, $arr1);
    }
```