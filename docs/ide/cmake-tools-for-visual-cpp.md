---
title: Les projets dans Visual C++ CMake | Documents Microsoft
ms.custom: ''
ms.date: 08/08/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3a65ae6cc58f649fee5f47b33a146263a3b6c55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="cmake-projects-in-visual-c"></a>CMake des projets dans Visual C++

Cet article suppose que vous êtes familiarisé avec CMake, un outil open source interplateformes pour définir le processus de génération qui s’exécutent sur plusieurs plateformes.

Jusqu'à récemment, les utilisateurs de Visual Studio peuvent utiliser CMake pour générer des fichiers projet MSBuild, puis, l’IDE consommé pour IntelliSense, navigation et la compilation. À compter de Visual Studio 2017, le **des outils Visual C++ pour CMake** composant utilise le **ouvrir le dossier** fonctionnalité pour activer l’IDE consommer des fichiers projet CMake (par exemple, CMakeLists.txt) directement dans le cadre d’IntelliSense et de navigation. Si vous utilisez un générateur de Visual Studio, un fichier temporaire du projet est généré et transmis à msbuild.exe, mais n’est jamais chargé pour IntelliSense ou à des fins de navigation. 

**Visual Studio 2017 version 15.3**: prise en charge est fournie pour les générateurs Ninja et Visual Studio.

**Visual Studio 2017 version 15.4**: prise en charge est ajoutée pour CMake sur Linux. Pour plus d’informations, consultez [Configurer un projet CMake Linux](../linux/cmake-linux-project.md).

**Visual Studio 2017 version 15.5**: prise en charge est ajoutée pour l’importation d’un cache de CMake existant. Visual Studio automatiquement extrait des variables personnalisées et crée un fichier CMakeSettings.json prérempli.


## <a name="installation"></a>Installation

**Les outils Visual C++ pour CMake** est installé par défaut dans le cadre de la **bureau développement avec C++** la charge de travail.

![Composant de CMake dans la charge de travail de bureau C++](media/cmake-install.png)
 
## <a name="ide-integration"></a>Intégration IDE

Lorsque vous choisissez **fichier | Ouvrez | Dossier** pour ouvrir un dossier contenant un fichier CMakeLists.txt, les événements suivants se produisent :

- Visual Studio ajoute un **CMake** élément de menu au menu principal, avec des commandes pour l’affichage et modification de scripts de CMake.
- **L’Explorateur de solutions** affiche la structure de dossiers et les fichiers.
- Visual Studio exécute CMake.exe et génère le cache pour la valeur par défaut de CMake *configuration*, qui est x86 déboguer. La ligne de commande CMake s’affiche dans le **fenêtre sortie**, ainsi que de sortie supplémentaires à partir de CMake.
- En arrière-plan, Visual Studio démarre à indexer les fichiers sources pour activer IntelliSense, des informations de navigation, la refactorisation et ainsi de suite. Lorsque vous travaillez, Visual Studio surveille les modifications dans l’éditeur, ainsi que sur le disque à synchroniser son index avec les sources.
 
Vous pouvez ouvrir les dossiers contenant n’importe quel nombre de projets de CMake. Visual Studio détecte et configure tous les fichiers CMakeLists.txt « root » dans votre espace de travail. Les opérations de CMake (configurer, générer, déboguer) ainsi que de C++ IntelliSense et de navigation sont disponibles à tous les projets de CMake dans votre espace de travail.

![Projet de CMake avec plusieurs racines](media/cmake-multiple-roots.png) 

## <a name="import-an-existing-cache"></a>Importer un cache existant

Lorsque vous importez un fichier CMakeCache.txt existant, Visual Studio extrait des variables personnalisées et crée un fichier CMakeSettings.json prérempli basé sur ces automatiquement. Le cache d’origine n’est pas modifié de quelque manière et peut encore servir à partir de la ligne de commande ou avec n’importe quel outil ou l’IDE a été utilisé pour sa génération. Le nouveau fichier CMakeSettings.json est placé à côté de la racine du projet CMakeLists.txt. Visual Studio génère un nouveau cache en fonction du fichier de paramètres. Pas tout le contenu dans le cache est importé.  Propriétés telles que le générateur et l’emplacement des compilateurs sont remplacées par les valeurs par défaut qui sont connus pour fonctionner avec l’IDE.

### <a name="to-import-an-existing-cache"></a>Pour importer un cache existant

1. Dans le menu principal, choisissez **fichier | Ouvrez | CMake**:

   ![Ouvrez CMake](media/cmake-file-open.png "fichier, ouvrir, CMake") 

   Ceci fait apparaître la **CMake importation à partir du Cache** Assistant. 
   
2. Accédez au fichier CMakeCache.txt que vous souhaitez importer, puis cliquez sur **OK**. Le **CMake importer un projet à partir du Cache** Assistant s’affiche :

   ![Importer un cache de CMake](media/cmake-import-wizard.png "ouvrir l’Assistant Importation de cache de CMake") 

   Lorsque l’Assistant terminé, vous pouvez voir le nouveau fichier CMakeCache.txt dans **l’Explorateur de solutions** en regard du fichier de CMakeLists.txt racine dans votre projet.


## <a name="building-cmake-projects"></a>Génération de projets CMake

Pour générer un projet de CMake, vous avez ces possibilités :

1. Sélectionnez la cible dans le **déboguer** liste déroulante et appuyez sur **F5**, ou cliquez sur le **exécuter** bouton (triangle vert). Le projet est généré automatiquement en premier lieu, tout comme une solution Visual Studio.
1. Cliquez avec le bouton droit sur le, puis sélectionnez CMakeLists.txt **générer** dans le menu contextuel. Si vous avez plusieurs cibles dans votre structure de dossiers, vous pouvez choisir de générer toutes les ou qu’une seule cible spécifique, ou
1. Dans le menu principal, sélectionnez **générer | Générez la Solution** (**F7** ou **Ctrl + Maj + B**). Assurez-vous qu’une cible de CMake est déjà sélectionnée dans le **élément de démarrage** liste déroulante dans le **général** barre d’outils.

![CMake générer la commande de menu](media/cmake-build-menu.png "Cmake générer le menu de commande") 

Si un générateur de Visual Studio est sélectionné pour la configuration active, MSBuild.exe est appelé avec `-m -v:minimal` arguments. Pour personnaliser la génération, dans le fichier CMakeSettings.json, vous pouvez spécifier des arguments de ligne de commande supplémentaires à passer au système de génération via la `buildCommandArgs` propriété :

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

Évidemment, les résultats de build sont affichés dans le **fenêtre sortie** et **liste d’erreurs**.
 
![Erreurs de build CMake](media/cmake-build-errors.png "CMake des erreurs de build")

Dans un dossier avec plusieurs cibles de génération, vous pouvez choisir le **générer** élément sur le **CMake** menu ou la **CMakeLists.txt** menu contextuel pour spécifier quelle cible CMake à générer. En appuyant sur **Ctrl + Maj + B** dans un CMake projet est généré dans le document actif.

## <a name="debug-the-project"></a>Déboguer le projet

Pour déboguer un projet de CMake, choisissez la configuration souhaitée et appuyez sur **F5**, ou appuyez sur la **exécuter** bouton dans la barre d’outils. Si le **exécuter** bouton est « Sélectionner un élément démarrage », sélectionnez la flèche déroulante et choisissez la cible que vous souhaitez exécuter. (Dans un projet de CMake, le « document actif » option est uniquement valide pour les fichiers .cpp.) 

![Bouton d’exécution de CMake](media/cmake-run-button.png "Cmake exécuter bouton")


Le **exécuter** ou **F5** commandes tout d’abord créer le projet si les modifications ont été apportées depuis la dernière build.

## <a name="configure-cmake-debugging-sessions"></a>Configurer des sessions de débogage de CMake

Toutes les cibles de CMake exécutables figurent dans le **élément de démarrage** liste déroulante dans le **général** barre d’outils. Pour démarrer une session de débogage, sélectionnez une et lancer le débogueur.

![Liste déroulante élément de démarrage de CMake](media/cmake-startup-item-dropdown.png "déroulante de l’élément démarrage CMake")


Vous pouvez également démarrer une session de débogage dans les menus de CMake.

Pour personnaliser les paramètres du débogueur pour toutes les cibles de CMake exécutable dans votre projet, avec le bouton droit sur le fichier CMakeLists.txt et sélectionnez **Debug et les paramètres de lancement**. Lorsque vous sélectionnez une cible de CMake dans le sous-menu, un fichier appelé launch.vs.json est créé. Ce fichier est préremplie avec des informations sur la cible de CMake que vous avez sélectionné et vous permet de spécifier des paramètres supplémentaires tels que les arguments de programme ou le type de débogueur. Pour faire référence à une clé dans un fichier CMakeSettings.json, préfixer avec « cmake. » dans launch.vs.json. L’exemple suivant montre un fichier launch.vs.json simple qui extrait dans la valeur de la clé « remoteCopySources » dans le fichier CMakeSettings.json pour la configuration sélectionnée :

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
   {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

Dès que vous enregistrez le fichier launch.vs.json, une entrée est créée dans le **élément de démarrage** liste déroulante avec le nouveau nom. En modifiant le fichier launch.vs.json, vous pouvez créer que de nombreuses configurations de débogage que vous le souhaitez pour n’importe quel nombre de cibles de CMake.

**Visual Studio 2017 version 15.4**: Launch.vs.json prend en charge les variables qui sont déclarés dans CMakeSettings.json (voir ci-dessous) et qui s’appliquent à la configuration actuellement sélectionnée. Il a également une clé nommée « currentDir », qui définit le répertoire actuel de l’application de lancement :


```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

Lorsque vous exécutez l’application, la valeur de `currentDir` est similaire à

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

## <a name="editing-cmakeliststxt-files"></a>Modification de fichiers CMakeLists.txt

Pour modifier un fichier CMakeLists.txt, avec le bouton droit sur le fichier dans **l’Explorateur de solutions** et choisissez **ouvrir**. Si vous apportez des modifications au fichier, une barre d’état jaune s’affiche et vous informe que IntelliSense mettra à jour et vous donne la possibilité d’annuler l’opération de mise à jour. Pour plus d’informations sur CMakeLists.txt, consultez la [CMake documentation](https://cmake.org/documentation/).

   ![Modification de fichiers CMakeLists.txt](media/cmake-cmakelists.png "CMakeLists.txt modification de fichiers")


Dès que vous enregistrez le fichier, l’étape de configuration s’exécute à nouveau automatiquement et affiche des informations dans le **sortie** fenêtre. Erreurs et avertissements sont affichés dans le **liste d’erreurs** ou **sortie** fenêtre. Double-cliquez sur une erreur dans le **liste d’erreurs** pour accéder à la ligne concernée dans CMakeLists.txt.

   ![Erreurs de fichier CMakeLists.txt](media/cmake-cmakelists-error.png "CMakeLists.txt les erreurs de fichier")

## <a name="cmake_settings"></a> Paramètres de CMake et les configurations personnalisées

Par défaut, Visual Studio fournit six configurations de CMake par défaut (« x86-Debug », « x86-version », « x64-Debug », « x64-version finale », « Linux-Debug » et « Linux-version »). Ces configurations définissent la façon dont CMake.exe est appelée pour créer le cache de CMake pour un projet donné. Pour modifier ces configurations, ou créer une configuration personnalisée, choisissez **CMake | Modifier les paramètres de CMake**, puis choisissez le fichier CMakeLists.txt que les paramètres s’appliquent à. Le **modifier les paramètres de CMake** commande est également disponible sur le menu contextuel du fichier **l’Explorateur de solutions**. Cette commande crée un fichier CMakeSettings.json dans le dossier du projet. Ce fichier est utilisé pour recréer le fichier de cache CMake, par exemple après une **Clean** opération. 

   ![Commande de menu principal CMake pour modifier les paramètres](media/cmake-change-settings.png)


JSON IntelliSense vous permet de modifier le fichier CMakeSettings.json :

   ![IntelliSense de JSON de CMake](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

L’exemple suivant montre un exemple de configuration, que vous pouvez utiliser comme point de départ pour créer vos propres dans CMakeSettings.json :

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

1. **nom**: le nom qui apparaît dans la liste déroulante de configuration C++. Cette valeur de propriété peut également être utilisée comme une macro, `${name}`, pour spécifier d’autres valeurs de propriété. Pour obtenir un exemple, consultez la **buildRoot** définition dans CMakeSettings.json.
1. **Générateur**: correspond à la **- G** basculer et spécifie le Générateur à utiliser. Cette propriété peut également être utilisée comme une macro, `${generator}`, pour aider à spécifier d’autres valeurs de propriété. Visual Studio prend actuellement en charge les générateurs de CMake suivantes :


    - « Ninja »
    - « Visual Studio 2015 de 14 »
    - « ARM 14/2015 de visual Studio »
    - « Win64 visual Studio 2015 de 14 »
    - « Visual Studio 15 2017 »
    - « ARM 15 2017 de visual Studio »
    - « Visual Studio 15 2017 Win64 »

Ninja est conçu pour les vitesses de builds rapides au lieu d’une grande souplesse et de fonction, il est défini comme la valeur par défaut. Toutefois, certains projets CMake peuvent être impossible de générer correctement l’à l’aide de Ninja. Si cela se produit, vous pouvez demander à CMake pour générer un projet Visual Studio à la place.

Pour spécifier un générateur de Visual Studio, ouvrez le CMakeSettings.json dans le menu principal en choisissant **CMake | Modifier les paramètres de CMake**. Supprimez « Ninja » et « V » de type. Cela permet d’activer IntelliSense, qui vous permet de choisir le générateur souhaité.

1. **buildRoot**: mappe à **-DCMAKE_BINARY_DIR** basculer et indique où le cache de CMake sera créé. Si le dossier n’existe pas, il est créé.
1. **variables**: contient une paire nom-valeur des variables de CMake seront passés en tant que **-D**_nom_**=**_valeur_ à CMake. Si vos instructions de génération de projet CMake spécifient l’ajout de toutes les variables directement dans le fichier de cache de CMake, il est recommandé de les ajouter ici à la place.
1. **cmakeCommandArgs**: Spécifie les commutateurs supplémentaires que vous souhaitez passer à CMake.exe.
1. **type de configuration**: définit le type de configuration de build pour le Générateur de sélectionné. Valeurs actuellement prises en charge sont « Debug », « MinSizeRel », « Release » et « RelWithDebInfo ».

### <a name="environment-variables"></a>Variables d’environnement

CMakeSettings.json prend également en charge les variables d’environnement beaucoup dans les propriétés mentionnées ci-dessus. La syntaxe à utiliser est `${env.FOO}` pour développer la variable d’environnement FOO %.
Vous avez également accès aux macros intégrées à l’intérieur de ce fichier :

- `${workspaceRoot}` : fournit le chemin d’accès complet du dossier de l’espace de travail
- `${workspaceHash}` – hachage de l’emplacement de l’espace de travail ; utile pour la création d’un identificateur unique pour l’espace de travail actuel (par exemple, à utiliser dans les chemins d’accès de dossier)
- `${projectFile}` : le chemin d’accès complet du fichier racine CMakeLists.txt
- `${projectDir}` : le chemin d’accès complet du dossier du fichier racine CMakeLists.txt
- `${thisFile}` : le chemin d’accès complet du fichier CMakeSettings.json
- `${name}` – le nom de la configuration
- `${generator}` – le nom du Générateur de CMake utilisé dans cette configuration

### <a name="ninja-command-line-arguments"></a>Arguments de ligne de commande Ninja

Si les cibles ne sont pas spécifiés, génère la cible de 'default' (voir le manuel).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Option|Description|
|--------------|------------|
| --version  | Imprimer ninja version (« 1.7.1 »)|
|   C - DIR   | modifier DIR avant d’exécuter toute autre opération|
|   f - fichier  | Spécifiez le fichier d’entrée de génération (default=build.ninja)|
|   j - N     | exécuter des tâches N en parallèle (valeur par défaut = 14, dérivée de processeurs disponibles)|
|   k - N     | Poursuivez la lecture jusqu'à ce que N tâches échouent (valeur par défaut = 1)|
|   l - N     | ne démarrez pas de nouvelles tâches si la moyenne de la charge est supérieure à N|
|   -n      | sec exécuter (ne pas exécuter des commandes mais agir comme si l’opération a réussi)|
|   -v       | afficher toutes les lignes de commande lors de la génération|
|   d - MODE  | Activer le débogage (utilisation des modes de liste à -d)|
|   t - outil  | Exécutez un subtool (utilisation de t - outils auxiliaires de liste à la liste). met fin à des options de niveau supérieur ; plus les indicateurs sont transmis à l’outil| 
|   w - indicateur  | ajuster les avertissements (utilisation des avertissements de liste à la liste -w)|

### <a name="inherited-environments-visual-studio-2017-version-155"></a>Environnements héritées (Visual Studio 2017 version 15.5)
CMakeSettings.json prend désormais en charge les environnements hérités. Cette fonctionnalité vous permet héritent des environnements de valeur par défaut (1) et (2) de créer des variables d’environnement personnalisées qui sont passées à CMake.exe lorsqu’il s’exécute.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

L’exemple ci-dessus est celle en cours d’exécution le **invite de commandes développeur pour VS 2017** avec la **-arch = amd64-host_arch = amd64** arguments.

Le tableau suivant montre les valeurs par défaut et leurs équivalents de ligne de commande :

|Nom de contexte|Description|
|-----------|-----------------|
|vsdev|L’environnement de Visual Studio par défaut|
|msvc_x86|Compiler pour x86 à l’aide de x86 outils|
|msvc_arm| Compiler pour ARM, à l’aide de x86 outils|
|msvc_arm64|Compiler pour ARM64 à l’aide de x86 outils|
|msvc_x86_x64|Compiler pour AMD64 à l’aide de x86 outils|
|msvc_x64_x64|Compiler pour AMD64 à l’aide d’outils 64 bits|
|msvc_arm_x64|Compiler pour ARM, à l’aide d’outils 64 bits|
|msvc_arm64_x64|Compiler pour ARM64 à l’aide d’outils 64 bits|

### <a name="custom-environment-variables"></a>Variables d’environnement personnalisées
Dans CMakeSettings.json, vous pouvez définir des variables d’environnement personnalisées globalement ou par configuration dans le **environnements** propriété. L’exemple suivant définit une variable globale, **BuildDir**, qui est hérité par les configurations de débogage x86 et de x64-Debug. Chaque configuration utilise la variable pour spécifier la valeur pour le **buildRoot** propriété pour cette configuration. Notez également comment chaque configuration utilise le **inheritEnvironments** propriété pour spécifier une variable qui s’applique uniquement à cette configuration.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

Dans l’exemple suivant, la configuration du débogage x86 définit sa propre valeur pour le **BuildDir** propriété et cette valeur remplace la valeur définie par l’élément global **BuildDir** propriété afin que  **BuildRoot** prend la valeur `D:\custom-builddir\x86-Debug`.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir",
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ], 
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="cmake-configure-step"></a>CMake configurer l’étape

Lorsque les modifications importantes sont apportées à la CMakeSettings.json ou aux fichiers CMakeLists.txt, Visual Studio automatiquement réexécute la CMake configurer étape. Si l’étape de configuration se termine sans erreur, les informations collectées est disponibles dans C++ IntelliSense et les services de langage et également dans la génération et débogage des opérations.

Lorsque plusieurs projets CMake utilisent le même nom de configuration de CMake (par exemple, x86-Debug), tous les sont configurés et générés (dans son propre dossier racine de la build) lorsque cette configuration est sélectionnée. Vous pouvez déboguer les cibles à partir de tous les projets de CMake qui participent à cette configuration de CMake.

   ![Élément de menu Générer uniquement le CMake](media/cmake-build-only.png "CMake générer uniquement des éléments de menu")

Pour limiter les builds et les sessions à un sous-ensemble des projets dans l’espace de travail de débogage, créer une configuration avec un nom unique dans le fichier CMakeSettings.json et l’appliquer à ces projets uniquement. Lorsque cette configuration est sélectionnée, les commandes IntelliSense et de génération et de débogage sont activées uniquement pour les projets spécifiés.

## <a name="troubleshooting-cmake-cache-errors"></a>Dépannage des erreurs de cache CMake

Si vous avez besoin de plus d’informations sur l’état du cache CMake pour diagnostiquer un problème, ouvrez le **CMake** menu principal ou le **CMakeLists.txt** menu contextuel dans **l’Explorateur de solutions**pour exécuter une des commandes suivantes :

- **Afficher le Cache** ouvre le fichier CMakeCache.txt à partir du dossier racine de build dans l’éditeur. (Toutes les modifications que vous apportez ici à CMakeCache.txt sont effacées si vous nettoyez le cache. Pour apporter des modifications conservées une fois que le cache est nettoyé, consultez [CMake paramètres et les configurations personnalisées](#cmake_settings) plus haut dans cet article.)
- **Ouvrez le dossier du Cache** ouvre une fenêtre d’Explorateur dans le dossier racine de génération.  
- **Nettoyage du Cache** supprime le dossier racine de build afin que le prochain CMake configurer étape commence un nettoyeur de cache.
- **Générer le Cache** force l’étape de génération s’exécute même si Visual Studio prend en compte dans l’environnement de mise à jour.
