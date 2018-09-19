# react-native-loading-image
基于React Native官方组件Image封装的具备加载生命周期视觉反馈的组件,具体实现功能如下：
* 网络图片Pending状态渲染，提供闪烁动画、loading.gif两种方式
* 网络图片Error状态渲染
* 继承官方Image组件的所有属性

## Installation

```bash
npm install react-native-loading-image --save
```

## Import into your project
```js
import LoadImage from 'react-native-loading-image';
```

## Examle useage

```js
<LoadImage 
  source={{ uri: `${Config.Host}/Assets/Images/Home/WechatIMG600.jpg` }} 
  style={[Styles.articleAvatar, { width: ARTICLE_PICUTRE_WIDTH, height: ARTICLE_PICUTRE_HEIGHT }]} 
  type='load'
  defaultSource={require("../../Image/default.png")}
  
  onLoadStart={this.onLoadStart.bind(this)}
  onLoadEnd={this.onLoadEnd.bind(this)}
  onLoad={this.handleImageLoaded.bind(this)}
  onError={this.handleImageErrored.bind(this)}
/>
```

## Properties
属性  | 描述    | 类型  | 默认    
------ | ------ | ------  | ------
source  | 图片资源 | ``` PropTypes.oneOfType([ PropTypes.object, PropTypes.number ]) ``` | 
defaultSource | 加载失败渲染的图片资源  | ```  PropTypes.oneOfType([ PropTypes.object, PropTypes.number ])  ``` | 默认渲染背景为'#eceff4'的同规格View  
type | 图片加载方式  | ``` PropTypes.oneOf(["animated", "load"]) ```  | 提供两种方式，"animated"代表北京闪烁动画，"load"代表gif加载动画，默认为"animated" 。

