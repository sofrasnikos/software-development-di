## Αναφορά πρώτου μέρους ανάπυξης λογισμικού για πληροφοριακά συστήματα

1115201200185 ΒΑΓΓΕΛΗΣ ΤΣΙΑΤΟΥΡΑΣ  
1115201200168 ΝΙΚΟΣ ΣΟΦΡΑΣ

### Παραδοχές & λεπτομέρειες υλοποίησης

* Δεσμεύουμε στατικό χώρο για λέξεις κάτω των 20 χαρακτήρων και δυναμικό χώρο για τις μεγαλύτερες λέξεις. Αυτή η επιλογή έγινε για ισσοροπία ταχύτητας και εξοικονόμησης χώρου.
  Χρησιμοποιούμε την trie_node_get_word για να παίρνουμε δείκτη στο σωστό αντικείμενο.
* Έχουμε φτιάξει μια δομή για προσωρινή αποθήκευση και εκτύπωση (όταν δοθεί F) των αποτελεσμάτων της trie_query.
Πιο συγκεκριμένα, είναι ένας δισδιάστατος πίνακας χαρακτήρων που μπορεί να μεγαλώσει οριζόντια ή κατακόρυφα αν χρειαστεί. Κάθε γραμμή μπορεί να έχει διαφορετικό μέγεθος. Αν χρειαστεί προστίθενται κι άλλες γραμμές. Η δομή αυτή έχει δικό της unit test.
* Κάθε φορά που χρειαζόμαστε να χωρίσουμε ένα ngram σε λέξεις, καλούμε την split_ngram η οποία καλεί την strtok και αποθηκεύει αυτό που επιστρέφει σε ένα πίνακα δεικτών. Σαν delimiters έχουμε τους χαρακτήρες ' '(κενό) και '\n'.
* Στην delete_ngram διατρέχουμε το δέντρο από πάνω προς τα κάτω και αποθηκεύουμε τον "γονιό" του κάθε κόμβου σε ένα τοπικό πίνακα δεικτών ώστε να μπορούμε να διασχίσουμε το δέντρο προς τα πάνω.
* Η συνάρτηση binary_search επιστρέφει ένα struct το οποίο περιέχει ένα flag για το αν βρέθηκε το στοιχείο και τη θέση του, αν βρέθηκε.


### Compilation

* __make__ παράγει εκτελέσιμο trie
* __make u_test__ παράγει εκτελέσιμο αρχείο για unit testing
* __make clean__ διαγράφει εκτελέσιμα και αντικείμενα αρχεία


### Unit testing

Για το unit testing χρησιμοποιήθηκε το framework [Check](https://libcheck.github.io/check/).
