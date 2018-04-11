---
title: vcpkg-- gestionnaire de package C++ pour Windows | Microsoft Docs
description: vcpkg est un gestionnaire de package en ligne de commande qui simplifie considérablement l’acquisition et l’installation des bibliothèques C++ open source sur Windows.
keywords: vcpkg
author: mikeblome
ms.author: mblome
ms.date: 04/06/2018
ms.technology:
- cpp-ide
ms.tgt_pltfrm: windows
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.topic: article
dev_langs:
- C++
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54d1f0cf2a6971435858a1a64bf3e163631822b5
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2018
---
# <a name="vcpkg-c-package-manager-for-windows"></a>vcpkg : Gestionnaire de package C++ pour Windows

vcpkg est un gestionnaire de package en ligne de commande qui simplifie considérablement l’acquisition et l’installation des bibliothèques tierces sur Windows. Si votre projet utilise des bibliothèques tierces, nous vous recommandons d’utiliser vcpkg pour les installer. vcpkg prend en charge les bibliothèques open source et propriétaires. Toutes les bibliothèques du catalogue public vcpkg ont été testées au niveau de la compatibilité avec Visual Studio 2015 et Visual Studio 2017. À compter de janvier 2018, plus de 600 bibliothèques sont listées dans le catalogue, et la Communauté C++ ajoute régulièrement des bibliothèques.

## <a name="simple-yet-flexible"></a>Simple et pourtant flexible

À l’aide d’une commande unique, vous pouvez télécharger des sources et constituer une bibliothèque. vcpkg lui-même est un projet open source, disponible sur GitHub. Vous pouvez personnaliser votre ou vos clones privés comme vous le souhaitez. Par exemple, vous pouvez spécifier des bibliothèques ou des versions de bibliothèques différentes de celles qui se trouvent dans le catalogue public. Vous pouvez avoir plusieurs clones de vcpkg sur un seul ordinateur, chacun d’eux produisant des ensembles de bibliothèques et/ou de commutateurs de compilation, etc. Chaque clone est un environnement autonome et reproductible avec son propre exemplaire de vcpkg.exe qui ne fonctionne que sur sa propre hiérarchie. vcpkg n’est ajouté à aucune variable d’environnement et n’a aucune dépendance au Registre Windows ou à Visual Studio.

## <a name="sources-not-binaries"></a>Des sources pas des fichiers binaires

Pour les bibliothèques du catalogue public, vcpkg télécharge les sources au lieu de fichiers binaires[1]. Il compile ces sources à l’aide de Visual Studio 2017 ou de Visual Studio 2015 si 2017 n’est pas installé. En C++, il est très important que toutes les bibliothèques que vous utilisez soient compilées avec le même compilateur et la même version de compilateur que ceux du code d’application qui y est lié. En utilisant vcpkg, vous éliminez ou au moins réduisez considérablement les risques de binaires incompatibles et les problèmes qu’ils peuvent engendrer. Dans les équipes qui sont standardisées sur une version spécifique du compilateur Visual C++, un membre de l’équipe peut utiliser vcpkg pour télécharger les sources et compiler un ensemble de fichiers binaires, puis utiliser la commande d’exportation et compresser ces fichiers binaires ainsi que les en-têtes pour les autres membres de l’équipe. Pour plus d’informations, consultez Exporter les fichiers binaires et les en-têtes compilés ci-dessous. 

Si vous créez un clone de vcpkg avec les bibliothèques privées dans la collection des ports, vous pouvez ajouter un port qui télécharge les en-têtes et les fichiers binaires prédéfinis, puis écrire un fichier portfile.cmake qui copie tout simplement ces fichiers à l’emplacement souhaité.

[1] *Remarque : Pour certaines bibliothèques propriétaires, les sources ne sont pas disponibles. Vcpkg télécharge alors les fichiers binaires prédéfinis qui sont compatibles.*

## <a name="installation"></a>Installation

Clonez le dépôt vcpkg à partir de GitHub : https://github.com/Microsoft/vcpkg. Vous pouvez télécharger vers n’importe quel emplacement de dossier de votre choix.

Exécutez le programme d’amorçage dans le dossier racine : **bootstrap-vcpkg.bat**.

## <a name="basic-tasks"></a>Tâches de base

## <a name="search-the-list-of-available-libraries"></a>Recherche dans la liste des bibliothèques disponibles

Pour afficher les packages qui sont disponibles, à l’invite de commandes, tapez : **vcpkg search**

Cette commande énumère les fichiers de contrôle dans les sous-dossiers vcpkg/ports. Une liste telle que celle-ci s’affiche :

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Vous pouvez filtrer sur un modèle, par exemple **vcpkg search ta** :

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library

```

### <a name="install-a-library-on-your-local-machine"></a>Installer une bibliothèque sur votre ordinateur local

Après avoir obtenu le nom d’une bibliothèque à l’aide de **vcpkg search**, vous utilisez **vcpkg install** pour télécharger la bibliothèque et la compiler. vcpkg utilise le portfile de la bibliothèque dans le répertoire des ports. Si aucun triplet n’est spécifié, vcpkg installe et compile pour windows x86. Si le portfile précise des dépendances, vcpkg les télécharge et les installe également. Après le téléchargement, vcpkg génère la bibliothèque à l’aide du système de génération que la bibliothèque utilise. Les fichiers de projets CMake et MSBuild sont préférables, mais MAKE est pris en charge de même que tout autre système de génération. Si vcpkg ne trouve pas le système de génération spécifié sur l’ordinateur local, il le télécharge et l’installe.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

## <a name="list-the-libraries-already-installed"></a>Répertorier les bibliothèques déjà installées
Après avoir installé certaines bibliothèques, vous pouvez utiliser **vcpkg list** pour voir ce que vous avez :

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="integrate-with-visual-studio"></a>Intégrer avec Visual Studio

### <a name="per-user"></a>Par utilisateur

Exécutez **vcpkg integrate install** pour configurer Visual Studio afin qu’il recherche par utilisateur tous les fichiers d’en-tête et les fichiers binaires vcpkg, sans qu’il soit nécessaire de modifier manuellement les chemins des répertoires VC ++. Si vous disposez de plusieurs clones, le clone à partir duquel vous exécutez cette commande devient le nouvel emplacement par défaut.

Désormais, vous pouvez #include des en-têtes en tapant juste le dossier/l’en-tête, et la saisie semi-automatique vous assiste. Aucune étape supplémentaire n’est nécessaire pour la liaison à des bibliothèques, ou pour l’ajout de références de projet. L’illustration suivante montre comment Visual Studio recherche les en-têtes azure-storage-cpp. vcpkg place ses en-têtes dans le sous-dossier **/installed**, partitionné par la plateforme cible. Le diagramme suivant présente la liste des fichiers include dans le sous-dossier **/was** pour la bibliothèque :

![Intégration de vcpkg Intellisense](media/vcpkg-intellisense.png "vcpkg et Intellisense")

### <a name="per-project"></a>Par projet

Si vous devez utiliser une version spécifique d’une bibliothèque qui est différente de la version de votre instance vcpkg active, effectuez les étapes suivantes :

1. Créez un clone de vcpkg. 
1. Modifiez le portfile de la bibliothèque pour obtenir la version dont vous avez besoin.
1. Exécutez **vcpkg install \<bibliothèque>**.
1. Utilisez **vcpkg integrate project** pour créer un package NuGet qui référence cette bibliothèque en fonction du projet.

## <a name="export-compiled-binaries-and-headers"></a>Exporter les fichiers binaires et les en-têtes compilés

Exiger que tous les membres d’une équipe téléchargent et génèrent des bibliothèques peut être inefficace. Un seul membre de cette équipe peut effectuer ce travail, puis utiliser **vcpkg export** pour créer un fichier zip contenant les fichiers binaires et les en-têtes qui peuvent alors être facilement partagés avec d’autres membres de l’équipe. 

## <a name="updateupgrade-installed-libraries"></a>Mettre à jour ou à niveau les bibliothèques installées

Le catalogue public est mis à jour avec les versions les plus récentes des bibliothèques. Pour déterminer lesquelles de vos bibliothèques locales sont obsolètes, utilisez **vcpkg update**. Quand vous êtes prêt à mettre à jour votre collection de ports avec la version la plus récente du catalogue public, exécutez la commande **vcpkg upgrade** pour télécharger et regénérer automatiquement tout ou partie de vos bibliothèques installées obsolètes.

Par défaut, la commande **upgrade** ne fait que lister les bibliothèques qui sont obsolètes ; elle ne les met pas à niveau. Pour effectuer la mise à niveau, utilisez l’option **--no-dry-run**. 

```cmd
  vcpkg upgrade --no-dry-run 
```

### <a name="upgrade-options"></a>Options de mise à niveau

- **--no-dry-run** Effectuer la mise à niveau ; quand cette option n’est pas spécifiée, la commande ne fait que lister les packages obsolètes. 
- **--keep-going** Continuer l’installation des packages, même si l’un d’eux échoue. 
- **--triplet \<t>** Définir le triplet par défaut pour les packages non qualifiés. 
- **--vcpkg-root \<chemin>** Spécifier le répertoire vcpkg à utiliser à la place du répertoire actif ou du répertoire de l’outil. 

### <a name="upgrade-example"></a>Exemple de mise à niveau

### <a name="per-project"></a>Par projet
Si vous devez utiliser une version spécifique d’une bibliothèque qui est différente de la version de votre instance vcpkg active, effectuez les étapes suivantes :

1. Créez un clone de vcpkg. 
1. Modifiez le portfile de la bibliothèque pour obtenir la version dont vous avez besoin.
1. Exécutez **vcpkg install \<bibliothèque>**.
1. Utilisez **vcpkg integrate project** pour créer un package NuGet qui référence cette bibliothèque en fonction du projet.


## <a name="export-compiled-binaries-and-headers"></a>Exporter les fichiers binaires et les en-têtes compilés
Exiger que tous les membres d’une équipe téléchargent et génèrent des bibliothèques peut être inefficace. Un seul membre de cette équipe peut effectuer ce travail, puis utiliser **vcpkg export** pour créer un fichier zip contenant les fichiers binaires et les en-têtes qui peuvent alors être facilement partagés avec d’autres membres de l’équipe. 

## <a name="updateupgrade-installed-libraries"></a>Mettre à jour ou à niveau les bibliothèques installées
Le catalogue public est mis à jour avec les versions les plus récentes des bibliothèques. Pour déterminer lesquelles de vos bibliothèques locales sont obsolètes, utilisez **vcpkg update**. Quand vous êtes prêt à mettre à jour votre collection de ports avec la version la plus récente du catalogue public, exécutez la commande **vcpkg upgrade** pour télécharger et regénérer automatiquement tout ou partie de vos bibliothèques installées obsolètes.

Par défaut, la commande **upgrade** ne fait que lister les bibliothèques qui sont obsolètes ; elle ne les met pas à niveau. Pour effectuer la mise à niveau, utilisez l’option **--no-dry-run**. 

```cmd
  vcpkg upgrade --no-dry-run 
```

### <a name="upgrade-options"></a>Options de mise à niveau

- **--no-dry-run** Effectuer la mise à niveau ; quand cette option n’est pas spécifiée, la commande ne fait que lister les packages obsolètes. 
- **--keep-going** Continuer l’installation des packages, même si l’un d’eux échoue. 
- **--triplet \<t>** Définir le triplet par défaut pour les packages non qualifiés. 
- **--vcpkg-root \<chemin>** Spécifier le répertoire vcpkg à utiliser à la place du répertoire actif ou du répertoire de l’outil. 

### <a name="upgrade-example"></a>Exemple de mise à niveau

L’exemple suivant montre comment mettre à niveau les bibliothèques spécifiées uniquement. Notez que vcpgk extrait automatiquement les dépendances en fonction des besoins.

```cmd
c:\users\satyan\vcpkg> vcpkg upgrade tiny-dnn:x86-windows zlib
The following packages are up-to-date:
   tiny-dnn:x86-windows

The following packages will be rebuilt:
    * libpng[core]:x86-windows
    * tiff[core]:x86-windows
      zlib[core]:x86-windows
Additional packages (*) will be modified to complete this operation.
If you are sure you want to rebuild the above packages, run this command with the --no-dry-run option.
```

## <a name="contribute-new-libraries"></a>Apporter de nouvelles bibliothèques
Vous pouvez inclure toutes les bibliothèques que vous souhaitez dans votre collection de ports privés. Pour suggérer une nouvelle bibliothèque pour le catalogue public, ouvrez un problème sur la [page des problèmes vcpkg de GitHub](https://github.com/Microsoft/vcpkg/issues).

## <a name="remove-a-library"></a>Supprimer une bibliothèque
Tapez **vcpkg remove** pour supprimer une bibliothèque installée. Si d’autres bibliothèques dépendent de celle-ci, vous êtes invité à réexécuter la commande avec **--recurse**, ce qui entraîne la suppression de toutes les bibliothèques en aval.

## <a name="customize-vcpkg"></a>Personnaliser vcpkg
Vous pouvez modifier votre clone de vcpkg comme vous le souhaitez. Vous pouvez créer plusieurs clones de vcpkg et modifier les portfiles dans chacun d’eux pour obtenir des versions spécifiques de bibliothèques, ou pour spécifier des paramètres de ligne de commande. Dans une entreprise, par exemple, un groupe de développeurs peut travailler sur des logiciels disposant d’un ensemble de dépendances tandis qu’un autre groupe peut utiliser un ensemble différent. Vous pouvez configurer deux clones de vcpkg et, selon vos besoins, modifier chacun d’eux pour télécharger les versions des bibliothèques et des commutateurs de compilation, etc. 

## <a name="uninstall-vcpkg"></a>Désinstaller vcpkg
Supprimez simplement le répertoire. 

## <a name="send-feedback-about-vcpkg"></a>Envoyer des commentaires à propos de vcpkg
Utilisez la commande **--survey** pour envoyer des commentaires à Microsoft sur vcpkg, notamment des rapports de bogues et des suggestions de fonctionnalités.

## <a name="the-vcpkg-folder-hierarchy"></a>La hiérarchie des dossiers vcpkg
Toutes les données et les fonctionnalités de vcpkg sont autonomes dans une hiérarchie de répertoires unique, appelée « instance ». Il n’existe pas de paramètre de Registre ni de variable d’environnement. Vous pouvez avoir le nombre d’instances de vcpkg que vous voulez sur une machine ; celles-ci n’interfèrent pas les unes avec les autres. 

Une instance de vcpkg comporte les éléments suivants : 

- buildtrees -- Contient les sous-dossiers des sources à partir desquelles chaque bibliothèque est générée.
- docs -- Documentation et exemples.
- downloads -- Copies mises en cache des sources ou outils téléchargés. vcpkg commence par rechercher ici lorsque vous exécutez la commande d’installation.
- installed -- Contient les en-têtes et les fichiers binaires de chaque bibliothèque installée. Pendant l’intégration à Visual Studio, vous lui dites en fait d’ajouter ce dossier à ses chemins de recherche.
- packages -- Dossier interne pour l’environnement intermédiaire entre les installations.
- ports -- Fichiers qui décrivent chaque bibliothèque dans le catalogue, sa version et l’endroit où la télécharger. Le cas échéant, vous pouvez ajouter vos propres ports.
- scripts -- Scripts (cmake, powershell) utilisés par vcpkg.
- toolsrc -- Code source C++ de vcpkg et des composants associés.
- triplets -- Contient les paramètres pour chaque plateforme cible prise en charge (par exemple, windows x86 ou uwp x64).

## <a name="command-line-reference"></a>Informations de référence sur la ligne de commande

|Commande|Description|
|---------|---------|
|**vcpkg search [pat]**|Rechercher des packages disponibles pour l’installation|
|**vcpkg install \<pkg>...**|Installer un package|
|**vcpkg remove \<pkg>...**|Désinstaller un package|
|**vcpkg remove --outdated**|Désinstaller tous les packages obsolètes|
|**vcpkg list**|Lister les packages installés|
|**vcpkg update**|Afficher la liste des packages pour la mise à jour|
|**vcpkg upgrade**|Regénérer tous les packages obsolètes|
|**vcpkg hash \<fichier> [alg]**|Hacher un fichier à l’aide d’un algorithme spécifique, par défaut SHA512|
|**vcpkg integrate install**|Mettre les packages installés à la disposition des utilisateurs. Nécessite des privilèges d’administrateur lors de la première utilisation|
|**vcpkg integrate remove**|Supprimer l’intégration à l’échelle de l’utilisateur|
|**vcpkg integrate project**|Générer un package NuGet de référence pour un usage de projet VS individuel|
|**vcpkg export \<pkg>... [opt]...**|Exporter un package|
|**vcpkg edit \<pkg>**|Ouvrir un port pour la modification (utilise %EDITOR%, 'code' par défaut)|
|**vcpkg import \<pkg>**|Importer une bibliothèque prédéfinie|
|**vcpkg create \<pkg> \<url> [archivename]**|Créer un package|
|**vcpkg owns \<pat>**|Rechercher des fichiers dans les packages installés|
|**vcpkg cache**|Lister les packages compilés mis en cache|
|**vcpkg version**|Afficher les informations de version|
|**vcpkg contact**|Afficher les coordonnées pour envoyer des commentaires|

### <a name="options"></a>Options :
|Option|Description|
|---------|---------|
|**--triplet \<t>**|Spécifier le triplet de l’architecture cible. (valeur par défaut : `%VCPKG_DEFAULT_TRIPLET%`, voir aussi **vcpkg help triplet**)|
|**--vcpkg-root \<chemin>**|Spécifier le répertoire racine de vcpkg (valeur par défaut : `%VCPKG_ROOT%`)|
