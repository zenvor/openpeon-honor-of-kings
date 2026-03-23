# openpeon-honor-of-kings

A [peon-ping](https://github.com/PeonPing/peon-ping) voice pack featuring Honor of Kings (王者荣耀) game announcements and character voice lines. Your AI coding assistant will now sound like a MOBA battlefield.

## Install

```bash
peon packs install honor_of_kings
peon packs use honor_of_kings
```

## Sound Map

| Event | Trigger | Voice Lines |
|---|---|---|
| `session.start` | Session opens | "欢迎来到王者峡谷" / "欢迎来到王者荣耀" / "敌军还有5秒到达战场" / "来和我玩吧" / "你怎么知道是我" / "哇，你是我见过最帅的客人" |
| `task.acknowledge` | AI accepts task | "全军出击" / "准备迎战" / "大招已经好了" / "正在前往支援" / "清理兵线" / "跟着我" / "我来抓人了" / "优先推塔" / "准备越塔强攻" / and more |
| `task.complete` | Task finished | First Blood / Double Kill / Triple Kill / Quadra Kill / Pentakill / Hexakill / Heptakill / Octokill / Killing Spree / Rampage / Unstoppable / Legendary / Godlike / Victory / "干的漂亮" |
| `task.error` | Something failed | "You Have Been Slain" / "Your Turret Has Been Destroyed" / "有人偷塔" / "小心对方偷塔" / "开始撤退" / "回防高地" |
| `input.required` | Waiting for input | "请求支援" / "请求集合" / "打团了，别单带" / "支援我！" / "我方水晶正在被攻击" |
| `resource.limit` | Rate limit hit | "经济落后，别团" / "猥琐发育，别浪" / "兵线没到，撤退" / "别团，等人齐" / "状态不好，撤退" |
| `user.spam` | Too many messages | "不要一直戳人家了" / "你不喜欢看我吗" / Aced |
| `task.progress` | Long task running | "稳住，我们能赢" / "等等我，马上到" / "继续推，我回防" / "等我集合打团" |
| `session.end` | Session closes | Defeat / "别忘了常来看我哦" |

## Sources

- System announcements from *Honor of Kings* (王者荣耀)
- XiShi (西施) character voice lines from *Honor of Kings*
- Store VO from *Honor of Kings*

## License

MIT
