// 初始化游戏变量
var maiMaiLoveScore = 0;

// 序幕：节目邀请
scene("邀请");
bgImage("path/to/invite-bg.jpg");
narrator("你收到了《再见爱人》节目的邀请，决定参与节目，希望通过节目修复与伴侣的关系。");

// 第一章：乐高事件
scene("乐高事件");
bgImage("path/to/lego-bg.jpg");
chara("麦麦", "path/to/mai-mai.png", "left");
chara("李行亮", "path/to/li-xing-liang.png", "right");
maiMai("我们去购物吧，你想买什么？");
option([
    { text: "买乐高", next: "legoChoice", score: 10 },
    { text: "不买乐高", next: "noLegoChoice", score: 5 }
]);

scene("legoChoice");
maiMai("你真的想要乐高吗？");
liXingLiang("其实...我不太喜欢乐高。");
maiMaiLoveScore += 10;
reward("体贴爱人");

scene("noLegoChoice");
maiMai("那我们看看别的吧。");
maiMaiLoveScore += 5;
reward("务实伴侣");

// 第二章：青团事件
scene("青团事件");
bgImage("path/to/qingtuan-bg.jpg");
maiMai("你喜欢吃蛋黄肉松的青团吗？");
option([
    { text: "喜欢", next: "qingtuanLike", score: 8 },
    { text: "不喜欢", next: "qingtuanDislike", score: 3 }
]);

scene("qingtuanLike");
maiMai("那我们买一些吧。");
maiMaiLoveScore += 8;
reward("细心厨师");

scene("qingtuanDislike");
maiMai("那我们试试别的口味？");
maiMaiLoveScore += 3;
reward("尝试新事物");

// 第三章：熏鸡事件
scene("熏鸡事件");
bgImage("path/to/chicken-bg.jpg");
maiMai("我们买些熏鸡怎么样？");
option([
    { text: "买两只", next: "buyTwoChickens", score: 7 },
    { text: "买一只", next: "buyOneChicken", score: 4 }
]);

scene("buyTwoChickens");
maiMai("买了两只，我们慢慢吃。");
maiMaiLoveScore += 7;
reward("慷慨分享");

scene("buyOneChicken");
maiMai("先买一只尝尝。");
maiMaiLoveScore += 4;
reward("谨慎消费");

// 第四章：毯子事件
scene("毯子事件");
bgImage("path/to/blanket-bg.jpg");
maiMai("天气冷了，我们拿毯子吧。");
option([
    { text: "给伴侣", next: "giveToPartner", score: 9 },
    { text: "自己用", next: "useForSelf", score: 2 }
]);

scene("giveToPartner");
maiMai("你先用毯子，别着凉了。");
maiMaiLoveScore += 9;
reward("温暖守护者");

scene("useForSelf");
maiMai("我先拿毯子，有点冷。");
maiMaiLoveScore += 2;
reward("自我保护");

// 第五章：绿色事件
scene("绿色事件");
bgImage("path/to/green-bg.jpg");
maiMai("你穿绿色很好看，要不要试试？");
option([
    { text: "鼓励尝试", next: "encourageGreen", score: 6 },
    { text: "不强迫", next: "dontForceGreen", score: 5 }
]);

scene("encourageGreen");
maiMai("试试看，绿色很适合你。");
maiMaiLoveScore += 6;
reward("时尚先锋");

scene("dontForceGreen");
maiMai("不喜欢就算了，我们看看别的。");
maiMaiLoveScore += 5;
reward("尊重个性");

// 第六章：密码事件
scene("密码事件");
bgImage("path/to/password-bg.jpg");
maiMai("家里的支付密码，你知道的，对吧？");
option([
    { text: "告诉伴侣", next: "tellPassword", score: 8 },
    { text: "保密", next: "keepSecret", score: 3 }
]);

scene("tellPassword");
maiMai("这是我们的共同账户，你也应该知道密码。");
maiMaiLoveScore += 8;
reward("信任伴侣");

scene("keepSecret");
maiMai("这个密码还是我来保管吧。");
maiMaiLoveScore += 3;
reward("独立自主");

// 第七章：夫妻单线旅行路线三选一事件
scene("旅行路线选择");
bgImage("path/to/travel-bg.jpg");
maiMai("我们计划一下旅行吧，有三个地方可以选择。");
option([
    { text: "选择伴侣喜欢的", next: "choosePartners", score: 10 },
    { text: "选择自己喜欢的", next: "chooseOwn", score: 6 }
]);

scene("choosePartners");
maiMai("我们去你一直想去的地方吧。");
maiMaiLoveScore += 10;
reward("浪漫旅行家");

scene("chooseOwn");
maiMai("我想去这个地方，你愿意陪我吗？");
maiMaiLoveScore += 6;
reward("自我实现");

// 第八章：家务事件
scene("家务事件");
bgImage("path/to/housework-bg.jpg");
maiMai("家里的家务活，我们怎么分配？");
option([
    { text: "公平分配", next: "fairShare", score: 7 },
    { text: "自己多做一些", next: "doMore", score: 4 }
]);

scene("fairShare");
maiMai("我们按照各自的时间来分配家务吧。");
maiMaiLoveScore += 7;
reward("公平伴侣");

scene("doMore");
maiMai("我今天比较有空，多做一些吧。");
maiMaiLoveScore += 4;
reward("勤劳蜜蜂");

// 结局：再见爱人
scene("结局");
bgImage("path/to/goodbye-bg.jpg");
narrator("节目接近尾声，你和伴侣的关系如何发展，取决于你的选择。");
if (maiMaiLoveScore > 50) {
    narrator("你获得了'模范爱人'的称号。");
} else if (maiMaiLoveScore > 30) {
    narrator("你获得了'成长伴侣'的称号。");
} else {
    narrator("你获得了'需要努力'的称号。");
}

// 结束游戏
endGame();
