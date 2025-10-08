项目布局概述
===
本项目包含多种 Android 布局实现，主要展示了 LinearLayout（线性布局）、TableLayout（表格布局）和 ConstraintLayout（约束布局）的使用方式  

布局文件详情
---
1. 线性布局 - exp_linearlayout.xml  
布局采用垂直方向的线性布局作为根布局，内部包含四个水平方向的线性布局（每行一个），每个水平布局中包含 4 个 Button 控件。通过设置不同的 layout_weight 属性，使按钮在每行中占据不同比例的宽度，同时使用 autoSizeTextType 实现文本自适应大小。  
2. 表格布局 - exp_tablelayout.xml  
本布局文件是一个基于 Android TableLayout 的示例，展示了表格布局的核心用法：  
布局包含标题行、多个功能行、分隔线行，整体为固定3列结构，根布局为 TableLayout，通过android:stretchColumns="2"设置第3列自动拉伸以填充剩余空间；  
标题行和分隔线通过layout_span="3"实现跨列效果；  
功能行每行含3个TextView，第 1 列用于占位或显示 “X” 标识，第2列显示功能名称，第3列显示对应快捷键并右对齐。  
3. 约束布局 1 - activity_main.xml  
本布局文件基于 ConstraintLayout 实现了一个计算器界面，整体采用约束布局的灵活特性构建：  
根布局ConstraintLayout占满屏幕，通过约束关系精确定位各控件。顶部是标题 TextView，以深绿色背景显示 “ConstraintLayoutTest”，通过约束与父布局顶部、左右边缘对齐，确保居中显示。  
标题下方是输入区域，包含 “Input” 标签和输入框，输入框背景为浅灰，文本右对齐（显示 “0.0”），通过约束与父布局左右边缘对齐，宽度自适应。  
核心的按键区域按4列网格排列，包含数字键、运算符键、小数点和等号，所有按钮宽度设为0dp并通过layout_constraintHorizontal_weight="1"实现水平权重分配，确保列宽均匀；    
每行按钮通过 top_toBottomOf 约束与上一行按钮关联，左右通过 start_toEndOf 和 end_toStartOf 相互约束，配合margin控制间距，形成整齐的网格结构。  
4. 约束布局 2 - exp_constraintlayout02.xml  
本布局文件基于ConstraintLayout实现了一个航天主题界面，通过嵌套约束布局和约束关系构建多层级结构：  
根布局占满屏幕，顶部区域包含三个水平分布的功能模块（Space Stations、Flights、Rovers），每个模块由ConstraintLayout包裹图标与文字，通过 layout_constraintHorizontal_weight="1" 实现三等分宽度，图标居中显示，文字位于图标下方且居中对齐。  
中间区域展示出发地与目的地信息，以绿色背景的文本框分别显示 “DCA” 和 “MARS”，中间用双向箭头图标连接，三者通过约束形成水平排列的整体结构，宽度自适应屏幕。其中，先声明DCA，再声明MARS，最后声明双向箭头，且双向箭头图标的左右外边距设置为负，以达到图示效果。  
下方区域包含 “One Way” 开关、“1 Traveller” 文本框、小型火箭图标、星系图标和 “DEPART” 按钮，各元素通过约束明确位置关系，开关和文本框居左排列，图标按层级分布，按钮位于底部且宽度占满屏幕。
