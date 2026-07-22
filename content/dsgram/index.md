---
title: "DSGram"
author_profile: false
---

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
<link rel="stylesheet" href="/assets/css/project-page.css">

<div class="project-container">

  <header class="project-header">
    <div class="project-venue-badge"><i class="fas fa-award"></i> AAAI 2025</div>
    <h1 class="project-title">DSGram：大语言模型时代语法纠错的动态加权子指标</h1>

    <p class="pp-hero-tagline">
      BLEU 等基于参考的指标在处理基于大语言模型的语法纠错系统时效果不佳。<strong>DSGram</strong> 引入了一种动态加权框架，包含三个新的子指标，与人类判断的契合度<strong>显著更高</strong>。
    </p>
    
    <div class="project-authors">
      <a href="https://jxtse.github.io">Jinxiang Xie</a><sup>1,2</sup>,
      Yilin Li<sup>1</sup>,
      Xunjian Yin<sup>1</sup>,
      <a href="https://wanxiaojun.github.io/">Xiaojun Wan</a><sup>1</sup>
    </div>
    <div class="affiliations">
      <sup>1</sup>Peking University &nbsp;|&nbsp;
      <sup>2</sup>Beijing Jiaotong University
    </div>

    <div class="links-bar">
      <a href="https://arxiv.org/abs/2412.12832" class="btn-arxiv" target="_blank"><i class="fas fa-file-alt"></i> 论文</a>
      <a href="https://arxiv.org/pdf/2412.12832" class="btn-pdf" target="_blank"><i class="fas fa-file-pdf"></i> 全文</a>
      <a href="https://github.com/jxtse/GEC-Metrics-DSGram" class="btn-code" target="_blank"><i class="fab fa-github"></i> 代码</a>
    </div>
  </header>

  <section class="teaser-section">
    <img src="/images/dsgram-fig2-architecture.png" alt="DSGram Architecture" class="teaser-image">
    <div class="teaser-caption">
      <strong>图 1：</strong>DSGram 方法的架构。首先输入句子对（原句和改正句），利用大语言模型生成动态权重，通过判断矩阵和一致性检查进行优化。这些动态权重经归一化后用于对各子指标进行评分，最终得到整体评估分数。
    </div>
  </section>

  <section class="abstract-section">
    <div class="abstract-title"><i class="fas fa-align-left"></i> 摘要</div>
    <div class="abstract-text">
      评估语法纠错（GEC）模型的性能日益具有挑战性，因为基于大语言模型（LLM）的语法纠错系统产生的改正结果往往与给定的黄金参考不一致。这种差异削弱了传统基于参考的评估指标的可靠性。
      <br><br>
      在本研究中，我们提出了一种新的语法纠错模型评估框架<strong>DSGram</strong>，该框架整合了<strong>语义连贯性</strong>、<strong>编辑程度</strong>和<strong>流畅度</strong>三个维度，并采用了<strong>动态加权机制</strong>。我们的框架利用层次分析法（AHP）结合大语言模型来确定各项评估标准的相对重要性。此外，我们还构建了一个包含人工标注和大语言模型模拟句子的数据集，用于验证我们的算法并微调更具成本效益的模型。
      <br><br>
      实验结果表明，我们提出的方法提升了语法纠错模型评估的有效性。
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">动机</h2>
    <p style="font-size: 1.05em; line-height: 1.7; color: #444; margin-bottom: 20px;">
      传统的语法纠错评估指标在处理基于大语言模型的系统时存在显著局限性。如下图所示，BLEU 无法区分过度纠正和纠正不足，而 SOME 无法捕捉过度纠正。DSGram 通过一个全面的评估框架弥补了这些不足。
    </p>
    <div class="figure-block">
      <img src="/images/dsgram-fig1-examples.png" alt="Motivation Examples">
      <div class="figure-caption">
        <strong>图 2：</strong>现有指标的运行示例和评估结果。BLEU 无法区分过度纠正和纠正不足，而 SOME 无法捕捉过度纠正。蓝色高亮表示过度纠正；红色表示流畅度不佳。
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">主要贡献</h2>
    <div class="pp-contrib-grid pp-fadeup-stagger">
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">01</div>
        <h3 class="pp-contrib-title">新的子指标</h3>
        <p class="pp-contrib-text">我们引入了重新设计的语法纠错评估子指标——<strong>语义连贯性</strong>、<strong>编辑程度</strong>和<strong>流畅度</strong>——有效解决了基于大语言模型的语法纠错模型中的过度编辑问题。</p>
      </div>
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">02</div>
        <h3 class="pp-contrib-title">基于层次分析法的动态加权</h3>
        <p class="pp-contrib-text">一种新颖的动态加权方法，将<strong>层次分析法</strong>与大语言模型相结合，以确定评估标准在上下文中的相对重要性。</p>
      </div>
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">03</div>
        <h3 class="pp-contrib-title">评估数据集</h3>
        <p class="pp-contrib-text">我们发布了<strong>DSGram-Eval</strong>（人工标注）和<strong>DSGram-LLMs</strong>（GPT-4 模拟）两个数据集，均基于 CoNLL-2014 和 BEA-2019 测试集构建，用于严格的评估。</p>
      </div>
      <div class="pp-contrib-card">
        <div class="pp-contrib-num">04</div>
        <h3 class="pp-contrib-title">更强的相关性</h3>
        <p class="pp-contrib-text">在 SEEDA 基准上，DSGram 与人类判断的<strong>相关性高于</strong>所有传统的基于参考和无参考的指标。</p>
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">方法</h2>
    <p style="font-size: 1.05em; line-height: 1.7; color: #444; margin-bottom: 25px;">
      DSGram 包含两个主要组成部分：<strong>分数生成</strong>和<strong>权重生成</strong>。通过对生成的分数应用上下文相关的权重，得到整体的评估分数。
    </p>
    
    <div class="method-grid">
      <div class="method-card">
        <h3><i class="fas fa-chart-bar"></i> 三个子指标</h3>
        <p><strong>语义连贯性：</strong>原始含义被保留的程度。<strong>编辑程度：</strong>纠正确认的必要性和恰当性。<strong>流畅度：</strong>语法正确性和自然流畅程度。</p>
      </div>
      <div class="method-card">
        <h3><i class="fas fa-balance-scale"></i> 基于层次分析法的动态加权</h3>
        <p>利用大语言模型为每个句子构建两两比较矩阵，并辅以一致性检查和特征向量归一化。正式文本强调编辑程度；非正式文本优先考虑流畅度。</p>
      </div>
    </div>

    <div class="figure-block">
      <img src="/images/dsgram-fig5-score-computation.png" alt="Score Computation">
      <div class="figure-caption">
        <strong>图 3：</strong>两个不同句子的 DSGram 分数计算。句子（a）为非正式对话，流畅度被赋予更高权重。句子（b）为正式表达，编辑程度获得更大权重。
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">子指标分析</h2>
    <p style="font-size: 1.05em; line-height: 1.7; color: #444; margin-bottom: 20px;">
      我们重新设计了子指标以减少冗余并提高覆盖度。原始的 SOME 指标中，语法正确性与流畅度之间呈现高相关性（0.89）。我们的新子指标实现了更均衡的分布。
    </p>

    <div class="results-grid">
      <div class="result-item">
        <img src="/images/dsgram-fig3-heatmap-some.png" alt="SOME Heatmap" style="max-width: 100%; border-radius: 8px;">
        <div class="result-label" style="margin-top: 12px;"><strong>SOME 子指标：</strong>语法正确性与流畅度之间高度相关（0.89）</div>
      </div>
      <div class="result-item">
        <img src="/images/dsgram-fig4-heatmap-ours.png" alt="Our Heatmap" style="max-width: 100%; border-radius: 8px;">
        <div class="result-label" style="margin-top: 12px;"><strong>DSGram 子指标：</strong>相关性分布更加均衡</div>
      </div>
    </div>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">实验结果</h2>
    
    <div class="results-grid">
      <div class="result-item">
        <div class="result-number">0.8764</div>
        <div class="result-label">与人类评分的皮尔逊相关性（AHP 动态加权）</div>
      </div>
      <div class="result-item">
        <div class="result-number">0.8544</div>
        <div class="result-label">与人类评分的皮尔逊相关性（平均加权基线）</div>
      </div>
      <div class="result-item">
        <div class="result-number">12</div>
        <div class="result-label">在 SEEDA 基准上评估的语法纠错系统数量</div>
      </div>
    </div>

    <p style="font-size: 1.05em; line-height: 1.7; color: #444; margin-top: 25px;">
      DSGram 与人类反馈的相关性超过了所有传统的基于参考指标（M²、ERRANT、BLEU）和无参考指标（GLEU、Scribendi Score）。在 DSGram-LLMs 数据集上微调的 LLaMA3-8B 和 LLaMA2-13B 模型也优于其少样本学习的对应模型，证明了该框架在成本效益模型上的实用性。
    </p>
  </section>

  <section class="project-section pp-fadeup">
    <h2 class="section-title">引用方式</h2>
    <div class="bibtex-section">
      <button class="bibtex-copy-btn" onclick="navigator.clipboard.writeText(this.nextElementSibling.innerText);this.textContent='已复制';setTimeout(()=>this.textContent='复制',2000);">复制</button>
      <div class="bibtex-code">@misc{xie2025dsgramdynamicweightingsubmetrics,
      title={DSGram: Dynamic Weighting Sub-Metrics for Grammatical Error Correction in the Era of Large Language Models}, 
      author={Jinxiang Xie and Yilin Li and Xunjian Yin and Xiaojun Wan},
      year={2025},
      eprint={2412.12832},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      doi={https://doi.org/10.1609/aaai.v39i24.34746},
      url={https://arxiv.org/abs/2412.12832}, 
}</div>
    </div>
  </section>

  <section class="project-section" style="margin-top: 50px; padding-top: 30px; border-top: 1px solid #e1e4e8;">
    <p style="font-size: 0.9em; color: #666; line-height: 1.6;">
      <strong>致谢：</strong>本工作在作者于北京大学访问研究期间完成。感谢万小军教授以及王选计算机研究所所有同事的指导与支持。
    </p>
  </section>

</div>

{{< project-enhance >}}
