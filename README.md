1.  a. Create User :

        - koda
        command : sudo useradd -ms /bin/sh koda

        - dako
        command : sudo useradd -ms /bin/sh dako

    b. Create group and add 2 user into group

        - command : sudo groupadd devteam

        - koda
            command : sudo usermod -aG devteam koda

        - dako
            command : sudo usermod -aG devteam dako

    c. Create project direktori

        - command : sudo mkdir -p /srv/projectX

2.  command : sudo chown koda:devteam /srv/projectX

3.  a. - Owner: full access → rwx → 7

        - Group: read & execute → r-x → 5

        - Others: no access → --- → 0

        b. command : sudo chmod 750 /srv/projectX

4.  #### - sebagai user koda<br/>

    - command : cd /srv/projectX

    - command : mkdir src <br/>

    - command : mkdir data <br/>

    - command : touch README.md <br/>

    - command : touch src/app.sh <br/>

    - command : touch data/input.txt

5.  ### boleh kasih permission dasar dulu

    command : chmod u=rw, g=r, o=r src/app.sh

    ### tambah execute untuk owner dan group

    command : chmod ug+x src/app.sh

    ### pastikan others tidak punya x

    command : chmod o-x src/app.sh

6.  command : chmod 600 data/input.txt

7.  command : chmod -R g+rwX /srv/projectX/src

8.  command : chown -R koda:devteam /srv/projectX
