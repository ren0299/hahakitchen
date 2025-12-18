# 微信分享调试指南

## 当前配置

- **网站 URL**: https://www.hahakitchen.com.au/
- **Open Graph 图片**: https://www.hahakitchen.com.au/image/og.png
- **标题**: 哈哈私厨 | 墨尔本
- **描述**: 体验地道美味与欢乐用餐。欢迎来到哈哈私厨，在这里卓越的烹饪技艺与温馨的待客之道完美融合。

## 微信分享不显示的常见原因

### 1. 图片格式问题
微信可能对 PNG 格式支持不佳，建议使用 JPG 格式：
- 当前：`og.png`
- 建议：转换为 `og.jpg` 或同时提供两种格式

### 2. 图片尺寸要求
- 推荐尺寸：1200x630px（1.91:1 比例）
- 文件大小：建议小于 300KB
- 格式：JPG 或 PNG（JPG 更推荐）

### 3. 微信缓存问题
微信会缓存 Open Graph 信息，需要清除缓存：
- 方法1：使用微信的分享调试工具（如果有）
- 方法2：在链接后添加参数 `?v=时间戳` 强制刷新
- 方法3：等待 24-48 小时让缓存自动更新

### 4. 图片可访问性
确保图片 URL 可以公开访问：
- 测试：在浏览器中直接访问 `https://www.hahakitchen.com.au/image/og.png`
- 必须返回 200 状态码
- 不能有访问限制或需要登录

### 5. HTTPS 要求
- 所有 URL 必须是 HTTPS（不是 HTTP）
- 图片 URL 也必须是 HTTPS

### 6. 域名验证
- 确保 `www.hahakitchen.com.au` 正确指向您的网站
- 检查 DNS 配置是否正确

## 调试步骤

### 步骤 1：验证图片可访问
在浏览器中打开：
```
https://www.hahakitchen.com.au/image/og.png
```
应该能看到图片，而不是 404 错误。

### 步骤 2：检查 Open Graph 标签
使用在线工具检查：
- Facebook Sharing Debugger: https://developers.facebook.com/tools/debug/
- 输入 URL: `https://www.hahakitchen.com.au/`
- 查看是否能正确抓取 Open Graph 信息

### 步骤 3：测试图片 URL
在浏览器中直接访问图片 URL，确认：
- 图片可以正常显示
- 返回正确的 Content-Type（image/png 或 image/jpeg）
- 没有 CORS 限制

### 步骤 4：清除微信缓存
如果之前分享过这个链接：
1. 在微信中长按链接
2. 选择"刷新"或"重新加载"（如果有）
3. 或者等待一段时间后重试

### 步骤 5：使用新链接测试
在链接后添加随机参数：
```
https://www.hahakitchen.com.au/?v=123456
```
这样可以绕过微信的缓存。

## 建议的改进

1. **将 PNG 转换为 JPG**
   - 微信对 JPG 格式支持更好
   - 文件大小通常更小

2. **优化图片尺寸**
   - 确保是 1200x630px
   - 压缩图片大小到 300KB 以下

3. **添加备用图片格式**
   - 同时提供 og.png 和 og.jpg
   - 在 Open Graph 中使用 JPG 版本

## 当前配置检查清单

- [x] Open Graph 标签已添加
- [x] 使用正确的域名 (hahakitchen.com.au)
- [x] 图片 URL 使用 HTTPS
- [x] 添加了微信兼容标签
- [ ] 图片格式（建议改为 JPG）
- [ ] 图片可访问性验证
- [ ] 微信缓存清除

## 联系支持

如果问题仍然存在，可能需要：
1. 检查服务器配置
2. 验证 DNS 设置
3. 检查网站部署状态
4. 联系微信技术支持（如果有）

