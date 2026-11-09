# Mghogha FloodWatch

Site web pédagogique en français consacré à un projet IoT de surveillance simulée du niveau d'eau dans la zone industrielle de Mghogha, Tanger.

## Démarrage

Ouvrir `index.html` dans un navigateur moderne. Aucun serveur, compte ni installation de dépendances n'est nécessaire. Les polices Google sont optionnelles (polices système de secours si hors ligne).

## Fonctionnalités

- Simulation locale d'une mesure entière entre 0 et 25 cm toutes les 5 secondes.
- Quatre niveaux : Normal < 5 cm ; Vigilance de 5 à < 10 cm ; Alerte de 10 à < 20 cm ; Critique >= 20 cm.
- Graphique Canvas, jauge, minimum/maximum, compteur, journal des événements.
- Pause/reprise, réinitialisation, tests manuels à 2, 7, 15 et 22 cm.
- Export CSV des données simulées de la session.
- Présentation de l'architecture Node-RED, Mosquitto/MQTT, InfluxDB et Grafana.
- Proposition conceptuelle d'installation physique : sonde JSN-SR04T, ESP32, panneau solaire, LiFePO4, régulateur et boîtier de protection.

## Limites importantes

Les données affichées sont générées dans le navigateur : il n'y a **aucune connexion réelle** à Node-RED, Mosquitto, InfluxDB, Grafana ou à un capteur. Les seuils sont pédagogiques et ne sont pas validés pour la sécurité routière. Le schéma du prototype est conceptuel et non à l'échelle.

## Pour connecter une installation réelle

Une intégration en production nécessiterait un service backend sécurisé (par exemple une passerelle HTTP/WebSocket) pour consommer les données MQTT/InfluxDB. Ne jamais exposer de token InfluxDB ni d'identifiants MQTT dans le code client. Authentification, HTTPS, validation des données et tests de terrain sont indispensables.
