# sedatoolsGenerator
Générateur automatique de bordereaux basé sur SedaTools

Le principe de fonctionnement du générateur de bordereaux basé sur les SEDATOOLS s'inspire du fonctionnement du générateur ProBANT (voir https://github.com/PatPercot/Seda-Generator).
Toutefois, la notion de profil d'archivage ne semblant pouvoir être pérennisée avec le SEDA 2, cette notion est abandonnée au profit d'un guide de génération.

Les deux objectifs du guide de génération sont :
  1) de permettre à l'archiviste de donner ses instructions au développeur pour le formatage des métadonnées et la production des balises du bordereau de transfert ;
  2) de servir de modèle pour que du code générique produise le bordereau de transfert par une mise en correspondance avec un fichier de données métier produit par un code spécfique qui les récupère dans les applications ou les données à archiver.

Un scénario simple d'utilisation du guide de génération pour traiter un flux de données spécifiques à archiver peut ressembler à ceci :
  1) L'archiviste rédige le guide de génération, le valide avec un outil de vérification qui génére un fichier exemple de métadonnées ;
  2) L'archiviste transmet le guide de génération et le fichier d'exemple de métadonnées au développeur ;
  3) Le développeur lit le guide de génération et le fichier de métadonénes et s'assure de la faisabliité des développements spécifiques ;
  4) Le développeur écrit le code spécifique au flux pour extraire les fichiers et les métadonnées?. Le rôle de ce code est de créer un fichier de métadonnées à partir d'un jeu de données. Bien évidemment le contenu du fichier de métadonnées change d'un flux à un autre, le guide de génération lui est toujours le même pour un flux spécifique ;
  5) Le développeur s'assure qu'apès la génération des données métier, le code générique du générateur sera appelé avec pour paramètres le guide de génération et le fichier de métdonnées spécifique.
  6) Après l'appel du générateur, le bordereau de transfert est produit. Il ne reste plus qu'à envoyé le bordereau et les fichiers à archiver dans le SAE.

Description du guide de génération :


