# 中国学术出版AI政策分析方法

这是中国学术出版AI政策文本分析项目。仓库公开分析代码、环境文件、VerbAtlas相关资源、固定谓词映射和方法说明，便于查看研究流程与开展独立方法复核。

为保护尚未发表的研究成果、政策原文的再分发边界和来源附件，本仓库不公开：

- 252条政策的完整正文；
- 逐句AMR结果、事件表、网络表和详细结果报告；
- 论文工作稿、结论稿及未公开的研究材料。

完整研究包保存在作者本地。公开仓库中的`data/predicate_mapping.csv`仅用于展示固定的谓词—VerbAtlas编码结构；它不包含政策正文。

## 目录

- `src/`：切句、AMR事件抽取、VerbAtlas映射、统计和制图代码；
- `data/`：公开的语义映射材料，不含政策原文；
- `docs/`：方法、字段、边界和检查说明；
- `resources/`：VerbAtlas、字体和必要的第三方资源及许可证；
- `tests/`：代码边界测试；
- `requirements-*.txt`、`environment.yml`：运行环境说明。

## 使用方式

本仓库不能直接执行完整的252条分析。获得合法授权的自有语料后，可按如下格式运行：

```bash
python run.py analyze \\
  --corpus your_policies.csv \\
  --mapping data/predicate_mapping.csv \\
  --amr your_amr_predictions.csv \\
  --output outputs/custom
```

输入至少需要`record_id`、`title`以及`analysis_text`或`text`；AMR缓存需要包含`doc_id`、`sentence_id`、`sentence_sha256`和`amr_string`。

## 研究边界

政策文本的权利归相应发布主体。第三方资源、上游代码和许可证说明见`THIRD_PARTY_NOTICES.md`。本仓库不授予政策原文、第三方资源或上游代码的额外许可。
