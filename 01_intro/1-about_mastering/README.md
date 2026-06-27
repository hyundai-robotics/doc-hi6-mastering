## 1.1 关于机器人掌控

<div style="width: 630px; line-height: 1.5; word-break: keep-all;">
  <ul style="margin: 0; padding-left: 20px;">
    <li>掌控通过补偿每个轴的机械零位置来提高机器人的准确性。</li>
    <li>当第一次定义机械零或由于轴扭曲、组件更换或磨损而发生变化时，必须执行掌控。</li>
    <li><strong>掌控与校准</strong>
      <ul style="list-style-type: circle; padding-left: 20px;">
        <li>掌控：为坐标计算建立机械零参考。</li>
        <li>校准：基于已建立的零纠正位置错误。</li>
        <li>校准必须始终在掌控之后进行。</li>
      </ul>
    </li>
  </ul>

  <br>

  <div style="width: 630px; margin: 10px 0; background-color: #fcfcfc; padding: 5px 0;">
    本手册使用<strong>数字接触传感器</strong>进行掌控。传感器附加在每个轴上，通过在<strong>-1.5°到+1.5°</strong>的范围内移动来检测V形槽。检测到的V形槽位置随后会被修正到机械原点。
  </div>
</div>

<br>

<figure style="text-align: left; width: 100%; margin: 0;">
  <img src="../../_assets/12_mastering_concept_eng.PNG" style="width: 630px; margin-left: 25px;" alt="Mastering Concept">
  
  <figcaption style="font-size: 0.9em; margin-left: 0px; white-space: nowrap;">
    图 1.1. a. 起始点（轴扭曲状态），b. 在掌控期间的V形槽检测
  </figcaption>
</figure>