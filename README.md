# Video-editing-auxiliary-tool-based-on-barrage-analysis-
原理是这样子的： 假设观众的弹幕是大众趣味的正确反馈，在精彩时刻就会有大量特定弹幕， 那么可以反向通过统计一段时间内特定弹幕的数量，来识别出一个长视频中受欢迎的部分。 统计是通过输入关键词来进行的，例如对于特别有趣的片段，观众倾向于发送“草”这一弹幕。 假设在一段时间内，草的弹幕超出了预设的限制（limit），工具应当记下该时间轴，并提供给剪辑者一个参考时间轴。 在一段时间内，由于网络延迟的问题，弹幕的出现不是同步的， 观众见证一个亮点时刻时，作为反应的弹幕也会分散在数秒之中。 因此将统计的范围放到当前时刻开始的5秒之内。只要总计的弹幕达到了阈值（limit） 就记下当前时刻，并且从20秒间隔（interval）后重新开始新一轮判定。 若当前时刻并不达标，将当前时间往后推进1秒。 之所以设置了20秒的冷却间隔（interval），是为了减少重复记轴—— 精彩镜头从来不是瞬间，而是从某个时间点开始的时间段 如果不设置冷却时间，那么相邻的数秒都会被纳入统计。 这样输出的数个结果的参考意义是很有限的。 统计开始容易，统计结束位置很难，但是结束位置可以人为判断，未必要越厨代庖。 因此这个工具旨在提供一个“精彩片段的开始大致时间”， 给剪辑者、补长视频的观众作为跳转参考。 这样一来工具的运行时间也能一定程度上减少。
