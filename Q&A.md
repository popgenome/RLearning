# Questions about R usage

1. Q：绝大部分文件处理依靠Linux和excel完成，R不太会用，也不知道从何下手。
  
   A：R主要用于统计模型和科研作图，超大文本数据处理并非强项。建议用linux将数据处理成标准输入格式（tab分隔、等列数等等），在个人电脑上进行作图优化，大文本数据用优化后的脚本在服务器上投递任务。

2. Q：怎么快速找到合适的包？符合要求的包很多，在众多选项之中如何精准抓住我们要的？有什么判断依据？

   A：建议使用有引用、常维护、文档清晰的包，可以根据文献引用、下载量、更新频率判断是否合适。优先使用R studio、Bioconductor的包。
   
3. Q：如何快速上手我们下载的包，可以通过哪些命令，或浏览哪些文件来掌握需要知晓的内容？

   A：常用包如ggplot2应当单独学习，了解设计原理和基本功能。为了解决某一问题而下载的包，可以运行manual中quick start部分（或者相应的基本函数）跑通pipeline，在用部分或全部数据快速得到结果；之后可通过manual或者help(package="pkg")浏览其他函数，达到更好的使用。
      

# Questions about I/O

1. Q：读入数据时，excel表格生成的格式读取容易报错，如读取CSV格式时，有的时候需要加一个UTF=8的条件才不会报错，不知道为什么
   
   A：使用txt作为输入数据格式，office格式输入经常会遇到问题。
   
2. Q：中文标题读取会报错或者读进去乱码
   
   A：改用英文header，空格用下划线或者句号代替。

3. Q：如何同时读取一个文件夹下多个同类文件
   
   A：可以将文件名存于vector，使用for循环读入。
   
4. Q：输入文件后，有空值，影响后续操作，是否可以通过参数设置，容纳空值，若以其他填充该使用什么形式？（0/NA/平均值?）
   
   A：空值主要会影响对齐，建议输入数据中用tab分隔列；其次对于NA值，可以na.strings参数设定；若无必要不进行空位填充，保持NA。


# Questions about data manipulation

# Questions about graphics
  
1. Q：不同数据类型应该以什么形式呈现？（如什么时候画点图、线图、箱线图、热图）
   
   A：作图是为了更好的理解数据（通常分为numerical和categorical），而不同图形适用不同数据类型的不同展示场景。具体而言，（1）一维数值根据数据类型，对数值数据用histogram/density line展示（可结合如mean/variance/median/IQR等统计数值），分类数据可以用barplot展示count；（2）二维数据，均为数值数据可用scatterplot散点图展示关系（可附以回归线，对于太密的点使用smoothScatter函数进行color density转化），数值和类别数据使用boxplot/violin plot或者叠加密度分布（后者不易超过6个），均为类别数据使用列联表统计可用热图展示；（3）三维数据，均为数值数据的话可用三维散点图表示，但通常使用二维数据的思路作图，将次要信息以颜色/symbol大小等展示，该策略也适用于第三维数据是类别数据；（4）高维数据，思路与三维数据类似，根据图形复杂度考虑使用分面facet函数进行分别展示。


# Questions about statistics

# Questions about R packages

# Questions about R development
