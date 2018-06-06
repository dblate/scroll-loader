# scroll loader

对“滑动加载更多”的处理方法的抽象，用流行点的术语来说，算是 HOC(high order component)

## 使用

```javascript
    import ScrollLoader from 'scroll-loader';

    const el = document.getElementById('el-to-listen');
    const scrollloader = new ScrollLoader();
    
    // 当 el 元素滑动到屏幕底部时，执行 updateCnt
    scrollloader.addListener(el, updateCnt);

    // 如果涉及异步操作，那么应该返回 promise，因为在执行该函数后， scroll-loader 还有事做
    function updateCnt(page) {
        return new Promise((resolve, reject) => {
            $.ajax({
                url: '',
                data: {},
                success() {
                    // do someting here..

                    resolve();
                },
                error() {
                    reject();
                }
            })
        });
    }

```
