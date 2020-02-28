# 数据库--part2

## 基因功能数据库

可用于注释基因的生物学功能，比如几处有变异的突变在功能上时候有联系。

1. Gene Ontology (http://geneontology.org/)

   主要分为三个子类：1）Biological Process (BP); 2) Molecular Function (MF); 3) Cellular Component (CC)

   一般而言根据自己需求选择其中一个注释即可，比如对于我们肿瘤来说，BP明显是最有意义的一个

   

2. KEGG (https://www.genome.jp/kegg/)

   KEGG主要分为三大类数据库、共16个数据库，可以注释出从通路、代谢物到疾病、药物等一系列信息。但值得注意的是，KEGG的开放权限非常有限，即使是免费的部分也需要使用学校账号才能下载使用。

   我们可以通过一些二级数据库来间接使用KEGG的数据，最直接的方法是使用 KEGG.db 这个R包，其他方法后面会介绍

   

3. Harmonizome (http://amp.pharm.mssm.edu/Harmonizome/dataset/Biocarta+Pathways)

   类似的数据库，收集了114个数据集的功能数据库，可对基因和蛋白进行功能注释。官网提供了API和写好的python脚本可以直接调用

   

4. DAVID (https://david.ncifcrf.gov/)

   以上的原始数据库之间常常会有很多冲突，不仅仅是结果之间，连输入文件也差异巨大，gene ID可有多达39种的表达方法，DAVID的最大贡献在于人工整合了这几大数据库，对输入文件进行了规范性校准。同样可下载、 有API。



## 进化（同源）数据库

1. Aminode (http://www.aminode.org/)

   提供了基因的/蛋白的进化描述，并且允许用户计算进化限制区域（ECR）

2. orthoDB (https://www.orthodb.org/)

   信息非常全的同源数据库，可以查找一个蛋白在各个物种的homology，以及该蛋白的进化率，并且注释了domain、功能等信息。数据可通过API调用

3. HOGENOM (http://doua.prabi.fr/databases/hogenom/home.php?contents=query)

   相较于orthoDB，数据库提供的信息很少，仅提供了蛋白、基因在各物种间的同源体，但数据库可直接下载

## 蛋白质结构域

1. Gene3D (http://gene3d.biochem.ucl.ac.uk/Gene3D/)

   不仅包含了蛋白质的各domain、motifs，还汇总了该蛋白上发现的突变，是否致病等情况。网页做的非常漂亮，值得借鉴。可直接下载，无api

   

2. InterPro (https://www.ebi.ac.uk/interpro/)

   提供了序列搜索的功能；相较于Gene3D，提供了蛋白质的整体结构，序列特征，以及在其他物种上的同源蛋白等。数据库可下载，还有一份linux上的软件可下载使用

   

3. Pfam (http://pfam.xfam.org/)

   特点是它根据蛋白的序列、结构、HMM的形态将其整合为一个个clan。数据可下载

   

4. PRINTS-S (http://130.88.97.239/PRINTS/index.php)

   蛋白质指纹数据库，包含了各种motifs。数据仅可通过搜索来进行浏览，无法下载。

   

5. PRODOM(http://prodom.prabi.fr/prodom/current/html/home.php)

   仅可通过PD ID或者序列进行搜索来浏览数据。内容相对单一，前面几个数据库均可实现。数据无法下载

   

6. PROSITE （https://prosite.expasy.org/）

   瑞士ExPASy旗下的蛋白数据库，搜索功能丰富，可以通过motif名称之类来搜索出相应蛋白。结果数据中包含了各个蛋白、domain的详解，以及相关的paper。数据可下载

   

7. SMART (http://smart.embl-heidelberg.de/)

   数据库分为一般的（Normal）和准确测序过(Genomic )的蛋白，Normal SMART当中包含了很多预测的结构，因此非常冗余。网站也仅有搜索功能，但是搜索结果可供下载

   

8. superfamily2 (http://www.supfam.org/)

   用于蛋白质及基因的结果和功能注释，注释信息均基于HMM模型SCOP2，可将结构相似的蛋白一同注释出来。数据无法下载，仅可搜索

## 蛋白间作用关系

1. BioGRID（https://thebiogrid.org/）

   全人工校准的作用关系数据库，对七万多篇文献中的上万的蛋白、基因、化学联系和表观修饰间的关系进行了阐明。数据库可直接下载，亦可使用API

   

2. DIP (https://dip.doe-mbi.ucla.edu/dip/Main.cgi)

   收集了实验论证的蛋白互作信息，需要注册使用

   

3. intAct (https://www.ebi.ac.uk/intact/)

   EMBL下的分子互作数据库，包含了基因、蛋白、RNA等等。其中软件预测的和实验验证的分为两个子集。数据每月更新，可直接下载

   

4. UCSC TFBS (http://genome.ucsc.edu/cgi-bin/hgTrackUi?hgsid=502642519_lKex7xjVm0YB4DD1qYQqwapAKDYJ&c=chr1&g=wgEncodeTfBindingSuper)

   不同于以上数据库，这个数据库的功能很专一，可用于查找某一基因的TF结合位点。主要描述的是TF与基因之间的作用关系。

## 基因相关文献查询

1. PubMed (https://www.ncbi.nlm.nih.gov/pubmed)

   原始数据库，世界上最全的文献存储地址

2. GeneRIF (https://www.ncbi.nlm.nih.gov/gene/about-generif)

   同样由ncbi提供，对PubMed和Gene进行再整理，对基因进行更加简介的描述，可直接下载（[ftp://ftp.ncbi.nih.gov/gene/GeneRIF/](ftp://ftp.ncbi.nih.gov/gene/GeneRIF/)）

3. iHOP (http://www.ihop-net.org)

   将pubmed上的信息进行提取整合，利用自然语言处理将感兴趣的基因/蛋白信息直接提取出来，并且对影响因子、发表日期等进行排序

4. CoreMine (https://www.coremine.com/)

   企业级的软件，功能类似，但是付费

5. EVEX ([http://evexdb.org](http://evexdb.org/))

   类似于ihop，使用起来非常简单，并且可以使用API直接访问。相较之下更推荐这个，iHOP的服务器非常不稳定，基本打不开

   

