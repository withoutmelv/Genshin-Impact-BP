# BP网页

1. BP角色设计
    采用面向对象，将角色抽象为类
    ```js
    class character {
        this.name; // 名称
        this.image; // 图片
        this.elementType; // 元素类型
        this.stars; // 星级
        this.banVoice; // ban掉的语音
        this.chooseVoice; // 选择的语音
        this.status; // 状态 （未选择，ban, 选择）
    }
    ```
2. 主要模块
    <el-aside> 左      <el-container>中     <el-aside>右

3. ban选数量，可设置，分为上下场两次ban选
4. 搜索， 支持名称模糊搜索，支持元素类型分类查找
5. BAN选点击时，播报语音，语音分为BAN和选两种不同类型的 (背景音乐)
6. 倒计时，中间板块，时间到之后，自动选取角色
7. 蓝红双方，选方 + 如何对应到指定方（路由参数），没有方位参数的属于观赛
8. 房间号（路由参数）
9. websocket