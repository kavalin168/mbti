[mbti.html](https://github.com/user-attachments/files/26294440/mbti.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>超准MBTI16型人格测试｜解锁你的专属</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'PingFang SC', 'Microsoft YaHei', 'Helvetica Neue', sans-serif;
    }
    body {
      background: linear-gradient(135deg, #f0f9ff 0%, #e6f7ff 100%);
      color: #333;
      padding: 15px;
      min-height: 100vh;
      user-select: none;
      -webkit-user-select: none;
      overflow-x: hidden;
    }
    .container {
      max-width: 700px;
      margin: 30px auto;
      background: #fff;
      border-radius: 20px;
      padding: 30px 25px;
      box-shadow: 0 10px 30px rgba(0,119,255,0.08);
    }
    .test-header {
      text-align: center;
      margin-bottom: 30px;
    }
    .test-title {
      font-size: 26px;
      font-weight: 700;
      background: linear-gradient(90deg, #1a73e8, #7b61ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .test-subtitle {
      font-size: 14px;
      color: #666;
    }
    .progress-box {
      width: 100%;
      height: 8px;
      background: #f1f5f9;
      border-radius: 4px;
      margin-bottom: 25px;
      overflow: hidden;
    }
    .progress {
      height: 100%;
      background: linear-gradient(90deg, #1a73e8, #7b61ff);
      transition: width 0.3s ease;
      width: 0%;
    }
    .question-item {
      display: none;
      animation: slideIn 0.4s ease forwards;
    }
    .question-item.active {
      display: block;
    }
    @keyframes slideIn {
      from { opacity: 0; transform: translateX(30px); }
      to { opacity: 1; transform: translateX(0); }
    }
    .q-num {
      font-size: 17px;
      font-weight: 600;
      color: #1a73e8;
      margin-bottom: 12px;
    }
    .q-content {
      font-size: 16px;
      line-height: 1.8;
      margin-bottom: 20px;
    }
    .options {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }
    .option {
      padding: 14px 18px;
      border: 1px solid #e2e8f0;
      border-radius: 12px;
      cursor: pointer;
      font-size: 15px;
      color: #555;
    }
    .option:hover {
      border-color: #1a73e8;
      background: #f8faff;
    }
    .option.selected {
      background: #1a73e8;
      color: #fff;
      border-color: #1a73e8;
    }
    .btn-group {
      display: flex;
      gap: 10px;
      margin-top: 30px;
    }
    .btn {
      flex: 1;
      padding: 15px;
      border: none;
      border-radius: 12px;
      font-size: 15px;
      font-weight: 600;
      cursor: pointer;
    }
    .btn-pre {
      background: #f1f5f9;
      color: #64748b;
    }
    .btn-next {
      background: #1a73e8;
      color: #fff;
    }
    .btn-submit {
      width: 100%;
      background: #7b61ff;
      color: #fff;
      margin-top: 20px;
      display: none;
    }
    .result-box {
      display: none;
      text-align: center;
    }
    .free-result {
      padding: 20px;
      background: #f8faff;
      border-radius: 16px;
      margin-bottom: 25px;
    }
    .mbti-code {
      font-size: 28px;
      font-weight: 700;
      color: #1a73e8;
      margin: 10px 0;
    }
    .free-desc {
      font-size: 15px;
      color: #666;
      line-height: 1.7;
    }
    .tip {
      color: #fa8c16;
      margin: 10px 0;
    }
    .drainage-box {
      padding: 20px;
      background: #fff7e6;
      border-radius: 16px;
      border: 1px dashed #fa8c16;
    }
    .pay-box {
      padding: 25px;
      background: #fdf7ff;
      border-radius: 16px;
      border: 1px solid #7b61ff;
    }
    .pay-btn {
      padding: 16px;
      background: linear-gradient(90deg, #7b61ff, #1a73e8);
      color: #fff;
      border: none;
      border-radius: 12px;
      width: 100%;
      font-weight: 700;
    }
    .copyright {
      text-align: center;
      font-size: 12px;
      color: #999;
      margin-top: 30px;
    }
    @media (max-width: 576px) {
      .btn-group {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
<div class="container">
  <div class="test-header">
    <h1 class="test-title">MBTI16型人格测试</h1>
    <p class="test-subtitle">全网超300万人实测，测出你的真实人格</p>
  </div>
  <div class="progress-box">
    <div class="progress" id="progressBar"></div>
  </div>
  <div id="questionBox">
    <div class="question-item active" data-index="0">
      <div class="q-num">第1题</div>
      <div class="q-content">社交场合中，你更倾向于</div>
      <div class="options">
        <div class="option" data-type="E">主动搭话，享受热闹</div>
        <div class="option" data-type="I">被动回应，偏爱安静</div>
      </div>
    </div>
    <div class="question-item" data-index="1">
      <div class="q-num">第2题</div>
      <div class="q-content">你获取信息时更相信</div>
      <div class="options">
        <div class="option" data-type="S">眼见为实，关注细节</div>
        <div class="option" data-type="N">直觉联想，关注可能</div>
      </div>
    </div>
    <div class="question-item" data-index="2">
      <div class="q-num">第3题</div>
      <div class="q-content">做决策时更看重</div>
      <div class="options">
        <div class="option" data-type="T">逻辑对错，理性分析</div>
        <div class="option" data-type="F">他人感受，情感共鸣</div>
      </div>
    </div>
    <div class="question-item" data-index="3">
      <div class="q-num">第4题</div>
      <div class="q-content">你的生活状态更偏向</div>
      <div class="options">
        <div class="option" data-type="J">提前规划，按部就班</div>
        <div class="option" data-type="P">随性而为，灵活应变</div>
      </div>
    </div>
    <div class="question-item" data-index="4">
      <div class="q-num">第5题</div>
      <div class="q-content">疲惫时你更倾向于</div>
      <div class="options">
        <div class="option" data-type="I">独自待着恢复精力</div>
        <div class="option" data-type="E">和朋友倾诉放松</div>
      </div>
    </div>
    <div class="question-item" data-index="5">
      <div class="q-num">第6题</div>
      <div class="q-content">你更喜欢学习哪种内容？</div>
      <div class="options">
        <div class="option" data-type="S">实用技巧、可落地</div>
        <div class="option" data-type="N">理论概念、有想象力</div>
      </div>
    </div>
  </div>
  <div class="btn-group">
    <button class="btn btn-pre" id="prevBtn">上一题</button>
    <button class="btn btn-next" id="nextBtn">下一题</button>
  </div>
  <button class="btn btn-submit" id="submitBtn">提交测试</button>
  <div class="result-box" id="resultBox">
    <div class="free-result">
      <div class="free-title">你的MBTI人格类型</div>
      <div class="mbti-code" id="mbtiCode">INFJ</div>
      <div class="free-desc">提倡者型人格，富有洞察力和创造力</div>
      <div class="tip">* 基础结果，完整分析需解锁</div>
    </div>
    <div class="drainage-box">
      <div>分享好友可解锁完整报告</div>
    </div>
    <div class="pay-box">
      <div>💎 解锁完整报告（仅9.9元）</div>
      <button class="pay-btn">立即解锁</button>
    </div>
  </div>
  <div class="copyright">© 2025 MBTI测试</div>
</div>
<script>
  const totalQuestions = 6;
  let currentIndex = 0;
  let selectedAnswers = {};
  const progressBar = document.getElementById('progressBar');
  updateProgress();
  document.querySelectorAll('.option').forEach(option => {
    option.addEventListener('click', function() {
      this.parentElement.querySelectorAll('.option').forEach(item => item.classList.remove('selected'));
      this.classList.add('selected');
      selectedAnswers[currentIndex] = this.dataset.type;
    });
  });
  document.getElementById('prevBtn').onclick = () => {
    if(currentIndex>0){
      document.querySelector(`.question-item[data-index="${currentIndex}"]`).classList.remove('active');
      currentIndex--;
      document.querySelector(`.question-item[data-index="${currentIndex}"]`).classList.add('active');
      updateProgress();
    }
  }
  document.getElementById('nextBtn').onclick = () => {
    if(!document.querySelector(`.question-item[data-index="${currentIndex}"] .option.selected`)){
      alert('请选择一个选项');
      return;
    }
    if(currentIndex < totalQuestions-1){
      document.querySelector(`.question-item[data-index="${currentIndex}"]`).classList.remove('active');
      currentIndex++;
      document.querySelector(`.question-item[data-index="${currentIndex}"]`).classList.add('active');
      updateProgress();
      if(currentIndex === totalQuestions-1){
        document.getElementById('nextBtn').style.display='none';
        document.getElementById('submitBtn').style.display='block';
      }
    }
  }
  document.getElementById('submitBtn').onclick = () => {
    if(!document.querySelector(`.question-item[data-index="${currentIndex}"] .option.selected`)){
      alert('请选择一个选项');
      return;
    }
    const mbti = calculateMBTI();
    document.getElementById('mbtiCode').innerText = mbti;
    document.getElementById('questionBox').style.display='none';
    progressBar.style.display='none';
    document.getElementById('prevBtn').style.display='none';
    document.getElementById('submitBtn').style.display='none';
    document.getElementById('resultBox').style.display='block';
  }
  function updateProgress(){
    progressBar.style.width = ((currentIndex+1)/totalQuestions)*100 + '%';
  }
  function calculateMBTI(){
    const count={E:0,I:0,S:0,N:0,T:0,F:0,J:0,P:0};
    for(let i=0;i<totalQuestions;i++){
      const t=selectedAnswers[i];
      if(t)count[t]++;
    }
    return (count.E>=count.I?'E':'I') + (count.S>=count.N?'S':'N') + (count.T>=count.F?'T':'F') + (count.J>=count.P?'J':'P');
  }
</script>
</body>
</html>
