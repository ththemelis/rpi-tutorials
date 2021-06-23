# Διακομιστής ιστοσελίδων

Για να έχουμε έναν πλήρως λειτουργικό διακομιστή δυναμικών ιστοσελίδων, θα πρέπει να εγκαταστήσουμε τουλάχιστον 3 λογισμικά. Τον διακομιστή στατικών ιστοσελίδων **Apache**, την **PHP** για την παραγωγή δυναμικών ιστοσελίδων και μια βάση δεδομένων **MariaDB**.

## Εγκατάσταση Apache

Η εγκατάσταση του Apache Web Server, γίνεται πολύ απλά με την παρακάτω εντολή:

`sudo apt install apache2 -y`

Από αυτήν την στιγμή. ο Apache είναι ενεργός. Για να ελέγξουμε την λειτουργία του, θα πρέπει να αρχικά να μάθουμε της διεύθυνση ΙΡ που έχει το Raspberry Pi. Για αυτό τον λόγο γράφουμε την εντολή:

`sudo ifconfig`

<p align="center">
    <img src="images/ip-address.png" alt="Η διεύθυνση ΙΡ του Raspberry Pi" />
</p>

Αφού γνωρίζουμε τη διεύθυνση ΙΡ, αν ανοίξουμε έναν φυλλομετρητή και γράψουμε την συγκεκριμένη διεύθυνση, θα μας δείξει την δοκιμαστική ιστοσελίδα του Apache. Στην περίπτωσή μας όμως, θα πρέπει να κάνουμε ακόμα ένα βήμα. Να ανοίξουμε την πόρτα 80 στο τοίχος προστασίας γράφοντας:

`sudo ufw allow 80`

και πλέον είμαστε έτοιμοι να ελέγξουμε την λειτουργία του διακομιστή ιστοσελίδων.

<p align="center">
    <img src="images/apache-first-page.png" alt="Δοκιμαστική ιστοσελίδα Apache" />
</p>

Ο προεπιλεγμένος φάκελος στον οποίο αποθηκεύονται οι ιστοσελίδες είναι στο μονοπάτι **/var/www/html**.

## Εγκατάσταση PHP

Η PHP μας δίνει τη δυνατότητα να δημιουργούμε δυναμικές ιστοσελίδες και η εγκατάσταση της, στον Apache, γίνεται με την παρακάτω εντολή:

`sudo apt install php libapache2-mod-php`

Για να ελέγξουμε την καλή λειτουργία της εγκατάστασης της PHP, θα πρέπει να δημιουργήσουμε μια ιστοσελίδα η οποία θα περιέχει εντολές της PHP. Αρχικά, θα πρέπει να αλλάξουμε τρέχοντα φάκελο με την εντολή `cd /var/www/html` και στη συνέχεια να δημιουργήσουμε μια απλή ιστοσελίδα. Γράφουμε `sudo nano test.php` και στον κειμενογράφο επικολλούμε την εντολή `<?php phpinfo(); ?>`. 

Αποθηκεύουμε πατώντας **Ctrl+O** και βγαίνουμε από το nano πατώντας **Ctrl+X**.

Ανοίγουμε έναν φυλλομετρητή και γράφουμε τη διεύθυνση του **http://<Διεύθυνση του Raspberry Pi>/test.php**


## Εγκατάσταση MariaDB