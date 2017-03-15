---
title: "Erreur LNK2001 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2001
dev_langs:
- C++
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: 21
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 3629075e5659cb89ab751b011f3ce2cbf89397cc
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2001"></a>Erreur des outils Éditeur de liens LNK2001
symbole externe non résolu « symbole »  
  
 Code référence quelque chose que l’éditeur de liens ne peut pas trouver dans les bibliothèques et les fichiers d’objets (par exemple, une fonction, variable ou étiquette).  
  
 Ce message d’erreur est suivi d’une erreur irrécupérable [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md).  
  
 **Causes possibles**  
  
-   Lors de la mise à niveau d’une bibliothèque managée ou un projet de service web à partir de Visual C++ 2003, les **/Zl** a été ajoutée à la **ligne de commande** page de propriétés. Cela provoquera une erreur LNK2001.  
  
     Pour résoudre cette erreur, ajoutez msvcrt.lib et msvcmrt.lib à la propriété Dépendances supplémentaires de l’éditeur de liens. Ou bien, supprimez **/Zl** à partir de la **ligne de commande** page de propriétés. Pour plus d’informations, consultez [/Zl (omettre les nom de bibliothèque par défaut)](../../build/reference/zl-omit-default-library-name.md) et [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
-   Ce que le code demande n’existe pas (le symbole est mal orthographié ou utilise une casse incorrecte, par exemple).  
  
-   Le code demande un objet erroné (vous utilisez des versions mixtes des bibliothèques, certains à partir d’une version du produit, d’autres à partir d’une autre version).  
  
 **Causes spécifiques**  
  
 **Problèmes de codage**  
  
-   Si le texte du diagnostic LNK2001 rapporte que `__check_commonlanguageruntime_version` est un symbole externe non résolu, consultez [l’erreur LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) pour plus d’informations sur la façon de les résoudre.  
  
-   La définition de modèle de membre est en dehors de la classe. Visual C++ a une limite dans lequel les modèles de membre doivent être entièrement définis au sein de la classe englobante. Consultez l’article Q239436 pour plus d’informations sur les modèles LNK2001 et membre.  
  
-   Casse différente dans votre code ou de définition de module (.def) fichier peut causer l’erreur LNK2001. Par exemple, si vous avez nommé une variable `var1` dans un C++ fichier source et tentez d’y accéder en tant que `VAR1` dans un autre.  
  
-   Un projet qui utilise [fonction inline](../../error-messages/tool-errors/function-inlining-problems.md) mais définit les fonctions dans un fichier .cpp, plutôt que dans l’en-tête de fichier peut causer l’erreur LNK2001.  
  
-   Appeler une fonction C à partir d’un programme C++ sans utiliser `extern` « C » (qui impose au compilateur d’utiliser la convention d’affectation de noms C) peut causer l’erreur LNK2001. Options du compilateur [/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) et [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) le compilateur de compiler les fichiers sous forme C++ ou C, respectivement, quelle que soit l’extension de nom de fichier. Ces options peuvent provoquer des noms de fonction différentes de ce que vous attendez.  
  
-   Tentez de référencer des fonctions ou des données qui n’ont pas une liaison externe peut causer l’erreur LNK2001. En C++, les fonctions inline et `const` données ont une liaison interne sauf spécification explicite `extern`.  
  
-   A [corps de fonction ou variable manquant](../../error-messages/tool-errors/missing-function-body-or-variable.md) peut causer l’erreur LNK2001. Avec seulement un prototype de fonction ou `extern` déclaration, le compilateur peut poursuivre sans erreur, mais l’éditeur de liens ne peut pas résoudre un appel à une adresse ou une référence à une variable, car il n’existe pas de code de fonction ou variable espace réservé.  
  
-   Appel d’une fonction avec des types de paramètres qui ne correspondent pas à ceux de la déclaration de fonction peut causer l’erreur LNK2001. [Décoration de nom](../../error-messages/tool-errors/name-decoration.md) incorpore les paramètres d’une fonction dans le nom décoré final de la fonction.  
  
-   Incorrectement inclus prototypes, ce qui conduit le compilateur à attendre un corps de fonction qui n’est pas fourni peuvent causer l’erreur LNK2001. Si vous avez une classe et la classe de mise en œuvre d’une fonction `F`, prenez garde aux règles de résolution de portée C++.  
  
-   En C++, y compris un prototype de fonction dans une définition de classe et ne peut pas [incluent la mise en oeuvre](../../error-messages/tool-errors/missing-function-body-or-variable.md) de la fonction pour cette classe peut causer l’erreur LNK2001.  
  
-   Essayez d’appeler une fonction virtuelle pure depuis le constructeur ou un destructeur de classe de base abstraite peut causer l’erreur LNK2001. Une fonction virtuelle pure n’a aucune implémentation de la classe de base.  
  
-   Essayez d’utiliser une variable déclarée dans une fonction ([une variable locale](../../error-messages/tool-errors/automatic-function-scope-variables.md)) en dehors de la portée de cette fonction peut causer l’erreur LNK2001.  
  
-   Lorsque vous créez une version d’un projet ATL, indique que le code de démarrage CRT est requis. Pour corriger le problème, effectuez l’une des opérations suivantes,  
  
    -   Supprimer `_ATL_MIN_CRT` dans la liste du préprocesseur définit pour autoriser le code de démarrage CRT à inclure. Consultez la page [Page de propriétés de paramètres de Configuration général](../../ide/general-property-page-project.md) pour plus d’informations.  
  
    -   Si possible, supprimez les appels aux fonctions CRT qui nécessitent le code de démarrage CRT. Utilisez plutôt leurs équivalents Win32. Par exemple, utilisez `lstrcmp` au lieu de `strcmp`. Les fonctions connues qui requièrent le code de démarrage CRT sont certaines des fonctions à virgule flottante et string.  
  
 **Compilation et liaison de problèmes**  
  
-   Il manque une référence à une bibliothèque de projet (. LIB) ou un objet (. Fichier OBJ). Consultez la page [fichiers .lib en tant qu’entrée de l’éditeur de liens](../../build/reference/dot-lib-files-as-linker-input.md) pour plus d’informations.  
  
-   Si vous utilisez [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) ou [/Zl](../../build/reference/zl-omit-default-library-name.md), bibliothèques de code requis ne seront pas liés dans le projet, sauf si vous les avez incluses explicitement. (Lors de la compilation avec **/clr** ou **/CLR : pure**, vous verrez une référence à .cctor ; consultez [l’initialisation d’assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md) pour plus d’informations.)  
  
-   Si vous utilisez Unicode et MFC, vous obtiendrez un symbole externe non résolu sur `_WinMain@16` si vous ne créez pas un point d’entrée pour `wWinMainCRTStartup`; utilisez la [/ENTRY](../../build/reference/entry-entry-point-symbol.md). Consultez la page [synthèse de la programmation Unicode](../../text/unicode-programming-summary.md).  
  
     Consultez les articles suivants de la Base de connaissances, situés dans la bibliothèque MSDN, pour plus d’informations. Dans la bibliothèque MSDN, cliquez sur le **recherche** onglet, collez le numéro ou le titre de l’article dans la zone de texte, puis cliquez sur **liste des rubriques**. Si vous recherchez le numéro d’article, vérifiez que le **recherche uniquement dans les titres** option est désactivée.  
  
    -   Q125750 « PRB : erreur LNK2001 : '_WinMain@16' : symbole externe non résolu »  
  
    -   Q131204 « PRB : sélection du projet incorrecte entraîne l’erreur LNK2001 sur _WinMain@16»  
  
    -   Q100639 « prise en charge Unicode dans Microsoft Foundation Class Library »  
  
    -   Q291952 « PRB : lien d’erreur LNK2001 : _main de symbole externe non résolu »  
  
-   La liaison de code compilé avec /MT avec la bibliothèque LIBC.lib cause LNK2001 sur `_beginthread`, `_beginthreadex`, `_endthread`, et `_endthreadex`.  
  
-   La liaison de code requérant les bibliothèques multithreads (tout code MFC ou le code compilé avec [/MT](../../build/reference/md-mt-ld-use-run-time-library.md)) entraîne l’erreur LNK2001 sur [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md), `_beginthreadex`, [_endthread](../../c-runtime-library/reference/endthread-endthreadex.md), et `_endthreadex`. Consultez l’article suivant de la Base de connaissances pour plus d’informations :  
  
    -   Q126646 « PRB : message d’erreur : erreur LNK2001 sur __beginthreadex et \__endthreadex »  
  
    -   Q128641 « INFO : Options de compilateur /Mx et le LIBC LIBCMT, MSVCRT Libs »  
  
    -   Q166504 « PRB : MFC et CRT et doivent concorder debug/release statique/dynamique »  
  
-   Lors de la compilation avec **/MD**, une référence à « func » dans votre source devient une référence à «`__imp__func`» dans l’objet puisque tout le runtime est maintenant dans une DLL. Si vous essayez d’effectuer une liaison avec les bibliothèques statiques LIBC.lib ou LIBCMT.lib, vous obtiendrez LNK2001 sur `__imp__func`. Si vous essayez d’effectuer une liaison avec MSVCxx.lib lors de la compilation sans/MD, vous n’obtiendrez pas toujours LNK2001, mais vous disposerez probablement d’autres problèmes.  
  
-   Liaison avec les bibliothèques en mode lors de la création d’une version debug d’une application peut causer l’erreur LNK2001. À l’aide de la même façon, un **/Mxd** option (**/MTd**, ou **/MDd**) et/ou définissez `_DEBUG` et ensuite une liaison avec les bibliothèques vous donnera éventuels externes non résolus (entre autres problèmes). Liaison d’une version en mode Release avec les bibliothèques de débogage peut aussi causer des problèmes similaires.  
  
-   Mélange de versions de bibliothèques Microsoft et de produits compilateurs peut être problématique. Bibliothèques d’une nouvelle version du compilateur peuvent contenir des nouveaux symboles qui ne figurent pas dans les bibliothèques incluses dans les versions précédentes. Vous souhaiterez peut-être modifier l’ordre des répertoires dans le chemin de recherche, ou les modifier pour pointer vers la version actuelle.  
  
     Les outils | Options | Projets | Boîte de dialogue répertoires VC ++, dans la sélection de fichiers de bibliothèque, vous permet de modifier l’ordre de recherche. Le dossier de l’éditeur de liens dans la boîte de dialogue Pages de propriétés du projet peut également contenir des chemins d’accès qui pourraient être obsolètes.  
  
     Ce problème peut apparaître lorsque vous installez un nouveau SDK (peut-être à un autre emplacement), et l’ordre de recherche n’est pas mis à jour pour pointer vers le nouvel emplacement. En règle générale, vous devez placer le chemin d’accès à nouveaux kits de développement include et lib répertoires devant l’emplacement de Visual C++ par défaut. En outre, un projet contenant des chemins incorporés peut pointer vers d’anciens chemins qui sont valides mais obsolètes de nouvelles fonctionnalités ajoutées par la nouvelle version qui est installée dans un emplacement différent.  
  
-   Il n’existe actuellement aucune norme pour [d’affectation de noms C++](../../error-messages/tool-errors/name-decoration.md) entre éditeurs de compilateurs ou même entre différentes versions d’un compilateur. Par conséquent, la liaison de fichiers objets compilés avec d’autres compilateurs ne peut pas produire le même schéma d’affectation de noms et donc causer l’erreur LNK2001.  
  
-   [Options de compilation de mixage inline et non inline](../../error-messages/tool-errors/function-inlining-problems.md) sur des modules différents peut causer l’erreur LNK2001. Si une bibliothèque C++ est créée avec la fonctionnalité inline activée (**/Ob1** ou **/Ob2**), mais le fichier d’en-tête correspondant décrivant les fonctions a désactivé cette fonctionnalité (aucun `inline` mot clé), vous obtiendrez cette erreur. Pour éviter ce problème, ont les fonctions inline défini avec `inline` dans le fichier d’en-tête que vous allez inclure dans d’autres fichiers.  
  
-   Si vous utilisez la `#pragma inline_depth` Assurez-vous directive du compilateur que vous avez un [valeur égale ou supérieure à 2](../../error-messages/tool-errors/function-inlining-problems.md)et vérifiez que vous utilisez la [/Ob1](../../build/reference/ob-inline-function-expansion.md) ou [/Ob2](../../build/reference/ob-inline-function-expansion.md) option du compilateur.  
  
-   L’omission de l’option lien /NOENTRY lors de la création d’une DLL de ressource uniquement provoquera une erreur LNK2001.  
  
-   À l’aide de paramètres /SUBSYSTEM ou /ENTRY incorrects peut causer l’erreur LNK2001. Par exemple, si vous écrivez une application basée sur les caractères (une application console) et spécifiez/SUBSYSTEM : Windows, vous obtiendrez un symbole externe non résolu pour `WinMain`. Pour plus d’informations sur ces options et les points d’entrée, consultez le [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) et [/ENTRY](../../build/reference/entry-entry-point-symbol.md) les options de l’éditeur de liens.  
  
 **Problèmes d’exportation**  
  
-   Quand vous portez une application de 16 à 32 ou 64 bits, LNK2001 peut survenir. La syntaxe actuelle du fichier de définition de module (.def) requiert que `__cdecl`, `__stdcall`, et `__fastcall` fonctions apparaissent dans la section EXPORTS sans les caractères de soulignement (non décorées). Cela diffère de la syntaxe de 16 bits, où elles doivent apparaître avec les caractères de soulignement (décorées). Pour plus d’informations, consultez la description de la [exportations](../../build/reference/exports.md) section des fichiers de définition de module.  
  
-   Toute exportation répertoriés dans le fichier .def et non trouvée cause LNK2001. Il peut s’agir, car il n’existe pas, est mal orthographié ou utilise des noms décorés C++ (fichiers .def ne prennent pas de noms décorés)  
  
 **Interprétation de la sortie**  
  
 Lorsqu’un symbole n’est pas résolu, vous pouvez obtenir des informations sur la fonction par les indications suivantes :  
  
 Sur x86 plates-formes, la décoration de convention d’appel pour les noms compilés en C ou pour extern « C » les noms en C++, est :  
  
 `__cdecl`  
 Fonction a un préfixe de trait de soulignement (_).  
  
 `__stdcall`  
 Fonction a un préfixe caractère de soulignement (_) et un suffixe @ suivi par la valeur dword aligné taille des paramètres de la pile.  
  
 `__fastcall`  
 Fonction a un préfixe @ et un suffixe @ suivi par la valeur dword aligné taille des paramètres de la pile.  
  
 Utilisez undname.exe pour obtenir la forme non décorée d’un nom décoré.  
  
 Pour plus d’informations sur certaines des causes mentionnées ci-dessus, consultez la page [décoration de nom](../../error-messages/tool-errors/name-decoration.md).
