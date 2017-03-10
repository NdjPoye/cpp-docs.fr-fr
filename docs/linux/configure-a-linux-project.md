---
title: Configurer un projet Linux | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: dff1e9e03911f65dfcffcd078e0739224f73f4aa
ms.openlocfilehash: b110994cab92d2151f63912d2b08af56059b82d7
ms.lasthandoff: 02/24/2017

---

# <a name="configure-a-linux-project"></a>Configurer un projet Linux

## <a name="general-settings"></a>Paramètres généraux
Différentes options peuvent être configurées pour un projet Linux avec Visual Studio.  Pour afficher ces options, sélectionnez le menu **Projet > Propriétés** ou cliquez avec le bouton droit sur le projet dans l’**Explorateur de solutions** et sélectionnez **Propriétés** dans le menu contextuel :

![Configuration générale](media/settings_general.png)

Par défaut, un fichier exécutable (.out) est créé avec l’outil.  Pour générer une bibliothèque statique ou dynamique, ou utiliser un fichier makefile existant, utilisez la sélection **Type de configuration**.

## <a name="remote-settings"></a>Paramètres distants
Pour modifier les paramètres relatifs à l’ordinateur Linux distant, sélectionnez l’élément **Paramètres distants** :

![Paramètres distants](media/settings_remote.png)

* Pour modifier l’ordinateur Linux cible, utilisez l’entrée **Ordinateur cible**.  Cela vous permet de sélectionner l’une des connexions créées précédemment.  Pour créer une entrée, consultez la section [Connexion à votre ordinateur Linux distant](connect-to-your-remote-linux-computer.md).

* Le **Répertoire racine distant** détermine l’emplacement racine de l’endroit où le projet est généré sur l’ordinateur Linux distant.  Par défaut et en l’absence de modification, il s’agit de **~/projects**.

* Le **Répertoire de projet distant** est l’emplacement où ce projet spécifique est généré sur l’ordinateur Linux distant.  Par défaut, il s’agit de **$(RemoteRootDir)/$(ProjectName)**, qui se développe jusqu’à un répertoire nommé d’après le projet actuel, sous le répertoire racine défini ci-dessus.

* Enfin, pour modifier les compilateurs C et C++ par défaut, ou l’éditeur de liens et le programme d’archivage utilisés pour générer le projet, utilisez les entrées appropriées dans la section **Valeurs par défaut des outils**.  Vous pouvez les définir pour utiliser une version spécifique de GCC ou même le compilateur Clang, par exemple.

## <a name="vc-directories"></a>Répertoires VC++
Par défaut, Visual Studio n’inclut aucun fichier Include au niveau système de l’ordinateur Linux.  Par exemple, les éléments dans le répertoire **/usr/include** ne sont pas présents dans Visual Studio.  Pour une prise en charge [IntelliSense](/visualstudio/ide/using-intellisense) complète, vous devez copier ces fichiers au même emplacement sur votre ordinateur de développement et faire pointer Visual Studio vers celui-ci.  Une option consiste à utiliser SCP (Secure Copy) pour copier les fichiers.  Sur Windows 10, vous pouvez utiliser [Bash sur Windows](https://msdn.microsoft.com/commandline/wsl/about) pour exécuter SCP.  Pour les versions précédentes de Windows, vous pouvez employer un outil tel que [PSCP (PuTTY Secure Copy)](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html).

Vous pouvez copier les fichiers en utilisant une commande semblable à la suivante :

`scp -r linux_username@remote_host:/usr/include .`

Remplacez évidemment les valeurs **linux_username** et **remote_host** ci-dessus par des valeurs appropriées à votre propre environnement.

Une fois que les fichiers sont copiés, utilisez l’élément **Répertoires VC++** dans les propriétés de projet pour indiquer à Visual Studio où se trouvent les fichiers Include supplémentaires récemment copiés.

![Répertoires VC++](media/settings_directories.png)

## <a name="copy-sources"></a>Copier les sources
Lors de la génération, les fichiers sources sur votre PC de développement sont copiés sur l’ordinateur Linux où ils sont compilés.  Par défaut, toutes les sources dans le projet Visual Studio sont copiées aux emplacements définis dans les paramètres ci-dessus.  Toutefois, des sources supplémentaires peuvent également être ajoutées à la liste, ou la copie des sources peut être entièrement désactivée, ce qui est le paramètre par défaut d’un projet Makefile.

* L’option **Sources à copier** détermine quelles sources sont copiées sur l’ordinateur distant.  Par défaut, **@(SourcesToCopyRemotely)** correspond à tous les fichiers du projet.

* L’option **Copier les sources** peut être activée et désactivée pour activer et désactiver la copie des fichiers sources sur l’ordinateur distant.

* L’option **Sources supplémentaires à copier** vous permet d’ajouter des fichiers sources supplémentaires qui seront copiés sur le système distant.  Vous pouvez spécifier une liste délimitée par des points-virgules ou utiliser la syntaxe **:=** pour spécifier un nom local et distant à utiliser :

  `C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Événements de build
Étant donné que toute la compilation se produit sur un ordinateur distant, plusieurs événements de build supplémentaires ont été ajoutés à la section Événements de build dans les propriétés de projet.  Il s’agit des événements suivants : **Événement prébuild distant**, **Événement de préédition des liens distant** et **Événement post-build distant**. Ils se produisent sur l’ordinateur distant avant ou après les étapes individuelles du processus.

![Événements de build](media/settings_buildevents.png)

## <a name="see-also"></a>Voir aussi
[Utilisation des propriétés de projet](../ide/working-with-project-properties.md)
