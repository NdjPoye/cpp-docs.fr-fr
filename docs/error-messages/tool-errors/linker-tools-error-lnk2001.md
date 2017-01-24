---
title: "Erreur des outils &#201;diteur de liens LNK2001 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2001"
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole externe non résolu "symbole"  
  
 Le code référence quelque chose \(fonction, variable ou étiquette\) que l'éditeur de liens ne peut trouver dans les bibliothèques ni dans les fichiers objets.  
  
 Ce message d'erreur est suivi de l'erreur irrécupérable [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md).  
  
 **Causes possibles**  
  
-   Lors de la mise à niveau d'une bibliothèque managée ou d'un projet de service Web à partir de Visual C\+\+ 2003, l'option de compilateur **\/Zl** est ajoutée dans la page de propriétés **Ligne de commande**.  Cela provoquera une erreur LNK2001.  
  
     Pour résoudre cette erreur, ajoutez les fichiers msvcrt.lib et msvcmrt.lib à la propriété Dépendances supplémentaires de l'Éditeur de liens.  Ou bien, supprimez **\/Zl** de la page de propriétés **Ligne de commande**.  Pour plus d’informations, consultez [\/Zl \(Omettre le nom de la bibliothèque par défaut\)](../../build/reference/zl-omit-default-library-name.md) et [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
-   Ce que le code recherche n'existe pas \(le symbole a une orthographe incorrecte ou une combinaison incorrecte de majuscules et minuscules, par exemple\).  
  
-   Le code recherche un objet erroné \(vous utilisez des versions mixtes des bibliothèques, certaines provenant d'une version du produit et d'autres d'une version différente\).  
  
 **Causes spécifiques**  
  
 **Problèmes de codage**  
  
-   Si le texte du diagnostic LNK2001 rapporte que `__check_commonlanguageruntime_version` est un symbole externe non résolu, consultez [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) pour obtenir des informations sur la résolution de cette erreur.  
  
-   La définition d'un modèle de membre est en dehors de la classe.  Une limitation de Visual C\+\+ est que les modèles de membres doivent être complètement définis dans la classe englobante.  Consultez l'article de la Base de connaissances Q239436 pour plus d'informations sur LNK2001 et les modèles de membres.  
  
-   Une différence dans la configuration de majuscules et minuscules entre votre code et le fichier de définition du module \(.def\) peut causer LNK2001.  Par exemple, si vous avez nommé une variable `var1` dans un fichier source C\+\+ et tentez d'y accéder par `VAR1` dans un autre fichier.  
  
-   Un projet qui utilise la [fonction inline](../../error-messages/tool-errors/function-inlining-problems.md) mais définit les fonctions dans un fichier .cpp au lieu du fichier d'en\-tête peut causer LNK2001.  
  
-   L'appel d'une fonction C depuis un programme C\+\+ sans utilisation de `extern` "C" \(qui impose au compilateur d'utiliser la convention de noms C\) peut causer LNK2001.  Les options du compilateur [\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) et [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) font compiler les fichiers sous forme C\+\+ ou C, respectivement, quelle que soit l'extension du nom de fichier.  Ces options peuvent causer des noms de fonctions différents de ceux attendus.  
  
-   Une tentative de référencer des fonctions ou des données qui n'ont pas de liaison externe peut causer LNK2001.  En C\+\+, les fonctions inline et données `const` ont une liaison interne sauf spécification explicite `extern`.  
  
-   Un [corps de fonction ou variable manquant](../../error-messages/tool-errors/missing-function-body-or-variable.md) peut causer LNK2001.  Avec seulement un prototype de fonction ou une déclaration `extern` le compilateur peut poursuivre sans erreur, mais l'éditeur de liens ne peut pas résoudre un appel à une adresse ou une référence à une variable parce qu'il n'y a pas de code de fonction ou d'espace réservé pour la variable.  
  
-   L'appel d'une fonction avec des types de paramètres qui ne correspondent pas à ceux de la déclaration de la fonction peut générer l'erreur LNK2001.  La [décoration de nom](../../error-messages/tool-errors/name-decoration.md) incorpore les paramètres d'une fonction dans le nom décoré final de la fonction.  
  
-   Des prototypes inclus de façon incorrecte, ce qui conduit le compilateur à attendre un corps de fonction qui n'est pas fourni, peuvent causer LNK2001.  Si vous avez à la fois une implémentation de classe et non\-classe d'une fonction `F`, prenez garde aux règles de résolution de portée de C\+\+.  
  
-   En C\+\+, l'inclusion d'un prototype de fonction dans une définition de classe sans [inclure l'implémentation](../../error-messages/tool-errors/missing-function-body-or-variable.md) de la fonction pour cette classe peut causer LNK2001.  
  
-   Une tentative d'appel d'une fonction virtuelle pure depuis le constructeur ou le destructeur d'une classe de base abstraite peut causer LNK2001.  Une fonction virtuelle pure n'a pas d'implémentation de classe de base.  
  
-   La tentative d'utilisation d'une variable déclarée à l'intérieur d'une fonction \([variable locale](../../error-messages/tool-errors/automatic-function-scope-variables.md)\) en dehors de la portée de cette fonction peut causer LNK2001.  
  
-   Lors de la génération d'une version de référence d'un projet ATL, indique que le code de démarrage CRT est requis.  Pour corriger, effectuez l'une des opérations suivantes :  
  
    -   Supprimez `_ATL_MIN_CRT` de la liste des définitions du préprocesseur pour permettre l'inclusion du code de démarrage CRT.  Pour plus d'informations, consultez [Général, page de propriétés Paramètres de configuration](../../ide/general-property-page-project.md).  
  
    -   Si possible, supprimez les appels aux fonctions CRT qui nécessitent le code de démarrage CRT.  Utilisez plutôt leurs équivalents Win32.  Par exemple, utilisez `lstrcmp` au lieu de `strcmp`.  Les fonctions connues qui requièrent le code de démarrage CRT sont certaines des fonctions de chaîne ou de virgule flottante.  
  
 **Problèmes de compilation et de liaison**  
  
-   Le projet ne comporte pas de référence à une bibliothèque \(.LIB\) ou à un fichier objet \(.OBJ\).  Pour plus d'informations, consultez [Fichiers .lib en tant qu'entrée dans l'éditeur de liens](../../build/reference/dot-lib-files-as-linker-input.md).  
  
-   Si vous utilisez [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) ou [\/Zl](../../build/reference/zl-omit-default-library-name.md), les bibliothèques qui contiennent le code requis ne sont pas liées dans le projet à moins que vous les ayez incluses explicitement. \(Lorsque vous compilez avec **\/clr** ou **\/clr:pure**, vous pouvez voir une référence à .cctor ; consultez [Initialisation d'assemblys mixtes](../../dotnet/initialization-of-mixed-assemblies.md) pour plus d'informations.\)  
  
-   Si vous utilisez Unicode et MFC, vous obtiendrez un symbole externe non résolu sur `_WinMain@16` si vous ne créez pas un point d'entrée vers `wWinMainCRTStartup` ; utilisez [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  Consultez [Synthèse de la programmation Unicode](../../text/unicode-programming-summary.md).  
  
     Consultez les articles suivants de la Base de connaissances, dans MSDN Library, pour plus d'informations.  Dans MSDN Library, cliquez sur l'onglet **Search**, collez le numéro ou le titre de l'article dans la zone de texte, puis cliquez sur **List Topics**.  Si vous effectuez la recherche sur le numéro d'article, vérifiez que l'option **Search titles only** n'est pas sélectionnée.  
  
    -   Q125750   « PRB: Error LNK2001: '\_WinMain@16': Unresolved External Symbol » \(article en anglais\)  
  
    -   Q131204   « PRB: Wrong Project Selection Causes LNK2001 on \_WinMain@16 » \(article en anglais\)  
  
    -   Q100639   « Unicode Support in the Microsoft Foundation Class Library » \(article en anglais\)  
  
    -   Q291952    « PRB: Link Error LNK2001: Unresolved External Symbol \_main » \(article en anglais\)  
  
-   La liaison de code compilé avec \/MT avec la bibliothèque LIBC.lib cause LNK2001 sur `_beginthread`, `_beginthreadex`, `_endthread` et `_endthreadex`.  
  
-   La liaison de code requérant les bibliothèques multithread \(tout code MFC ou code compilé avec [\/MT](../../build/reference/md-mt-ld-use-run-time-library.md)\) entraîne l'erreur LNK2001 sur [\_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md), `_beginthreadex`, [\_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) et `_endthreadex`.  Voir l'article de la Base de connaissances ci\-dessous pour plus d'informations :  
  
    -   Q126646 « PRB: Error Msg: LNK2001 on \_\_beginthreadex and \_\_endthreadex » \(article en anglais\)  
  
    -   Q128641 « INFO: \/Mx Compiler Options and the LIBC, LIBCMT, MSVCRT Libs » \(article en anglais\)  
  
    -   Q166504 « PRB: MFC and CRT Must Match in debug\/release and static\/dynamic » \(article en anglais\)  
  
-   Lors de la compilation avec **\/MD**, une référence à "func" dans votre source devient une référence à "`__imp__func`" dans l'objet puisque tout le runtime est maintenant dans une DLL.  Si vous tentez une édition de liens avec des bibliothèques statiques LIBC.lib ou LIBCMT.lib, l'erreur LNK2001 est générée sur `__imp__func`.  Si vous tentez une édition de liens avec MSVCxx.lib lors de la compilation sans \/MD, vous n'obtiendrez pas toujours LNK2001, mais vous aurez probablement d'autres problèmes.  
  
-   La liaison avec les bibliothèques en mode référence lors de la génération d'une version de débogage d'une application peut causer LNK2001.  De la même façon, si vous utilisez une option **\/Mxd** \(**\/MTd** ou **\/MDd**\) et\/ou définissez `_DEBUG`, puis établissez la liaison avec les bibliothèques en mode référence, vous obtenez d'éventuels symboles externes non résolus \(entre autres problèmes\).  La liaison d'une génération en mode référence avec les bibliothèques de débogage peut aussi causer des problèmes similaires.  
  
-   Le mélange de versions de bibliothèques Microsoft et de produits compilateurs peut être problématique.  Les bibliothèques d'une nouvelle version du compilateur peuvent contenir des nouveaux symboles qui ne peuvent être trouvés dans les bibliothèques incluses avec les versions précédentes.  Vous pouvez modifier l'ordre des répertoires du chemin de recherche ou les modifier pour pointer vers la version actuelle.  
  
     Outils &#124; Options &#124; Projets &#124; Boîte de dialogue VC\+\+, dans la sélection de fichiers de bibliothèques, permet de modifier l'ordre de recherche.  Le dossier de l'éditeur de liens dans la boîte de dialogue Pages de propriétés du projet peut aussi contenir des chemins d'accès obsolètes.  
  
     Ce problème peut apparaître à l'installation d'un nouveau SDK \(peut\-être à un emplacement différent\) quand l'ordre de recherche n'est pas mis à jour pour pointer vers le nouvel emplacement.  Normalement, vous devez placer les chemins d'accès aux répertoires include et lib du nouveau SDK devant l'emplacement par défaut de Visual C\+\+.  Un projet contenant des chemins incorporés peut pointer vers d'anciens chemins qui sont valides mais obsolètes parce que de nouvelles fonctionnalités ont été ajoutées par la nouvelle version installée à un emplacement différent.  
  
-   Il n'y a pour l'instant pas de norme pour l'[affectation de noms C\+\+](../../error-messages/tool-errors/name-decoration.md) entre éditeurs de compilateurs ou même entre différentes versions d'un même compilateur.  Donc la liaison de fichiers objets compilés avec d'autres compilateurs peut ne pas produire le même schéma d'affectation de noms et donc causer l'erreur LNK2001.  
  
-   [Le mélange d'options de compilation en ligne et non en ligne](../../error-messages/tool-errors/function-inlining-problems.md) sur des modules différents peut causer LNK2001.  Si une bibliothèque C\+\+ est créée avec la fonctionnalité inline activée \(**\/Ob1** ou **\/Ob2**\), alors que le fichier d'en\-tête correspondant décrivant les fonctions a désactivé cette fonctionnalité \(pas de mot clé `inline`\), cette erreur survient.  Pour éviter ce problème, définissez les fonctions en ligne avec `inline` dans le fichier d'en\-tête que vous allez inclure dans d'autres fichiers.  
  
-   Si vous utilisez la directive du compilateur `#pragma inline_depth`, vérifiez que vous utilisez une [valeur supérieure ou égale à 2](../../error-messages/tool-errors/function-inlining-problems.md), et que vous utilisez l'option [\/Ob1](../../build/reference/ob-inline-function-expansion.md) ou [\/Ob2](../../build/reference/ob-inline-function-expansion.md).  
  
-   L'omission de l'option \/NOENTRY de LINK lors de la création d'une DLL de ressources seulement cause LNK2001.  
  
-   L'utilisation de paramètres \/SUBSYSTEM ou \/ENTRY incorrects peut causer LNK2001.  Si vous écrivez par exemple une application en mode caractère \(application console\) et spécifiez \/SUBSYSTEM:WINDOWS, vous obtiendrez un symbole externe non résolu pour `WinMain`.  Pour plus d'informations sur ces options et les points d'entrée, consultez les options de l'éditeur de liens [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) et [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  
  
 **Problèmes d'exportation**  
  
-   Quand vous portez une application de 16 en 32 ou 64 bits, l'erreur LNK2001 peut se produire.  La syntaxe actuelle des fichiers de définition des modules \(.def\) requiert que les fonctions `__cdecl`, `__stdcall` et `__fastcall` apparaissent dans la section EXPORTS sans les caractères de soulignement \(non décorées\).  Cette syntaxe est différente de celle qui est utilisée en 16 bits, où elles doivent apparaître avec les caractères de soulignement \(décorées\).  Pour plus d'informations, consultez la description des fichiers de définition de module de la section [EXPORTS](../../build/reference/exports.md).  
  
-   Toute exportation mentionnée dans le fichier .def et non trouvée cause LNK2001.  Ce peut être parce qu'elle n'existe pas, que l'orthographe est incorrecte ou qu'elle utilise des noms décorés C\+\+ \(les fichiers .def ne prennent pas de noms décorés\).  
  
 **Interprétation de la sortie**  
  
 Quand un symbole est non résolu, vous pouvez obtenir des informations sur la fonction par les indications suivantes :  
  
 Sur les plateformes x86, la décoration de convention d'appels pour les noms compilés en C ou pour les noms "C" externes en C\+\+ est :  
  
 `__cdecl`  
 La fonction a un préfixe caractère de soulignement \(\_\).  
  
 `__stdcall`  
 La fonction a un préfixe caractère de soulignement \(\_\) et un suffixe @ suivi par la taille des paramètres de la pile alignée sur un dword.  
  
 `__fastcall`  
 La fonction a un préfixe @ et un suffixe @ suivi par la taille des paramètres de la pile alignée sur un dword.  
  
 Utilisez undname.exe pour obtenir la forme non décorée d'un nom décoré.  
  
 Pour plus d'informations sur certaines des causes mentionnées ci\-dessus, consultez [Décoration de nom](../../error-messages/tool-errors/name-decoration.md).