---
permalink: /
title: "Nanhe Chen - 陈楠禾"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<!-- <audio autoplay loop controls>
  <source src="../videos/Lorien.mp3" type="audio/mpeg">
</audio> -->

<audio id="bgm" loop>
  <source src="{{ '/videos/Lorien.mp3' | relative_url }}" type="audio/mpeg">
</audio>

<div id="music-btn" style="
  position: fixed;
  bottom: 25px; right: 25px;
  width: 60px; height: 60px;
  background: linear-gradient(135deg, #a2d2ff, #cdb4db);
  border-radius: 50%;
  box-shadow: 0 3px 10px rgba(0,0,0,0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: transform 0.2s;
  z-index: 9999;
">
  <span id="music-icon" style="font-size: 24px;">🎵</span>
</div>

<script>
document.addEventListener("DOMContentLoaded", () => {
  const audio = document.getElementById('bgm');
  const btn = document.getElementById('music-btn');
  const icon = document.getElementById('music-icon');
  let playing = false;
  let started = false; // 用于标记是否已经自动播放过

  // 手动点击按钮控制播放/暂停
  btn.addEventListener('click', async () => {
    if (!playing) {
      try {
        await audio.play();
        playing = true;
        icon.textContent = '🔊';
        btn.style.transform = 'rotate(20deg)';
      } catch (err) {
        console.warn('Play blocked:', err);
      }
    } else {
      audio.pause();
      playing = false;
      icon.textContent = '🎵';
      btn.style.transform = 'rotate(0deg)';
    }
  });

  // 自动播放函数（仅执行一次）
  const startMusic = async () => {
    if (started) return;
    try {
      await audio.play();
      started = true;
      playing = true;
      icon.textContent = '🔊';
      btn.style.transform = 'rotate(20deg)';

      // 播放后移除监听器（避免性能浪费）
      ['click','scroll','keydown','touchstart','wheel'].forEach(evt => {
        document.removeEventListener(evt, startMusic);
      });
    } catch (err) {
      console.warn('Auto play blocked:', err);
    }
  };

  // 一旦有交互（滑动/点击/按键/触摸）就尝试播放
  ['click','scroll','keydown','touchstart','wheel'].forEach(evt => {
    document.addEventListener(evt, startMusic);
  });
});
</script>


I'm a [master student](http://zju-fast.com/nanhe-chen/) at the [FASTLAB](http://zju-fast.com/) of Zhejiang University, supervised by Prof.[Yanjun Cao](http://zju-fast.com/research-group/yanjun-cao/), [Fei Gao](http://zju-fast.com/research-group/fei-gao/), and [Chao Xu](http://zju-fast.com/research-group/chao-xu/). 
I graduated with a Bachelor's degree of Robotics Engineering with honor from Chu Kochen Honors College, Zhejiang University. 
Currently, I'm preparing to apply for PhD research program.

Research Interests
======
My research lies in planning, including decision-making and motion planning. 
I mainly focus on optimization-based and explainable learning-based methods. 
I am committed to enabling robots to collaboratively and actively perceive in unknown spaces, to overcome single robot's shortages. 
At the same time, I focus on developing efficient and explainable motion planning algorithms for robots field navigation in challenging scenarios. 
I'd like to see robots could adjust self behaviors smartly based on its learned knowledge and current observations. Making robots move elegantly is my passion. My current research interets include
- Multi-robot active perception for collaboration
- Large scale parallel motion planning
- Model-based policy optimization

Scholarships
=====
- National Scholarship in Zhejiang University (2024-2025)
- Merit Scholarships in Zhejiang University (2019-2020, 2020-2021)

Publications
======
- Cost-effective Swarm Navigation System via Close Cooperation [[paper](https://ieeexplore.ieee.org/document/10545578/)] [[video](https://www.bilibili.com/video/BV1X7421Z7Gv/?vd_source=b2528621e6c9d392d6d429b1093e0eb2)]

  **Nanhe Chen**, Zhehan Li, Lun Quan, Xinwei Chen, Chao Xu, Fei Gao, and Yanjun Cao
  
  IEEE Robotics and Automation Letters

  <iframe width="560" height="315" src="https://www.youtube.com/embed/1Hn2U4-WZ7Q?si=oaF8bPKmYGIl6mAg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- TOP: Trajectory Optimization via Parallel Optimization towards Constant Time Complexity [[paper](https://arxiv.org/abs/2507.10290)] [[video](https://www.youtube.com/watch?v=00LBW0G8CwU)]

  Jiajun Yu*, **Nanhe Chen\***, Guodong Liu, Chao Xu, Fei Gao, and Yanjun Cao

  IEEE Robotics and Automation Letters 

  <iframe width="560" height="315" src="https://www.youtube.com/embed/00LBW0G8CwU?si=EOkoMg8erNjLdzbi" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- Universal Trajectory Optimization Framework for Differential Drive Robot Class [[paper](https://ieeexplore.ieee.org/document/10924228)] [[video](https://www.youtube.com/watch?v=fo64QufedPo&feature=youtu.be)] [[code](https://zju-fast-lab.github.io/DDR-opt/)]

  Mengke Zhang, **Nanhe Chen**, Hu Wang, Jianxiong Qiu, Zhichao Han, Qiuyu Ren, Chao Xu, Fei Gao, and Yanjun Cao

  IEEE Transactions on Automation Science and Engineering

  <iframe width="560" height="315" src="https://www.youtube.com/embed/fo64QufedPo?si=__moHW1dzJvThFad" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- ColAG: A Collaborative Air-Ground Framework for Perception-Limited UGVs’ Navigation [[paper](https://ieeexplore.ieee.org/document/10611264)] [[video](https://www.youtube.com/watch?v=yK9SyL2PPGc)]

  Zhehan Li\*, Rui Mao\*, **Nanhe Chen**, Chao Xu, Fei Gao, and Yanjun Cao

  2024 IEEE International Conference on Robotics and Automation (ICRA)

  <iframe width="560" height="315" src="https://www.youtube.com/embed/yK9SyL2PPGc?si=9I18ESkTIxwNMHYx" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- Cross-Vehicle Transition Framework for Quadrotor Control in Air-Ground Cooperation [[paper](https://link.springer.com/article/10.1007/s10514-025-10209-4)]

  Qiuyu Ren, Miao Xu, Mengke Zhang, **Nanhe Chen**, Mingwei Lai, Chao Xu, Fei Gao, and Yanjun Cao

  Autonomous Robots

  <iframe width="560" height="315" src="//player.bilibili.com/player.html?isOutside=true&aid=115042712293478&bvid=BV1oBYrzVEzV&cid=25843670040&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

