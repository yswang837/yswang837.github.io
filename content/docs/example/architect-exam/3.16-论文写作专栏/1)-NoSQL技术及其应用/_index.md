---
weight: 1
title: NoSQL数据库技术及其应用
---

## 题目：NoSQL 数据库技术及其应用

&emsp;&emsp;随着互联网web2.0网站的兴起，传统关系数据库在应对web2.0网站，特别是超大规模和高并发的web2.0纯动态SNS网站上已经显得力不从心，暴露了很多难以克服的问题,而非关系型的数据库则由于其本身的特点得到了非常迅速的发展。

&emsp;&emsp;NoSQL(Not only SQL)的产生就是为了解决大规模数据集合及多种数据类型带来的挑战，尤其是大数据应用难题。目前NoSQL数据库并没有一个统一的架构，根据其所采用的数据模型可以分为4类:键值(Key-Value)存储数据库、列存储数据库、文档型数据库和图(Graph)数据库。

&emsp;&emsp;请围绕"NoSQL 数据库技术及其应用”论题，依次从以下三个方面进行论述

&emsp;&emsp;1.概要叙述你参与管理和开发的软件项目以及你在其中所担任的主要工作。

&emsp;&emsp;2.详细论述常见的 NoSQL 数据库技术及其所包含的主要内容，并说明 NoSQL 数据库的主要适用场景。

&emsp;&emsp;3.结合你具体参与管理和开发的实际项目，说明具体采用哪种NOSQL数据库技术，并说明架构设计过程及其应用效果。

---

## 摘要

&emsp;&emsp;2021年4月，我所在的国内某头部互联网公司决定搭建全新的移动设备指纹分析处理平台，旨在为集团各业务线提供高效、可靠的移动设备指纹分析、存储及唯一标识移动设备的能力，我有幸地担任本次系统开发的架构师，负责整个系统的架构设计，对项目的技术活动进行指导和协调。为了应对海量数据读写和峰值QPS达到7万的高并发场景，我们选择了非关系数据库与关系数据库相互融合的技术作为该项目在存储上的解决方案。本文介绍了常见的NoSql技术及其使用场景，同时探讨了在该项目中如何实际应用非关系数据库。实践证明：恰当地使用NoSql数据库，使得系统的开发取得了成功，目前系统已稳定运行1年多，赢得了亿级用户的一致好评。

## 正文

&emsp;&emsp;随着移动互联网的迅猛发展，手机等移动设备已经成为人们生活中不可或缺的一部分，为我们带来了更便捷的沟通交流方式。在此背景下，我就职的国内最大的社交媒体平台之一的公司，于2021年4月决定建设一套全新的移动设备指纹分析处理系统，旨在给集团提供全面的移动设备指纹分析、存储和唯一标识移动设备的能力，为公司的多元化的业务提供坚实的底层支持。移动设备的广泛应用使得此类系统的需求变得尤为迫切，我们面临着如何高效处理日活2.6亿的移动设备指纹的读写、以及峰值QPS达7万的高并发场景的问题。

&emsp;&emsp;作为这一重要项目的核心，我有幸被委以重任，担任本次系统开发的架构师，负责系统整体的架构设计，以及对项目中的技术活动进行指导和协调等。调研发现该系统需要处理海量的读写需求，同时还要在高峰时段高达7万的每秒查询数(QPS)的高并发场景下保持卓越的可用性。我意识到，即使基于读写分离、分库分表的关系型数据库集群在面对如此巨大的数据量和流量的压力时，也会显得力不从心。面对这一挑战，我决定采用一种融合了关系数据库与非关系数据库特点的解决方案，从而在存储与性能层面找到了平衡。

&emsp;&emsp;本文深入探讨了这一技术方案的实际应用。特别是，重点介绍了常见的NoSql技术及其适用场景，探讨如何在该项目中合理应用非关系数据库。

&emsp;&emsp;键值对数据库的基本单位是一对键值，其中键是数据的唯一标识符，值则是与键相关联的数据，值可以是字符串、列表、集合、有序集合、哈希表类型，这样简单的数据结构，使得其拥有非常强大的灵活性，适用于热门榜单、高速缓存等实时数据处理场景。Redis是键值对数据库的代表。

&emsp;&emsp;文档数据库可认为是键值对数据库的一个升级，升级之处在于存储的值是以Json、Bson为代表的半结构化数据；相比于键值对数据库，文档数据库拥有更为复杂的数据查询能力。通常用于存储半结构化、变化频繁或不规则的数据，适用场景通常有：日志、社交媒体数据等。其代表产品是MongoDB。

&emsp;&emsp;列式数据库的存储方式是按列存储。列式数据库中同一列的相似数据使得压缩率更高，适用于海量数据的场景；在查询分析时通常涉及到对列的聚合、统计操作使得列式数据库在这样的场景下更是游刃有余。其代表产品是HBase。

&emsp;&emsp;图数据库的基本存储单位是以节点和边组成的图模型数据，节点和边的动态增减使得图数据库拥有非常强大的灵活性，图的遍历带来了强大的查询分析能力，适用于社交网络数据，推荐系统和知识图谱等场景。其代表产品是Neo4j。

&emsp;&emsp;时间序列数据库通常以时间为索引，所以能高效地进行聚合查询，如计算平均值、求和、最大最小值、斜率以及标准差等；非常适用于监控和报警的场景，其代表产品有TSDB。

&emsp;&emsp;我权衡了关系型和非关系型数据库各自的优缺点，根据项目的实际情况，选择了关系型数据库mysql存储业务上的结构化数据，用非关系型数据库Redis、HBase、TSDB存储非结构化或者半结构化数据；将两者搭配起来共同作为本系统的数据支撑。从本项目服务的各职能部门的角度进行分类，将系统抽象成与各个职能部门对应的子系统，如商业化子系统、数仓子系统、报警子系统。

&emsp;&emsp;Redis在商业化子系统中发挥着重要的作用。该系统面临的主要问题是峰值QPS达到7万高并发的海量数据；对此，我采用了读写分离和主从同步的分布式集群架构，考虑到集团业务的复杂性，我为该系统设计了19个Redis实例，其中最大的实例是用于存储“用户与设备关系”，包含了128个端口，并且每个端口都使用了长链接的连接池保持服务的稳定性。通常来说从库负责读，主库负责写，但是由于各业务数据之间存在一定程度的耦合，使得我们需要格外注意分布式存储架构中各数据节点的一致性问题，对此我们采用了两种策略：一是对于数据一致性要求很高且修改量不大的接口(如用户修改设备名称)，永远从主库读取该数据，保证用户提交的数据能立刻被自己查询；二是对于更通用的场景，我们在客户端记录最近一次写入主库的时间戳，请求来了首先查询从库，如果从库的时间戳不够新，再去查询主库并返回数据。这两种策略都用主从同步来兜底，从而有效地保证了数据的最终一致性。为了优化系统性能、提高内存使用效率，我们对每个Redis实例中的数据都设置了合理的过期时间，这样可以确保热数据一直保存在缓存中，而冷数据则会被自动删除。此外我们还利用Redis自增key的特性，对系统中各个重要功能做了接口调用的频次限制，以确保接口调用的合理性，如：在一小时内一个IP下的同一个移动设备调用该接口不能超过1800次等。总之，通过以上优化措施，我们成功地解决了商业化子系统中的痛点问题，在降低企业服务器成本的同时，极大地提高了系统的性能和服务质量。

&emsp;&emsp;HBase在数仓子系统中扮演了重要角色。在个保法及用户授权的情况下，我们采集了移动设备本身的273项经过脱敏处理的指纹信息，包括系统类型、是否双开应用、是否手机模拟器等；商业化子系统中的4个采集指纹的接口，将每天约2.6亿的移动设备指纹的全量信息格式化到HBase的二维表中，使得该表每日数据量高达2TB。为了提高查询分析性能，我们对该表设计了按天、按系统类型分区，这种方法可以有效地将数据按照时间和系统类型进行组织，使得查询和分析操作更加高效，为项目中的各项决策提供了强有力的数据支持。

&emsp;&emsp;TSDB是报警子系统中的核心组件。通过prometheus在程序代码中埋点，将程序执行状态的实时数据不间断地写入到TSDB中，通过对这些数据按时间进行聚合查询，我们对部署在全国各地的服务器资源、redis等软件资源以及商业化子系统中的42个接口均做了翔实的报警，并将报警信息实时发送到通讯软件中。例如：该系统报警指出数据中心XX市的redis查询操作在每天早上8时左右的P99高于既定阈值等。TSDB为系统提供了可靠的时间序列数据存储和实时查询能力，其支持的实时报警，保障了系统平稳、可靠地运行。

&emsp;&emsp;经历了一年半的开发，该项目于2022年10月成功上线，并且在过去的一年多时间里，系统架构稳定运行，实现了项目的既定目标，赢得了过亿用户一致好评。虽然我们取得了这些成就，但也意识到了一些不足之处，特别是在自动化运维方面。这些挑战带给我们宝贵的经验和教训，为未来的工作提供了重要的参考，这正是我最大的收获。
