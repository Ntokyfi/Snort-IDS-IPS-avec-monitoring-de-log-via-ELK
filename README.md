# Snort-IDS-IPS-avec-monitoring-de-log-via-ELK
Projet de cybersécurité qui intégre Snort pour la détection/prévention des intrusions et ELK pour l'analyse des logs  
---
## En claire:  
Ce projet met en place **Snort** comme système de détection et de prévention d'intrusion (IDS/IPS), avec un monitoring des logs via la stack **ELK** (Elasticsearch, Logstash, Kibana) pour une analyse approfondie et la visualisation des événements de sécurité.  

## Prérequis

Avant de commencer, il est important d’avoir les éléments suivants installés sur notre système :
- **Snort** (pour IDS/IPS)
- **Filebeat** (pour collecter les logs)
- **ELK Stack** (Elasticsearch, Logstash, Kibana)
- **Linux** (Ubuntu ou autre distribution compatible)

## Étapes du projet

### 1. **Installation de Snort**
   - Installation de Snort sur une machine Linux.
   - Configuration de Snort en mode IDS/IPS.
   - Test du bon fonctionnement de Snort en générant des événements de détection.
   
   ![Capture d'écran de l'installation de Snort](images/snort_install.png)

### 2. **Configuration des interfaces réseau**
   - **Interface enp0s3** : Trafic entrant (Interface du réseau local).
   - **Interface enp0s8** : Trafic sortant vers le WAN.
   - Mise en place de Snort pour analyser le trafic entre ces deux interfaces.

   ![Schéma de la configuration réseau](images/network_config.png)

### 3. **Configuration de Filebeat**
   - Installation et configuration de **Filebeat** pour collecter les logs de Snort.
   - Configuration de **Filebeat** pour envoyer les logs vers **Logstash**.

   ![Configuration de filebeat.yml](images/filebeat_config.png)

### 4. **Installation et configuration de la stack ELK**
   - Installation d'  
   **Elasticsearch**:[elasticsearch](https://www.elastic.co/guide/en/elasticsearch/reference/8.16/install-elasticsearch.html)  
   **Logstash** [Logstash](https://www.elastic.co/guide/en/logstash/8.16/installing-logstash.html)  
   **Kibana** [Kibana](https://www.elastic.co/guide/en/kibana/8.16/install.html)  
   - Configuration de **Logstash** pour recevoir et traiter les logs de **Filebeat**.
   - Visualisation des logs dans **Kibana**.
   
   ![Capture d'écran de Kibana avec des logs](images/kibana_dashboard.png)

### 5. **Création de Dashboards dans Kibana**
   - Création de visualisations dans **Kibana** pour afficher les événements et alertes de sécurité détectés par Snort.
   - Mise en place de tableaux de bord pour un monitoring en temps réel.

   ![Exemple de tableau de bord Kibana](images/kibana_dashboard_example.png)

### 6. **Test du système**
   - Générer des événements de test avec **Snort** pour vérifier l'efficacité du système IDS/IPS.
   - Visualiser ces événements dans **Kibana** via les logs traités par **Filebeat** et **Logstash**.

   ![Graphique Kibana montrant les alertes](images/kibana_alerts.png)
