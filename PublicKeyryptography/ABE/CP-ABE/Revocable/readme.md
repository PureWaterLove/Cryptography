# 综述
### 2023年, 李莉等
目前比较新的综述，缺点是不够深入全面
李莉,朱江文,杨春艳.基于属性加密的可撤销机制研究综述[J].信息网络安全,2023,23(04):39-50.

# 可撤销CP-ABE
## 直接撤销
### 2007年, Ostrovsky等
提出第一种直接撤销的CP-ABE方案, 在被撤销用户中加入标识"非", 使之不能解密对应数据. 缺陷是效率不高.
Rafail Ostrovsky, Amit Sahai, and Brent Waters. 2007. Attribute-based encryption with non-monotonic access structures. In Proceedings of the 14th ACM conference on Computer and communications security (CCS '07). Association for Computing Machinery, New York, NY, USA, 195–203.
### 2009年, Attrapadung等
基于广播加密机制提出一种直接撤销CP-ABE方案. 效率高.
Attrapadung N., Imai H. (2009) Conjunctive Broadcast and Attribute-Based Encryption. In: Shacham H., Waters B. (eds) Pairing-Based Cryptography – Pairing 2009.
### 2009年, Attrapadung等
新提出一种混合撤销的CP-ABE方案, 支持数据拥有者选择直接和间接撤销的方式, 但之后不能更改.
Attrapadung N., Imai H. (2009) Attribute-Based Encryption Supporting Direct/Indirect Revocation Modes. In: Parker M.G. (eds) Cryptography and Coding. IMACC 2009.
### 2009年, Zhang等
提出一种支持与门的CP-ABE方案, 支持直接属性撤销. 缺陷是表达力不足.
Zhang, Yinghui & Chen, Xiaofeng & Li, Jin & Li, Hui & Li, Fenghua. (2013). FDR-ABE: Attribute-Based Encryption with Flexible and Direct Revocation. Proceedings - 5th International Conference on Intelligent Networking and Collaborative Systems, INCoS 2013. 38-45. 10.1109/INCoS.2013.16.
### 2014年, 张应辉等
提出基于与门访问结构的密文恒定的可撤销CP-ABE方案. 缺陷是表达力不足.
张应辉, 郑东, 李进, 李晖 密文长度恒定且属性直接可撤销的基于属性的加密 Journal Article 2014 密码学报 10.13868/j.cnki.jcr.000044 465-480.
### 2017年, Wang等
基于合数阶群提出直接撤销的CP-ABE方案. 在标准模型下, 基于双系统加密技术证明了该方案的适应性安全.
Wang, H., Zheng, Z., Wu, L. et al. New directly revocable attribute-based encryption scheme and its application in cloud storage environment. Cluster Comput 20, 2385–2392 (2017).
### 2018年, Liu等
提出有效直接撤销CP-ABE方案, 通过在密文嵌入撤销列表实现撤销, 仅包含撤销用户的未过期私钥, 所以撤销列表很短.
Liu J.K., Yuen T.H., Zhang P., Liang K. (2018) Time-Based Direct Revocable Ciphertext-Policy Attribute-Based Encryption with Short Revocation List. In: Preneel B., Vercauteren F. (eds) Applied Cryptography and Network Security. ACNS 2018.

## 间接撤销
### 2006年, Pirretti等
提出第一个实现用户间接撤销的CP-ABE方案. 为每个用户属性设置有效期, 属性授权周期性发布密钥更新参数, 如果属性有效期到了, 属性授权停止更新该属性的参数, 进而完成属性撤销. 缺陷是要求授权者需要时刻在线进行更新操作, 而且拥有者发布密文时需要和授权确定有效期.
Matthew Pirretti, Patrick Traynor, Patrick McDaniel, and Brent Waters. 2006. Secure attribute-based systems. In Proceedings of the 13th ACM conference on Computer and communications security (CCS '06). Association for Computing Machinery, New York, NY, USA, 99–112.
### 2007年, Bethencourrt等
第一篇经典的CP-ABE, 基于访问树构造, 是对前一个方案的优化, 用属性终止日期代替有效期, 将密文与时间关联(密钥也和时间关联), 解密时需要密钥关联时间大于密文关联时间才能成功(终止日期之前). 方案不需要数据拥有者和授权者进行协商有效期, 但是仍需要授权者定期更新.
J. Bethencourt, A. Sahai and B. Waters, “Ciphertext-Policy Attribute-Based Encryption,” 2007 IEEE Symposium on Security and Privacy (SP '07), 2007, pp. 321-334.
### 2010年, Liang等
在上面研究的基础上, Liang等为了解决授权者需要定期更新的负担, 提出基于二叉树结构实现的用户撤销CP-ABE方案. 通过发布公钥参数更新密钥, 不过是定时发布, 所以虽然不用授权者实时更新密钥, 但是不能立即撤销. 而且需要授权者参与用户撤销, 增加了授权者的负担.
Liang, Xiaohui & Lu, Rongxing & Lin, Xiaodong. (2010). Ciphertext Policy Attribute Based Encryption with Efficient Revocation.

## 用户撤销




## 属性撤销
### [2011年, Hur等](https://doi.org/10.1109/TPDS.2010.203)
提出第一种具有属性级撤销能力的CP-ABE方案, 增强了用户访问控制的前向安全和后向安全, 但由于KEK密钥是对用户通用的(不同用户没有区别), 所以不能抵抗已撤销用户和未撤销用户的合谋攻击.
Hur, Junbeom & Noh, Dong Kun. (2011). Attribute-Based Access Control with Efficient Revocation in Data Outsourcing Systems. IEEE Transactions on Parallel and Distributed Systems, 22. 1214 - 1221. 10.1109/TPDS.2010.203.

### [2011年, Yang等](https://dl.acm.org/doi/10.1145/2484313.2484383)
提出云存储环境下支持细粒度属性撤销的CP-ABE方案, 相对Hur等的工作有所优化, 不需要数据拥有者实时在线, 不需要云服务器协作访问控制. 但是安全性是基于随机预言模型证明, 不够理想.
Yang, Kan & Jia, Xiaohua & Ren, Kaili. (2013). Attribute-based fine-grained access control with efficient revocation in cloud storage systems. ASIA CCS 2013 - Proceedings of the 8th ACM SIGSAC Symposium on Information, Computer and Communications Security. 523-528. 10.1145/2484313.2484383.

### [2018年, Xue等](https://doi.org/10.1016/j.ins.2018.02.015)
基于非单调访问结构提出一种细粒度属性撤销的CP-ABE方案, 缺陷是基于合数阶群构造, 效率低下.
Xue, Liang & Yu, Yong & Li, Yannan & Au, Man Ho & Du, Xiaojiang & Yang, Bo. (2018). Efficient Attribute-based Encryption with Attribute Revocation for Assured Data Deletion. Information Sciences. 479. 10.1016/j.ins.2018.02.015.

### [2018年, 闫玺玺等](http://netinfo-security.org/CN/abstract/abstract6372.shtml#1)
提出具有隐私保护和支持用户撤销的CP-ABE方案, 但是不能抵抗已撤销用户和未撤销用户的合谋攻击.
闫玺玺, 叶青, 刘宇; 云环境下支持隐私保护和用户撤销的属性基加密方案, 信息网络安全, Netinfo Security

### [2021年, Tu等](https://doi.org/10.1016/j.comnet.2021.108196)
基于属性群密钥的撤销, 访问策略是LSSS, 但是密钥管理的结构是二叉树结构
