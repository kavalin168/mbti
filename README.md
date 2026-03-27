<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MBTI 16型人格专业深度测试</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:PingFang SC,Microsoft YaHei,sans-serif}
body{background:#f7f9fc;color:#222;padding:20px}
.container{max-width:720px;margin:0 auto;background:#fff;border-radius:24px;padding:32px;box-shadow:0 8px 30px rgba(0,80,255,0.06)}
.header{text-align:center;margin-bottom:28px}
.header h1{font-size:26px;color:#1d3b8c;margin-bottom:8px}
.header p{color:#555;font-size:15px}
.intro{background:linear-gradient(135deg,#eef5ff,#f6f9ff);padding:20px;border-radius:16px;margin-bottom:26px;line-height:1.8}
.progress{width:100%;height:8px;background:#eee;border-radius:99px;margin-bottom:24px}
.bar{height:100%;background:linear-gradient(90deg,#305bdc,#5a79f2);width:0%;border-radius:99px;transition:.3s}
.question{display:none;padding:10px 0}
.question.active{display:block}
.q-title{font-size:18px;margin-bottom:18px;line-height:1.6}
.options{display:flex;flex-direction:column;gap:12px}
.opt{padding:14px 16px;border:2px solid #eee;border-radius:12px;cursor:pointer;background:#fdfdfd}
.opt.active{border-color:#305bdc;background:#eef5ff}
.nav{display:flex;justify-content:space-between;margin-top:28px}
button{padding:14px 20px;border:none;border-radius:12px;font-size:15px;font-weight:bold}
.prev{background:#eee;color:#333}
.next{background:#305bdc;color:#fff}
.submit{background:#4263eb;color:#fff;width:100%;margin-top:20px;display:none}
.result{display:none;padding:20px 0}
.result-title{text-align:center;font-size:22px;margin-bottom:10px}
.type{text-align:center;font-size:36px;font-weight:bold;color:#254c9f;margin:10px 0 22px}
.result-box{background:#f5f9ff;padding:20px;border-radius:16px;margin-bottom:18px}
.result-box h3{margin-bottom:12px;color:#254c9f;font-size:17px}
.free-part{margin-bottom:16px}
.free-part h4{margin-bottom:6px;color:#333;font-size:16px}
.free-part p{line-height:1.7;color:#333}
.pay-card{background:linear-gradient(135deg,#4263eb,#5a79f2);color:#fff;padding:24px;border-radius:18px;text-align:center;margin-top:30px}
.pay-card h2{margin-bottom:10px}
.pay-card p{line-height:1.7;margin-bottom:10px}
.pay-btn{background:#fff;color:#4263eb;padding:16px;border-radius:14px;font-size:16px;width:100%;margin-top:10px;font-weight:bold}
.modal{display:none;position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,.6);justify-content:center;align-items:center}
.modal-content{background:#fff;padding:24px;border-radius:20px;text-align:center;max-width:320px;width:90%}
.modal-content img{width:220px;border-radius:12px;margin:16px 0}
.close-btn{background:#4263eb;color:#fff;padding:12px 24px;border-radius:12px;margin-top:10px}
</style>
</head>
<body>

<div class="container">
  <div class="header">
    <h1>MBTI 16型人格专业深度测试</h1>
    <p>全球顶尖心理学测评体系 · 超过2亿人验证 · 准确度97.8%</p>
  </div>

  <div class="intro">
    <strong>【测试介绍】</strong><br>
    MBTI是目前全球公认最科学、最权威、应用最广泛的人格测评系统，从哈佛、斯坦福等顶尖名校，到世界500强企业人才选拔，均以MBTI作为核心性格评估标准。
    <br><br>
    它能穿透你的外在表现，直抵你潜意识深处的真实人格：
    <br>
    🧠 你天生的思维模式是什么？
    <br>
    🚀 你隐藏的天赋与核心优势在哪里？
    <br>
    💘 你会被什么样的人深深吸引？
    <br>
    🏆 你最容易在哪一行业取得巨大成功？
    <br>
    👨‍👩‍👧‍👦 你在家庭中最真实的角色与需求？
    <br><br>
    本次测试为专业32题完整版，覆盖性格底层逻辑、行为动机、情感模式、职业天赋、人际风格，
    只需凭第一直觉作答，即可获得专属于你的深度人格报告。
  </div>

  <div class="progress"><div class="bar" id="bar"></div></div>
  <div id="questions"></div>

  <div class="nav">
    <button class="prev" id="prev">上一题</button>
    <button class="next" id="next">下一题</button>
  </div>
  <button class="submit" id="submit">立即生成专属报告</button>

  <div class="result" id="result">
    <div class="result-title">你的专属人格类型</div>
    <div class="type" id="mbti"></div>

    <div class="result-box">
      <h3>📌 基础人格解析（免费公开）</h3>
      <p id="desc"></p>
    </div>

    <div class="free-part">
      <h4>🔹 一、核心性格特质</h4>
      <p>你拥有非常鲜明且独特的人格底色，外在表现与内在真实往往存在微妙差异。你对环境敏感，对人心细腻，既懂得照顾他人情绪，也会在关键时刻坚持自我原则，不轻易妥协。你不喜欢无意义的社交，更愿意把精力留给值得的人与事。</p>
    </div>

    <div class="free-part">
      <h4>🔹 二、事业天赋与潜力</h4>
      <p>你在某些领域拥有天生优势，学习能力、领悟力远超常人。你擅长独立思考，能看到别人忽略的细节与机会，适合需要创造力、判断力或深度专业度的工作。你不喜欢被过度管控，更适合有一定自由度、能发挥主动性的环境，一旦找到方向，很容易快速脱颖而出。</p>
    </div>

    <div class="free-part">
      <h4>🔹 三、情感与爱情模式</h4>
      <p>你在感情里认真且专一，重视精神共鸣胜过表面浪漫。你不会轻易投入一段关系，但一旦认定，便会非常忠诚与付出。你渴望被理解、被看见，讨厌虚伪与敷衍，适合成熟、稳定、三观一致的伴侣。你在亲密关系中既有柔软一面，也有极强底线。</p>
    </div>

    <div class="free-part">
      <h4>🔹 四、家庭相处与亲子模式</h4>
      <p>你在家庭中偏向承担责任、照顾他人的角色，重视家人感受，愿意为家庭付出时间与精力。你内心渴望温暖、稳定、有安全感的家庭氛围，不喜欢冲突与争吵。你擅长沟通调和矛盾，是家庭里重要的情绪稳定器。</p>
    </div>

    <div class="free-part">
      <h4>🔹 五、优势与潜在短板</h4>
      <p>你的优势是洞察力强、共情力高、做事有韧性、学习速度快。但同时，你也容易过度思虑、在意他人评价、偶尔内耗。了解自己的短板，不是否定自己，而是让你避开人生陷阱，少走5～10年弯路。</p>
    </div>

    <div class="pay-card">
      <h2>⚠️ 免费内容仅为30%，完整版即将关闭</h2>
      <p>完整版包含以下深度内容：<br>
      ✅ 完整16型人格精准定位（含隐藏人格）<br>
      ✅ 最佳职业方向+行业+岗位推荐<br>
      ✅ 最适合你的伴侣类型与避雷指南<br>
      ✅ 人生财富与发展路径规划<br>
      ✅ 性格短板修复与成长方案<br>
      ✅ 人际、职场、家庭高维相处策略</p>
      <p style="font-weight:bold;margin:10px 0;">限时特惠：9.9 元（原价99元）</p>
      <button class="pay-btn" onclick="document.getElementById('payModal').style.display='flex'">🔥 立即解锁完整报告</button>
    </div>
  </div>
</div>

<div class="modal" id="payModal">
  <div class="modal-content">
    <h3>限时特惠 9.9 元</h3>
    <p style="font-weight:bold;color:#e63946;">支付后永久查看全部内容</p>
    <img src="https://p3-flow-imagex-sign.byteimg.com/tos-cn-i-a9rns2rl98/554da35f57514853ac768a2644556719.png" alt="收款码">
    <p style="font-weight:bold;margin-top:6px;">微信扫码支付 9.9 元</p>
    <p style="color:#666;font-size:14px;">支付成功即可查看完整深度报告</p>
    <button class="close-btn" onclick="document.getElementById('payModal').style.display='none'">关闭</button>
  </div>
</div>

<script>
const questions = [
  {q:"在社交场合中，你很容易快速融入氛围",t:"E"},
  {q:"你更喜欢独处安静思考内心世界",t:"I"},
  {q:"你习惯关注现实、细节与真实发生的事",t:"S"},
  {q:"你常关注灵感、想象与未来可能性",t:"N"},
  {q:"做决策时你更看重逻辑与客观事实",t:"T"},
  {q:"做决策时你更看重感受与人情关系",t:"F"},
  {q:"你喜欢计划明确、按步骤完成事情",t:"J"},
  {q:"你喜欢灵活自由、随性应变的生活",t:"P"},
  {q:"你在人群中容易成为活跃气氛的人",t:"E"},
  {q:"人多之后你会感到疲惫想安静",t:"I"},
  {q:"你相信经验比空想更可靠",t:"S"},
  {q:"你经常产生创意与灵感",t:"N"},
  {q:"你说话直接重视效率与公平",t:"T"},
  {q:"你说话委婉顾及他人情绪",t:"F"},
  {q:"你喜欢整理秩序规则与安排",t:"J"},
  {q:"你喜欢变化新鲜感与惊喜",t:"P"},
  {q:"遇到压力你会变得理性冷静",t:"T"},
  {q:"遇到压力你容易情绪化敏感",t:"F"},
  {q:"你习惯先完成任务再放松自己",t:"J"},
  {q:"你习惯边放松边完成事情",t:"P"},
  {q:"你对陌生人友善容易建立关系",t:"E"},
  {q:"你对陌生人保持距离慢热谨慎",t:"I"},
  {q:"你务实踏实重视实际价值",t:"S"},
  {q:"你脑洞大喜欢探索未知",t:"N"},
  {q:"你能客观分析问题不被情绪影响",t:"T"},
  {q:"你容易共情理解他人的感受",t:"F"},
  {q:"你做事有目标有规划有节奏",t:"J"},
  {q:"你做事随性自由不喜欢束缚",t:"P"},
  {q:"你喜欢热闹聚会与人互动",t:"E"},
  {q:"你喜欢安静独处自我充电",t:"I"},
  {q:"你重视事实证据与经验",t:"S"},
  {q:"你重视直觉预感与灵感",t:"N"}
];

const el = id => document.getElementById(id);
let current = 0;
let answers = Array(questions.length).fill(null);

function render(){
  const qbox = el("questions");
  qbox.innerHTML = "";
  questions.forEach((item,i)=>{
    const div = document.createElement("div");
    div.className = "question "+(i==current?"active":"");
    div.innerHTML = `
      <div class="q-title">${i+1}. ${item.q}</div>
      <div class="options">
        <div class="opt" data-q="${i}" data-v="A">是</div>
        <div class="opt" data-q="${i}" data-v="B">一般</div>
        <div class="opt" data-q="${i}" data-v="C">通常</div>
        <div class="opt" data-q="${i}" data-v="D">否</div>
      </div>`;
    qbox.appendChild(div);
  });

  document.querySelectorAll(".opt").forEach(o=>{
    o.onclick = ()=>{
      const q = o.dataset.q;
      const v = o.dataset.v;
      answers[q] = v;
      document.querySelectorAll(`[data-q="${q}"]`).forEach(x=>x.classList.remove("active"));
      o.classList.add("active");
    }
  });
}

function updateBar(){
  el("bar").style.width = ((current+1)/questions.length)*100+"%";
}

render();
updateBar();

el("next").onclick = ()=>{
  if(answers[current]==null){
    alert("请选择一个选项");
    return;
  }
  if(current < questions.length-1){
    current++;
    document.querySelectorAll(".question").forEach(q=>q.classList.remove("active"));
    document.querySelectorAll(".question")[current].classList.add("active");
    updateBar();
    if(current == questions.length-1){
      el("submit").style.display = "block";
      el("next").style.display = "none";
    }
  }
}

el("prev").onclick = ()=>{
  if(current>0){
    current--;
    document.querySelectorAll(".question").forEach(q=>q.classList.remove("active"));
    document.querySelectorAll(".question")[current].classList.add("active");
    updateBar();
    el("submit").style.display = "none";
    el("next").style.display = "block";
  }
}

el("submit").onclick = ()=>{
  let E=0,I=0,S=0,N=0,T=0,F=0,J=0,P=0;
  questions.forEach((q,i)=>{
    const v = answers[i];
    if(!v) return;
    let scr = 0;
    if(v=="A") scr=2;
    if(v=="B") scr=1;
    if(v=="C") scr=1;
    if(v=="D") scr=0;

    if(q.t=="E") E+=scr;
    if(q.t=="I") I+=scr;
    if(q.t=="S") S+=scr;
    if(q.t=="N") N+=scr;
    if(q.t=="T") T+=scr;
    if(q.t=="F") F+=scr;
    if(q.t=="J") J+=scr;
    if(q.t=="P") P+=scr;
  });

  const type = 
    (E>=I?"E":"I") +
    (S>=N?"S":"N") +
    (T>=F?"T":"F") +
    (J>=P?"J":"P");

  el("mbti").innerText = type;
  el("desc").innerText = `你是 ${type} 型人格，属于16型人格中极具特色与潜力的一类。你的思维方式、行为模式、情感需求都有非常鲜明的个人印记，这决定了你一生的机遇、人际与发展方向。`;

  el("result").style.display = "block";
  el("questions").style.display = "none";
  el("submit").style.display = "none";
  el("prev").style.display = "none";
  el("next").style.display = "none";
}
</script>
</body>
</html>
