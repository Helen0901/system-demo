# Tokyo Seafood Order System

一个单文件餐厅点餐与后台管理系统，可直接用浏览器打开 `index.html` 运行。
填入 Firebase 配置后，订单和菜单会通过云端实时同步。

## 功能

- 菜品分类浏览与购物车
- 支付方式选择
- 桌号、人数、备注记录
- 后台订单状态管理
- 订单筛选、搜索、CSV 导出
- 菜品上下架管理
- 本地浏览器存储数据
- Firebase Realtime Database 云端同步

## 使用

直接打开 `index.html`。

如果部署到 GitHub Pages，选择仓库根目录作为发布来源即可。

## 联网版配置

1. 打开 [Firebase Console](https://console.firebase.google.com/)
2. 创建项目
3. 添加一个 Web App
4. 创建 Realtime Database
5. 把 Firebase 提供的 `firebaseConfig` 填到 `index.html` 里的 `FIREBASE_CONFIG`
6. 发布到 GitHub Pages

测试阶段可以先使用下面的 Realtime Database 规则：

```json
{
  "rules": {
    "restaurants": {
      "$restaurantId": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

这套规则方便演示，但任何知道网址的人都能读写数据。正式使用前建议改成需要登录或只允许店员写后台状态。
