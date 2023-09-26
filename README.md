# ITM

huangz6@vdiubuntu026:~$ cd /work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out/
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk '{print $3, $7, $10, $17, $21, $24}' log_tcp_complete | head -n 1
c_pkts_all:3 c_bytes_uniq:7 c_pkts_retx:10 s_pkts_all:17 s_bytes_uniq:21 s_pkts_retx:24
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk '{ sum += $3 ; count++ } END { print "avg:" sum/count }' log_tcp_complete
avg:93.573
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ avg:93.573
bash: avg:93.573: command not found
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk '{sum3 += $3; sum7 += $7; sum10 += $10; sum17 += $17; sum21 += $21; sum24 += $24} END {print "Avg:", sum3/NR, sum7/NR, sum10/NR, sum17/NR, sum21/NR, sum24/NR}' log_tcp_complete 
Avg: 93.573 36741.1 0.491826 178.716 214087 2.2859
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk 'BEGIN {
>         threshold1 = 0.01;
>         threshold2 = 0.10;
>         threshold3 = 0.20;
>     }
>     NR > 1{
>         if ($7 != 0) {
>             if ($10 / $7 > threshold1) count1++;
>             if ($10 / $7 > threshold2) count2++;
>             if ($10 / $7 > threshold3) count3++;
>             total++;
>         }
>     }
>     END {
>         printf "Percentage exceeding %.2f: %.2f%%\n", threshold1, (count1 / total) * 100;
>         printf "Percentage exceeding %.2f: %.2f%%\n", threshold2, (count2 / total) * 100;
>         printf "Percentage exceeding %.2f: %.2f%%\n", threshold3, (count3 / total) * 100;
>     }' log_tcp_complete
Percentage exceeding 0.01: 1.96%
Percentage exceeding 0.10: 0.57%
Percentage exceeding 0.20: 0.35%
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk 'NR > 1 { if ($3 > max) max = $3 } END { print "Max Column 3:", max }' log_tcp_complete
Max Column 3: 1700014
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_1huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/ghuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/huangz6@vdiubuntu026:/work/courses/unix/T/huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_0huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstathuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/201huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04huangz6@vdiubuntu026:/work/chuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04huangz6@vdiubuntu026:/work/cohuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.huangz6@vhuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/genhuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tsthuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tsthuangz6@vdiubuntu026:/work/courses/unix/T/huangz6@vdiubuntu026:/work/courses/unix/T/huangz6@vdiubuntu026:/work/chuangz6@vdiubuntu026:/work/chuangz6@vdiubuhuangz6@vdiubuntu026:/work/chuangz6@vdiubuhuhuangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ 
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ 
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ 
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ 
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ 
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ 
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ 
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk 'NR > 1 { if ($3 > max) max = $3 } END { print "Max Column 3:", max }' log_tcp_complete
Max Column 3: 1700014
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk 'NR > 1 { if ($9 > max) max = $9 } END { print "Max Column 9:", max }' log_tcp_complete
Max Column 9: 313220528
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk 'NR > 1 { if ($17 > max) max = $17 } END { print "Max Column 17:", max }' log_tcp_complete
Max Column 17: 2791706
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk 'NR > 1 { if ($23 > max) max = $23 } END { print "Max Column 23:", max }' log_tcp_complete
Max Column 23: 3835783508
huangz6@vdiubuntu026:/work/courses/unix/T/ELEC/E7130/general/trace/tstat/2017_04_11_18_00.out$ awk 'NR > 1 { if ($31 > max) max = $31 } END { print "Max Column 31:", max }' log_tcp_complete
Max Column 31: 72901107.834000
