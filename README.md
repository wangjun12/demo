# 返回当前节点的父节点
/**
 * data 待处理的数组
 * key 待处理的url
 * 
 */
 ```js
function getParentNode2(data, key) {
    for (let i = 0; i < data.length; i++) {
        if (data[i].children?.length) {
            if (data[i].children.some((item) => item.url === key)) {
                return data[i]
            } else {
                const temp = getParentNode2(data[i].children, key)
                if (temp) return temp
            }
        }
    }
    return null
}
```
