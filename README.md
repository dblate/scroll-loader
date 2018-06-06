# scroll loader

对“滑动加载更多”的处理方法的抽象，用流行点的术语来说，算是 HOC(high order component)

## 使用

```javascript
    import ScrollLoader from 'scroll-loader';

    const el = document.getElementById('#el-to-listen');
    const scrollloader = new ScrollLoader();
    scrollloader.addListener(el, updateCnt);

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