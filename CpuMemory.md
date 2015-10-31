
```
#How to measure memory of a process over time

for((i=0;;++i)) { echo $i ` grep VmSize /proc/\`pidof firefox\`/status | grep -o '[0-9]*'`; sleep 1 || break; } > data

graph -T X data



#How to measure cpu usage over time...??

for((i=0;;++i)) { echo $i ` grep vruntime /proc/\`pidof firefox\`/sched | grep -o '[0-9]*'`; sleep .1 || break; } > data

cut -d ' ' -f1,3 data > new_data #????

graph -T X new_data

```