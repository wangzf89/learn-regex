<p align="center">
    <br/>
    <a href="https://github.com/ziishaned/learn-regex">
        <img src="https://i.imgur.com/bYwl7Vf.png" alt="Learn Regex">
    </a>
    <br /><br />
    <p>
        <a href="https://twitter.com/home?status=Learn%20regex%20the%20easy%20way%20by%20%40ziishaned%20http%3A//github.com/ziishaned/learn-regex">
            <img src="https://img.shields.io/badge/twitter-tweet-blue.svg?style=flat-square"/>
        </a>
        <a href="https://twitter.com/ziishaned">
            <img src="https://img.shields.io/badge/feedback-@ziishaned-blue.svg?style=flat-square" />
        </a>
    </p>
</p>


## Μεταφράσεις:

* [English](../README.md)
* [Español](../translations/README-es.md)
* [Français](../translations/README-fr.md)
* [Português do Brasil](../translations/README-pt_BR.md)
* [中文版](../translations/README-cn.md)
* [日本語](../translations/README-ja.md)
* [한국어](../translations/README-ko.md)
* [Turkish](../translations/README-tr.md)
* [Greek](../translations/README-gr.md)
* [Magyar](../translations/README-hu.md)
* [Polish](../translations/README-pl.md)

## Τι είναι μια Κανονική Έκφραση (Regular Expression);

> Μια κανονική έκφραση είναι μια ομάδα χαρακτήρων ή συμβόλων που χρησιμοποιούνται για την εύρεση ενός συγκεκριμένου μοτίβου χαρακτήρων μέσα σ'ένα κείμενο.

Μια κανονική έκφραση, είναι μια σειρά χαρακτήρων τους οποίους αναζητούμε μέσα σε ένα κείμενο. Η αναζήτηση αυτή
ξεκινά από τα αριστερά και συνεχίζει προς τα δεξιά. Ο όρος "Κανονική Έκφραση" είναι κάπως μεγάλος οπότε πολύ συχνά
θα τον συναντήσετε στην συντομότερη μορφή του ως "regex" ή "regexp". Οι εκφράσεις αυτές χρησιμοποιούνται
για αντικατάσταση λέξεων μέσα σε κείμενο, για επικυρώσεις τύπων, για αποκοπή ενός κομματιού
string με βάση κάποιου μοτίβου αναζήτησης και για πολλά άλλα.

Φανταστείτε ότι πρέπει να γράψουμε μια εφαρμογή και ότι θέλουμε να ορίσουμε κανόνες για την δημιουργία
ονόματος χρήστη (username). Σ'αυτή την περίπτωση, θέλουμε να επιτρέψουμε την χρήση γραμμάτων και
αριθμών καθώς και την παύλα και κάτω παύλα. Θέλουμε επίσης να περιορίσουμε τον αριθμό χαρακτήρων
του ονόματος χρήστη ώστε να μην φαίνεται μεγάλο και άσχημο. Για να το κάνουμε αυτό, μπορούμε να χρησιμοποιήσουμε
την παρακάτω κανονική έκφραση:

<br/><br/>
<p align="center">
  <img src="../img/regexp-en.png" alt="Regular expression">
</p>

Η παραπάνω κανονική έκφραση θα δεχτεί ως σωστά τα ονόματα χρήστη `john_doe`, `jo-hn_doe` και
`john12_as`. Όμως δεν θα δεχτεί το `Jo` αφού περιέχει ένα κεφαλαίο γράμμα και είναι πολύ
μικρό.

## Πίνακας Περιεχομένων

- [Βασικά Μοτίβα Αναζήτησης](#1-Βασικά-Μοτίβα-Αναζήτησης)
- [Μεταχαρακτήρες](#2-Μεταχαρακτήρες)
  - [Τελεία](#21-Τελεία)
  - [Σύνολα Χαρακτήρων](#22-Σύνολα-Χαρακτήρων)
    - [Σύνολο Χαρακτήρων προς Εξαίρεση](#221-Σύνολο-Χαρακτήρων-προς-Εξαίρεση)
  - [Επαναλήψεις](#23-Επαναλήψεις)
    - [Ο Αστερίσκος](#231-Ο-Αστερίσκος)
    - [Το Σύμβολο της Πρόσθεσης](#232-Το-Σύμβολο-της-Πρόσθεσης)
    - [Το Ερωτηματικό](#233-Το-Ερωτηματικό)
  - [Αγκύλες](#24-Αγκύλες)
  - [Ομάδα Χαρακτήρων](#25-Ομάδα-Χαρακτήρων)
  - [Εναλλαγή](#26-Εναλλαγή)
  - [Ειδικός Χαρακτήρας Διαφυγής](#27-Ειδικός-Χαρακτήρας-Διαφυγής)
  - [Σύμβολα "Άγκυρες"](#28-Σύμβολα-"Άγκυρες")
    - [Το Σύμβολο ^](#281-Το-Σύμβολο-^)
    - [Το Δολάριο](#282-Το-Δολάριο)
- [Συντομογραφίες Συνόλων Χαρακτήρων](#3-Συντομογραφίες-Συνόλων-Χαρακτήρων)
- [Αναζήτηση](#4-Αναζήτηση)
  - [Θετική Αναζήτηση προς τα Μπροστά](#41-Θετική-Αναζήτηση-προς-τα-Μπροστά)
  - [Αρνητική Αναζήτηση προς τα Μπροστά](#42-Αρνητική-Αναζήτηση-προς-τα-Μπροστά)
  - [Θετική Αναζήτηση προς τα Πίσω](#43-Θετική-Αναζήτηση-προς-τα-Πίσω)
  - [Αρνητική Αναζήτηση προς τα Πίσω](#44-Αρνητική-Αναζήτηση-προς-τα-Πίσω)
- [Σημαίες](#5-Σημαίες)
  - [Χωρίς Διάκριση Πεζών-Κεφαλαίων](#51-Χωρίς-Διάκριση-Πεζών-Κεφαλαίων)
  - [Καθολική Αναζήτηση](#52-Καθολική-Αναζήτηση)
  - [Πολλές Γραμμές](#53-Πολλές-Γραμμές)

## 1. Βασικά Μοτίβα Αναζήτησης

Μια κανονική έκφραση είναι απλώς ένα μοτίβο, δηλαδή μια σειρά χαρακτήρων, που χρησιμοποιούμε ώστε να κάνουμε
αναζήτηση σε ένα κείμενο (πχ για να βρούμε ένα γράμμα ή μια λέξη κλπ). Για παράδειγμα, η κανονική έκφραση `the`
αναπαριστά: το γράμμα `t`, ακολουθούμενο από το γράμμα `h`, ακολουθούμενο από το γράμμα `e`.

<pre>
"the" => The fat cat sat on <a href="#learn-regex"><strong>the</strong></a> mat.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/dmRygT/1)

Η κανονική έκφραση `123` "ταιριάζει" με το string `123`. Η έκφραση αυτή
αναζητείται μέσα σ'ένα string εισόδου αντιστοιχίζοντας κάθε χαρακτήρα της με κάθε
χαρακτήρα του string. Οι κανονικές εκφράσεις συνήθως λαμβάνουν υπόψη το αν τα γράμματα είναι
κεφαλαία ή πεζά και άρα η έκφραση `The` δεν θα ταίριαζε με το string `the`.

<pre>
"The" => <a href="#learn-regex"><strong>The</strong></a> fat cat sat on the mat.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/1paXsy/1)

## 2. Μεταχαρακτήρες

Οι μεταχαρακτήρες είναι τα δομικά στοιχεία των κανονικών εκφράσεων. Δεν αντιπροσωπεύουν
τον εαυτό τους αλλά ερμηνεύονται με ειδικό τρόπο. Μερικοί από αυτούς, έχουν
ειδικό νόημα και γι'αυτό γράφονται μέσα σε αγκύλες. Οι μεταχαρακτήρες είναι οι παρακάτω:

|Μεταχαρακτήρας|Περιγραφή|
|:----:|----|
|.|Η τελεία είναι ισοδύναμη με οποιονδήποτε μεμονωμένο χαρακτήρα εκτός από αυτόν για αλλαγή γραμμής.|
|[ ]|Κλάση χαρακτήρων. Είναι ισοδύναμη με οποιονδήποτε χαρακτήρα βρίσκεται μέσα σε αγκύλες.|
|[^ ]|Κλάση χαρακτήρων εξαίρεσης. Είναι ισοδύναμη με οποιονδήποτε χαρακτήρα δεν βρίσκεται μέσα σε αγκύλες|
|*|Ταιριάζει με 0 ή παραπάνω επαναλήψεις του προηγούμενου συμβόλου.|
|+|Ταιριάζει με 1 ή παραπάνω επαναλήψεις του προηγούμενου συμβόλου.|
|?|Κάνει το προηγούμενο σύμβολο προαιρετικό.|
|{n,m}|Αγκύλες. Ταιριάζει με τουλάχιστον "n" αλλά όχι με παραπάνω από "m" επαναλήψεις του προηγούμενου συμβόλου.|
|(xyz)|Ομάδα χαρακτήρων. Είναι ισοδύναμη με τους χαρακτήρες xyz ακριβώς με την σειρά στην οποία βρίσκονται.|
|&#124;|Εναλλαγή. Ταιριάζει είτε με τους χαρακτήρες που βρίσκονται πριν είτε μετά το σύμβολο.|
|&#92;|Παραλείπει το ειδικό νόημα του χαρακτήρα. Αυτό μας επιτρέπει να ταιριάξουμε χαρακτήρες
ειδικής χρήσης <code>[ ] ( ) { } . * + ? ^ $ \ &#124;</code>|
|^|Αναζητά το μοτίβο που ακολουθεί στην αρχή μιας εισόδου.|
|$|Αναζητά το μοτίβο που ακολουθεί στο τέλος μιας εισόδου.|

## 2.1 Τελεία

Η τελεία `.` είναι το πιο απλό παράδειγμα μεταχαρακτήρα. Είναι ισοδύναμη με οποιονδήποτε
μεμονωμένο χαρακτήρα με εξαίρεση τον χαρακτήρα για επιστροφή στην αρχή της γραμμής
και αυτόν για νέα σειρά. Για παράδειγμα, η κανονική έκφραση `.ar` αναπαριστά: οποιονδήποτε
χαρακτήρα που ακολουθείται από το γράμμα `a`, που με την σειρά του ακολουθείται από το γράμμα `r`.

<pre>
".ar" => The <a href="#learn-regex"><strong>car</strong></a> <a href="#learn-regex"><strong>par</strong></a>ked in the <a href="#learn-regex"><strong>gar</strong></a>age.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/xc9GkU/1)

## 2.2 Σύνολα Χαρακτήρων

Τα σύνολα χαρακτήρων καλούνται αλλιώς και κλάσεις χαρακτήρων. Τα σύνολα αυτά γράφονται μέσα
σε αγκύλες. Για τον ορισμό της εμβέλειας ενός τέτοιου συνόλου χρησιμοποιείται μια παύλα
για να διαχωρίζει την αρχή από το τέλος. Η σειρά των χαρακτήρων, που βρίσκονται μέσα στην
εμβέλεια του συνόλου που ορίζεται από τις αγκύλες, δεν έχει σημασία. Για παράδειγμα,
η κανονική έκφραση `[Tt]he` αναπαριστά: ένα κεφαλαίο `T` ή ένα πεζό `t`, που ακολουθείται
από το γράμμα `h`, που με τη σειρά του ακολουθείται από το γράμμα `e`.

<pre>
"[Tt]he" => <a href="#learn-regex"><strong>The</strong></a> car parked in <a href="#learn-regex"><strong>the</strong></a> garage.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/2ITLQ4/1)

Όμως, μια τελεία μέσα σε ένα σύνολο χαρακτήρων, είναι μια κλασική τελεία και δεν εκλαμβάνεται
ως μεταχαρακτήρας. Η κανονική έκφραση `ar[.]` αναπαριστά: ένα πεζό γράμμα `a`, που
ακολουθείται από το γράμμα `r`, που με την σειρά του ακολουθείται από τον χαρακτήρα `.`.

<pre>
"ar[.]" => A garage is a good place to park a c<a href="#learn-regex"><strong>ar.</strong></a>
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/wL3xtE/1)

### 2.2.1 Σύνολο Χαρακτήρων προς Εξαίρεση

Γενικά, το σύμβολο ^ αναπαριστά την αρχή ενός string, αλλά όταν βρίσκεται
μέσα σε αγκύλες ([] όχι {}), αναπαριστά ένα σύνολο χαρακτήρων που θα εξαιρεθούν από την διαδικασία
της αναζήτησης. Για παράδειγμα, η κανονική έκφραση `[^c]ar` αναπαριστά: οποιονδήποτε χαρακτήρα
εκτός από το `c`, που ακολουθείται από τον χαρακτήρα `a`, που ακολουθείται από
το `r`.

<pre>
"[^c]ar" => The car <a href="#learn-regex"><strong>par</strong></a>ked in the <a href="#learn-regex"><strong>gar</strong></a>age.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/nNNlq3/1)

## 2.3 Επαναλήψεις

Οι μεταχαρακτήρες `+`, `*` και `?`, χρησιμοποιούνται για να προσδιοριστεί
το πόσες φορές επαναλαμβάνεται ένα υπό-μοτίβο χαρακτήρων μέσα στο string εισόδου. Αυτοί οι
μεταχαρακτήρες συμπεριφέρονται διαφορετικά ανάλογα με την περίσταση.

### 2.3.1 Ο Αστερίσκος

Το σύμβολο `*` ψάχνει για μηδέν ή παραπάνω επαναλήψεις της έκφρασης
που βρίσκεται πριν από αυτό. Η κανονική έκφραση `a*` αναπαριστά: αναζήτηση για μηδέν ή παραπάνω
επαναλήψεις του πεζού χαρακτήρα `a`. Όταν το σύμβολο * βρίσκεται μετά από ένα σύνολο
ή κλάση χαρακτήρων, τότε εντοπίζει ολόκληρο το σύνολο όσες φορές και αν υπάρχει σε μια
γραμμή. Για παράδειγμα, η κανονική έκφραση `[a-z]*` αναπαριστά: οποιονδήποτε συνδυασμό
πεζών γραμμάτων που βρίσκονται στην σειρά.

<pre>
"[a-z]*" => T<a href="#learn-regex"><strong>he</strong></a> <a href="#learn-regex"><strong>car</strong></a> <a href="#learn-regex"><strong>parked</strong></a> <a href="#learn-regex"><strong>in</strong></a> <a href="#learn-regex"><strong>the</strong></a> <a href="#learn-regex"><strong>garage</strong></a> #21.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/7m8me5/1)

Το σύμβολο `*` μπορεί να χρησιμοποιηθεί σε συνδυασμό με τον χαρακτήρα `.` ώστε
να αναζητηθεί μια ακολουθία χαρακτήρων. Μπορεί επίσης να χρησιμοποιηθεί με τον
χαρακτήρα κενού `\s` ώστε να αναζητηθεί μια ακολουθία κενών. Για παράδειγμα, η
έκφραση `\s*cat\s*` αναπαριστά: μηδέν ή περισσότερα κενά, που ακολουθούνται από
τον πεζό χαρακτήρα `c`, που ακολουθείται από τον πεζό χαρακτήρα `a`, που ακολουθείται
 από τον πεζό χαρακτήρα `t`, που ακολουθείται από μηδέν ή περισσότερα κενά.

<pre>
"\s*cat\s*" => The fat<a href="#learn-regex"><strong> cat </strong></a>sat on the <a href="#learn-regex">con<strong>cat</strong>enation</a>.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/gGrwuz/1)

### 2.3.2 Το Σύμβολο της Πρόσθεσης

Με σύμβολο `+` γίνεται αναζήτηση για μία ή περισσότερες επαναλήψεις του προηγούμενου του χαρακτήρα.
Για παράδειγμα, η κανονική έκφραση `c.+t` αναπαριστά: το πεζό γράμμα `c`, που ακολουθείται
από τουλάχιστον ένα χαρακτήρα, που ακολουθείται από το πεζό γράμμα `t`. Πρέπει να διευκρινίσουμε
ότι το `t` είναι το τελευταίο `t` της πρότασης.

<pre>
"c.+t" => The fat <a href="#learn-regex"><strong>cat sat on the mat</strong></a>.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/Dzf9Aa/1)

### 2.3.3 Το Ερωτηματικό

Σε μια κανονική έκφραση, ο μεταχαρακτήρας `?` κάνει τον χαρακτήρα που βρίσκεται πριν από αυτόν,
προαιρετικό ως προς την εύρεσή του. Έτσι γίνεται αναζήτηση για μηδέν ή παραπάνω περιπτώσεις εμφάνισης
του προηγούμενου από το ερωτηματικό χαρακτήρα. Για παράδειγμα, η κανονική έκφραση `[T]?he` αναπαριστά:
το προαιρετικό κεφαλαίο `T`, που ακολουθείται από πεζό `h`, που ακολουθείται από
πεζό `e`.

<pre>
"[T]he" => <a href="#learn-regex"><strong>The</strong></a> car is parked in the garage.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/cIg9zm/1)

<pre>
"[T]?he" => <a href="#learn-regex"><strong>The</strong></a> car is parked in t<a href="#learn-regex"><strong>he</strong></a> garage.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/kPpO2x/1)

## 2.4 Αγκύλες

Οι αγκύλες στις κανονικές εκφράσεις ονομάζονται αλλιώς και "ποσοτικοποιητές" αφού
χρησιμοποιούνται για την εύρεση όλων επαναλήψεων ενός χαρακτήρα ή μιας
ομάδας χαρακτήρων μέσα σ'ένα κείμενο. Για παράδειγμα, η κανονική έκφραση `[0-9]{2,3}` αναπαριστά: την
αναζήτηση τουλάχιστον 2 ψηφίων το ένα μετά το άλλο αλλά όχι παραπάνω από 3 (στους χαρακτήρες από το 0 ως το 9).

<pre>
"[0-9]{2,3}" => The number was 9.<a href="#learn-regex"><strong>999</strong></a>7 but we rounded it off to <a href="#learn-regex"><strong>10</strong></a>.0.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/juM86s/1)

Μπορούμε να παραλείψουμε τον δεύτερο αριθμό. Για παράδειγμα, η κανονική έκφραση
`[0-9]{2,}` αναπαριστά: την αναζήτηση 2 ή περισσότερων ψηφίων το ένα μετά το άλλο. Αν αφαιρέσουμε και
την κόμμα, τότε η κανονική έκφραση `[0-9]{3}` αναπαριστά: την σύγκριση ακριβώς 3 ψηφίων.

<pre>
"[0-9]{2,}" => The number was 9.<a href="#learn-regex"><strong>9997</strong></a> but we rounded it off to <a href="#learn-regex"><strong>10</strong></a>.0.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/Gdy4w5/1)

<pre>
"[0-9]{3}" => The number was 9.<a href="#learn-regex"><strong>999</strong></a>7 but we rounded it off to 10.0.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/Sivu30/1)

## 2.5 Ομάδα Χαρακτήρων

Μια ομάδα χαρακτήρων είναι μια ομάδα υπό-μοτίβων που γράφονται μέσα σε παρενθέσεις `(...)`.
Όπως είπαμε και προηγουμένως, σε μια κανονική έκφραση, αν τοποθετήσουμε έναν ποσοτικοποιητή μετά από έναν
χαρακτήρα, τότε αυτός ο χαρακτήρας θα βρεθεί όσες φορές και αν υπάρχει μέσα στο κείμενο στο οποίο
εκτελείται η αναζήτηση. Παρομοίως, αν τον βάλουμε μετά από μια ομάδα χαρακτήρων. Για παράδειγμα,
η κανονική έκφραση `(ab)*` ταιριάζει με μηδέν ή παραπάνω επαναλήψεις του χαρακτήρα
"ab". Ακόμη, μπορούμε να χρησιμοποιήσουμε τον μεταχαρακτήρα εναλλαγής `|` μέσα σε μια ομάδα χαρακτήρων.
Για παράδειγμα, η κανονική έκφραση `(c|g|p)ar` αναπαριστά: τους πεζούς χαρακτήρες `c`,
`g` ή `p`, που ακολουθούνται από τον χαρακτήρα `a`, που ακολουθείται από τον χαρακτήρα `r`.

<pre>
"(c|g|p)ar" => The <a href="#learn-regex"><strong>car</strong></a> is <a href="#learn-regex"><strong>par</strong></a>ked in the <a href="#learn-regex"><strong>gar</strong></a>age.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/tUxrBG/1)

## 2.6 Εναλλαγή

Στις κανονικές εκφράσεις, η κάθετη γραμμή `|`, ορίζει μια εναλλαγή.
Έτσι δηλαδή γίνεται μια επιλογή μεταξύ πολλαπλών εκφράσεων. Ίσως σκέφτεστε ότι
η εναλλαγή και τα σύνολα , λειτουργούν με τον ίδιο τρόπο. Αλλά η μεγάλη διαφορά τους
είναι ότι τα σύνολα χαρακτήρων δουλεύουν με χαρακτήρες ενώ η εναλλαγή με εκφράσεις.
Για παράδειγμα, η κανονική έκφραση `(T|t)he|car` αναπαριστά: τον κεφαλαίο χαρακτήρα `T`
ή τον πεζό χαρακτήρα `t`, που ακολουθείται από πεζό χαρακτήρα `h`, που ακολουθείται από
πεζό χαρακτήρα `e` ή πεζό χαρακτήρα `c`, που ακολουθείται από πεζό χαρακτήρα `a`, που
ακολουθείται από πεζό χαρακτήρα `r`.

<pre>
"(T|t)he|car" => <a href="#learn-regex"><strong>The</strong></a> <a href="#learn-regex"><strong>car</strong></a> is parked in <a href="#learn-regex"><strong>the</strong></a> garage.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/fBXyX0/1)

## 2.7 Ειδικός Χαρακτήρας Διαφυγής

Το σύμβολο `\` χρησιμοποιείται στις κανονικές εκφράσεις ώστε να αγνοηθεί η ειδική σημασία
που μπορεί να έχει ο χαρακτήρας που βρίσκεται μετά από αυτό. Αυτό μας επιτρέπει να αναζητήσουμε ένα
σύμβολο, συμπεριλαμβανομένων των ειδικών χαρακτήρων `{ } [ ] / \ + * . $ ^ | ?`. Άρα για αναζήτηση
ειδικών χαρακτήρων, τοποθετούμε ακριβώς πριν το σύμβολο `\`.

Για παράδειγμα, η κανονική έκφραση `.` χρησιμοποιείται για αναζήτηση οποιουδήποτε χαρακτήρα εκτός από
αυτόν για την νέα γραμμή. Η παρακάτω κανονική έκφραση ψάχνει για το σύμβολο της τελείας `.` σε ένα string εισόδου. Η
`(f|c|m)at\.?` αναπαριστά: ένα πεζό γράμμα `f`, `c` ή `m`, που ακολουθείται από τον πεζό τον
χαρακτήρα `a`, που ακολουθείται από το πεζό γράμμα `t`, που ακολουθείται από τον προαιρετικό χαρακτήρα `.`.

<pre>
"(f|c|m)at\.?" => The <a href="#learn-regex"><strong>fat</strong></a> <a href="#learn-regex"><strong>cat</strong></a> sat on the <a href="#learn-regex"><strong>mat.</strong></a>
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/DOc5Nu/1)

## 2.8 Σύμβολα "Άγκυρες"

Σε μια κανονική έκφραση, χρησιμοποιούμε "άγκυρες" για να ελέγξουμε αν το σύμβολο που αναζητάμε είναι
το πρώτο ή το τελευταίο σύμβολο ενός string. Οι άγκυρες είναι δύο τύπων:
Πρώτα είναι το σύμβολο `^` που ελέγχει αν ο χαρακτήρας που ψάχνουμε είναι ο πρώτος
χαρακτήρας της εισόδου και μετά είναι το σύμβολο του δολαρίου `$` που ελέγχει αν ο χαρακτήρας που
ψάχνουμε είναι ο τελευταίος στο string εισόδου.

### 2.8.1 Το Σύμβολο ^

Το σύμβολο `^` χρησιμοποιείται για να ελέγξουμε αν ο χαρακτήρας που ψάχνουμε είναι ο πρώτος χαρακτήρας
του string εισόδου. Αν δοκιμάσουμε την κανονική έκφραση `^a` (ψάχνουμε δηλαδή αν το a είναι το πρώτο
σύμβολο) στο string εισόδου `abc`, τότε βλέπουμε ότι όντως το `a` είναι ο πρώτος χαρακτήρας. Αλλά
αν δοκιμάσουμε την κανονική έκφραση `^b` στην παραπάνω είσοδο, τότε δεν θα πάρουμε κάποιο αποτέλεσμα.
Αυτό συμβαίνει επειδή στην έκφραση `abc` το "b" δεν είναι ο πρώτος χαρακτήρας. Ας ρίξουμε μια ματιά
στην κανονική έκφραση `^(T|t)he` η οποία ψάχνει για: έναν κεφαλαίο χαρακτήρα `T` ή έναν
πεζό χαρακτήρα `t` που να είναι ο πρώτος χαρακτήρας της εισόδου και να ακολουθείται από
έναν πεζό χαρακτήρα `h`, που ακολουθείται από έναν πεζό χαρακτήρα `e`.

<pre>
"(T|t)he" => <a href="#learn-regex"><strong>The</strong></a> car is parked in <a href="#learn-regex"><strong>the</strong></a> garage.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/5ljjgB/1)

<pre>
"^(T|t)he" => <a href="#learn-regex"><strong>The</strong></a> car is parked in the garage.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/jXrKne/1)

### 2.8.2 Το Δολάριο

Το σύμβολο του δολαρίου `$` χρησιμοποιείται για να ελέγξουμε αν ο χαρακτήρας που αναζητάμε είναι ο τελευταίος
χαρακτήρας του string εισόδου. Για παράδειγμα, η κανονική έκφραση `(at\.)$` αναπαριστά: έναν
πεζό χαρακτήρα `a`, που ακολουθείται από έναν πεζό χαρακτήρα `t`, που ακολουθείται από μια τελεία `.`
και όλα αυτά πρέπει να είναι οι τελευταίοι χαρακτήρες της εισόδου.

<pre>
"(at\.)" => The fat c<a href="#learn-regex"><strong>at.</strong></a> s<a href="#learn-regex"><strong>at.</strong></a> on the m<a href="#learn-regex"><strong>at.</strong></a>
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/y4Au4D/1)

<pre>
"(at\.)$" => The fat cat. sat. on the m<a href="#learn-regex"><strong>at.</strong></a>
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/t0AkOd/1)

##  3. Συντομογραφίες Συνόλων Χαρακτήρων

Οι κανονικές εκφράσεις χρησιμοποιούν κάποιες συντομογραφίες για τα σύνολα χαρακτήρων που
χρησιμοποιούνται πιο συχνά και έτσι γίνονται πιο εύκολες και βολικές για τον χρήστη.
Οι συντομογραφίες των συνόλων χαρακτήρων είναι οι παρακάτω:

|Συντομογραφία|Περιγραφή|
|:----:|----|
|.|Αναζήτηση όλων των χαρακτήρων εκτός από αυτόν για νέα γραμμή|
|\w|Αναζήτηση αλφαριθμητικών χαρακτήρων: `[a-zA-Z0-9_]`|
|\W|Αναζήτηση μη αλφαριθμητικών χαρακτήρων: `[^\w]`|
|\d|Αναζήτηση στα ψηφία: `[0-9]`|
|\D|Αναζήτηση χαρακτήρων που δεν είναι αριθμοί: `[^\d]`|
|\s|Αναζήτηση του χαρακτήρα του κενού: `[\t\n\f\r\p{Z}]`|
|\S|Αναζήτηση χαρακτήρων που δεν είναι το κενό: `[^\s]`|

## 4. Αναζήτηση

Η προς τα μπροστά και προς τα πίσω αναζήτηση, είναι συγκεκριμένοι τύποι συνόλων που
ονομάζονται ***non-capturing groups*** (Χρησιμοποιούνται για αναζήτηση κάποιου μοτίβου
αλλά δεν συμπεριλαμβάνονται στην λίστα των χαρακτήρων που ψάχνουμε). Οι αναζητήσεις προς τα μπροστά, χρησιμοποιούνται
όταν το μοτίβο έχει πριν ή μετά ένα ακόμη μοτίβο. Για παράδειγμα, αν θέλουμε να βρούμε όλους
τους αριθμούς που βρίσκονται μετά τον χαρακτήρα `$` στο παρακάτω string
`$4.44 and $10.88`, τότε θα χρησιμοποιήσουμε την κανονική έκφραση `(?<=\$)[0-9\.]*`
η οποία: βρίσκει όλους τους αριθμούς που βρίσκονται μετά από το σύμβολο`$` και περιέχουν τον χαρακτήρα `.` .
Παρακάτω μπορείτε να δείτε τους τύπους αναζήτησης στις κανονικές εκφράσεις:

|Σύμβολο|Περιγραφή|
|:----:|----|
|?=|Θετική Αναζήτηση προς τα Μπροστά|
|?!|Αρνητική Αναζήτηση προς τα Μπροστά|
|?<=|Θετική Αναζήτηση προς τα Πίσω|
|?<!|Αρνητική Αναζήτηση προς τα Πίσω|

### 4.1 Θετική Αναζήτηση προς τα Μπροστά

Η θετική αναζήτηση προς τα μπροστά, εγγυάται ότι το πρώτο μέρος της έκφρασης θα
ακολουθείται από την ανάλογη έκφραση για προς τα μπροστά αναζήτηση. Το αποτέλεσμα
περιλαμβάνει μόνο το κείμενο που ταιριάζει στο πρώτο κομμάτι της έκφρασης. Για να ορίσουμε
μια τέτοια αναζήτηση, χρησιμοποιούμε παρενθέσεις. Μέσα σε αυτές, τοποθετούμε ένα ερωτηματικό
και ένα ίσον όπως παρακάτω: `(?=...)`. Η έκφραση για προς τα μπροστά αναζήτηση, γράφεται μετά
το σύμβολο του ίσον μέσα στις παρενθέσεις. Για παράδειγμα, η κανονική έκφραση
`(T|t)he(?=\sfat)` αναπαριστά: είτε το πεζό γράμμα `t` είτε το κεφαλαίο γράμμα
`T`, που ακολουθείται από το γράμμα `h`, που με την σειρά του ακολουθείται από το γράμμα `e`. Μέσα στις
παρενθέσεις, ορίζουμε την θετική προς τα μπροστά αναζήτηση, η οποία λέει στον μηχανισμό αναζήτησης
της κανονικής έκφρασης να βρει τα `The` ή τα `the` που ακολουθούνται από την λέξη `fat`.

<pre>
"(T|t)he(?=\sfat)" => <a href="#learn-regex"><strong>The</strong></a> fat cat sat on the mat.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/IDDARt/1)

### 4.2 Αρνητική Αναζήτηση προς τα Μπροστά

Η αρνητική αναζήτηση προς τα μπροστά, χρησιμοποιείται όταν θέλουμε όλες τις εκφράσεις που
ταιριάζουν με το μοτίβο που αναζητάμε, που όμως δεν ακολουθούνται από κάποιο άλλο μοτίβο.
Αυτή η αναζήτηση ορίζεται όπως και η παραπάνω αλλά αντί για το σύμβολο `=` χρησιμοποιούμε το `!`,
με αυτό τον τρόπο: `(?!...)`. Ας δούμε την κανονική έκφραση `(T|t)he(?!\sfat)` η οποία: επιστρέφει
όλα τα `The` ή `the` που υπάρχουν στο string εισόδου και δεν ακολουθούνται από την λέξη `fat`
μετά από κενό.

<pre>
"(T|t)he(?!\sfat)" => The fat cat sat on <a href="#learn-regex"><strong>the</strong></a> mat.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/V32Npg/1)

### 4.3 Θετική Αναζήτηση προς τα Πίσω

Η θετική αναζήτηση προς τα πίσω, χρησιμοποιείται όταν θέλουμε να βρούμε όλες τις εκφράσεις που
ταιριάζουν με ένα μοτίβο (που ορίζουμε εμείς) που βρίσκεται πριν από αυτές. Αυτή η αναζήτηση χρησιμοποιεί τα
σύμβολα `(?<=...)`. Για παράδειγμα, η κανονική έκφραση `(?<=(T|t)he\s)(fat|mat)`:
επιστρέφει όλες τις λέξεις `fat` ή `mat` που βρίσκονται μετά την λέξη `The` ή `the`.

<pre>
"(?<=(T|t)he\s)(fat|mat)" => The <a href="#learn-regex"><strong>fat</strong></a> cat sat on the <a href="#learn-regex"><strong>mat</strong></a>.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/avH165/1)

### 4.4 Αρνητική Αναζήτηση προς τα Πίσω

Η αρνητική αναζήτηση προς τα πίσω χρησιμοποιείται όταν θέλουμε να βρούμε όλες τις εκφράσεις που
ταιριάζουν με το μοτίβο αναζήτησης, χωρίς όμως να υπάρχει άλλο μοτίβο (που ορίζουμε εμείς) πριν από αυτές.
Αυτή η αναζήτηση χρησιμοποιεί τα σύμβολα  `(?<!...)`. Για παράδειγμα, η κανονική έκφραση
`(?<!(T|t)he\s)(cat)`: επιστρέφει όλες τις λέξεις `cat` που δεν βρίσκονται μετά από την λέξη `The` ή `the`.

<pre>
"(?&lt;!(T|t)he\s)(cat)" => The cat sat on <a href="#learn-regex"><strong>cat</strong></a>.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/8Efx5G/1)

## 5. Σημαίες

Οι σημαίες καλούνται αλλιώς και τροποποιητές αφού επηρεάζουν τον τρόπο αναζήτησης των
κανονικών εκφράσεων. Μπορούν να χρησιμοποιηθούν με οποιαδήποτε σειρά και σε οποιονδήποτε συνδυασμό
συμβόλων και είναι αναπόσπαστο κομμάτι των RegExp.

|Σημαία|Περιγραφή|
|:----:|----|
|i|Αλλάζει την αναζήτηση ώστε να μην ενδιαφέρεται για τον αν τα γράμματα είναι πεζά ή κεφαλαία.|
|g|Καθολική αναζήτηση: Ψάχνει ένα μοτίβο σε ολόκληρο το string εισόδου.|
|m|Πολλαπλές γραμμές: Οι μεταχαρακτήρες άγκυρας λειτουργούν σε όλες τις γραμμές.|

### 5.1 Χωρίς Διάκριση Πεζών-Κεφαλαίων

Ο τροποποιητής `i` χρησιμοποιείται για αναζήτηση που δεν κάνει διακρίσεις μεταξύ πεζών
και κεφαλαίων γραμμάτων. Για παράδειγμα, η κανονική έκφραση `/The/gi` αναπαριστά: ένα
κεφαλαίο γράμμα `T`, που ακολουθείται από έναν πεζό χαρακτήρα `h`, που ακολουθείται από τον χαρακτήρα `e`.
Στο τέλος της κανονικής έκφρασης υπάρχει η σημαία `i` η οποία λέει στην κανονική
έκφραση να αγνοήσει το αν ένας χαρακτήρας είναι πεζός ή κεφαλαίος. Όπως βλέπετε υπάρχει και η
σημαία `g` ώστε η αναζήτηση του μοτίβου να γίνει σε όλο το string εισόδου.

<pre>
"The" => <a href="#learn-regex"><strong>The</strong></a> fat cat sat on the mat.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/dpQyf9/1)

<pre>
"/The/gi" => <a href="#learn-regex"><strong>The</strong></a> fat cat sat on <a href="#learn-regex"><strong>the</strong></a> mat.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/ahfiuh/1)

### 5.2 Καθολική Αναζήτηση

Ο τροποποιητής `g`χρησιμοποιείται για καθολική αναζήτηση (για να βρεθούν δηλαδή όλες οι
περιπτώσεις που ταιριάζουν με το μοτίβο αναζήτησης και να μην σταματήσει στην πρώτη εύρεση). Για παράδειγμα, η
κανονική έκφραση `/.(at)/g` αναπαριστά: οποιονδήποτε χαρακτήρα εκτός από αυτόν για
νέα γραμμή, που ακολουθείται από τον πεζό χαρακτήρα `a`, που ακολουθείται από τον πεζό
χαρακτήρα `t` και αφού στο τέλος της κανονικής έκφρασης υπάρχει η σημαία `g`,
θα βρεθούν όλες οι περιπτώσεις που περιγράφονται από την παραπάνω κανονική έκφραση και όχι μόνο
η πρώτη (που είναι η προκαθορισμένη συμπεριφορά όταν δεν υπάρχει η σημαία `g`).

<pre>
"/.(at)/" => The <a href="#learn-regex"><strong>fat</strong></a> cat sat on the mat.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/jnk6gM/1)

<pre>
"/.(at)/g" => The <a href="#learn-regex"><strong>fat</strong></a> <a href="#learn-regex"><strong>cat</strong></a> <a href="#learn-regex"><strong>sat</strong></a> on the <a href="#learn-regex"><strong>mat</strong></a>.
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/dO1nef/1)

### 5.3 Πολλές Γραμμές

Ο τροποποιητής `m` χρησιμοποιείται για αναζήτηση σε πολλές γραμμές. Όπως είπαμε
προηγουμένως, οι άγκυρες `(^, $)` χρησιμοποιούνται για να ελέγξουμε αν ένα μοτίβο
βρίσκεται στην αρχή ή στο τέλος του string εισόδου. Αν θέλουμε οι άγκυρες αυτές να
ισχύουν για κάθε γραμμή, τότε χρησιμοποιούμε την σημαία `m`. Για παράδειγμα, η
κανονική έκφραση `/at(.)?$/gm` αναπαριστά: τον πεζό χαρακτήρα `a`, που ακολουθείται
από τον πεζό χαρακτήρα `t` και προαιρετικά οτιδήποτε άλλο εκτός από τον χαρακτήρα για
νέα γραμμή. Και αφού υπάρχει και η σημαία `m`, η κανονική έκφραση θα αναζητήσει
το μοτίβο στο τέλος κάθε γραμμής του string.

<pre>
"/.at(.)?$/" => The fat
                cat sat
                on the <a href="#learn-regex"><strong>mat.</strong></a>
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/hoGMkP/1)

<pre>
"/.at(.)?$/gm" => The <a href="#learn-regex"><strong>fat</strong></a>
                  cat <a href="#learn-regex"><strong>sat</strong></a>
                  on the <a href="#learn-regex"><strong>mat.</strong></a>
</pre>

[Δοκιμή της κανονικής έκφρασης](https://regex101.com/r/E88WE2/1)

## Contribution

* Report issues
* Open pull request with improvements
* Spread the word
* Reach out to me directly at ziishaned@gmail.com or [![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/ziishaned.svg?style=social&label=Follow%20%40ziishaned)](https://twitter.com/ziishaned)

## License

MIT &copy; [Zeeshan Ahmad](https://twitter.com/ziishaned)