---
title: Ouvrir les projets de dossier dans Visual C++ | Documents Microsoft
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72106bd363987d39fb11c9ec1a6d3fd0ceb5665d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="open-folder-projects-in-visual-c"></a>Ouvrir les projets de dossier dans Visual C++
Visual Studio 2017 introduit la fonctionnalité « Ouvrir le dossier », ce qui vous permet d’ouvrir un dossier de fichiers sources et immédiatement commencer à coder avec prise en charge IntelliSense, la navigation, la refactorisation, le débogage et ainsi de suite. Aucun fichier .sln ou .vcxproj n’est chargées ; Si nécessaire, vous pouvez spécifier des tâches personnalisées ainsi que générer et lancer des paramètres dans les fichiers .json simple. Géré par ouvrir le dossier, Visual C++ peut prennent désormais en charge non seulement des collections pertes de connexion de fichiers, mais également pratiquement n’importe quel système de génération, y compris CMake, Ninja, QMake (pour les projets de Qt), gyp, SCons, Gradle, Buck, vérifiez et bien plus encore. 

Pour utiliser un dossier ouvert, dans le menu principal, sélectionnez *fichier | Ouvrez | Dossier* ou appuyez sur *Ctrl + Maj + Alt + O*. L’Explorateur de solutions affiche immédiatement tous les fichiers dans le dossier. Vous pouvez cliquer sur n’importe quel fichier pour le modifier. En arrière-plan, Visual Studio démarre l’indexation des fichiers pour activer les fonctionnalités de refactorisation, IntelliSense et navigation. Comme vous modifiez, créez, déplacez ou supprimez des fichiers, Visual Studio effectue le suivi des modifications automatiquement et en permanence des mises à jour son index IntelliSense. 
  
## <a name="cmake-projects"></a>Projets de CMake
CMake est intégré dans l’IDE Visual Studio en tant qu’outils de CMake pour Visual C++, un composant de la charge de travail de bureau C++. Pour plus d’informations, consultez [Visual C++ Tools pour CMake](cmake-tools-for-visual-cpp.md).
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake les projets qui ciblent le framework Qt
Vous pouvez utiliser les outils de CMake pour Visual C++ pour cibler Qt pour générer des projets de Qt, ou vous pouvez utiliser l’Extension de Visual Studio Qt. Remarque : À compter d’août 2017, le [prise en charge de l’Extension Qt Visual Studio pour Visual Studio 2017](https://download.qt.io/development_releases/vsaddin/) est disponible en tant qu’une version bêta.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, inconvénients, SCons, Buck, etc.
Vous pouvez utiliser n’importe quel système de génération dans Visual C++ et toujours profiter des avantages de l’IDE de Visual C++ et le débogueur. Lorsque vous ouvrez le dossier racine de votre projet, Visual C++ utilise l’heuristique pour indexer les fichiers sources pour IntelliSense et la navigation. Vous pouvez fournir des indications sur la structure de votre code en modifiant le fichier CppProperties.json. De la même façon, vous pouvez configurer votre programme de build en modifiant le fichier launch.vs.json. 

## <a name="configuring-open-folder-projects"></a>Configuration de projets d’ouvrir le dossier
Vous pouvez personnaliser un projet d’ouvrir le dossier via trois fichiers JSON :
|||
|-|-|
|CppProperties.json|Spécifiez les informations de configuration personnalisée pour la navigation. Créer ce fichier, si nécessaire, dans votre dossier racine du projet.|
|Launch.VS.JSON|Spécifiez les arguments de ligne de commande. Accessible via la **l’Explorateur de solutions** élément de menu contextuel **Debug et les paramètres de lancement**.|
|Tasks.VS.JSON|Spécifiez les commandes de génération personnalisées et des commutateurs de compilation. Accessible via la **l’Explorateur de solutions** élément de menu contextuel **configurer les tâches**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>Configurer IntelliSense avec CppProperties.json
IntelliSense et navigation comportement partiellement dépend de la configuration de build active, qui définit #include chemins d’accès, les commutateurs du compilateur et les autres paramètres. Par défaut, Visual Studio fournit des configurations Debug et Release. Pour certains projets, vous devrez créer une configuration personnalisée pour IntelliSense et les fonctionnalités de navigation entièrement comprendre votre code. Pour définir une nouvelle configuration, créez un fichier appelé CppProperties.json dans le dossier racine. Voici un exemple :

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Une configuration peut avoir une des propriétés suivantes :

|||  
|-|-| 
|`name`|le nom de configuration qui s’affiche dans la liste déroulante de configuration C++|
|`includePath`|la liste des dossiers qui doivent être spécifiés dans le chemin d’accès include (qui correspond à /I pour la plupart des compilateurs)|
|`defines`|la liste des macros qui doit être définie (qui correspond à /D pour la plupart des compilateurs)|
|`compilerSwitches`|un ou plusieurs commutateurs supplémentaires qui peuvent influencer le comportement d’IntelliSense|
|`forcedInclude`|en-tête d’être inclus automatiquement dans chaque unité de compilation (mappe à /FI pour MSVC ou - inclure pour clang)|
|`undefines`|la liste des macros pour être non définie (qui correspond à /U de MSVC.)|
|`intelliSenseMode`|le moteur IntelliSense à utiliser. Vous pouvez spécifier les variantes spécifiques d’architecture pour MSVC, gcc et Clang :
- MSVC x x86 (valeur par défaut)
- MSVC-x64
- MSVC-arm
- Windows-clang-x86
- Windows-clang-x64
- Windows-clang-arm
- Linux-x64
- Linux-x86
- Linux-arm
- gccarm

Expansion variables d’environnement prend en charge CppProperties.json pour inclure des chemins d’accès et d’autres valeurs de propriété. La syntaxe est `${env.FOODIR}` pour développer une variable d’environnement `%FOODIR%`.

Vous avez également accès aux macros intégrées suivantes à l’intérieur de ce fichier :
|||
|-|-|
|`${workspaceRoot}`| le chemin complet vers le dossier de l’espace de travail|
|`${projectRoot}`| le chemin d’accès complet au dossier où se trouve CppProperties.json|
|`${vsInstallDir}`| le chemin d’accès complet au dossier où est installée l’instance en cours d’exécution de VS 2017|

Par exemple, si votre projet possède un dossier include et inclut également windows.h et les autres en-têtes courants du SDK Windows, peut vouloir mettre à jour votre CppProperties.json fichier de configuration avec ces inclut :

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**Remarque :** `%WindowsSdkDir%` et `%VCToolsInstallDir%` ne sont pas définies comme variables d’environnement globales par conséquent, assurez-vous de lancer devenv.exe à partir d’une « invite de commandes développeur pour VS 2017 » qui définit ces variables.

Pour résoudre les problèmes IntelliSense erreurs dues à l’absence d’incluent des chemins d’accès, ouvrez le **liste d’erreurs** et filtrez sa sortie à « IntelliSense uniquement » et E1696 code d’erreur « Impossible d’ouvrir le fichier de code source... ». 

Vous pouvez créer n’importe quel nombre de configurations dans CppProperties.json. Chaque apparaissent dans la liste déroulante de configuration :

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```
### <a name="define-tasks-with-tasksvsjson"></a>Définir des tâches avec tasks.vs.json
Vous pouvez automatiser les scripts de compilation ou d’autres opérations externes sur les fichiers que vous avez dans votre espace de travail actuel en les exécutant en tant que tâches directement dans l’IDE. Vous pouvez configurer une nouvelle tâche en cliquant sur un fichier ou dossier et en sélectionnant **configurer les tâches**. 

![Ouvrir le dossier configurer des tâches](media/open-folder-config-tasks.png)

Cela crée (ou en ouvre) le `tasks.vs.json` fichier dans le dossier .vs Visual Studio crée dans votre dossier racine du projet. Vous pouvez définir n’importe quelle tâche arbitraire dans ce fichier et appelez-la à partir de la **l’Explorateur de solutions** menu contextuel. L’exemple suivant montre un fichier tasks.vs.json qui définit une seule tâche. `taskName`définit le nom qui apparaît dans le menu contextuel. `appliesTo`définit les fichiers de la commande peut être effectuée sur. Le `command` propriété fait référence à la variable d’environnement COMSPEC, qui identifie le chemin d’accès de la console (cmd.exe sur Windows). Le `args` propriété spécifie la ligne de commande à appeler. Le `${file}` macro extrait le fichier sélectionné dans **l’Explorateur de solutions**. L’exemple suivant affiche le nom de fichier du fichier .cpp actuellement sélectionné.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
Après avoir enregistré tasks.vs.json, vous pouvez avec le bouton droit n’importe quel fichier .cpp dans le dossier, choisissez **écho le nom de fichier** à partir du menu contextuel et affichent le nom de fichier dans la fenêtre Sortie.

#### <a name="appliesto"></a>appliesTo
Vous pouvez créer des tâches de tout fichier ou dossier en spécifiant son nom dans la `appliesTo` champ, par exemple `"appliesTo" : "hello.cpp"`. Les masques de fichiers suivants peuvent être utilisés comme valeurs :
|||
|-|-|
|`"*"`| tâche n’est disponible pour tous les fichiers et dossiers dans l’espace de travail|
|`"*/"`| tâche n’est disponible pour tous les dossiers dans l’espace de travail|
|`"*.cpp"`| tâche n’est disponible pour tous les fichiers portant l’extension .cpp dans l’espace de travail|
|`"/*.cpp"`| tâche n’est disponible pour tous les fichiers portant l’extension .cpp dans la racine de l’espace de travail|
|`"src/*/"`| tâche n’est disponible pour tous les sous-dossiers du dossier « src »|
|`"makefile"`| tâche n’est disponible à tous les fichiers makefile dans l’espace de travail|
|`"/makefile"`| tâche est disponible uniquement pour le fichier Make à la racine de l’espace de travail|

#### <a name="output"></a>sortie
Utilisez le `output` propriété pour spécifier le fichier exécutable qui sera lancée lorsque vous appuyez sur **F5**. Exemple :

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Macros pour tasks.vs.json

|||
|-|-|
|`${env.<VARIABLE>}`| Spécifie toute variable d’environnement (par exemple, ${env. Chemin d’accès}, ${env.COMSPEC}, etc.) qui est défini pour l’invite de commandes développeur. Pour plus d’informations, consultez [invite de commandes développeur pour Visual Studio](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| le chemin complet vers le dossier de l’espace de travail (par exemple, « C:\sources\hello »)|
|`${file}`| le chemin d’accès complet du fichier ou du dossier sélectionné pour exécuter cette tâche sur (par exemple, « C:\sources\hello\src\hello.cpp »)|
|`${relativeFile}`| le chemin d’accès relatif au fichier ou dossier (par exemple, « src\hello.cpp »)|
|`${fileBasename}`| le nom de fichier sans chemin d’accès ou l’extension (par exemple, « hello »)|
|`${fileDirname}`| le chemin d’accès complet au fichier, à l’exclusion du nom de fichier (par exemple, « C:\sources\hello\src »)|
|`${fileExtname}`| l’extension du fichier sélectionné (par exemple, « .cpp »)|

#### <a name="custom-macros"></a>Macros personnalisées
Pour définir une macro personnalisée dans tasks.vs.json, ajoutez une paire nom-valeur avant les blocs de la tâche. L’exemple suivant définit une macro nommée `outDir` qui est utilisé dans le `args` propriété :

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Configurer les paramètres de débogage avec launch.vs.json
Pour personnaliser les arguments de ligne de commande de votre programme, cliquez sur le fichier exécutable dans **l’Explorateur de solutions** et sélectionnez **Debug et les paramètres de lancement**. Cela ouvre une existante `launch.vs.json` fichier, ou si aucune n’existe, il va créer un nouveau fichier avec les informations sur le programme que vous avez sélectionné. 

Pour spécifier des arguments supplémentaires, simplement les ajouter dans le `args` tableau JSON comme indiqué dans l’exemple suivant :

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

Lorsque vous enregistrez ce fichier, la nouvelle configuration apparaît dans la liste déroulante de cible de débogage et vous pouvez le sélectionner pour démarrer le débogueur. Vous pouvez créer plusieurs configurations de débogage que vous le souhaitez, pour n’importe quel nombre d’exécutables. Si vous appuyez sur **F5** maintenant, le débogueur lancer et appuyez sur n’importe quel point d’arrêt que vous avez déjà défini. Toutes les fenêtres du débogueur familière et leurs fonctionnalités sont désormais disponibles.

## <a name="see-also"></a>Voir aussi
[IDE et outils de développement Visual C++](ide-and-tools-for-visual-cpp-development.md)

