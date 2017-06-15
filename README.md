##  使用方法 ##
引入

three.min.js

photo-sphere-viewer.min.js

    <script src="js/three.min.js"></script>
    <script src="js/photo-sphere-viewer.min.js"></script>            
##  HTML结构 ##

可以创建一个空的<div>来放置全景图，通过CSS来设置它的尺寸。
	`<div id="container"></div>   ` 
  
         
##  初始化插件 ##

要初始化该全景图插件，可以创建一个新的PhotoSphereViewer对象，然后在这个对象中插入一个参数对象，有两个参数是必须设置的：

    var PSV = new PhotoSphereViewer({
    // Path to the panorama
    panorama: '1.jpg',
     
    // Container
    container: div
    });    
    
##  配置参数 ##
下面是该全景图插件的所有可用配置参数：

	panorama：必填参数，全景图的路径。
	container：必填参数，放置全景图的div元素。
	autoload：可选，默认值为true，true为自动调用全景图，false为在后面加载全景图（通过.load()方法）。
	usexmpdata：可选，默认值为true，如果Photo Sphere Viewer必须读入XMP数据则为true。
	default_position：可选，默认值为{}，定义默认的位置，及用户看见的第一个点，例如：{long: Math.PI, lat: Math.PI/2}。
	min_fov：可选，默认值为30，观察的最小区域，单位degrees，在1-179之间。
	max_fov：可选，默认值为90，观察的最大区域，单位degrees，在1-179之间。
	allow_user_interactions：可选，默认值为true，设置为false则禁止用户和全景图交互（导航条不可用）。
	tilt_up_max：可选，默认值为Math.PI/2，向上倾斜的最大角度，单位radians。
	tilt_down_max：可选，默认值为Math.PI/2，向下倾斜的最大角度，单位radians。
	zoom_level：可选，默认值为0，默认的缩放级别，值在0-100之间。
	long_offset：可选，默认值为PI/360，mouse/touch移动时每像素经过的经度值。
	lat_offset：可选，默认值为PI/180，mouse/touch移动时每像素经过的纬度值。
	time_anim：可选，默认值为2000，全景图在time_anim毫秒后会自动进行动画。（设置为false禁用它）
	theta_offset：过时的选项，可选，默认值为1440，自动动画时水平方向的速度。
	anim_speed：可选，默认值为2rpm，动画的速度，每秒/分钟多少radians/degrees/revolutions。
	navbar：可选值，默认为false。显示导航条。
	navbar_style：可选值，默认为{}。导航条的自定义样式。下面是可用的样式列表：
		backgroundColor：导航条的背景颜色，默认值为rgba(61, 61, 61, 0.5)。
		buttonsColor：按钮的前景颜色，默认值为transparent。
		activeButtonsBackgroundColor：按钮激活状态的背景颜色，默认值为rgba(255, 255, 255, 0.1)。
		buttonsHeight：按钮的高度，单位像素，默认值为20。
		autorotateThickness：autorotate图标的厚度，单位像素，默认值为1。
		zoomRangeWidth：缩放的范围，单位显示，默认值50。
		zoomRangeThickness：缩放的范围的厚度，单位像素，默认值1。
		zoomRangeDisk：缩放范围的圆盘直径，单位像素，默认值为7。
		fullscreenRatio：全屏图标的比例，默认值为3/4。
		fullscreenThickness：全屏图标的厚度，单位像素，默认值为2。
	loading_msg：可选，默认值为Loading…，图片加载时的提示文字。
	loading_img：可选，默认值为null，在加载时显示的图片的路径。
	size：可选，默认值null，全景图容器的最终尺寸。例如：{width: 500, height: 300}。
	onready：可选值，默认值为null。当全景图准备就绪并且第一张图片显示时的回调函数。