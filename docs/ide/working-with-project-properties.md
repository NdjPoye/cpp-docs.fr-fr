---
title: Utilisation des propriétés de projet | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- project properties [C++], modifying
- properties [C++]
- Visual C++ projects, properties
- projects [C++], properties
ms.assetid: 9b0d6f8b-7d4e-4e61-aa75-7d14944816cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c33a18ff0d492ef3a870a342c9d8ff292007748
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-project-properties"></a>Utilisation des propriétés de projet
Dans l’IDE, toutes les informations nécessaires pour générer un projet sont exposées en tant que *propriétés*. Ces informations comprennent le nom de l’application, l’extension (par exemple, les DLL, LIB, EXE), options du compilateur, options de l’éditeur de liens, paramètres du débogueur, les étapes de génération personnalisée et beaucoup d’autres choses. En général, vous utilisez *pages de propriétés* ( **projet &#124; propriétés**) pour afficher et modifier ces propriétés. 
  
 Lorsque vous créez un projet, le système assigne des valeurs pour les différentes propriétés. Les valeurs par défaut varient légèrement en fonction du type de projet et les options que vous choisissez dans l’Assistant Application. Par exemple, un projet ATL a les propriétés relatives aux fichiers MIDL, mais ils sont absents dans une application console Visual basic. Les propriétés par défaut sont affichées dans le volet Général dans les Pages de propriétés :  
  
 ![Visual C&#43; &#43; valeurs par défaut du projet](../ide/media/visual-c---project-defaults.png "par défaut des projets Visual C++")  
  
 Certaines propriétés, telles que le nom de l’application s’appliquent à toutes les variations de build, quelle que soit la plateforme cible ou s’il s’agit d’une build debug ou release. Mais la plupart des propriétés qui sont dépendantes de la configuration. Il s’agit, car le compilateur doit savoir quelle plate-forme spécifique, le programme s’exécutera sur ainsi que le compilateur spécifique d’options à utiliser pour générer le code correct. Par conséquent, lorsque vous définissez une propriété, il est important de faire attention à la configuration et la plateforme de la nouvelle valeur doit s’appliquer à qui. Doit s’appliquer uniquement à des builds de débogage Win32 ou devez également appliquer à déboguer une branche et de débogage x64 ? Par exemple, le **optimisation** , par défaut, est définie sur **augmenter la vitesse (/ O2)** dans une configuration Release, mais est désactivé dans la configuration Debug.  
  
 Les pages de propriétés sont conçus afin que vous pouvez toujours voir, et si nécessaire modifier, configuration et la plateforme qui une valeur de propriété doit s’appliquer à. L’illustration suivante montre les pages de propriétés à la configuration et les informations de plate-forme dans les zones de liste en haut. Lorsque le **optimisation** est définie ici, il s’applique uniquement aux versions de débogage Win32, ce qui se produit à la configuration active, comme indiqué par les flèches rouges.  
  
 ![Visual C&#43; &#43; configuration active de Pages de propriétés affichant](../ide/media/visual-c---property-pages-showing-active-configuration.png "configuration active affichant de Pages de propriétés Visual C++")  
  
 L’illustration suivante montre la même page de propriétés de projet, mais la configuration a été modifiée pour la mise en production. Notez la valeur différente pour la propriété de l’optimisation. Notez également que la configuration active est toujours de débogage. Vous pouvez définir des propriétés pour n’importe quelle configuration ici ; Il ne doit être actif.  
  
 ![Visual C&#43; &#43; Pages de propriétés affichant version config](../ide/media/visual-c---property-pages-showing-release-config.png "Pages de propriétés Visual C++ montrant version config")  
  
 Le système de projet lui-même est basé sur MSBuild, qui définit les formats de fichier et les règles pour générer les projets de tout type. MSBuild gère la complexité de construction pour plusieurs plateformes et configurations, mais vous devez comprendre un peu sur son fonctionnement. Cela est particulièrement important si vous souhaitez définir des configurations personnalisées ou créer des ensembles de propriétés que vous pouvez partager et l’importer dans plusieurs projets réutilisables.  
  
 Propriétés de projet sont stockées directement dans le fichier de projet (*.vcxproj) ou dans d’autres fichiers .xml ou .props que les importations du fichier projet, ainsi que fournir des valeurs par défaut. Comme indiqué précédemment, la même propriété pour la même configuration peut avoir une valeur différente dans différents fichiers. Lorsque vous générez un projet, le moteur MSBuild évalue le fichier projet et tous les fichiers importés dans un ordre bien défini (décrites ci-dessous). Comme chaque fichier est évaluée, des valeurs de propriété définis dans ce fichier remplacent les valeurs existantes. Toutes les valeurs qui ne sont pas spécifiés sont hérités des fichiers qui ont été évaluées précédemment. Par conséquent, lorsque vous définissez une propriété avec des pages de propriétés, il est également important de veiller à où vous la définissez. Si vous définissez une propriété à « X » dans un fichier .props, mais la propriété est définie à « Y » dans le fichier projet, le projet est généré avec la propriété définie sur « Y ». Si la même propriété est définie à « Z » sur un élément de projet, tel qu’un fichier .cpp, le moteur MSBuild utilisera la valeur de « Z ». Pour plus d’informations, consultez [l’héritage de propriété](#bkmkPropertyInheritance) plus loin dans cet article.  
  
## <a name="build-configurations"></a>Configurations de build  
 Une configuration est simplement un groupe arbitraire de propriétés qui portent un nom. Visual Studio fournit des configurations Debug et Release, et chacune définit différentes propriétés de manière appropriée pour une version debug ou une version Release. Vous pouvez utiliser la **Configuration Manager** pour définir des configurations personnalisées comme un moyen pratique de propriétés du groupe pour une version spécifique de build. Le Gestionnaire de propriétés est utilisé pour le travail avancé avec des propriétés, mais nous elle introduit ici car elle permet de visualiser les configurations de propriétés. Vous y accédez depuis **vue &#124; Gestionnaire de propriétés** ou **vue &#124; autres fenêtres &#124; Gestionnaire de propriétés** en fonction de vos paramètres. Il a des nœuds pour chaque paire de plateforme/configuration dans le projet. Dans chacun de ces nœuds sont des nœuds pour les feuilles de propriétés (fichiers .props) que définir des propriétés spécifiques pour cette configuration.  
  
 ![Gestionnaire de propriétés](../ide/media/property-manager.png "Gestionnaire de propriétés")  
  
 Si vous accédez au volet Général dans les Pages de propriétés (voir l’illustration ci-dessus) et définir la propriété du jeu de caractères « Ne pas définir » au lieu de « Utiliser Unicode », puis cliquez sur **OK**, Gestionnaire de propriétés affichera aucune **prise en charge Unicode** feuille de propriétés pour la configuration actuelle, mais il sera toujours présente pour d’autres configurations.  
  
 Pour plus d’informations sur le Gestionnaire de propriétés et les feuilles de propriétés, consultez [création de configurations de propriétés réutilisables](#bkmkPropertySheets) plus loin dans cet article.  
  
> [!TIP]
>  Le fichier .user est une fonctionnalité héritée et nous vous recommandons de supprimer afin de conserver correctement regroupées en fonction de la plateforme de la configuration des propriétés.  
  
## <a name="target-platforms"></a>Plateformes cibles  
 *Plateforme cible* fait référence au type de l’appareil et/ou le système d’exploitation que l’exécutable s’exécutera sur. Vous pouvez générer un projet pour plusieurs plateformes. Les plateformes cibles disponibles pour les projets C++ varient selon le type de projet ; ils incluent, mais ne sont pas limités à Win32, x64, ARM, Android et iOS.     Le **x86** plateforme cible que vous pouvez consulter dans **Configuration Manager** est identique à **Win32** dans les projets C++ natif. Win32 signifie que Windows 32 bits et **x64** signifie Windows 64 bits. Pour plus d’informations sur ces deux plateformes, consultez [applications en cours d’exécution de 32 bits](https://msdn.microsoft.com/library/windows/desktop/aa384249\(v=vs.85\).aspx).  
  
 Le **Any CPU** cibler la valeur de la plateforme que vous pouvez consulter dans **Configuration Manager** n’a aucun effet sur les projets natifs C++ ; il ne s’applique à C + c++ / CLI et autres .NET des types de projets. Pour plus d’informations, consultez l’article [/CLRIMAGETYPE (Spécifier le type d’une image CLR)](../build/reference/clrimagetype-specify-type-of-clr-image.md).  
  
## <a name="property-pages"></a>pages de propriétés  
 Comme indiqué précédemment, le système de projet Visual C++ est basé sur [MSBuild](/visualstudio/msbuild/msbuild-properties) et les valeurs sont stockées dans le fichier de projet XML, par défaut les fichiers .props et .targets. Pour Visual Studio 2015, ces fichiers se trouvent dans **\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**. Pour Visual Studio 2017, ces fichiers se trouvent dans  **\\Program Files (x86)\\Microsoft Visual Studio\\2017\\_édition_\\Common7\\ IDE\\VC\\VCTargets**, où _édition_ est l’édition de Visual Studio installée. Propriétés sont également stockées dans les fichiers .props personnalisé que vous pouvez ajouter à votre projet. Nous recommandons vivement que vous pas modifiez ces fichiers manuellement et utilisez à la place les pages de propriétés dans l’IDE pour modifier toutes les propriétés, en particulier ceux qui participent à l’héritage, à moins d’avoir une très bonne compréhension de MSBuild.  
  
 L’illustration suivante montre les pages de propriétés d’un projet Visual C++. Dans le volet gauche, le **répertoires VC ++ *** règle* est sélectionnée, et le volet droit répertorie les propriétés qui sont associées à cette règle. Le `$(...)` les valeurs sont appelées malheureusement *macros*. Il s’agit *pas* les macros C/C++, mais les constantes de compilation simplement. Les macros sont décrits dans le [macros de page de propriété](#bkmkPropertiesVersusMacros) section plus loin dans cet article.)  
  
 ![Pages de propriétés de projet](../ide/media/project_property_pages_vc.png "Project_Property_Pages_VC")  
  
> [!WARNING]
>  Le **propriétés communes** configurations dans les versions antérieures de Visual Studio ont été supprimées. Pour ajouter une référence à un projet, vous utilisez maintenant le **ajouter une référence** boîte de dialogue de la même façon que pour les langages managés. Consultez [gestion des références dans un projet](/visualstudio/ide/managing-references-in-a-project).  
  
#### <a name="to-set-a-property-for-a-project"></a>Pour définir une propriété pour un projet  
  
1.  La plupart des scénarios, vous pouvez définir des propriétés au niveau du projet sans créer une feuille de propriétés personnalisées. Dans le menu principal, choisissez **projet &#124; propriétés**, ou avec le bouton droit sur le nœud de projet dans **l’Explorateur de solutions** et choisissez **propriétés**.  
  
2.  Utilisez le **Configuration** et **plateforme** zones en haut de la boîte de dialogue pour spécifier les groupes de propriétés doivent appliquer vos modifications de liste. Dans de nombreux cas **toutes les plateformes** et **toutes les Configurations** sont le bon choix. Pour définir les propriétés pour certaines configurations, la sélection multiple dans **Gestionnaire de propriétés**, puis ouvrez le menu contextuel et choisissez **propriétés**.  
  
 Le **Pages de propriétés** boîte de dialogue affiche uniquement les pages de propriétés qui s’appliquent au projet actif. Par exemple, si le projet n'a pas de fichier .idl, la page de propriétés MIDL n'est pas affichée.  
  
 Lorsque vous sélectionnez une propriété dans une Page de propriétés, vous pouvez appuyer sur **F1** pour accéder à la rubrique de référence pour plus d’informations sur le commutateur du compilateur ou l’éditeur de liens correspondant.  
  
 Vous trouverez plus d’informations sur chaque Page de propriétés dans les rubriques suivantes :  
  
-   [Général, page de propriétés (Projet)](../ide/general-property-page-project.md)  
  
-   [Général, page de propriétés (Fichier)](../ide/general-property-page-file.md)  
  
-   [Ligne de commande, pages de propriétés](../ide/command-line-property-pages.md)  
  
-   [Paramètres de projet pour une configuration Debug C++](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration)  
  
-   [NMake, page de propriétés](../ide/nmake-property-page.md)  
  
-   [Éditeur de liens, page de propriétés](../ide/linker-property-pages.md)  
  
-   [Ressources, page de propriétés](../ide/resources-property-pages.md)  
  
-   [MIDL, page de propriétés](../ide/midl-property-pages.md)  
  
-   [Références web, page de propriétés](../ide/web-references-property-page.md)  
  
-   [XML Data Generator Tool, page de propriétés](../ide/xml-data-generator-tool-property-page.md)  
  
## <a name="to-quickly-browse-and-search-all-properties"></a>Pour parcourir rapidement et de toutes les propriétés de recherche  
 Le **toutes les Options** page de propriétés (sous la **propriétés de Configuration &#124; C/C++** nœud dans le **Pages de propriétés** boîte de dialogue) fournit un moyen rapide de rechercher et de recherche les propriétés qui sont disponibles dans le contexte actuel. Elle comporte une zone de recherche spéciale et possède une syntaxe simple pour aider à filtrer les résultats :  
  
 Aucun préfixe :  
 Effectuer une recherche dans les noms de propriétés uniquement (la sous-chaîne ne respecte pas la casse).  
  
 '/' ou '-' :  
 Effectuer une recherche uniquement dans les commutateurs de compilation (le préfixe ne respecte pas la casse)  
  
 v :  
 Effectuer une recherche uniquement dans les valeurs (la sous-chaîne ne respecte pas la casse).  
  
##  <a name="bkmkPropertiesVersusMacros"></a> Macros de page de propriété  
 A *macro* est une constante de compilation peut faire référence à une valeur qui est définie par Visual Studio ou le système MSBuild ou à une valeur définie par l’utilisateur. L'utilisation de macros au lieu de valeurs codées en dur telles que les chemins d'accès aux répertoires permet de partager facilement des paramètres de propriétés entre les ordinateurs et entre les versions de Visual Studio et de mieux s'assurer que les paramètres de projet participent correctement à l'héritage de propriété. Vous pouvez utiliser l’éditeur de propriétés pour afficher les valeurs de toutes les macros disponibles.  
  
### <a name="predefined-macros"></a>Macros prédéfinies  
 macros globales  
 S'applique à tous les éléments dans une configuration de projet. Possède la syntaxe `$(name)`. Un exemple de macro globale est `$(VCInstallDir)`, qui stocke le répertoire racine de votre installation de Visual Studio. Une macro globale correspond à `PropertyGroup` dans MSBuild.  
  
 macros d'élément  
 Possède la syntaxe `%(name)`. Pour un fichier, une macro d'élément s'applique uniquement à ce fichier ; par exemple, vous pouvez utiliser `%(AdditionalIncludeDirectories)` pour spécifier les répertoires Include qui s'appliquent uniquement à un fichier particulier. Ce genre de macro d'élément correspond à des métadonnées `ItemGroup` dans MSBuild. Lorsqu'elle est utilisée dans le contexte d'une configuration de projet, une macro d'élément s'applique à tous les fichiers d'un certain type. Par exemple, C/C++ **définitions de préprocesseur** propriété de configuration peut prendre un `%(PreprocessorDefinitions)` macro d’élément qui s’applique à tous les fichiers .cpp dans le projet. Ce genre de macro d'élément correspond à des métadonnées `ItemDefinitionGroup` dans MSBuild. Pour plus d’informations, consultez l’article [Item Definitions (Définitions des éléments)](/visualstudio/msbuild/item-definitions).  
  
### <a name="user-defined-macros"></a>macros définies par l'utilisateur  
 Vous pouvez créer *macros définies par l’utilisateur* à utiliser comme variables dans les générations de projet. Par exemple, vous pouvez créer une macro définie par l'utilisateur qui fournit une valeur pour une étape de génération personnalisée ou un outil de génération personnalisée. Une macro définie par l'utilisateur est une paire nom/valeur. Dans un fichier projet, utilisez le **$(***nom***)** notation pour accéder à la valeur.  
  
 Une macro définie par l’utilisateur est stockée dans une feuille de propriétés. Si votre projet ne contient pas déjà une feuille de propriétés, vous pouvez en créer un en suivant les étapes sous [création de configurations de propriétés réutilisables](#bkmkPropertySheets).  
  
##### <a name="to-create-a-user-defined-macro"></a>Pour créer une macro définie par l’utilisateur  
  
1.  Dans le **Gestionnaire de propriétés** fenêtre (dans la barre de menus, choisissez **vue**, **Gestionnaire de propriétés**), ouvrez le menu contextuel pour une feuille de propriétés (son nom se termine par .user), puis sélectionnez Propriétés. Le **Pages de propriétés** ouvre la boîte de dialogue pour cette feuille de propriétés.  
  
2.  Dans le volet gauche de la boîte de dialogue, sélectionnez **Macros utilisateur**. Dans le volet droit, choisissez le **ajouter une Macro** bouton pour ouvrir la **ajouter une Macro utilisateur** boîte de dialogue.  
  
3.  Dans la boîte de dialogue, spécifiez un nom et une valeur pour la macro. Si vous le souhaitez, sélectionnez le **définir cette macro en tant que variable d’environnement dans l’environnement de génération** case à cocher.  
  
## <a name="property-editor"></a>Éditeur de propriétés  
 Vous pouvez utiliser l'Éditeur de propriétés pour modifier certaines propriétés de type chaîne et sélectionner des macros comme valeurs. Pour accéder à l'Éditeur de propriétés, sélectionnez une propriété dans une page de propriétés, puis cliquez sur la flèche vers le bas située à droite. Si la liste déroulante contient  **\<Modifier >**, vous pouvez la choisir pour afficher l’éditeur de propriétés pour cette propriété.  
  
 ![Propriété&#95;éditeur&#95;déroulante](../ide/media/property_editor_dropdown.png "Property_Editor_Dropdown")  
  
 Dans l’éditeur de propriétés, vous pouvez choisir le **Macros** bouton pour afficher les macros disponibles et leurs valeurs actuelles. L’illustration suivante montre l’éditeur de propriétés pour le **autres répertoires Include** propriété après la **Macros** bouton a été choisi. Lorsque le **hériter des paramètres par défaut parent ou du projet** case à cocher est activée et vous ajoutez une nouvelle valeur, il est ajouté à toutes les valeurs actuellement héritées. Si vous désactivez la case à cocher, votre nouvelle valeur remplace les valeurs héritées. Dans la plupart des cas, laissez la case à cocher activée.  
  
 ![Éditeur de propriétés, Visual C#&#43;&#43;](../ide/media/propertyeditorvc.png "PropertyEditorVC")  
  
##  <a name="bkmkPropertySheets"></a> Création de configurations de propriétés réutilisables  
 Nous ne recommandons plus de définir les propriétés « globales » sur la base de chaque utilisateur et de chaque ordinateur. Au lieu de cela, nous vous recommandons d’utiliser **Gestionnaire de propriétés** pour créer un *feuille de propriétés* pour stocker les paramètres de chaque genre de projet que vous souhaitez pouvoir réutiliser ou partager avec d’autres utilisateurs. Avec les feuilles de propriétés, il est également moins probable que les paramètres de propriétés pour d’autres types de projets soient modifiés par inadvertance. Feuilles de propriétés sont présentées plus en détail [création de configurations de propriétés réutilisables](#bkmkPropertySheets).  
  
> [!IMPORTANT]
>  **les fichiers .user et pourquoi ils sont problématiques**  
>   
>  Versions précédentes de Visual Studio utilisaient des feuilles de propriétés globales qui avaient une extension de nom de fichier .user et se trouvaient dans le \<profil_utilisateur > \AppData\Local\Microsoft\MSBuild\v4.0\ dossier. Nous ne recommandons plus l'utilisation de ces fichiers, car ils définissent des propriétés pour les configurations de projet sur la base de chaque utilisateur et de chaque ordinateur. Ces paramètres « globaux » peuvent perturber les builds, surtout lorsque vous ciblez plusieurs plateformes sur votre ordinateur de build. Par exemple, si vous avez un projet MFC et un projet Windows Phone, les propriétés .user seraient non valides pour l'un d'eux. Les feuilles de propriétés réutilisables sont plus flexibles et plus fiables.  
>   
>  Bien que les fichiers .user soient toujours installés par Visual Studio et participent à l'héritage des propriétés, ils sont vides par défaut. La meilleure pratique consiste à supprimer la référence correspondante dans **Gestionnaire de propriétés** pour vous assurer que vos projets fonctionnent indépendamment de n’importe quel utilisateur, des paramètres par ordinateur cela est important pour garantir un comportement correct dans un contrôle de code source (code source environnement de contrôle).  
  
 Pour afficher les **Gestionnaire de propriétés**, dans la barre de menus, choisissez **vue**, **autres fenêtres**, **Gestionnaire de propriétés**.  
  
 Si vous avez un ensemble commun de propriétés que vous souhaitez appliquer à plusieurs projets fréquemment utilisé, vous pouvez utiliser **Gestionnaire de propriétés** pour les capturer dans un réutilisable *feuille de propriétés* fichier, qui par convention a une extension de nom de fichier .props. Vous pouvez appliquer la feuille (ou les feuilles) à de nouveaux projets afin de ne pas avoir à définir intégralement ses propriétés. Pour accéder à **Gestionnaire de propriétés**, dans la barre de menus, choisissez **vue**, **Gestionnaire de propriétés**.  
  
 ![Menu contextuel de gestionnaire de propriétés](../ide/media/sharingnew.png "partage d’indexnouvelle")  
  
 Sous chaque nœud de configuration, vous consultez des nœuds pour chaque feuille de propriétés qui s’applique à cette configuration. Le système ajoute des feuilles de propriétés qui définissent les valeurs selon les options que vous choisissez dans l’Assistant application lorsque vous créez le projet. Avec le bouton droit n’importe quel nœud et choisissez Propriétés pour afficher les propriétés qui s’appliquent à ce nœud. Les feuilles de propriétés sont importés automatiquement dans la feuille des propriétés « maître » du projet (ms.cpp.props) et sont évaluées dans l’ordre de qu'apparition dans le Gestionnaire de propriétés. Vous pouvez les déplacer pour modifier l’ordre d’évaluation. Feuilles de propriétés qui sont évaluées plus tard remplace les valeurs dans les feuilles de précédemment évaluée.  
  
 Si vous choisissez **ajouter une nouvelle feuille de propriétés de projet** et puis que vous sélectionnez, par exemple, la feuille de propriétés MyProps.props, une boîte de dialogue de page de propriétés apparaît. Remarquez qu'elle s'applique à la feuille de propriétés MyProps ; toutes les modifications que vous apportez sont écrites dans la feuille, et non dans le fichier projet (.vcxproj).  
  
 Les propriétés dans une feuille de propriétés sont remplacées si la même propriété est définie directement dans le fichier .vcxproj.  
  
 Vous pouvez importer une feuille de propriétés aussi souvent que nécessaire. Plusieurs projets d'une solution peuvent hériter des paramètres de la feuille de propriétés et un projet peut avoir plusieurs feuilles. Une feuille de propriétés peut hériter elle-même des paramètres d'une autre feuille de propriétés.  
  
 Vous pouvez également créer une feuille de propriétés pour plusieurs configurations. Pour ce faire, créez une feuille de propriétés pour chaque configuration, ouvrez le menu contextuel pour un d’eux, choisissez **ajouter la feuille de propriétés existante**, puis ajoutez les autres feuilles. Toutefois, si vous utilisez une feuille de propriétés commune, sachez que lorsque vous définissez une propriété, elle est définie pour toutes les configurations auxquelles la feuille s'applique et l'environnement IDE n'indique pas quels projets ou autres feuilles de propriétés héritent d'une feuille de propriétés donnée.  
  
 Dans les grandes solutions qui auront de nombreux projets, il peut être utile de créer une feuille de propriétés au niveau de la solution. Lorsque vous ajoutez un projet à la solution, utilisez **Gestionnaire de propriétés** pour ajouter cette feuille de propriétés pour le projet. Si nécessaire au niveau du projet, vous pouvez ajouter une nouvelle feuille de propriétés pour définir des valeurs spécifiques au projet.  
  
> [!IMPORTANT]
>  Un fichier .props par défaut ne participe pas au contrôle de code source car il n'est pas créé en tant qu'élément de projet. Vous pouvez ajouter manuellement le fichier comme élément de solution si vous souhaitez l'inclure dans le contrôle de code source.  
  
#### <a name="to-create-a-property-sheet"></a>Pour créer une feuille de propriétés  
  
1.  Dans la barre de menus, choisissez **vue**, **Gestionnaire de propriétés**. Le **Gestionnaire de propriétés** s’ouvre.  
  
2.  Pour définir la portée de la feuille de propriétés, sélectionnez l'élément auquel elle s'applique. Il peut s'agir d'une configuration particulière ou d'une autre feuille de propriétés. Ouvrez le menu contextuel pour cet élément, puis choisissez **ajouter une nouvelle feuille de propriétés de projet**. Spécifiez un nom et un emplacement.  
  
3.  Dans **Gestionnaire de propriétés**, ouvrez la nouvelle feuille de propriétés, puis définissez les propriétés que vous souhaitez inclure.  
  
##  <a name="bkmkPropertyInheritance"></a> Héritage de propriété  
 Les propriétés de projet sont superposées. Chaque couche hérite des valeurs de la couche précédente, mais une valeur héritée peut être substituée en définissant la propriété explicitement. Voici l’arborescence d’héritage de base :  
  
1.  Paramètres par défaut de l’ensemble d’outils MSBuild CPP (..\Program Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props, qui est importé par le fichier .vcxproj.)  
  
2.  Feuilles de propriétés  
  
3.  Fichier .vcxproj. (peut substituer les paramètres par défaut et les paramètres de feuille de propriétés.)  
  
4.  Métadonnées d'élément  
  
> [!TIP]
>  Sur une page de propriétés, une propriété dans `bold` est défini dans le contexte actuel. Une propriété en police normale est héritée.  
  
 Un fichier projet (.vcxproj) importe d'autres feuilles de propriétés au moment de la génération. Une fois toutes les feuilles de propriétés importées, le fichier projet est évalué et la dernière définition d'une valeur de propriété est celle qui est utilisée. Il est parfois utile d'afficher le fichier développé pour déterminer comment une valeur de propriété donnée est héritée. Pour afficher la version développée, entrez la commande suivante à une invite de commandes Visual Studio. (Remplacez les espaces réservés des noms de fichiers par ceux que vous voulez utiliser.)  
  
 **msbuild /pp:** *temp* **.txt** *mon_application* **.vcxproj**  
  
 Les fichiers projet développés peuvent être volumineux et difficiles à comprendre si MSBuild ne vous est pas familier. Voici la structure de base d'un fichier projet :  
  
1.  Propriétés de projet fondamentales, qui ne sont pas exposées dans l'environnement IDE.  
  
2.  Importation de Microsoft.cpp.default.props, qui définit des propriétés de base et indépendantes des ensembles d'outils.  
  
3.  Propriétés de Configuration globales (exposées en tant que **PlatformToolset** et **projet** propriétés par défaut sur le **Configuration générale** page. Ces propriétés déterminent l'ensemble d'outils et les feuilles de propriétés intrinsèques importés dans Microsoft.cpp.props à l'étape suivante.  
  
4.  Importation de Microsoft.cpp.props, qui définit la plupart des paramètres par défaut du projet.  
  
5.  Importation de toutes les feuilles de propriétés, y compris les fichiers .user. Ces feuilles de propriétés peuvent tout remplacer, sauf le **PlatformToolset** et **projet** propriétés par défaut.  
  
6.  Les propriétés restantes de la configuration du projet. Ces valeurs peuvent remplacer celles définies dans les feuilles de propriétés.  
  
7.  Éléments (fichiers) avec leurs métadonnées. Il s’agit toujours du dernier mot dans les règles d’évaluation MSBuild, même s’ils se produisent avant d’autres propriétés et importations.  
  
 Pour plus d’informations, consultez l’article [Propriétés MSBuild](/visualstudio/msbuild/msbuild-properties).  
  
## <a name="adding-an-include-directory-to-the-set-of-default-directories"></a>Ajout d'un répertoire Include au jeu de répertoires par défaut  
 Lorsque vous ajoutez un répertoire Include à un projet, il est important de ne pas remplacer tous les répertoires par défaut. La méthode correcte pour ajouter un répertoire consiste à ajouter le nouveau chemin, par exemple « C:\MyNewIncludeDir\", puis à ajouter le **$ (includepath)** macro pour que la valeur de propriété.  
  
## <a name="setting-environment-variables-for-a-build"></a>Définition des variables d'environnement pour une génération  
 Le compilateur Visual C++ (cl.exe) reconnaît certaines variables d’environnement, plus spécifiquement LIB, LIBPATH, PATH et INCLUDE. Lorsque vous générez avec l’IDE, les propriétés sont définies dans le [Page de propriétés répertoires VC ++](../ide/vcpp-directories-property-page.md) page de propriétés sont utilisées pour définir ces variables d’environnement. Si les valeurs LIB, LIBPATH et INCLUDE ont déjà été définies, par exemple par une invite de commandes développeur, elles sont remplacées par les valeurs des propriétés MSBuild correspondantes. La génération ajoute ensuite la valeur de la propriété de répertoires d'exécutables Répertoires VC++ à PATH. Vous pouvez définir une variable d’environnement définie par l’utilisateur en créant une macro définie par l’utilisateur et en activant la case **définir cette macro en tant que variable d’environnement dans l’environnement de génération**.  
  
## <a name="setting-environment-variables-for-a-debugging-session"></a>Définition des variables d'environnement pour une session de débogage  
 Dans le volet gauche du projet **Pages de propriétés** boîte de dialogue, développez **propriétés de Configuration** , puis sélectionnez **débogage**. 
  
 Dans le volet droit, modifiez le **environnement** ou **fusion de l’environnement** paramètres du projet, puis choisissez le **OK** bouton.  

## <a name="modifying-properties-and-targets-without-changing-the-project-file"></a>Modification des propriétés et les cibles sans modifier le fichier de projet
Vous pouvez remplacer les propriétés de projet et des cibles à partir de l’invite de commandes MSBuild sans modifier le fichier projet. Cela est utile lorsque vous souhaitez appliquer certaines propriétés temporairement ou occasionnellement. Il suppose une connaissance de MSBuild. Pour plus d’informations, consultez [MSBUild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild).

> [!IMPORTANT]
> Vous pouvez utiliser l’éditeur XML dans Visual Studio, ou n’importe quel éditeur de texte pour créer le fichier .props ou .targets. N’utilisez pas le **Gestionnaire de propriétés** dans ce scénario, car elle ajoute les propriétés au fichier projet.

*Pour remplacer les propriétés du projet :*
- Créez un fichier .props qui spécifie les propriétés que vous souhaitez remplacer. 
- À partir de l’invite de commandes : définissez ForceImportBeforeCppTargets="C:\sources\my_props.props »
 
*Pour remplacer le projet cible :*
1) Créer un fichier .targets avec leur implémentation ou d’une cible particulière
2) À partir de l’invite de commandes : définissez ForceImportAfterCppTargets = « C:\sources\my_target.targets »
 
Vous pouvez également définir l’option de la ligne de commande msbuild à l’aide de l’option/p: :

```cmd
> msbuild myproject.sln /p:ForceImportBeforeCppTargets="C:\sources\my_props.props" 
> msbuild myproject.sln /p:ForceImportAfterCppTargets="C:\sources\my_target.targets" 
```  

Substitution de propriétés et les cibles de cette façon est équivalente à l’ajout les importations suivantes à tous les fichiers .vcxproj dans la solution :

```cmd 
<Import Project=="C:\sources\my_props.props" />
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
<Import Project==" C:\sources\my_target.targets"" />
```  

## <a name="see-also"></a>Voir aussi  
 [Création et la gestion des projets de Visual C++](../ide/creating-and-managing-visual-cpp-projects.md) [structure du fichier .vcxproj et .props](vcxproj-file-structure.md) [fichiers XML de page Propriétés](property-page-xml-files.md)