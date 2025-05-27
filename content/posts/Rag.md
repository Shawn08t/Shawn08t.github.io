---
title: Rag 基础-1
date: 2020-09-15T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["first"]
author: "Me"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Desc Text."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page

---
## RAG 是什么？
RAG（Retrieval Augmented Generation），检索增强生成，将外部知识库与大语言模型(LLM)结合，实现更准确和可控的文本生成。

与直接使用大模型相比，RAG 主要有以下优点：
- 提高准确性：可以引入外部知识库，从而减少回答的幻觉。
- 信息时效性：可以访问最新信息。
- 可追溯性：生成的内容有明确的信息来源。

## RAG的基本流程
从RAG的名字看，RAG包含两个步骤：检索、生成。
事实上，RAG一般包含三个步骤：索引（index）阶段、检索（Retrieval）阶段、生成(Generation)阶段。
1. 索引（index）阶段是对上传的文件进行拆分、向量化处理。
处理过程：
上传文件 -（切割器）-> 文件被拆分成块 -（embedding模型）-> 生成文本向量 -（存入）-> 向量数据库

2. （检索（Retrieval）阶段是将问题进行向量化处理后，在数据库中匹配相关向量并在参考文档中找到对应的文本块。
处理过程：
