<!--
 * @Author: liujie tiandiweb@qq.com
 * @Date: 2022-11-28 11:14:46
 * @LastEditors: liujie tiandiweb@qq.com
 * @LastEditTime: 2022-11-28 11:53:56
 * @FilePath: \mk-webd:\work\svgdemo\css-scale2\README.md
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
# css-scale
屏幕适配插件，采用scale模式，只需要简单配置即可实现scale。
# Usage
调用函数 cssScale(_scaleSplitPix,_effectScreen,__config);
_scaleSplitPix：决定缩放时基于的像素。

    例子：var _scaleSplitPix = {
			minPix: 1766,//当屏幕在小屏时候，以1766进行缩放。
			maxPix: 1920,//当屏幕在大屏时候，以1920进行缩放。
		};
		
_effectScreen：生效的屏幕尺寸

    例子：var _effectScreen = {
			minScreenSize: 1540,//宽度小于1540像素的屏幕为小屏
			maxScreenSize: 1920,//宽度大于1920像素的屏幕为大屏。
		};
		
__config：其他配置

    例子：var __config = {
			forceMinScale:false,//在大屏时是否强制开启缩放。
			forbidMinScale:false,//在大屏时候，是否禁止进行缩放
			selector:'#response',//需要缩放的容器，
			parentSelector:'#app',//需要缩放容器的父容器，父容器的父节点的宽高需要100%，如果是body，则 body和html都要 width：100%，height：100%。
			// boxMinWidth:900,
			// boxMinHeight:450,
			// enable:false,//是否开启功能 false禁用，true 任何情况都缩放 ，不设置则按照条件
			onScale:function(scale){//缩放后调用
                //参数 scale：缩放率
				console.log('缩放完成，缩放率:'+scale)
			},
			onReady:function(isScale){//准备缩放时候调用 
                //参数 isScale：根据屏幕判断是否需要进行缩放
				console.log('你的屏幕是否需要缩放:'+isScale)
			},
		};
