### 导出excel时实现loading效果
> 在一次导出比较长的excel时，发现导出2-3秒后，使用者会以为没点到，会重复按
1. 者另一个页面打开
1. 设置状态导出时可以加loading、按钮置为不可点击
    - 状态可以设置，但什么时候解除呢？
    - 取巧的办法是直接loading个4-5s就重置状态
    - 上面这种呢没办法知道导出服务到底什么时候导出成功或者失败，想要知道状态就必须往服务器发送请求
    - 如果不额外发送请求是否能够解决？
    - 还真有，因为刚刚的下载请求
    - 无论导出成功或者失败都会有响应，而且还会有响应头
    - 所以我们可以响应的时候把我们需要的状态信息放到响应头中即可