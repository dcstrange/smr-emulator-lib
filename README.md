smr-emulator-lib


待验证：

1. PB是否为覆盖写？
  方法：fio 随机写0 ~ 500MB后，在随机写100 ~ 500MB。观测有无高延迟出现。
  
2. 验证PB是否为band journal? 需要在STL-emu层维护 fifo band map.

依次写入 ：
0 ~ 100M; 200 ~ 300M; 400~500M; 200~300M; --|-- 1G ~ +
然后在1G ~ + 的过程中多次顺序读取 100 ~ 500M 
观测read latency. 

3. 验证清理时出现的空洞是否被新的写入填充？



