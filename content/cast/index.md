---
title: "CAST"
author_profile: false
---

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
<link rel="stylesheet" href="/assets/css/project-page.css">

<div class="project-container">

  <header class="project-header">
    <div class="project-venue-badge"><i class="fas fa-award"></i> ACL 2026  Findings 论文集</div>
    <h1 class="project-title">CAST：实现基于LLM的稳定文本分析以支持数据分析</h1>
    <div class="project-subtitle">通过算法提示与稳定思维实现一致性</div>

    <p class="pp-hero-tagline">
      基于LLM的文本分析在不同运行轮次间不稳定，这对数据分析而言是不可接受的。<strong>CAST</strong>通过约束潜在推理路径，在不牺牲质量的前提下提供一致且近乎确定性的输出。
    </p>
    
    <div class="project-authors">
      <a href="https://jxtse.github.io">Jinxiang Xie</a><sup>1</sup>,
      Zihao Li<sup>2</sup>,
      Wei He<sup>3</sup>,
      Rui Ding<sup>4</sup>,
      Shi Han<sup>4</sup>,
      Dongmei Zhang<sup>4</sup>
    </div>
    <div class="affiliations">
      <sup>1</sup>南京大学 &nbsp;|&nbsp;
      <sup>2</sup>清华大学 &nbsp;|&nbsp;
      <sup>3</sup>北京大学 &nbsp;|&nbsp;
      <sup>4</sup>微软研究院
    </div>

    <div class="links-bar">
      <a href="https://arxiv.org/abs/2602.15861" class="btn-arxiv" target="_blank"><i class="fas fa-file-alt"></i> 论文</a>
      <a href="https://arxiv.org/pdf/2602.15861" class="btn-pdf" target="_blank"><i class="fas fa-file-pdf"></i> 全文</a>
      <a href="https://github.com/jxtse/CAST-text-analysis" class="btn-code" target="_blank"><i class="fab fa-github"></i> 代码</a>
    </div>
  </header>

  <section class="teaser-section">
    <img src="/images/cast-fig2-framework.png" alt="CAST Framework Overview" class="teaser-image">
    <div class="teaser-caption">
      <strong>图 1：</strong>CAST框架总览。传统方法（左）采用不受控的推理路径，导致输出分布宽泛且高熵。CAST（右）通过算法提示（Algorithmic Prompting）和三思而后言（Thinking-before-Speaking）缓解不稳定性，将生成过程压缩为集中尖峰状的输出分布。
    </div>
  </section>

  <section class="abstract-section">
    <div class="abstract-title"><i class="fas fa-align-left"></i> 摘要</div>
    <div class="abstract-text">
      表格数据的文本分析依赖两个核心操作：用于语料级主题提取的<strong>摘要（summarization）</strong>和用于行级标注的<strong>标记（tagging）</strong>。将这些任务交给大语言模型（LLM）的一个关键局限在于，它们无法达到数据分析所要求的<em>输出稳定性</em>的高标准。
      <br><br>
      为解决这一问题，我们提出了<strong>CAST</strong>（<strong>C</strong>onsistency via <strong>A</strong>lgorithmic Prompting and <strong>S</strong>table <strong>T</strong>hinking，通过算法提示与稳定思维实现一致性），一个通过约束模型潜在推理路径来提升输出稳定性的框架。CAST结合了两种机制：（i）<strong>算法提示（Algorithmic Prompting）</strong>，为有效的推理转移提供程序化支架；（ii）<strong>三思而后言（Thinking-before-Speaking）</strong>，在最终生成之前强制明确显式的中间承诺。
      <br><br>
      为衡量进展，我们引入了<strong>CAST-S</strong>和<strong>CAST-T</strong>——分别面向要点式摘要和标记任务的稳定性评估指标，并验证了它们与人类判断的一致性。在多个LLM骨干网络上的公开基准测试实验表明，CAST在所有基线方法中始终取得最佳稳定性，稳定性评分最高提升<strong>16.2%</strong>，同时保持或提高了输出质量。
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">主要贡献</h2>
    <div class="pp-contrib-grid pp-fadeup-stagger">
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">01</div>
        <h3 class="pp-contrib-title">TADA的形式化</h3>
        <p class="pp-contrib-text">我们将面向数据分析的文本分析（TADA）形式化为一个以表格为中心的新范式，强调<strong>稳定性作为功能上的必要条件</strong>，以将概率性LLM输出集成到确定性的OLAP工作流中。</p>
      </div>
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">02</div>
        <h3 class="pp-contrib-title">CAST框架</h3>
        <p class="pp-contrib-text">一种通过<strong>算法提示</strong>和中间承诺约束生成过程的新方法，在不依赖昂贵的搜索方法的情况下降低潜在路径的熵。</p>
      </div>
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">03</div>
        <h3 class="pp-contrib-title">稳定性指标</h3>
        <p class="pp-contrib-text">我们引入<strong>CAST-S</strong>和<strong>CAST-T</strong>，一种结合语义匹配与顺序敏感性（Kendall's Tau）的稳定性评估指标，以捕捉人类感知的一致性。</p>
      </div>
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">04</div>
        <h3 class="pp-contrib-title">强实证结果</h3>
        <p class="pp-contrib-text">在多个LLM骨干网络上实现最高<strong>16.2%的稳定性评分提升</strong>，且准确率无下降。</p>
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">方法</h2>
    <p style="font-size: 1.05em; line-height: 1.7; color: #444; margin-bottom: 25px;">
      CAST通过两种互补机制约束LLM的潜在推理轨迹来解决不稳定问题：
    </p>
    
    <div class="method-grid">
      <div class="method-card">
        <h3><i class="fas fa-sitemap"></i> 算法提示（Algorithmic Prompting）</h3>
        <p>为任务指定一个算法化支架，将经典的确定性工作流转化为结构化的提示序列。该支架充当有效推理转移的强先验，从而有效剪枝高熵路径。</p>
      </div>
      <div class="method-card">
        <h3><i class="fas fa-brain"></i> 三思而后言（Thinking-before-Speaking）</h3>
        <p>通过要求模型在输出最终结果之前产生明确定义的中间状态（领域、主题模式、聚类）来强制执行支架。通过提交这些中间状态，模型遵循一条更稳定的推理路径。</p>
      </div>
    </div>

    <div class="figure-block">
      <img src="/images/cast-fig1-tada.png" alt="TADA Operations">
      <div class="figure-caption">
        <strong>图 2：</strong>TADA中摘要与标记操作示意图。这些原子操作可以组合复用于复杂的TADA任务中。
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">实证观察</h2>
    <p style="font-size: 1.05em; line-height: 1.7; color: #444; margin-bottom: 20px;">
      我们通过实验证明，要求相关的中间状态确实能显著锐化模型的输出分布。如下所示，CAST产生了最尖锐、最集中的分布，表明运行间稳定性得到了实质性提升。
    </p>
    
    <div class="figure-block">
      <img src="/images/cast-fig3-kde.png" alt="Output Length Stability">
      <div class="figure-caption">
        <strong>图 3：</strong>不同提示策略下的输出长度稳定性。经KDE平滑后的摘要长度分布比较了：（i）直接提示、（ii）不相关中间状态、（iii）相关中间状态和（iv）完整CAST提示。CAST产生了最尖锐的分布，输出紧密围绕一个中心值。
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">实验结果</h2>
    
    <div class="results-grid">
      <div class="result-item">
        <div class="result-number">16.2%</div>
        <div class="result-label">稳定性评分最大提升</div>
      </div>
      <div class="result-item">
        <div class="result-number">32</div>
        <div class="result-label">数据集-查询对评估</div>
      </div>
      <div class="result-item">
        <div class="result-number">5,100+</div>
        <div class="result-label">涵盖4个不同领域的项目</div>
      </div>
    </div>

    <div class="figure-block">
      <img src="/images/cast-fig4-tagging.png" alt="Tagging Pipeline">
      <div class="figure-caption">
        <strong>图 4：</strong>用于标记任务的CAST框架，展示了从查询分解和领域识别开始，引导核心算法提示阶段，并以输出验证结束的流水线。
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">引用</h2>
    <div class="bibtex-section">
      <button class="bibtex-copy-btn" onclick="navigator.clipboard.writeText(this.nextElementSibling.innerText);this.textContent='已复制';setTimeout(()=>this.textContent='复制',2000);">复制</button>
      <div class="bibtex-code">@misc{xie2026castachievingstablellmbased,
      title={CAST: Achieving Stable LLM-based Text Analysis for Data Analytics}, 
      author={Jinxiang Xie and Zihao Li and Wei He and Rui Ding and Shi Han and Dongmei Zhang},
      year={2026},
      eprint={2602.15861},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2602.15861}, 
}</div>
    </div>
  </section>

  <section class="project-section" style="margin-top: 50px; padding-top: 30px; border-top: 1px solid #e1e4e8;">
    <p style="font-size: 0.9em; color: #666; line-height: 1.6;">
      <strong>致谢：</strong>本研究是在作者于微软研究院实习期间完成的。感谢DKI小组的所有同事和导师的支持与宝贵反馈。
    </p>
  </section>

</div>

{{< project-enhance >}}
