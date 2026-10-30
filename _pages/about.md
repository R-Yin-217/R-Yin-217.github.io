---
layout: about
title: About
permalink: /
subtitle: 

profile:
  align: right
  image: ren_pic.jpg
  image_circular: true # crops the image to make it circular
  more_info: |
    <section class="profile-contact" aria-labelledby="profile-contact-heading">
      <h2 id="profile-contact-heading" class="profile-sidebar-heading"><i class="fa-solid fa-envelope" aria-hidden="true"></i> CONTACT</h2>
      <p class="profile-email"><a href="mailto:yin-ren217@g.ecc.u-tokyo.ac.jp">yin-ren217 [at] g.ecc.u-tokyo.ac.jp</a></p>
    </section>

selected_papers: true # includes a list of papers marked as "selected={true}"
social: false # profile links are shown below the name

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

## About Me

Hi! I am an undergraduate student at the University of Tokyo, interested in how machine learning systems can learn reliably from incomplete, noisy, and interaction-dependent feedback.

I am currently a member of the [Interactive Intelligent Systems Lab](https://iis-lab.org/) at the University of Tokyo, advised by [Prof. Koji Yatani](https://iis-lab.org/member/koji-yatani/). Previously, I conducted research at RIKEN AIP with [Prof. Masashi Sugiyama](https://www.ms.k.u-tokyo.ac.jp/sugi/) and [Prof. Takashi Ishida](https://takashiishida.github.io/). During my exchange at Northeastern University, I also worked in [Prof. Jennifer Dy](https://mllabneu.github.io/)'s research group.

My research interests lie at the intersection of trustworthy machine learning and human–AI interaction. As foundation models become increasingly capable, I believe understanding how humans provide feedback and interact with AI systems will remain essential. I am particularly interested in combining insights from HCI with statistical machine learning to understand how feedback is generated through interaction and how AI systems can learn reliably from it.

<!-- research-section -->

## Research Interests

**My research aims to develop reliable AI systems that can learn from imperfect human feedback.** I am particularly interested in how feedback is generated through human–AI interaction, what can be learned from it, and how reliable supervision can be scaled. My research focuses on three connected directions:

- **Learning from Imperfect Feedback:** Human supervision is often incomplete, noisy, or selectively observed. My **ICLR 2026** paper develops statistically principled estimators for scalable oversight under partitioned human supervision. In a separate **manuscript under review**, I explore how human corrections can serve as supervision in human-in-the-loop data curation.

- **Interaction and Feedback Generation:** Feedback is shaped by the interactions through which it is generated. I study how multi agent LLM interactions affect diversity and convergence, particularly when consensus emerges before complementary information has been fully explored. This research is ongoing at the University of Tokyo.

- **Scaling Reliable Feedback:** As AI systems become increasingly capable, obtaining reliable evaluation signals for LLM alignment becomes increasingly challenging. I am interested in model mediated evaluation and how uncertainty in AI generated feedback affects learning and post training. My ongoing work explores these challenges (*manuscript in preparation*).

I'm always happy to discuss research or answer questions. Feel free to reach out!
