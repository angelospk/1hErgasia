#3η εργασία


1. To dyanmic power αφορά την κατανάλωση του συστήματος σε λειτουργία, δηλαδή όταν εκτελεί ένα πρόγραμμα, ενώ το leakage αφορά την κατανάλωση του συστήματος, λόγω διαρροών ενέργειας από τα τρανζίστορ. Ακόμα και όταν βρίσκονται σε ανάστροφη πόλωση, μπορεί να υπάρχουν μικρές διαρροές ρεύματος. Είναι ένα δείγμα λοιπόν, της κατανάλωσης του συστήματος, ανεξαρτήτως αν τρέχει κάποιο πρόγραμμα, κάποιο task ή αν είναι stand by.

2. Ένας σύγχρονος επεξεργαστής καταναλώνει διαφορετική ενέργεια όταν βρίσκεται υπό φόρτο εργασίας και διαφορετική όταν είναι σε αναμονή, δίχως να εκτελεί κάτι. Η σωστότερη και αποδοτικότερη διαχείριση της ενέργειας που καταναλώνει ένας επεξεργαστής μπορεί να αφορά λοιπόν την εξοικονόμηση ενέργειας σε κατάσταση αναμονής, όπου επηρεάζουν την κατανάλωση στατικοί παράγοντες, όπως το leakage, και όχι δυναμικοί. Επομένωης, αν ο πρώτος επεξεργαστής ξοδεύει σταθερά 5 Watts, αλλά ο δεύτερος όταν βρίσκεται σε αναμονή και δεν υπάρχει ισχύς δυναμικής κατανάλωσης ξοδεύει αισθητά λιγότερα από 5 Watts θα μπορούσε να έχει μεγαλύτερη διάρκεια μπαταρίας εν τέλει (υποθέτοντας ότι δε λειτουργεί συνεχώς με φόρτο).

3. Κάποια βασικά από τα αποτελέσματα του McPAT για τον Xeon είναι τα εξής:
Technology 65 nm
  Using Long Channel Devices When Appropriate
  Interconnect metal projection= aggressive interconnect technology projection
  Core clock Rate(MHz) 3400

*****************************************************************************************
Processor: 
  Area = 410.507 mm^2
  Peak Power = 134.938 W
  Total Leakage = 36.8319 W
  Peak Dynamic = 98.1063 W
  Subthreshold Leakage = 35.1632 W
  Subthreshold Leakage with power gating = 16.3977 W
  Gate Leakage = 1.66871 W
  Runtime Dynamic = 72.9199 W

Αντίστοιχα, τα αποτελέσματα του McPAT για τον A9 επεξεργαστή:
Technology 40 nm
  Using Long Channel Devices When Appropriate
  Interconnect metal projection= conservative interconnect technology projection
  Core clock Rate(MHz) 2000

*****************************************************************************************
Processor: 
  Area = 5.39698 mm^2
  Peak Power = 1.74189 W
  Total Leakage = 0.108687 W
  Peak Dynamic = 1.6332 W
  Subthreshold Leakage = 0.0523094 W
  Gate Leakage = 0.0563774 W
  Runtime Dynamic = 2.96053 W

Μπορείτε να τα δείτε πιο αναλυτικά στα αντίστοιχα αρχεία results.τχτ .



http://www.gem5.org/wiki/images/b/bf/Summit2017_powerframework.pdf

