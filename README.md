# honor_of_kings

A [peon-ping](https://github.com/PeonPing/peon-ping) voice pack featuring Honor of Kings (王者荣耀) game announcements and character voice lines. Your AI coding assistant will now sound like a MOBA battlefield.

## Install

```bash
peon packs use --install honor_of_kings
```

## Sound Map

| Event | Trigger | Voice Lines |
|---|---|---|
| `session.start` | Session opens | "欢迎来到王者荣耀" / "欢迎来到王者峡谷" / "来和我玩吧" / "你怎么知道是我" / "哇，你是我见过最帅的客人" / "这么多好货别错过哟" / "你是买不到我的哟" / "朋友齐心，排位上星" |
| `task.acknowledge` | AI accepts task | "跟着我" / "集合埋伏" / "我来抓人了" / "优先推塔" / "注意野区" / "收到" / "帮我看蓝，谢谢" / "保护我方输出" / "等等我，马上到" / "敌人消失" / "集合准备团战" / "求人BUFF，谢谢" / "全体进攻中路" / "拖住，我偷塔" / "猥琐发育，别浪" / "优先攻击输出" / "正在前往支援" |
| `task.complete` | Task finished | Double Kill / Triple Kill / Quadra Kill / Pentakill / Killing Spree / Rampage / Unstoppable / Legendary / Godlike / Shut Down / Victory / "干的漂亮" / Enemy Double Kill / Enemy Triple Kill / Enemy Quadra Kill / Enemy Pentakill / Enemy Hexakill / Enemy Heptakill / Enemy Killing Spree / Enemy Rampage / Enemy Unstoppable / Enemy Legendary / Enemy Godlike / Enemy Off to Kill / Enemy Ought to Kill / Enemy Up to Kill |

Note: High-tier streak variants above Pentakill are kept only for `enemy` announcements in this pack.
| `task.error` | Something failed | "You Have Been Slain" / "Your Turret Has Been Destroyed" / "我方高地防御塔正在被攻击" / "有人偷塔" / "小心对方偷塔" / "开始撤退" / "回防高地" |
| `input.required` | Waiting for input | "打团了，别单带" / "我方水晶正在被攻击" / "我方防御塔正在被攻击" |
| `resource.limit` | Rate limit hit | "经济落后，别团" / "猥琐发育，别浪" / "兵线没到，撤退" / "别团，等人齐" / "清完兵线再团" / "状态不好，撤退" |
| `user.spam` | Too many messages | "不要一直戳人家了" / "你不喜欢看我吗" / Aced |
| `task.progress` | Long task running | "稳住，我们能赢" / "等等我，马上到" / "继续推，我回防" / "等我集合打团" |
| `session.end` | Session closes | Defeat / "You Have Been Slain" / "别忘了常来看我哦" |

## Sources

- System announcements from *Honor of Kings* (王者荣耀)
- XiShi (西施) character voice lines from *Honor of Kings*
- Store VO from *Honor of Kings*
