# 1η εργασία

1. Στο σκριπτάκι se_py.starter βρίσκουμε τα βασικά χαρακτηριστικά του συστήματος από τις προκαθορισμένες τιμές, δηλαδή:
* CPU freq: 4Ghz
* Memory Type: DDR3_1600_8x8
* Memory Channels: 2
* Memory size: 2GB

2. Στο αρχείο stats.txt, βρίσκουμε στη γραμμή 9 ότι:
>sim_freq                                 1000000000000
Αντίστοιχα, στο config.json, βρίσκουμε στη γραμμή 613:
>"type": "MinorOpClassSet"
που μας επιβεβαιώνει ότι έχουμε μοντέλο CPU minor.

3. Αν τρέξουμε την εντολή:
>./build/ARM/gem5.opt configs/example/se.py --list-cpu-types
μας εμφανίζει όλους τους πιθανούς τύπους cpu:
>Available BaseCPU classes:
	O3_ARM_v7a_3
	AtomicSimpleCPU
		Simple CPU model executing a configurable number of instructions per
		cycle. This model uses the simplified 'atomic' memory mode.
	ex5_big
	DerivO3CPU
	MinorCPU
	HPI
		The High-Performance In-order (HPI) CPU timing model is tuned to be
		representative of a modern in-order ARMv8-A implementation. The HPI
		core and its supporting simulation scripts, namely starter_se.py and
		starter_fs.py (under /configs/example/arm/) are part of the ARM
		Research Starter Kit on System Modeling. More information can be
		found at: http://www.arm.com/ResearchEnablement/SystemModeling
	ex5_LITTLE
	NonCachingSimpleCPU
		Simple CPU model based on the atomic CPU. Unlike the atomic CPU,
		this model causes the memory system to bypass caches and is
		therefore slightly faster in some cases. However, its main purpose
		is as a substitute for hardware virtualized CPUs when stress-testing
		the memory system.
	TimingSimpleCPU

3. α) Βλέπουμε ότι όταν τρέχουμε το πρόγραμμα hello στον minorCPU, έχουμε
διάρκεια 0.000026 seconds, ενώ με τον TimingSimpleCPU έχουμε 0.000029 seconds
από τα αντίστοιχα αρχεία stats.txt.

ΣΗΜΕΙΩΣΗ: Δεν καταφέραμε να κάνουμε compile και να τρέξουμε στον gem5 το πρόγραμμα που φτιάξαμε στη c, γι' αυτό χρησιμοποιήσαμε το hello.

3. β) Το μοντέλο TimingSimpleCPU δεν υποστήριζει pipeline, σε αντίθεση με τον MinorCPU
που υποστηρίζει 4 στάδια pipeline.

3. γ) Μείωσαμε τη συχνότητα του CPU στο Options.py στη γραμμή 85 σε 0.5GHz και ξανατρέξαμε το πρόγραμμα.
Παρατηρήσαμε στα stats.txt άνοδο στο χρόνο εκτέλεσης σε 0.000030 και  0.000035 seconds αντίστοιχα, λόγω της μείωσης της συχνότητας.



