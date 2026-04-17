
---

### 1 Fondations et Serveur de Signalisation
Le serveur Node.js est le "standard téléphonique" qui permettra aux deux appareils de se trouver.

* **Objectif :** Créer un serveur capable de relayer les messages SDP (Session Description Protocol) et les candidats ICE.
* **Tâches :**
    * Réutilisation du serveur `server.js` (Socket.io).
    * Implémentation les listeners : `offer`, `answer`, `ice-candidate`.
    * **Test de validation :** Créer deux clients web simples qui s'échangent un texte via le serveur pour valider que le relais Socket.io est bidirectionnel et synchrone.

### 2 Emetteur Mobile - React Native
Partie technique. Maîtrise de l'accès aux APIs natives.

* **Objectif :** Capturer l'écran Android et créer un flux `MediaStream`.
* **Tâches :**
    * Initialiser le projet: npxnpx @react-native-community/cli init Nom_de_projet
    * Installer `react-native-webrtc`.
    * **Configuration native :** Modifier `AndroidManifest.xml` (Permissions + Foreground Service pour la capture).
    * Implémenter `mediaDevices.getDisplayMedia` pour récupérer le flux de l'écran.
    * Créer l'interface de contrôle (Bouton "Démarrer", "Arrêter").
    * **Jalon important :** Afficher le flux capturé dans une balise `<RTCView>` à l'intérieur de l'application mobile pour confirmer la capture.

### 3 Récepteur Web - React
Validation du fonctionnement du transfert réseau.

* **Objectif :** Recevoir le flux vidéo et l'afficher.
* **Tâches :**
    * Créer une application React propre.
    * Implémenter `RTCPeerConnection` pour recevoir l'offre (`offer`) envoyée par le téléphone.
    * Gérer l'événement `ontrack` pour attacher le flux vidéo à un élément `<video>`.
    * **Test de validation :** Tester la connexion en Wi-Fi local (Téléphone -> PC).

### 4 Optimisation et Réseau
Passage du prototype web à une application.

* **Objectif :** Assurer la stabilité et réduire la latence.
* **Tâches :**
    * **STUN/TURN :** Configurer un serveur STUN (Google propose des serveurs gratuits `stun:stun.l.google.com:19302`) pour que le mirroring fonctionne même si les appareils ne sont pas sur le même réseau local.
    * **Qualité :** Ajuster les paramètres vidéo (bitrate, résolution, FPS) pour éviter de saturer la connexion (commencer en 720p 30fps).
    * **Gestion des erreurs :** Gérer les cas de coupure réseau (auto-reconnexion).

### 5 Packaging Desktop & Finalisation
* **Objectif :** Livrer une application Desktop native.
* **Tâches :**
    * Encapsuler l'application React dans **Electron**.
    * Tester le build final.
    * **Documentation :** Rédaction d'un guide d'installation.

---

### Critical Path (Les risques majeurs à surveiller)

1.  **Permissions Android :**
2.  **WebRTC et NAT :** Problème de pare-feu. Solution possible: La configuration du serveur STUN.
3.  **Encodage :** La capture d'écran est intensive. Si le téléphone s'échauffe trop, il y aura une baisse de résolution tout seul (throttling).
