# sedatoolsGenerator
Générateur automatique de bordereaux basé sur SedaTools

Le principe de fonctionnement du générateur de bordereaux basé sur SEDATOOLS s'inspire du fonctionnement du générateur ProBANT (voir https://github.com/PatPercot/Seda-Generator).
Toutefois, la notion de profil d'archivage ne semblant pouvoir être pérennisée avec le SEDA 2, cette notion est abandonnée au profit d'un guide de génération.

Les deux objectifs du guide de génération sont :
  1) de permettre à l'archiviste de donner ses instructions au développeur pour le formatage des métadonnées et la production des balises du bordereau de transfert ;
  2) de servir de modèle pour que du code générique produise le bordereau de transfert par une mise en correspondance avec un fichier de données métier produit par un code spécfique qui les récupère dans les applications ou les données à archiver.

Un scénario simple d'utilisation du guide de génération pour traiter un flux de données spécifiques à archiver peut ressembler à ceci :
  1) L'archiviste rédige le guide de génération, le valide avec un outil de vérification qui génére un fichier exemple de métadonnées ;
  2) L'archiviste transmet le guide de génération et le fichier d'exemple de métadonnées au développeur ;
  3) Le développeur lit le guide de génération et le fichier de métadonénes et s'assure de la faisabliité des développements spécifiques ;
  4) Le développeur écrit le code spécifique au flux pour extraire les fichiers et les métadonnées. Le rôle de ce code est de créer un fichier de métadonnées à partir d'un jeu de données. Bien évidemment le contenu du fichier de métadonnées change d'une instance du flux à une autre, le guide de génération lui est toujours le même pour un flux spécifique ;
  5) Le développeur s'assure qu'après la génération des données métier, le code générique du générateur sera appelé avec les trois paramètres ; "guide de génération", "fichier de métdonnées spécifique" et "paramètres du flux".
  6) Après l'appel du générateur, le bordereau de transfert est produit. Il ne reste plus qu'à envoyer le bordereau et les fichiers à archiver dans le SAE.

Un flux d'archivage peut aussi nécessiter des données que l'on ne retrouve ni dans le guide ni dans les métadonnées de l'instance du flux. Ces données correspondent aux informations transmises au deux méthodes setAgencies et setArchivalAgreement de la classe SIPBuilder. À savoir archivalAgencyIdentifier, transferringAgencyIdentifier, originatingAgencyIdentifier, submissionAgencyIdentifier, pour setAgencies et archivalAgreement pour setArchivalAgreement. Ces données seront considérées comme le paramétrage du flux.

Description du guide de génération :
  1) Le guide de génération indique l'ordre d'appartion des informations et des unités documentaires ;
  2) Le guide de génération utilise des codes pour désigner les métadonnées et les unités documentaires. Ces codes seront réutilisés dans le fichier de métadonnées pour permettre une association automatisée par le code générique du générateur de bordereaux. EX : DELIBERATION[#1] désigne la première délibération.



