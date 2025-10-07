#项目布局概述
本项目包含多种 Android 布局实现，主要展示了 LinearLayout（线性布局）、TableLayout（表格布局）和 ConstraintLayout（约束布局）的使用方式
##布局文件详情
###1. 线性布局 - exp_linearlayout.xml  
采用垂直方向嵌套水平线性布局的方式，实现了四行四列的按钮网格布局。  
根布局为垂直方向的 LinearLayout，高度和宽度均匹配父容器  
包含 4 个子 LinearLayout（每行一个），通过layout_weight属性平均分配高度  
每行的按钮通过layout_weight设置不同比例宽度，实现灵活的列宽分配  
按钮使用自定义背景（@drawable/button），并设置了自动调整文字大小属性  
按钮间距通过layout_margin控制，内部文字边距通过padding调整  
###2. 表格布局 - exp_tablelayout.xml  
表格布局以行列结构展示类似菜单的列表内容，包含操作名称和快捷键说明。  
特点：
根布局为 TableLayout，背景色为深灰色（#1A1A1A）
通过stretchColumns="2"设置第三列可拉伸，适应不同屏幕宽度
使用 TableRow 作为行容器，每个 TableRow 包含 1-3 个 TextView
通过layout_span="3"实现跨列效果（标题行和分隔线）
使用 View 作为分隔线，增强视觉层次感
文字颜色统一设置为浅灰色（#B0B0B0），标题行使用加粗样式
适用场景： 适合展示具有清晰行列关系的数据，如菜单列表、参数配置表等。
###3. 约束布局 1 - activity_main.xml
基础约束布局示例，仅包含一个居中显示的文本。
特点：
根布局为 ConstraintLayout，匹配父容器大小
单个 TextView 通过约束条件（上下左右均约束到父容器）实现居中显示
简单展示了 ConstraintLayout 的基本用法
适用场景： 适合简单界面的快速构建，或作为复杂布局的基础容器。
###4. 约束布局 2 - exp_constraintlayout02.xml
复杂约束布局示例，实现了一个模拟太空旅行预订的界面。
特点：
多层嵌套 ConstraintLayout，实现模块化布局结构
使用layout_constraintHorizontal_weight和layout_constraintVertical_weight实现比例分配
通过约束关系精确定位元素位置，如：
顶部三个图标区域（Space Stations、Flights、Rovers）水平平均分布
中间 "DCA" 和 "MARS" 区域通过箭头图标连接
底部包含开关、文本、图片和按钮等多种元素
元素间通过 id 相互约束，形成复杂的布局关系