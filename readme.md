项目布局概述
===
本项目包含多种 Android 布局实现，主要展示了 LinearLayout（线性布局）、TableLayout（表格布局）和 ConstraintLayout（约束布局）的使用方式   

布局文件详情   
---
1. 线性布局 - exp_linearlayout.xml  
采用垂直方向嵌套水平线性布局的方式，实现了四行四列的按钮网格布局：根布局与子布局通过layout_weight=1实现垂直方向均匀分配；按钮宽设0dp，按不同layout_weight分配水平宽度，搭配5dp间距；按钮文本通过autoSizeTextType自适应尺寸。
2. 表格布局 - exp_tablelayout.xml  
本布局文件是一个基于Android TableLayout的示例，展示了表格布局的核心用法：根布局 TableLayout 采用深灰色背景，宽度和高度均占满父容器，且通过 android:stretchColumns="2" 设置第3列自动拉伸以填充剩余空间；布局包含标题行、多个功能行、分隔线行，整体为固定 3 列结构。标题行的 TextView通过android:layout_span="3"横跨3列；功能行每行含3个TextView，第1列用于占位或显示 “X” 标识，第2列显示功能名称，第3列显示对应快捷键并右对齐；分隔线行则通过横跨3列的View实现。
3. 约束布局 1 - activity_main.xml   
本布局文件基于ConstraintLayout实现了一个计算器界面，整体采用约束布局的灵活特性构建：根布局 ConstraintLayout 占满屏幕，通过约束关系精确定位各控件。顶部是标题 TextView，以深绿色背景显示 “ConstraintLayoutTest”，通过约束与父布局顶部、左右边缘对齐，确保居中显示。标题下方是输入区域，包含 “Input” 标签和输入框，输入框背景为浅灰，文本右对齐（显示 “0.0”），通过约束与父布局左右边缘对齐，宽度自适应。核心的按键区域按4列网格排列，包含数字键、运算符键、小数点和等号，所有按钮宽度设为0dp并通过 layout_constraintHorizontal_weight="1" 实现水平权重分配，确保列宽均匀；每行按钮通过 top_toBottomOf 约束与上一行按钮关联，bottom_toTopOf约束与下一行按钮关联，左右通过 start_toEndOf 和 end_toStartOf 相互约束，形成整齐的网格结构。
4. 约束布局 2 - exp_constraintlayout02.xml   
本布局文件基于 ConstraintLayout 实现了一个航天主题界面，通过嵌套约束布局和精细的约束关系构建多层级结构：根布局占满屏幕，顶部区域包含三个水平分布的功能模块（Space Stations、Flights、Rovers），每个模块由 ConstraintLayout 包裹图标与文字，通过layout_constraintHorizontal_weight="1" 实现三等分宽度，图标居中显示，文字位于图标下方且居中对齐。中间区域展示出发地与目的地信息，以绿色背景的文本框分别显示 “DCA” 和 “MARS”，中间用双向箭头图标连接，三者通过约束形成水平排列的整体结构，宽度自适应屏幕，其中先声明dca，再声明mars，最后声明双向箭头，且设置负边距来让双向箭头向左右方向 “延伸”。下方详情区域包含 “One Way” 开关、“1 Traveller” 文本框、小型火箭图标、星系图标和 “DEPART” 按钮，各元素通过约束明确位置关系 。
