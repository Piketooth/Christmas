# Père Noël Surprise

Tirage au sort pour un Père Noël surprise (Secret Santa), en appli Android.

## Ce que fait l'appli

- **Participants** : ajout un par un, ou collage d'une liste entière (un prénom par ligne ou séparés par des virgules). Les doublons sont signalés.
- **Budget** facultatif : « 25 » s'affiche « 25 € ».
- **Groupes** : glissez les prénoms dans des groupes ; les membres d'un même groupe ne se tirent pas entre eux (couples, familles). Fonctionne au doigt comme à la souris, ou en touchant un prénom puis un groupe. Bouton **Annuler** (ou Ctrl+Z) pour revenir en arrière.
- **Une seule chaîne** : le tirage relie toujours tout le monde, chacun offrant au suivant jusqu’à revenir au premier (Léa → Hugo → Camille → Jules → Léa).
- **Mot de l’organisateur** : un message affiché à chacun en ouvrant son paquet et dans les messages copiés.
- **Tirage** : personne ne voit les paires. On se passe le téléphone : chacun touche son étiquette, confirme son prénom et maintient le bouton pour ouvrir son paquet.
- **Mode organisateur** : afficher toutes les paires (après confirmation) et copier un message prêt à envoyer à chacun.
- **Mes listes** : l’organisateur enregistre ses listes (prénoms, groupes, budget, mot de l’organisateur) et le tirage, pour les retrouver plus tard. Elles restent sur le téléphone.

Tout est calculé sur l'appareil : rien n'est envoyé sur Internet, et l'appli fonctionne hors ligne.

## Installer sur Android

Ouvrez la dernière [release](../../releases/latest), téléchargez **pere-noel-surprise.apk**, ouvrez-le et autorisez l'installation.

## Compilation

Chaque envoi sur `main` lance la GitHub Action **APK Android**, qui compile l'APK et publie une release `v1.0.N`.

**Signature.** L'APK est signé avec la clé décrite par trois secrets du dépôt (*Settings → Secrets and variables → Actions*) : `ANDROID_KEYSTORE_BASE64` (fichier keystore encodé en base64), `ANDROID_KEYSTORE_PASSWORD` et `ANDROID_KEY_ALIAS`. Sans eux, l'APK est signé avec une clé de debug et chaque mise à jour demande de désinstaller la précédente.

## Structure

- `web/` : l'appli (un seul `index.html`, polices et icônes embarquées).
- `android/` : projet Android généré par [Capacitor](https://capacitorjs.com).
- `.github/workflows/apk.yml` : compilation et publication de l'APK.

Pour essayer en local : ouvrez `web/index.html` dans un navigateur. Après une modification de `web/`, `npm run sync` recopie l'appli dans le projet Android.

## Polices

Bricolage Grotesque, Instrument Sans et JetBrains Mono, sous licence SIL Open Font License 1.1.
