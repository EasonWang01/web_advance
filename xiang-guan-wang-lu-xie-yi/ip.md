# IP

## A,  B , C 網段

IP都是以`Class A`、`Class B`、`Class C`、`Class D`來做分級

`Class A`級的IP前8個bits決定了它的`網路位址`，剩下的24個bits都是`主機位址`

`所以假設拿到 class A 網段，則可分配的 IP 位置為 2 ^ 24`

獲得一個`Class B`級IP的組織卻只有255\(2^16\)個`主機位址`能用

獲得一個`Class C`級IP的組織卻有255\(2^8\)個`主機位址`能用

## 子網路遮罩

用來判斷某個 IP 屬於哪個網域，例如 140.112.21.1/16 的 網域就是 140.112 而

Network ID 為 140.112.0.0。

> /16 代表的是 11111111 11111111 00000000 00000000 即為 \( Network Mask \)
>
> 前 16 bit 為 1，把 他跟 IP 位置做 AND 運算後會得到 Network ID

假設台灣的某個大學被分配到的網段為 140.112 ，那 140.112.0.1到 140.112.255.254都是可以分配的 IP 位置。

**範例 2**

假設學校想把192.83.167.1到192.83.167.127給電腦教室學生用

把192.83.167.128到192.83.167.254給教授及行政用

就可以把`子網路遮罩`設成255.255.255.128 

所以分配完後

```text
原本除了原本的兩組 IP 不能用
192.83.167.0 (最後8個bits為00000000 網段)
192.83.167.255 (最後8個bits為11111111 廣播位置) 

現在又多了兩組IP，每個網段的頭尾
192.83.167.127 (最後8個bits為01111111)
192.83.167.128 (最後8個bits為10000000)

這四組IP已經變成保留IP無法使用
```

推薦文章：[https://notes.andywu.tw/2018/ip%E7%AD%89%E7%B4%9A%E8%88%87%E5%AD%90%E7%B6%B2%E8%B7%AF%E9%81%AE%E7%BD%A9%E4%BB%8B%E7%B4%B9/](https://notes.andywu.tw/2018/ip%E7%AD%89%E7%B4%9A%E8%88%87%E5%AD%90%E7%B6%B2%E8%B7%AF%E9%81%AE%E7%BD%A9%E4%BB%8B%E7%B4%B9/)

相關計算工具：[http://www.subnetmask.info/](http://www.subnetmask.info/)

