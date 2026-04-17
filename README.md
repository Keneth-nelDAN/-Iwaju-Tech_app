# iwaju_mirroring_app

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

## ####################


###### ####### Architecture prévu pour le projet
# -SERVEUR (Node.js)
    Il s'occupe des échanges grâce à Socket.io
# -ÉMETTEUR (Mobile - React Native)
    Utilise react-native-webrtc pour capturer l'écran et envoyer le flux.
# -RÉCEPTEUR (Desktop/Web - React)
    Utilise l'API WebRTC native du navigateur pour recevoir et afficher le flux.


###### ####### Clarification conceptuelle
# -react-native-webrtc
    Est un module open-source qui permet d'intégrer des capacités de communication en temps réel (audio, vidéo et données) directement dans les applications React Native pour Android, iOS et tvOS. 
    Il fournit une interface JavaScript native pour utiliser les fonctionnalités WebRTC, notamment :
        Appels vidéo et audio : Établissement de connexions pair-à-pair (P2P) à faible latence. 
        Partage d'écran : Capture et transmission de l'écran de l'appareil. 
        Canal de données : Transmission de données arbitraires entre les pairs. 
        Compatibilité : Utilise la révision M124 de WebRTC et supporte le Unified Plan (désactivant le Plan B) et le simulcast depuis les versions récentes.

# L'API WebRTC native du navigateur
    Désigne l'ensemble des interfaces JavaScript standardisées (définies par le W3C et l'IETF) intégrées directement dans les navigateurs modernes pour permettre la communication en temps réel (audio, vidéo, données) sans aucun plugin tiers.  Ces API natives reposent sur une architecture pair à pair (P2P) qui établit une connexion directe entre les navigateurs, en utilisant un serveur de signalisation uniquement pour la négociation initiale. 

    Les trois composants principaux de cette API sont :
    MediaStream (et getUserMedia) : Permet d'accéder aux ressources locales comme la caméra et le microphone pour capturer et manipuler des flux audio/vidéo. 
    RTCPeerConnection : Gère l'établissement et la maintenance de la connexion réseau entre deux pairs, en s'occupant de la négociation des codecs et de la traversée des pare-feux grâce aux protocoles ICE, STUN et TURN.
    RTCDataChannel : Offre un canal de communication bidirectionnel et fiable pour échanger des données arbitraires (textuelles ou binaires) directement entre les navigateurs.



###### ####### Ressources

- [Cours / Tuto débutant] Apprendre Javascript de A à Z – Les bases (1/6) (https://youtu.be/Ew7KG2j8eII?si=MS3gnJgz5GkJwsov)
-















# FEUILLE DE ROUTE DE DÉVELOPPEMENT
1- Créer une application flutter avec le package flutter_webrtc

webrtc: Web Real-Time Communications
C'est une technologie qui permet aux applications ou site d'établir des connexions peer-to-peer (modèle de réseau décentralisé où chaque ordinateur connecté agit simultanément comme client et serveur, permettant des échanges directs sans passer par un serveur central) entre navigateurs sans intermédiaires pour réaliser le streaming vidéo et ou la transmission de flux audio ou d'autres données arbitraires.
WebRTC ne sert pas uniquement à créer des applications de bureau; il est aussi utilisé pour créer des applications iOS et Android. La principale différence entre WebRTC pour les applications de bureau et mobiles, vous devez utiliser une bibliothèque tierce pour que le navigateur des appareils mobiles puisse accéder à la caméra et au microphone.

Flutter WebRTC:
Flutter WebRTC est à l'avant-garde de la communication en temps réel dans les applications mobiles et Web.
Flutter WebRTC est un plugin utilisé dans les applications flutter pour permettre la communication en temps réel. Il utilise la technologie Web Real-Time Communications pour permettre que l'audio et la communication vidéo se produire directement entre les navigateurs et les appareils sans avoir besoin de serveur intermédiaire à l'exeption de la signalisation initiale et de l'établissement de la connexion.
En intégrant le plugin Flutter WebRTC, les développeurs peuvent créer des applications Flutter multiplateformes prenant en charge appels vidéo en direct et appels audio, connexions peer-to-peer et canaux de données. Ceci est particulièrement utile pour créer des applications qui nécessitent une interaction en temps réel, telles que outils de visioconférence, applications de diffusion en direct, plateformes collaboratives et plus encore.
C'est ce qui nous concerne ici nous: <span style="color: blue;">la diffusion en direct</span>

















A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
