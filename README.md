# picard
Ansible playbook for kiratech

## Playbook

Realizzare un playbook Ansible che permetta di svolgere le seguenti attivita':

1. [ ] Provisioning di due VM CentOS. Le VM possono essere locali oppure su un Cloud provider a scelta.
2. [ ] Configurare le VM:
    1. [ ] Assicurarsi che la partizione utilizzata da Docker abbia almeno 40GB di spazio disponibile, effettuando un opportuno resize.
3. [ ] Setup di Docker sulle VM
4. [ ] Configurare Docker:
    1. [ ] Esporre le API REST del Docker Daemon in modo sicuro
    2. [ ] Assicurarsi che il Docker Daemon sia configurato come un servizio che parta automaticamente all'avvio del sistema
5. [ ] Configurare un Docker Swarm sulle VM, che sia accessibile in modo sicuro. Assicurarsi di riuscire ad interagire e deployare servizi sullo Swarm dalla macchina locale.
6. [ ] _Opzionalmente:_ Testare un task a scelta dei precedenti utilizzando Molecule

Rappresentare ogni attivita' con opportuni ruoli Ansible e relativi task. E' altamente consigliato il riuso di ruoli e playbook Ansible resi disponibili nella community open-source (alcuni dei quali gia' linkati nel testo a mo' di esempio e in basso tra i riferimenti utili). In caso di riutilizzo di codice e' importante motivare I criteri di selezione del ruolo, conoscerne le feature e I contenuti, e saper descrivere eventuali
personalizzazioni effettuate ai fini di svolgere le attivita' di cui sopra. 

Versioning del Codice:
1. [x] Versionare il codice su un repository pubblico su Github.com, in modo che vi sia una chiara descrizione del lavoro svolto nella History del repository; 

Continuous Integration:
1. [ ] Configurare una pipeline di Continuous Integration su un tool a scelta (consiglio: Travis, per la semplice integrazione con GitHub, Ansible Docker);
2. [ ] La pipeline deve:
    1. [ ] Eseguire il linting del codice e fallire in caso di errori, che vanno
    opportunamente corretti
    2.[ ] _Opzionalmente:_ Eseguire il test realizzato al punto 6 in automatico ad ogni push di codicesul repository

Riferimenti utili:
* Ansible User Guide: https://docs.ansible.com/ansible/latest/user_guide/index.html
* Ansible Galaxy: https://galaxy.ansible.com/
* Best Practices: http://hakunin.com/six-ansible-practices
* Testing Ansible provisioning locally: https://www.hamvocke.com/blog/local-ansible-testing/
* Testing Ansible roles and playbooks: https://www.digitalocean.com/community/tutorials/how-to-implement-continuous-testing-of-ansible-roles-using-molecule-and-travis-ci-on-ubuntu-18-04
* Importanza del version pinning: [in generale](https://medium.com/the-guild/how-should-you-pin-your-npm-dependencies-and-why-2b8d545c7312), [legato a Docker](https://www.tjohearn.com/2018/03/01/the-case-for-pinning-versions-of-docker-dependencies/) e infrastruttura
* Playbook ricco di ruoli e ben documentato per il setup di Docker Enterprise Edition: https://github.com/HewlettPackard/Docker-SimpliVity